# Hearthstone-Deck-Tracker

## Unabridged research summary
- repo_url: https://github.com/HearthSim/Hearthstone-Deck-Tracker.git
- org: HearthSim
- role: overlay_state_ingest_and_overrides
- confidence: 0.88
- must_use_for: battlegrounds_tag_overrides, live_anomaly_and_tier_rules
- risk_flags: Cross-platform behavior complexity
- capability_scores: live_fidelity=0.7, simulation_coverage=0.09, data_freshness=0.64, parser_strength=0.63, ml_integration=0.51

## Repository-level observed structure
- top directories: Bootstrap, HDTTests, HDTUninstaller, HDTUpdate, HearthWatcher, HearthWatcher.Test, Hearthstone Deck Tracker, SignToolShim, build-scripts, lib, licenses, packages, raw-assets
- top files: .gitattributes, .gitignore, CHANGELOG.md, CONTRIBUTING.md, Hearthstone Deck Tracker.sln, Hearthstone Deck Tracker.sln.DotSettings, README.md, bootstrap.ps1, generate_whizbang_decks.bat, nuget.config
- dominant file types: .cs, .js, .md

## Readability anchor
> # Hearthstone-Deck-Tracker
> [![Build status](https://ci.appveyor.com/api/projects/status/3wow545sjaq9ybji/branch/master?svg=true)](https://ci.appveyor.com/project/azeier/hearthstone-deck-tracker/branch/master)
> 
> Hearthstone Deck Tracker is an automatic deck tracker and deck manager for Hearthstone.
> 
> ## Installation
> - Requirements:
>   - Windows Vista or higher
>   - .NET Framework 4.5 or higher
> - [Download and run the installer](https://hsdecktracker.net/download/).
> 
> ## Community & Troubleshooting
> - [Follow HDT on Twitter](https://twitter.com/hsdecktracker)
> - Join the Community Discord: [![Join HearthSim Community Discord](https://discordapp.com/api/guilds/265636998700728321/widget.png)](https://discord.gg/hearthsim)
> - You can find the [FAQ here](https://github.com/HearthSim/Hearthstone-Deck-Tracker/wiki/FAQ).
> - Streamers: Please read [Streaming instructions for OBS and XSplit](https://github.com/HearthSim/Hearthstone-Deck-Tracker/wiki/Streaming-Instructions) and [Twitch extension setup](https://hsdecktracker.net/twitch/setup/).
> - HSReplay.net integration: Please email <support@hsdecktracker.net> for support.
> 
> ## Contributing
> - Please read the [coding style and Commit/Pull Request guidelines](https://github.com/HearthSim/Hearthstone-Deck-Tracker/blob/master/CONTRIBUTING.md).
> - Developer Discord: [![joindeveloper#hdt](https://discordapp.com/api/guilds/195326447118712832/widget.png)](https://discord.gg/hearthsim-devs)
> - Hearthstone Deck Tracker is a [HearthSim](https://hearthsim.info) project.
> 
> ## Features
> An in-game overlay:
> 
> ![Overlay](https://github.com/HearthSim/Hearthstone-Deck-Tracker/raw/master/raw-assets/readme/overlay.png "Overlay")
> 
> The app: 
> 
> ![Tracker](https://github.com/HearthSim/Hearthstone-Deck-Tracker/raw/master/raw-assets/readme/hdt-ui.png "HDT UI")
> 
> - **Tracks**:
>   - Cards left in your deck or cards drawn from your deck.
>   - Your handcount, deckcount and draw chances.
>   - Cards played by your opponent.
>   - Your opponent's handcount, deckcount and probablities of him having/drawing cards.
>   - How long your opponent had each card in his hand and what cards have been mulliganed, stolen or returned.  
> - **Timer** for the current turn and total time spent for you and your opponent.  
> - The tracker tries to **automatically select the deck you are playing**.

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
