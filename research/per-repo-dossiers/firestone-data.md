# firestone-data

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/firestone-data.git
- org: Zero-to-Heroes
- role: static_patch_and_config_feed
- confidence: 0.71
- must_use_for: patch_lookup_seed_input, tier_anomaly_config_inputs
- risk_flags: Not a rules engine; Requires external regeneration to stay current
- capability_scores: live_fidelity=0.52, simulation_coverage=0.08, data_freshness=0.34, parser_strength=0.28, ml_integration=0.12

## Repository-level observed structure
- top directories: file, generator
- top files: .gitignore, README.md, package-lock.json, package.json, tsconfig.json
- dominant file types: .js, .json, .md, .ts

## Readability anchor
> aws s3 cp file/secrets_config.json s3://static.zerotoheroes.com/hearthstone/data/ --acl public-read
> aws s3 cp file/patches.json s3://static.zerotoheroes.com/hearthstone/data/ --acl public-read
> aws s3 cp file/ai_decks s3://static.zerotoheroes.com/hearthstone/data/ai_decks --recursive --acl public-read
> aws s3 cp file/ai_decks s3://static.zerotoheroes.com/hearthstone/data/ai_decks --recursive --acl public-read
> aws s3 cp file/tavern-brawl-open-lists s3://static.zerotoheroes.com/hearthstone/data/brawl_lists --recursive --acl public-read
> 
> aws s3 cp file/expert-contributors.json s3://static.zerotoheroes.com/hearthstone/data/expert-contributors.json --acl public-read
> aws s3 cp file/lottery-config.json s3://static.zerotoheroes.com/api/lottery/lottery-config.json --acl public-read
> aws s3 cp file/lottery-seasons.json s3://static.zerotoheroes.com/api/lottery/lottery-seasons.json --acl public-read

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
