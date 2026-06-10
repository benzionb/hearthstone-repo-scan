# HSTracker

## Unabridged research summary
- repo_url: https://github.com/HearthSim/HSTracker.git
- org: HearthSim
- role: overlay_state_ingest_and_overrides
- confidence: 0.9
- must_use_for: overlay_state_streaming, overrides_ingest
- risk_flags: Large native codebase; platform-specific coupling
- capability_scores: live_fidelity=0.74, simulation_coverage=0.1, data_freshness=0.67, parser_strength=0.64, ml_integration=0.52

## Repository-level observed structure
- top directories: HSTracker, HSTracker.xcodeproj, HSTrackerTests, Translations, fastlane, scripts
- top files: .gitattributes, .gitignore, CHANGELOG.md, CONTRIBUTING.md, Config.xcconfig, Gemfile, Gemfile.lock, LICENSE, README.md, hs-build-dates.json, hstracker.jpg, manager.jpg
- dominant file types: .h, .json, .md, .swift, .yml

## Readability anchor
> # HSTracker
> [![Build Status](https://travis-ci.org/HearthSim/HSTracker.svg?branch=master)](https://travis-ci.org/HearthSim/HSTracker)
> 
> HSTracker is an automatic deck tracker and deck manager for Hearthstone on macOS.
> 
> 
> ## Installation
> - Requirements:
>   - macOS 10.10 or higher
>   - For Windows support please look at [**Hearthstone Deck Tracker**](https://github.com/HearthSim/Hearthstone-Deck-Tracker/)
> - Download the latest version [from here](https://hsdecktracker.net/hstracker/download/)
> - Extract the archive
> - Move `HSTracker.app` to your `Applications` directory
> - Launch HSTracker before Hearthstone
> - Create a new deck from the Deck Manager or import it from a deckstring. HSTracker will also auto-detect the deck you play with.
> 
> 
> ## Community & Troubleshooting
> - Join the Community Discord: [![Join HearthSim Community Discord](https://discordapp.com/api/guilds/265636998700728321/widget.png)](https://discord.gg/hearthsim)
> - [Follow HSTracker on Twitter](https://twitter.com/hstracker_mac)
> - HSReplay.net integration: Please email <support@hsdecktracker.net> for support.
> 
> 
> ## Contributing
> - Please read the [contributing guidelines](https://github.com/HearthSim/HSTracker/blob/master/CONTRIBUTING.md).
> - Developer Discord: [![Join HearthSim #hstracker](https://img.shields.io/badge/discord-join%20chat-blue.svg)](https://discord.gg/hearthsim-devs)
> - HSTracker is a [HearthSim](https://hearthsim.info) project.
> 
> 
> ## Features
> ### Deck Tracker
> ![Deck Tracker](https://github.com/HearthSim/HSTracker/blob/master/hstracker.jpg)
> 
> ### Deck Manager
> ![Deck Manager](https://github.com/HearthSim/HSTracker/blob/master/manager.jpg)
> 
> 
> ### HSReplay.net Integration
> HSTracker uploads your games to [HSReplay.net](https://hsreplay.net).

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
