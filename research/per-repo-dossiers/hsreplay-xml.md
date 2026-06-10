# hsreplay-xml

## Unabridged research summary
- repo_url: https://github.com/HearthSim/hsreplay-xml.git
- org: HearthSim
- role: replay_format_spec
- confidence: 0.55
- must_use_for: xml schema interoperability
- risk_flags: No executable parser
- capability_scores: live_fidelity=0.57, simulation_coverage=0.02, data_freshness=0.16, parser_strength=0.58, ml_integration=0.09

## Repository-level observed structure
- top directories: (none)
- top files: .gitattributes, LICENSE, README.md, hsreplay.dtd
- dominant file types: .md

## Readability anchor
> # HSReplay
> 
> HSReplay is a replay format for [Hearthstone](https://playhearthstone.com/).
> 
> It is an XML-based format, with a structure closely mirroring that of the
> game's protocol.
> 
> The extension for HSReplay files is `.hsreplay`.
> The MIME Type is `application/vnd.hearthsim-hsreplay+xml`.
> 
> 
> ## Documentation
> 
> Spec docs are available [here](https://hearthsim.info/hsreplay/).
> 
> Documentation for the Hearthstone Gamestate Protocol, which HSReplay mirrors,
> is available [here](https://hearthsim.info/docs/gamestate-protocol/).
> 
> 
> ## Implementations
> 
> There is currently only one official implementation of the HSReplay format:
> 
> * https://github.com/HearthSim/python-hsreplay (read, write)
> 
> If you are interested in developing reference implementations in other
> languages, please get in touch by filing an issue!
> 
> 
> ## License
> 
> The HSReplay spec is licensed CC0. This puts it in the public domain.
> The full license text is available in the LICENSE file.
> 
> 
> ## Community
> 
> HSReplay is a [HearthSim](https://hearthsim.info) project.
> Join the community: <https://hearthsim.info/join/>

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
