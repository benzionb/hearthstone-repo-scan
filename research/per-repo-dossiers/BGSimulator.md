# BGSimulator

## Unabridged research summary
- repo_url: https://github.com/yossielimelech/BGSimulator.git
- org: yossielimelech
- role: historical_full_simulation_reference
- confidence: 0.22
- must_use_for: old_sim_benchmark_baseline
- risk_flags: Stale 2020-era mechanics; No maintained patch update path; Limited BG rule parity
- capability_scores: live_fidelity=0.12, simulation_coverage=0.46, data_freshness=0.06, parser_strength=0.18, ml_integration=0.08

## Repository-level observed structure
- top directories: BGSimulator
- top files: .gitattributes, .gitignore, BGSimulator.sln, README.md
- dominant file types: .cs, .md

## Readability anchor
> # BGSimulator
> 
> BGSimulator is a Hearthstone Battlegrounds simulator developed to be used together with deep learning and reinforcement learning algorithms.
> 
> To learn more about Hearthstone Battlegrounds follow this link: https://playhearthstone.com/en-us/blog/23156373
> 
> The Hearthstone Battlegrounds game mode consist of two phases.
> 
> The Recruiting phase:
> 
> In Battlegrounds, rather than building a deck of cards, you’ll construct an ever-evolving board of Minions during visits to Bob’s Tavern at the start of the match and between combat rounds. As the match progresses, you’ll be granted an increasing amount of Coin to be spent upgrading and modifying your board. Most things you do in the Tavern will cost you Coin, and Coins can’t be saved up to be spent in future rounds.
> 
> The Combat phase:
> 
> Once your time in the Tavern is over, combat will begin! During the combat phase, you will be pitted against a randomly chosen opponent and your recruited Minions will battle to the death until a victor is decided. Minions will take turns attacking, starting with each player’s left-most Minion. Minion keywords work just as they would in a normal game of Hearthstone. For example, Taunt Minions must be attacked first, Poisonous Minions destroy any Minion they deal damage to, Divine Shield will block the first source of damage, etc.
> 
> 
> Current development stage: done with all the cards and mechanics. No heroes.
> 
> If you are intrested to contribute and improve the codebase feel free to ask.
> 
> 
> 
> Copyright © Yossi Elimelech. All Rights Reserved.

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
