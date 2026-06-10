# stone_ground_hearth_battles

## Unabridged research summary
- repo_url: https://github.com/JDBumgardner/stone_ground_hearth_battles
- org: JDBumgardner
- role: legacy_full_simulator_reference
- confidence: 0.18
- must_use_for: old_rules_architecture
- risk_flags: Single outdated snapshot; Hardcoded patch data
- capability_scores: live_fidelity=0.09, simulation_coverage=0.62, data_freshness=0.06, parser_strength=0.31, ml_integration=0.41

## Repository-level observed structure
- top directories: benchmarks, data, doc, frozenlist, hearthstone, plackett_luce, proto, rust, tensorboard_vega_embed, tests
- top files: .gitignore, LICENSE.txt, Readme.md, mypy.ini, requirements.txt, setup.py
- dominant file types: .json, .md, .py

## Readability anchor
> ## Stone Ground Hearth Battles
> 
> Hearthstone battlegrounds simulator is licensed under the Apache 2.0 License
> 
> This repository includes a simulator along with bots and allows the user to play against the bots. There are various
> attempts to use Pytorch to train a bot.
> 
> ### Tensorboard Plugin
> 
> This repo also contains a Tensorboard plugin for displaying vega/vega-lite/altair plots in tensorboard. We use this to
> plot debug information about our pytorch bots, but this plugin works standalone.
> 
> ![Example Screenshot of Tensorboard_Vega_Embed plugin](doc/Tensorboard_Vega_Embed_example.png)
> 
> To use it, run
> 
> `$ python setup.py develop`
> 
> from within the `tensorboard_vega_embed/` directory. When you launch tensorboard, it will show up as a new tab labeled "
> VEGA_EMBEDX". To uninstall it, run `$ python setup.py develop --uninstall`.
> 
> ### Distributed Training Environment
> 
> This repo also contains a distributed training setup to play several games in parallel using a single GPU, using Pytorch
> Distributed and python asyncio.
> 
> ![Architecture Diagram](doc/architecture.svg)
> 
> ### Benchmarks
> 
> Speed of simulation can be important for Reinforcement Learning. Woe is upon us for choosing to write the simulator in
> python, thinking that it would not be the bottleneck. CPU is the bottleneck for experience generation, not GPU :(
> 
> Therefore, we have benchmarks to profile the performance of our simulator, and identify bottlenecks. To run one of the
> profiles, run, e.g.
> 
> ```shell
> $ PYTHONPATH=. python3 -m cProfile -o benchmarks/profiles/simulation.cprof benchmarks/benchmark_simulation.py
> ```

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
