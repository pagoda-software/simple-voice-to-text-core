# simple-voice-to-text-core

English | [Tiếng Việt](README.vi.md)

An offline speech-to-text core library written in TypeScript. Vietnamese first.

> Status: just getting started, no working code yet.

## Goals

- **Input:** an audio file (first priority) and live recording from the microphone.
- **Output:** the text (a paragraph) transcribed from that audio.
- Runs on an offline model and makes a best guess even when the speech is unclear.
- Works on low-end machines (CPU) as well as machines with a GPU.
- Easy to install and set up, and usable on multiple platforms later.

## Scope of this repo

This repo only contains the **core processing logic**, not a full app. The core does not print to the screen or parse command-line arguments; everything goes in and out through functions and return values. A small CLI is included for trying things out and as an example of how to use the core.

The apps (desktop, mobile, web) will come later, in separate repos, and will reuse this core.

## Decisions so far

| Item | Choice |
| --- | --- |
| Language | TypeScript (JS/TS, TS preferred) |
| First interface | CLI (terminal) |
| Speech recognition | Offline model |
| First language | Vietnamese |
| First test platform | Windows 11 |

## Roadmap

- [ ] **Step 0:** try models by hand on a 30-60 second recording, compare quality and speed (CPU vs GPU), pick the model and library.
- [ ] **Step 1:** CLI that takes a file path, converts it to the format the model needs, runs the model and prints the text to the terminal.
- [ ] **Step 2:** support long files (chunking), show progress, save to a `.txt` file, handle errors.
- [ ] **Step 3:** live recording from the microphone.
- [ ] **Step 4:** try noise reduction and measure the before/after effect (keep it only if it actually helps).
- [ ] **Later:** desktop app, mobile app, web app (if needed) with a simple, practical interface.

## Design principles

- Split processing into separate modules: audio reading/conversion, transcriber, result output.
- Make it easy to swap models without touching the rest of the code.
- Prefer libraries that ship prebuilt binaries so users don't have to compile anything.
- Download the model automatically on first run, with a progress indicator.

## Notes

- Audio files and model files are **not** committed (see `.gitignore`).
- This is a learning project: the core is written by hand, and AI is used to explain, review and help with side tasks.

## License

Not chosen yet.
