# api-simulate-battlegrounds-battle

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/api-simulate-battlegrounds-battle.git
- org: Zero-to-Heroes
- role: combat_reference_engine
- confidence: 0.76
- must_use_for: combat_rollout_scoring, replay_board_state_sim_evaluation
- risk_flags: No buy-phase/lobby simulation; Patch assumptions implicit in ref-data dependency
- capability_scores: live_fidelity=0.42, simulation_coverage=0.73, data_freshness=0.46, parser_strength=0.58, ml_integration=0.33

## Repository-level observed structure
- top directories: sim-samples, src, test
- top files: .gitignore, README.md, package-lock.json, package.json, template.yaml, tsconfig.json, webpack.config.js
- dominant file types: .js, .json, .md, .ts, .yaml

## Readability anchor
> # Test it
> 
> ```
> npm install
> npm run test-board
> ```
> 
> Then you can just modify the `test/full-game/game3.json` file to change the boards initial compositions.
> 
> ## Get a board state from the app
> 
> Look for the `MainWindow.html.log` file located in `%localappdata%\Overwolf\Log\Apps\Firestone`. Do a search for `[bgs-simulation] battle simulation request prepared`, and this line should log the full JSON that you can use as an input (typically, this is what you put in the `game3.json` file referenced above).
> 
> ## Check a simulation output
> 
> You first need to download, build and run a local instance of [Coliseum](https://github.com/Zero-to-Heroes/coliseum)
> 
> Then, at the end of the test (e.g. `full-test.test` mentioned above), add / uncomment these lines:
> 
> ```
> const sample = simulationResult.outcomeSamples.lost[0];
> const base64 = encode(JSON.stringify(sample));
> ```
> 
> (using `won` or `tied` instead of `lost` if that's what you're looking for).
> 
> A big base64 string will be output to the console.
> 
> Copy it, and open a new tab in your navigator at the following URL: `file:///<path_to_your_coliseum_repo>/dist/index.html?bgsSimulation=<the_big_base64_string`. It will then replay the simulation.
> 
> # Deploy
> 
> ```
> npm run build && npm run package && npm run deploy
> 
> rm -rf dist && tsc && rm -rf dist/node_modules && 'cp' -rf dist/ /e/Source/zerotoheroes/firestone/node_modules/\@firestone-hs/simulate-bgs-battle/
> rm -rf dist && tsc && rm -rf dist/node_modules && 'cp' -rf dist/ /e/Source/zerotoheroes/coliseum/node_modules/\@firestone-hs/simulate-bgs-battle/
> rm -rf dist && tsc && rm -rf dist/node_modules && 'cp' -rf dist/ /e/Source/zerotoheroes/firestone-libs/node_modules/\@firestone-hs/simulate-bgs-battle/
> rm -rf dist && tsc && rm -rf dist/node_modules && npm publish
> ```

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
