# coliseum

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/coliseum.git
- org: Zero-to-Heroes
- role: replay_visualization_frontend
- confidence: 0.49
- must_use_for: replay_rendering_reference, simulation_output_consumption
- risk_flags: Deprecated Angular codebase; Not a source of rules
- capability_scores: live_fidelity=0.41, simulation_coverage=0.05, data_freshness=0.31, parser_strength=0.56, ml_integration=0.12

## Repository-level observed structure
- top directories: dependencies, replays, src, test
- top files: .gitignore, README.md, THIS PROJECT IS DEPRECATED.md, package-lock.json, package.json, replay.xml, tsconfig.json, webpack.config.js
- dominant file types: .js, .json, .md, .ts, .xml

## Readability anchor
> Coliseum is an online replay viewer for Hearthstone. It uses an [HSReplay](https://github.com/HearthSim/HSReplay) log file as a source (se below).
> 
> # Demo
> 
> See https://replays.firestoneapp.com. You can also access it from any review on https://www.zerotoheroes.com and clicking on the "New replay viewer" link at the top.
> 
> # Screenshots
> 
> See the [imgur album](https://imgur.com/a/2K3asZ9)
> 
> ![mulligan](https://i.imgur.com/fPsi8gR.jpg)
> ![spell](https://i.imgur.com/yfOek19.png)
> ![victory screen](https://i.imgur.com/ZIcStEY.png)
> 
> # How to get a replay file for local use?
> 
> -   Get one from zerotoheroes.com (go to any review, then open your inspector, go to Network tab, then copy/paste the resulting XML into the replay.xml file)
> -   You can also download one from hsreplay.net
> -   Or you can build one from your Power.log file, using for instance the [C# converter](https://github.com/Zero-to-Heroes/hs-game-converter-csharp-port) (open the project in Visual Studio, then run the test)
> 
> # Contacts & support
> 
> Join us on [Discord](https://discord.gg/H4Hj7bC)
> 
> # Contributing
> 
> ```
> $ git clone ...
> $ npm install  # You need to have node installed
> $ npm run dev # For development
> $ npm run build # For release
> 
> aws s3 cp ./dist s3://replays.firestoneapp.com --acl public-read --recursive
> aws s3 cp ./dist/coliseum.js s3://replays.firestoneapp.com --acl public-read
> ```
> 
> # Local dev (just for me)
> 
> ```
> cp dist/coliseum.js ../firestone/core/dependencies/

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
