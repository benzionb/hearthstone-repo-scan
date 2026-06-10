# hs-reference-data

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/hs-reference-data.git
- org: Zero-to-Heroes
- role: bg_reference_rules_data
- confidence: 0.91
- must_use_for: patch_manifest_seed, tier/race/card-rule lookup
- risk_flags: Not a rules executor; requires engine layer
- capability_scores: live_fidelity=0.78, simulation_coverage=0.31, data_freshness=0.74, parser_strength=0.61, ml_integration=0.21

## Repository-level observed structure
- top directories: ref, src, test
- top files: .gitignore, README.md, package-lock.json, package.json, tsconfig.json
- dominant file types: .js, .json, .md, .ts

## Readability anchor
> # Copy the files to S3
> 
> ```
> aws s3 cp ./src/hs-achievements.json s3://static.zerotoheroes.com/hearthstone/jsoncards/ --acl public-read
> aws s3 cp ./src/card-backs.json s3://static.zerotoheroes.com/hearthstone/data/ --acl public-read
> 
> # I now upload to a zipped endpoint from the pipeline
> # aws s3 cp ./src/deck-templates.json s3://static.zerotoheroes.com/hearthstone/data/ --acl public-read
> 
> aws s3 cp ./src/tavern-brawls.json s3://static.zerotoheroes.com/hearthstone/data/ --acl public-read
> aws s3 cp ./src/mercenaries/ s3://static.zerotoheroes.com/hearthstone/data/mercenaries/ --recursive --acl public-read
> aws s3 cp ./src/cards/ s3://static.zerotoheroes.com/hearthstone/jsoncards/ --recursive --acl public-read
> aws s3 cp ./src/cards/ s3://static.firestoneapp.com/data/cards/ --recursive --acl public-read
> ```
> 
> Generate the card back data from the Blizzard API, eg
> 
> # Dev stuff
> 
> rm -rf dist && tsc && rm -rf dist/node_modules && npm publish --access public
> 
> rm -rf dist && tsc && rm -rf dist/node_modules && 'cp' -rf dist/ /e/Source/zerotoheroes/firestone/core/node_modules/\@firestone-hs/reference-data/

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
