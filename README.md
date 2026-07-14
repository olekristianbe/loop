<p align="center">
  <img src="assets/icon.png" width="128" height="128" alt="Loop icon">
</p>

<h1 align="center">Loop</h1>

<p align="center">
  Native macOS workspace for running Claude Code, Codex, and Cursor across
  projects with chat, terminals, Git, preview, planning, building, and review.
</p>

<p align="center">
  <a href="https://github.com/olekristianbe/loop/releases/latest">Download Loop</a>
</p>

---

Loop v1.3.0 is the first stable release backed by a Tauri desktop shell and a
bundled native backend. It brings local coding-agent sessions, project context,
Git workflows, terminal access, preview, planning, building, and review into one
desktop application.

> [!WARNING]
> Loop is pre-2.0 software. Expect bugs and artifact-format changes. The latest
> stable release represented by this distribution commit is v1.3.0.

## Install

1. Download the latest macOS `.dmg` from the
   [Releases page](https://github.com/olekristianbe/loop/releases/latest).
2. Open the DMG and drag Loop to Applications.
3. Launch Loop.

## Requirements

Loop requires an Apple silicon Mac running macOS 15 or newer. Install and
authenticate at least one supported local provider runtime:

- **Claude Code** — install the `claude` CLI and authenticate once.
- **Codex** — install the `codex` CLI and sign in.
- **Cursor** — install a current Cursor Agent CLI with ACP support.

Provider executable paths can be changed in **Settings → Providers**.

## Updates

Loop checks for stable updates in the background and shows an update prompt when
a newer release is available. Downloads and installation remain user initiated.

## Support

- [Report issues](https://github.com/olekristianbe/loop/issues)
- [Discussions](https://github.com/olekristianbe/loop/discussions)

## License

Copyright 2026 Lytic AS. All rights reserved. Source code is not included in
this distribution.
