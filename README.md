# Mi Work

A native macOS AI agent workspace. Run multiple independent AI sessions in tabs, each with its own conversation context, tool access, and the ability to spawn parallel sub-agents for complex tasks.

## Why It Matters

- Native desktop interface for long-running agent work instead of a single browser chat
- Parallel sub-agents and local tool access in the same session model
- Public release surface for a production-shaped macOS AI product

## Download

Download the latest DMG from [Releases](https://github.com/itsklimov/mi-work/releases).

The public repository currently ships release artifacts and product documentation rather than the full application source tree.

## What It Does

- **Multi-session tabs** — each tab runs an independent AI agent conversation
- **Sub-agents** — sessions can spawn child agents that work in parallel and report back
- **Local tools** — agents interact with your machine through plugins running in isolated subprocesses
- **Speech-to-text** — built-in voice input with configurable keyboard/mouse triggers
- **Streaming output** — real-time token streaming with activity indicators
- **Background execution** — sessions keep running when the app is minimized

## Install

Download the latest DMG from [Releases](https://github.com/itsklimov/mi-work/releases), open it, and drag Mi Work to `/Applications`.

Auto-updates are built in via Sparkle — the app checks for new versions automatically.

**Requirements:** macOS 15 (Sequoia) or later.

## Quick Start

1. Launch Mi Work from `/Applications`.
2. On first launch, open Settings and connect an Anthropic API key.
3. Create a new tab to start an isolated work session.
4. Enable the tools you want that session to access.
5. Use sub-agents when the task benefits from parallel execution.

## API Key Setup

Settings supports two setup paths:

- **Sign In with Anthropic** — OAuth flow opens your browser, creates an API key automatically
- **Manual entry** — paste an existing API key from [console.anthropic.com](https://console.anthropic.com)

The key is stored securely in macOS Keychain.

## Architecture Highlights

- **Native AppKit** — no Electron, no web views, built with Swift and AppKit
- **Swift concurrency** — actors for isolation, structured concurrency for all async work
- **Plugin system** — external processes communicate via JSON-RPC over Unix sockets
- **Dual-stream UI** — content stream (conversation) and activity stream (status bar) rendered independently at up to 120fps

## License

Proprietary. All rights reserved. See [LICENSE](LICENSE).
