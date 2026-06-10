# DeepBattler

## Unabridged research summary
- repo_url: https://github.com/william-Dic/DeepBattler.git
- org: william-Dic
- role: live_state_plugin_and_agent_harness
- confidence: 0.66
- must_use_for: live_snapshot_ingest, action_prompt_orchestration_patterns
- risk_flags: Windows + HDT coupling; Research prototype, limited portability
- capability_scores: live_fidelity=0.62, simulation_coverage=0.07, data_freshness=0.39, parser_strength=0.51, ml_integration=0.85

## Repository-level observed structure
- top directories: Agent, DeepBattlerPlugin
- top files: .gitignore, GRPO_TRAINING_GUIDE.md, README.md
- dominant file types: .cs, .json, .md, .py

## Readability anchor
> # DeepBattler - Your BEST LLM Battlegrounds Coach/Friend！🍻🍻 <a id="english"></a>
> 
> **[English](#english)** | **[中文](#chinese)** | **[日本語](#japanese)**
> 
> ### Well met, hero! I'm DeepBattler, the tavern master who brews brilliant plays, belly laughs, and more pep than a dancing Murloc on espresso! 🍻🐟
> 
> DeepBattler, a LLM-Driven Hearthstone Battlegrounds enthusiast like us. DeepBattler seamlessly integrates with the Hearthstone Deck Tracker (HDT) plugin to provide you with **real-time strategic advice**. Whether you're aiming to climb the ranks or just improve your game experience, DeepBattler has got your back!
> 
> DeepBattler's strength can match that of the **top 0.1% players on EU servers (8K ELO)**, thanks to its insightful, voice-assisted guidance that helps you make the best decisions on the fly. Let's take your gameplay to the next level!
> 
> **Demos can be found here! [YouTube Link](https://drive.google.com/file/d/1DY8hDdvVe-Iw7zKItOB1B-rvaf87l_Jc/view?usp=sharing)**
> 
> ## ✨ New Features
> 
> ### 🎯 Real-Time Visual Suggestion Window
> - **In-Game Overlay**: A beautiful floating window displays DeepBattler's strategic suggestions directly in your game interface
> - **Live Updates**: Suggestions update in real-time as the game state changes
> - **Clear Formatting**: Easy-to-read bullet points with larger, clearer fonts
> - **Position Control**: Draggable window that stays in your preferred location (default: bottom-left corner)
> 
> ### 🎤 Voice + Text Dual Output
> - **Voice Interaction**: Natural voice conversation using Google Gemini Live API
> - **Text Display**: Simultaneous text output using Gemini 2.5 Flash Lite for visual reference
> - **Parallel Processing**: Audio and text responses generated simultaneously for the best of both worlds
> - **Smart Updates**: Text suggestions automatically refresh with each agent response
> 
> ### 🔄 Dynamic Game State Integration
> - **Auto-Detection**: Automatically detects when a game starts and adapts accordingly
> - **Real-Time Monitoring**: Continuously monitors game state changes and updates system prompts
> - **Casual Chat Mode**: When no game is active, DeepBattler switches to friendly conversation mode
> - **Seamless Transitions**: Smoothly transitions between game mode and chat mode
> 
> ## System Components  
> 
> ### 1. Hearthstone Deck Tracker (HDT) Plugin - Real-Time Data Collection API  
> The DeepBattler Plugin serves as a **real-time API endpoint for Battleground Board data**, continuously monitoring and capturing all board state information during gameplay.
> 
> - **Real-Time Monitoring:** Continuously tracks your game state as it happens, capturing every change in real-time
> - **Comprehensive Data Collection:** Records all board data including:
>   - Player hero information (name, health, hero power with cost)

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
