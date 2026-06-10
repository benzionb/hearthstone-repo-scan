# python-hearthstone

## Unabridged research summary
- repo_url: https://github.com/HearthSim/python-hearthstone.git
- org: HearthSim
- role: parser_and_schema_library
- confidence: 0.88
- must_use_for: replay_parsing, entity modeling, bg enum handling
- risk_flags: No behavior engine
- capability_scores: live_fidelity=0.66, simulation_coverage=0.1, data_freshness=0.71, parser_strength=0.8, ml_integration=0.48

## Repository-level observed structure
- top directories: hearthstone, scripts, tests
- top files: .gitignore, LICENSE, README.md, setup.cfg, setup.py, tox.ini
- dominant file types: .md, .py, .xml

## Readability anchor
> # python-hearthstone
> 
> [![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/hearthsim/python-hearthstone/ci.yml?branch=master)](https://github.com/HearthSim/python-hearthstone/actions/workflows/ci.yml)
> [![PyPI](https://img.shields.io/pypi/v/hearthstone.svg)](https://pypi.org/project/hearthstone/)
> 
> A Hearthstone Python library containing:
> 
> * A CardDefs.xml parser (`hearthstone.cardxml`)
> * A DbfXml parser (`hearthstone.dbf`)
> * A deck code encoder and decoder (`hearthstone.deckstrings`)
> * Hearthstone enums as IntEnum (`hearthstone.enums`)
> 
> The CardDefs.xml data for the latest build can optionally be installed from the
> [python-hearthstone-data repository](https://github.com/HearthSim/python-hearthstone-data)
> or on PyPI with `pip install hearthstone_data`. Otherwise, they will be download at runtime.
> 
> 
> ## Requirements
> 
> * Python 3.6+
> * lxml
> 
> ## Installation
> 
> * To install from PyPI: `pip install hearthstone`
> 
> 
> ## License
> 
> This project is licensed under the MIT license. The full license text is
> available in the LICENSE file.
> 
> 
> ## Community
> 
> This is a [HearthSim](https://hearthsim.info) project.
> Join the HearthSim Developer community [on Discord](https://discord.gg/hearthsim-devs).

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
