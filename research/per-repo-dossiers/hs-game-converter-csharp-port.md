# hs-game-converter-csharp-port

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/hs-game-converter-csharp-port.git
- org: Zero-to-Heroes
- role: replay_converter
- confidence: 0.65
- must_use_for: BG replay event parsing
- risk_flags: C#/.NET runtime coupling; Parser-only scope
- capability_scores: live_fidelity=0.61, simulation_coverage=0.07, data_freshness=0.22, parser_strength=0.66, ml_integration=0.21

## Repository-level observed structure
- top directories: HearthstoneReplayTests, HearthstoneReplays, TestResults
- top files: .gitignore, HearthstoneReplays.sln, LICENSE, README.md, report.xsl
- dominant file types: .cs, .md

## Readability anchor
> Port of the [hs-game-converter](https://github.com/Zero-to-Heroes/hs-game-converter) project to C# to be used in the [Overwolf application](https://github.com/Zero-to-Heroes/overwolf-replay-app)

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
