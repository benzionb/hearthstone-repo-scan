# hs-reference-data-parser

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/hs-reference-data-parser.git
- org: Zero-to-Heroes
- role: reference_data_etl
- confidence: 0.39
- must_use_for: normalizing external feeds into local JSON
- risk_flags: Legacy java build/setup; Limited active maintenance
- capability_scores: live_fidelity=0.47, simulation_coverage=0.09, data_freshness=0.12, parser_strength=0.64, ml_integration=0.12

## Repository-level observed structure
- top directories: src, target
- top files: .gitignore, README.md, out.json, pom.xml
- dominant file types: .json, .md, .xml

## Readability anchor
> Standalone applications to transform reference Hearthstone JSON file (cards and string) into something more easily usable by the application.
> 
> Also contains a few other small apps that didn't deserve to have their own separate project
> 
> If you're interested in contributing, feel free to [join us on Gitter](https://gitter.im/zerotoheroes/Lobby)

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
