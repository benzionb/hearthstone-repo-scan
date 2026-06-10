# hs-replay-xml-parser

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/hs-replay-xml-parser.git
- org: Zero-to-Heroes
- role: replay_event_to_model_parser
- confidence: 0.83
- must_use_for: replay_conformance_input
- risk_flags: Parser output quality tied to upstream logs
- capability_scores: live_fidelity=0.68, simulation_coverage=0.16, data_freshness=0.23, parser_strength=0.74, ml_integration=0.36

## Repository-level observed structure
- top directories: src
- top files: .gitignore, README.md, package-lock.json, package.json, tsconfig.json
- dominant file types: .js, .json, .md, .ts

## Readability anchor
> rm -rf dist && tsc && 'cp' -rf dist/ /e/Source/zerotoheroes/firestone/core/node_modules/\@firestone-hs/hs-replay-xml-parser/
> 
> rm -rf dist && tsc && 'cp' -rf dist/ /e/Source/zerotoheroes/public-lambdas/trigger-build-match-stats/node_modules/\@firestone-hs/hs-replay-xml-parser/
> rm -rf dist && tsc && 'cp' -rf dist/ /e/Source/zerotoheroes/public-lambdas/api-user-bgs-post-match-stats/node_modules/\@firestone-hs/hs-replay-xml-parser/
> rm -rf dist && tsc && 'cp' -rf dist/ /e/Source/zerotoheroes/public-lambdas/trigger-assign-archetype/node_modules/\@firestone-hs/hs-replay-xml-parser/
> 
> rm -rf dist && tsc && npm publish --access public

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
