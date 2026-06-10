# python-hslog

## Unabridged research summary
- repo_url: https://github.com/HearthSim/python-hslog.git
- org: HearthSim
- role: log_parser_and_exporter
- confidence: 0.86
- must_use_for: live_log_to_state pipeline
- risk_flags: Python-only and focused on parser layer
- capability_scores: live_fidelity=0.64, simulation_coverage=0.11, data_freshness=0.52, parser_strength=0.79, ml_integration=0.58

## Repository-level observed structure
- top directories: hslog, tests
- top files: .gitignore, LICENSE, README.md, setup.cfg, setup.py, tox.ini
- dominant file types: .md, .py

## Readability anchor
> # hslog
> 
> [![GitHub Workflow Status (branch)](https://img.shields.io/github/actions/workflow/status/HearthSim/python-hslog/ci.yml?branch=main)](https://github.com/HearthSim/python-hslog/actions/workflows/ci.yml)
> [![PyPI](https://img.shields.io/pypi/v/hslog.svg)](https://pypi.org/project/hslog/)
> 
> hslog is a powerful Hearthstone Power.log deserializer.
> 
> 
> ## Concepts
> 
> The data read from Power.log is deserialized into packets.
> The log is read line by line using a regex-based approach, with packets
> accumulating data when they span over multiple lines.
> The `BLOCK_START` and `BLOCK_END` packets are serialized into a Block packet,
> which is nestable.
> We call the totality of the packets for a game the "Packet Tree".
> 
> 
> ## Exporting a PacketTree
> 
> The `PacketTree` object makes it easy to recursively iterate over, which in
> turn makes it very easy to export into various other formats. The `.export()`
> method on `PacketTree` will natively export the entire tree to a `Game` entity,
> using the `hearthstone.entities` module by default.
> 
> This is achieved through a very flexible class-based Exporter system, which can
> be found in `hslog.export`.
> The syntax to call an exporter directly is: `MyExporter(packet_tree).export()`.
> 
> The base logic for the Exporter is in the `BaseExporter` class.
> Calling `export()` will iterate over each packet and call `export_packet(packet)`
> on them. That method will look at the packet's type, get the matching method in
> the `self.dispatch` dict (populated by `get_dispatch_dict()`) and call it on it.
> 
> This is the default dispatch lookup:
> 
> * `CreateGame` -> `handle_create_game()`
> * `CreateGame.Player`: `handle_player()`
> * `Block`: `handle_block`
> * `FullEntity`: `handle_full_entity`

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
