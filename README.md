# Mi Work

A native macOS AI agent interface. Run multiple independent AI sessions in tabs, each with its own conversation context, tool access, and the ability to spawn parallel sub-agents for complex tasks.

## What It Does

- **Multi-session tabs** — each tab runs an independent AI agent conversation
- **Sub-agents** — sessions can spawn child agents that work in parallel and report back
- **Local tools** — agents interact with your machine through plugins running in isolated subprocesses
- **Speech-to-text** — built-in voice input with configurable keyboard/mouse triggers
- **Streaming output** — real-time token streaming with activity indicators
- **Background execution** — sessions keep running when the app is minimized

## Install

Download the latest DMG from [Releases](https://github.com/itsklimov/mi-work/releases), open it, and drag Mi Work to Applications.

Auto-updates are built in via Sparkle — the app checks for new versions automatically.

**Requirements:** macOS 15 (Sequoia) or later.

## Setup

On first launch, the app opens Settings to set up your Anthropic API key:

- **Sign In with Anthropic** — OAuth flow opens your browser, creates an API key automatically
- **Manual entry** — paste an existing API key from [console.anthropic.com](https://console.anthropic.com)

The key is stored securely in macOS Keychain.

## Architecture

- **Native AppKit** — no Electron, no web views, built with Swift and AppKit
- **Swift concurrency** — actors for isolation, structured concurrency for all async work
- **Plugin system** — external processes communicate via JSON-RPC over Unix sockets
- **Dual-stream UI** — content stream (conversation) and activity stream (status bar) rendered independently at up to 120fps

## License

Proprietary. All rights reserved.
