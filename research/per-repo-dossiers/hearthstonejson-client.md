# hearthstonejson-client

## Unabridged research summary
- repo_url: https://github.com/HearthSim/hearthstonejson-client.git
- org: HearthSim
- role: raw_card_metadata_fetch_client
- confidence: 0.79
- must_use_for: dynamic_card_dataset_refresh
- risk_flags: No behavioral semantics
- capability_scores: live_fidelity=0.58, simulation_coverage=0.05, data_freshness=0.79, parser_strength=0.4, ml_integration=0.08

## Repository-level observed structure
- top directories: src
- top files: .gitignore, CHANGELOG.md, LICENSE, README.md, index.d.ts, package.json, rollup.config.js, tsconfig.json, yarn.lock
- dominant file types: .js, .json, .md, .ts

## Readability anchor
> # HearthstoneJSON Client
> [![GitHub Workflow Status (branch)](https://img.shields.io/github/actions/workflow/status/HearthSim/hearthstonejson-client/ci.yml?branch=main)](https://github.com/HearthSim/npm-hearthstonejson-client/actions/workflows/ci.yml)
> [![npm](https://img.shields.io/npm/v/hearthstonejson-client.svg)](http://npmjs.com/package/hearthstonejson-client)
> 
> Fetches Hearthstone card data from [HearthstoneJSON](https://hearthstonejson.com/).
> 
> 
> ## Install
> 
> Install the package from npm using your favourite package manager:
> 
> ```
> $ yarn add hearthstonejson-client
> ```
> 
> In order to use this package in a browser you'll need something like Webpack or Browserify.
> 
> 
> ## Examples
> 
> ```javascript
> import HearthstoneJSON from "hearthstonejson-client";
> 
> var hsjson = new HearthstoneJSON();
> 
> // get the latest data
> hsjson.getLatest().then(cards => {
>   console.log(cards);
> });
> 
> // specify a language
> hsjson.getLatest("deDE").then(cards => {/*...*/});
> 
> // specify a certain Hearthstone build number
> hsjson.get(54613).then(cards => {/*...*/});
> ```
> 
> 
> ## Typings

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
