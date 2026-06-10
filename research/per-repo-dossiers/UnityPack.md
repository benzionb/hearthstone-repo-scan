# UnityPack

## Unabridged research summary
- repo_url: https://github.com/Zero-to-Heroes/UnityPack.git
- org: Zero-to-Heroes
- role: unity_asset_extraction_tool
- confidence: 0.22
- must_use_for: offline_asset_recovery
- risk_flags: Unmaintained; Only low-level binary parsing
- capability_scores: live_fidelity=0.05, simulation_coverage=0.01, data_freshness=0.05, parser_strength=0.18, ml_integration=0.03

## Repository-level observed structure
- top directories: bin, lib, unitypack
- top files: .gitignore, CONTRIBUTING.md, LICENSE, README.md, libogg.dll, libvorbis.dll, out.txt, setup.cfg, setup.py
- dominant file types: .json, .md, .py, .yml

## Readability anchor
> Preamble: it looks like the original repo at https://github.com/HearthSim/UnityPack is either not maintained, or the evolutions are kept private.
> 
> The goal of this repo is to try and keep things working for the newest udpates of Hearthstone (it might also work for other games or unity files, but I don't test anything with them).
> Also, I am on Windows, so things might be different from where you are.
> 
> # UnityPack
> [![Build Status](https://api.travis-ci.org/HearthSim/UnityPack.svg?branch=master)](https://travis-ci.org/HearthSim/UnityPack)
> 
> A library to deserialize Unity3D Assets and AssetBundles files (*.unity3d).
> 
> ## Dependencies
> 
> * [python-lz4](https://github.com/python-lz4/python-lz4) (For UnityFS-compressed files)
> 
> 
> ## How Unity packs assets
> 
> Most extractors for Unity3D files (such as [Disunity](https://github.com/ata4/disunity))
> deal with the format as a "file store", treating it as one would treat a zip. This is
> not how the format actually works.
> 
> Unity files are binary-packed, serialized collections of Unity3D classes. To this end,
> they are much closer to a json file containing arrays of objects.
> 
> Some of those classes have fields which contain raw data, such as Texture2D's `image data`
> field or TextAsset's `m_Script` field. Using this, files can be "extracted" from the asset
> bundles by using their `m_Name` and an appropriate extension. But doing so leaves out all
> the "unextractable" classes which one might want to deal with.
> 
> 
> ## Usage
> 
> ### Usage for noobs
> 
> If, like myself, you are not a frequent / fluent python speaker, this is what you have to do after cloning UnityPack:
> 
> * You need to have python3 installed
> * Copy the `libogg.dll` and `libvorbis.dll` from `./lib` into the root folder (`.`)
> * Run `./setup.py install`
> * Extract the data you're interested, for insance `./bin/unityextract --audio -o out/audio /d/Games/Hearthstone/Data/Win/gameobjects0.unity3d`

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
