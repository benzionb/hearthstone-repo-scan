# firestone

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/firestone.git
- org: Zero-to-Heroes
- role: production_overlay_and_workflow_orchestrator
- confidence: 0.82
- must_use_for: service_integration_patterns, simulation_worker_integration
- risk_flags: Large app surface; harder to isolate to engine-only logic
- capability_scores: live_fidelity=0.46, simulation_coverage=0.22, data_freshness=0.52, parser_strength=0.67, ml_integration=0.33

## Repository-level observed structure
- top directories: apps, build-tools, docs, external-libs, libs, overwolf, overwolf-plugins, test-tools, tools
- top files: .gitignore, CONTRIBUTING.md, NX, README.md, beta-test.md, decorate-angular-cli.js, dev-notes.md, electron-builder.yml, electron-prep.md, jest.config.ts, jest.preset.js, nx.json, package-lock.json, package.json, test-clean-implementation.js, tos.md, tsconfig.base.json
- dominant file types: .js, .json, .md, .ts, .xml, .yml

## Readability anchor
> [<img src="https://user-images.githubusercontent.com/43519401/188874356-9a7dd2d1-af15-4d82-8fd7-40c4f1a69259.png" width="166px" height="49px"> ](https://www.overwolf.com/app/Sebastien_Tromp-Firestone)
> 
> # What is Firestone?
> 
> Firestone is an app you run on Overwolf alongside Hearthstone (like HearthArena).
> 
> See the [list of features](https://github.com/Zero-to-Heroes/firestone/wiki/Firestone-features) and the list of [premium-exclusive features](https://github.com/Zero-to-Heroes/firestone/wiki/Premium-features).
> 
> # Contributing
> 
> More information [here](https://github.com/Zero-to-Heroes/firestone/blob/master/CONTRIBUTING.md)
> 
> # Links
> 
> - The app can be downloaded from here: https://www.overwolf.com/app/sebastien_tromp-firestone
> - If you want to come and say hi on Discord: https://discord.gg/vKeB3gnKTy
> - Stay up-to-date with what we're doing and bugs found on X: https://x.com/Firestone_HS
> - See the list of all the app's features: https://github.com/Zero-to-Heroes/firestone/wiki/Firestone-features
> - And all the premium features: https://github.com/Zero-to-Heroes/firestone/wiki/Premium-features
> 
> ## Twitter features threads
> 
> - Perils in Paradise QoL improvements: https://x.com/ZerotoHeroes_HS/status/1816439954932715608
> - Twitch features list: https://x.com/ZerotoHeroes_HS/status/1833410453487096251

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
