<p align="center">
  <img src="assets/icon.png" width="128" height="128" alt="Loop icon">
</p>

<h1 align="center">Loop</h1>

<p align="center">
  Native macOS app for running Claude Code and Codex coding sessions across
  your projects — with a JSON planner, build orchestrator, and in-app preview.
</p>

<p align="center">
  <a href="https://github.com/olekristianbe/loop/releases/latest">Download</a>
</p>

---

## Why Loop?

Loop is a desktop coding agent for local AI workflows. Instead of babysitting
terminal windows or losing context between phases, you get:

- **Plan → Build → Review in one app.** The planner turns your dump of ideas
  into a JSON task list. The build orchestrator drives the agent through it,
  one commit per task. Review surfaces issues into the next round.
- **Multiple providers.** Claude Code (via the Anthropic SDK) and Codex CLI,
  picked per task from a single provider/model dropdown.
- **Multi-project workspace.** Switch between projects instantly. Each keeps
  its own chat history, planner state, terminals, files panel, and git view.
- **Human-check queue.** Tasks that need your eyes land in a queue with inline
  notes; your feedback turns into the next plan round automatically.
- **In-app web preview.** A `WebContentsView` next to the chat for previewing
  the thing you're building, with browser automation hooks.
- **Generate-then-edit.** Commit messages and PR titles are drafted by the
  agent and edited by you before they ship.

## Workflow

**Plan** — Drop ideas, bugs, or feature requests into the chat. The planner
asks clarifying questions and produces a JSON task list with dependencies and
scoped state. Existing plans can be edited or upgraded in place.

**Build** — The orchestrator runs tasks sequentially with their declared
dependencies, validates after each (typecheck / test / lint), and commits one
task at a time. You can queue messages, edit them while they wait, or steer
mid-response.

**Review** — Loop scans the changes for bugs, checks against documentation
and references, and feeds findings into the next planning round through the
human-check queue.

## Install

1. Download the latest `.dmg` from the [Releases page](https://github.com/olekristianbe/loop/releases/latest).
2. Open the DMG and drag Loop to Applications.
3. Launch Loop.

## Requirements

Loop drives external coding agents. Install at least one before first run:

- **Claude Code** — `npm install -g @anthropic-ai/claude-code`, then
  `claude auth login`.
- **Codex CLI** — install [Codex CLI](https://github.com/openai/codex) and
  run `codex login`.

**System:**
- macOS 15 (Sequoia) or later
- Apple Silicon (arm64). Intel Macs are not supported.

## Updates

Loop checks for updates in the background and surfaces a sidebar pill when one
is available. Downloads and installs are user-initiated. You can also check
manually from Settings.

## Support

- [Report Issues](https://github.com/olekristianbe/loop/issues)
- [Discussions](https://github.com/olekristianbe/loop/discussions)

## License

Copyright 2026 Lytic AS. All rights reserved. Source code is not included in
this distribution.
