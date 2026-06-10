# hs-game-entities

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/hs-game-entities.git
- org: Zero-to-Heroes
- role: protocol_entity_schema
- confidence: 0.47
- must_use_for: replay_xml_modeling, cross-lang type alignment
- risk_flags: Sparse updates
- capability_scores: live_fidelity=0.49, simulation_coverage=0.04, data_freshness=0.09, parser_strength=0.6, ml_integration=0.25

## Repository-level observed structure
- top directories: src
- top files: .gitignore, README.md, pom.xml
- dominant file types: .md, .xml

## Readability anchor
> Object model to represent a Game and hearthstone game constants. Used as a dependency by other Zero to Heroes projects through Maven
> 
> If you're interested in contributing, feel free to [join us on Discord](https://discord.gg/uEh9gvJ)

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
