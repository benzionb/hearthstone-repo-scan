# hsdata

## Unabridged research summary
- repo_url: https://github.com/HearthSim/hsdata.git
- org: HearthSim
- role: raw_client_data_dump
- confidence: 0.76
- must_use_for: authoritative_card_and_locale_baseline, tag recovery
- risk_flags: Manual refresh + large binary deltas
- capability_scores: live_fidelity=0.72, simulation_coverage=0.03, data_freshness=0.36, parser_strength=0.55, ml_integration=0.09

## Repository-level observed structure
- top directories: Strings
- top files: .gitignore, BountyDefs.xml, CardDefs.xml, MercenaryDefs.xml, README.md, RaceTagMap.xml
- dominant file types: .md, .xml

## Readability anchor
> Hearthstone Data
> ================
> 
> DBF and CardXML files extracted from the
> [Hearthstone](http://playhearthstone.com) game client.
> 
> If you are looking for JSON-based data, you can use HearthstoneJSON instead:
> 
> https://hearthstonejson.com
> 
> ---
> 
> Version: 34.6.0.235290
> 
> https://hearthsim.info

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
