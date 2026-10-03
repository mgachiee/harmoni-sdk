<div align="center">
  <img width="256" height="256" alt="harmoni-logo" src="https://github.com/user-attachments/assets/20566383-9654-4342-a7c4-4ec95a38ee6c" />
  <h1>HARMONI SDK</h1>
  <p><strong>A Generative Multi-Agent Music System for Real-Time Interactive Media</strong></p>

  <!-- Badges -->
  <p>
    <img src="https://img.shields.io/badge/integration-TCP%20Socket-blue.svg" alt="Integration" />
    <img src="https://img.shields.io/badge/architecture-Multi--Agent-orange" alt="Architecture" />
    <img src="https://img.shields.io/badge/release-Beta-brightgreen" alt="Release State" />
  </p>
</div>

## 📖 Overview

**Hybrid Affective Rule & Markov Orchestration for Non-linear Immersion (HARMONI)** is a pure-affective, zero-latency procedural music engine built on a multi-agent architecture. 

Harmoni is designed to run as a standalone, local-first sidecar process beside your game. Instead of cross-fading static audio loops, it synthesizes dynamic, multi-stem musical scores in real-time based on two simple psychological metrics: **Valence** (positivity/negativity) and **Arousal** (intensity/energy). 

By feeding the engine your game's telemetry over a lightweight TCP socket, Harmoni orchestrates melody, harmony, bass, and percussion to perfectly match your player's exact emotional state—all with zero network latency and no cloud dependencies.

---

## ✨ Features

- **Pure Affective Control:** Drive the entire engine using only Valence [-1.0, 1.0] and Arousal [-1.0, 1.0]. The engine handles the music theory, voice leading, and orchestration.
- **Direct OS Audio:** The engine outputs audio directly to the player's speakers via a built-in FluidSynth backend and 4-stage DSP mixing bus. Your game engine doesn't have to process or mix a single audio frame.
- **Dynamic Orchestration:** Features a 5-tier continuous arousal hierarchy with 11 distinct instrumental agents (including Concert Piano, Cello, Contrabass, and Percussion Batteries).
- **Acoustic Humanization:** Built-in Gaussian velocity noise and strict low-interval limits ensure the generated MIDI data sounds like a human performance, not AI slop.
- **Engine Agnostic:** Connects via a standard TCP socket. Works instantly with Unity, Unreal, Godot, or any custom engine capable of sending JSON strings.

---

## 🚀 Getting Started

To keep integration as frictionless as possible, the Harmoni Engine is distributed as a single, pre-compiled standalone executable. **No Python or audio programming experience is required.**

### 1. Download the Engine
Grab the latest release bundle for your operating system from the [**Releases Tab**](https://github.com/YOUR_USERNAME/harmoni-sdk/releases/latest).

### 2. Start the Sidecar
Extract the archive and run the executable beside your game project's local tooling. The engine runs quietly in the background on port `6767`:
```bash
# Windows
./harmoni-server.exe --port 6767

# macOS / Linux
chmod +x harmoni-server
./harmoni-server --port 6767
```
*(Tip: You can launch this silently as a background process directly from your Game Engine using OS process creation commands).*

### 3. Connect Your Game
Open a TCP socket to `127.0.0.1:6767` and send a handshake. As you stream JSON telemetry frames containing `valence` and `arousal` values, Harmoni will immediately begin synthesizing and playing the adapted score directly to the player's speakers.

---

## 📚 Documentation & Integration Guide

For full integration instructions and the TCP JSON schema definitions, please visit the official documentation:

👉 **[Read the Harmoni TCP Integration Guide](https://your-docs-website.com)** 👈

*(Note: The documentation includes a complete mapping guide to help you translate your game metrics—like player health, enemy proximity, and zone changes—into Valence and Arousal values).*

---

## ⚖️ License & Attribution

Harmoni is proprietary middleware provided free of charge for both commercial and non-commercial games, provided that strict attribution requirements are met. 

**You must include the following text in your game's credits:**
> *"Procedural Music powered by the Harmoni Engine, created by Mark Allen G. Bobadilla, Sharwyn C. Degulacion, Marcus Jenne C. Gutierrez, and Karl Joseph M. Logdat."*

For the full legal terms, including restrictions against reverse-engineering and standalone redistribution, please read the [LICENSE.md](./LICENSE.md) file included in this repository.

---
*Built for the future of interactive audio.*
