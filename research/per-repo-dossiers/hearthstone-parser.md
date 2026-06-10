# hearthstone-parser

## Unabridged research summary
- repo_url: https://github.com/Tespa/hearthstone-parser.git
- org: Tespa
- role: lightweight_log_parser
- confidence: 0.51
- must_use_for: legacy_log_watch_fallback, event_stream_parsing
- risk_flags: Maintenance stale; Limited modern BG coverage
- capability_scores: live_fidelity=0.41, simulation_coverage=0.08, data_freshness=0.12, parser_strength=0.73, ml_integration=0.22

## Repository-level observed structure
- top directories: data, scripts, src, test
- top files: .gitattributes, .gitignore, CODE_OF_CONDUCT.md, LICENSE, README.md, commitlint.config.js, log.config, package-lock.json, package.json, release.config.js, tsconfig.json, tsconfig.lint.json
- dominant file types: .js, .json, .md, .ts

## Readability anchor
> # Hearthstone Parser [![CircleCI](https://circleci.com/gh/Tespa/hearthstone-parser.svg?style=svg&circle-token=05f88c42a2f9db1a70dbcd5df487818bcc6e9887)](https://circleci.com/gh/Tespa/hearthstone-parser) [![npm](https://img.shields.io/npm/v/hearthstone-parser.svg)](https://www.npmjs.com/package/hearthstone-parser) [![codecov](https://codecov.io/gh/Tespa/hearthstone-parser/branch/master/graph/badge.svg)](https://codecov.io/gh/Tespa/hearthstone-parser)
> 
> > A Node.js module for real-time parsing of Hearthstone game log files. 
> 
> ## Why make another Hearthstone log parser/watcher?
> 
> We needed to be able to rapidly implement new functionality on an as-needed basis for various broadcasts. We also wanted to ensure that the library was sound, and could be relied upon in a broadcast context. To that end, this library has been written in TypeScript, and includes tests for most functionality.
> 
> ## Install
> 
> ```sh
> npm i hearthstone-parser
> ```
> 
> ## Table of Contents
> - [Example](#example)
> - [Features](#features)
> - [Planned Features](#planned-features)
> - [API](#api)
>   - [`start`](#start)
>   - [`stop`](#stop)
>   - [`update`](#update)
>   - [`parseBuffer`](#update)
> - [Events](#events)
> - [Adding Functionality](#adding-functionality)
> - [Acknowledgements](#acknowledgements)
> 
> ## Example
> 
> By default, `hearthstone-parser` will attempt to automatically discover your Hearthstone install directory:
> ```js
> const {LogWatcher} = require('hearthstone-parser');
> const logWatcher = new LogWatcher();
> logWatcher.start();
> ```
> 
> But, you can of course pass in an explicit directory if you prefer:
> ```js
> const {LogWatcher} = require('hearthstone-parser');
> const logWatcher = new LogWatcher({

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
