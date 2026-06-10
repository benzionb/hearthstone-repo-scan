# SabberStone

## Unabridged research summary
- repo_url: https://github.com/HearthSim/SabberStone.git
- org: HearthSim
- role: legacy_generic_simulator
- confidence: 0.34
- must_use_for: generic_engine_design_inspiration
- risk_flags: No concrete BG buy-phase layer; Stale data
- capability_scores: live_fidelity=0.08, simulation_coverage=0.18, data_freshness=0.05, parser_strength=0.26, ml_integration=0.03

## Repository-level observed structure
- top directories: SabberStoneCore, SabberStoneCoreTest, SabberStoneGui, core-extensions, docs
- top files: .gitattributes, .gitignore, LICENSE, README.md, SabberStone.sln, SabberStone.sln.DotSettings, SabberStone.sln.licenseheader, appveyor.yml
- dominant file types: .cs, .json, .md, .yml

## Readability anchor
> <p align="center">
> <img src="docs/readme/sabberstoneNew.png" alt="SabberStone logo" height="80%"/>
> </p>
> 
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
> [![Build status](https://ci.appveyor.com/api/projects/status/051e59v5u9hm10qr?svg=true)](https://ci.appveyor.com/project/darkfriend77/sabberstonecore)
> [![Build status master](https://ci.appveyor.com/api/projects/status/051e59v5u9hm10qr/branch/master?svg=true)](https://ci.appveyor.com/project/darkfriend77/sabberstonecore/branch/master)
> [![nuget](https://img.shields.io/nuget/v/SabberStoneCore)](https://img.shields.io/nuget/v/SabberStoneCore)
> [![license](https://img.shields.io/github/license/HearthSim/SabberStone)](https://img.shields.io/github/license/HearthSim/SabberStone)
> [![contributors](https://img.shields.io/github/contributors/HearthSim/SabberStone)](https://img.shields.io/github/contributors/HearthSim/SabberStone)
> # SabberStone 2.1
> Massive changes and updates are applied!
> Please check the Changelog: https://github.com/HearthSim/SabberStone/wiki/Changelog
> 
> # Overview
> 
> **State of Implementation: 98% (Rise of Shadows 94%, Rastakhan's Rumble 95%, The Boomsday Project 98%, The Witchwood 99%) of current Standard Cards (Year of the Dragon)!** ***(23.07.2019)***
> 
> SabberStone is just another Hearthstone simulator and implementation, written in C#. The project was started in Nov'16 while trying to implement aura, buffs & triggers into Brimstone. Focused to prototype my so called onion system I created SabberStone, which is using a layer approach to handle entity changing enchantments. Since then I haven't stopped implementing day by day new cards, new tests and new stuff. I created for fun a visualisation and a scoring based tree search a.i. which can be used to play games ([SabberStoneGui](/extensions/SabberStoneGui)).
> 
> By now this is a one man show, but there is still a lot of work to do, so any help is appreciated. The base code of Brimstone was a great inspiration for this project. Big thanks to **@Pattux**, **@Patashu** for helping on hearthstone super science problems ^^ thx **@Katy** for inspiration. And thx a lot to **@Citiral**, **@BertP** for working out on the stove implementation. And thx to **@Milva** who did a refactoring on the aura & enchantment system, with great value and is working hard for this project! You're welcome!
> 
> If you enjoy using SabberStone consider supporting us at [buymeacoffee.com/darkfriend77](https://www.buymeacoffee.com/darkfriend77)
> 
> Join us on [Discord](https://discord.gg/my9WTwK)!
> 
> **Sabberstone Simulator has an own visualisation and client/server architecture for AI research!**
> ![Preview SabberStone connected to the Stove project](docs/readme/clientserver.PNG)
> 
> ### Project Structure ###
> 
> * **SabberStoneCore** *(.NET Core)*
> 
>   Core simulator engine, all the functions needed for the simulator are in here. Check out the Wiki [Link](https://github.com/HearthSim/SabberStone/wiki) for informations about the core and how to use it.
> 
> * **SabberStoneCoreTest** *(.NET Core)*
> 
>   UnitTest for the simulator, there is a generated test for each card in the current game.
> 
> * **SabberStoneCoreConsole** *(.NET Core)*

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
