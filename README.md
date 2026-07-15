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

Loop is a macOS desktop control plane for local coding agents. It brings Claude
Code, Codex, and Cursor into one project workspace with chat, terminals, diffs,
preview, Git, and dedicated Plan, Build, and Review modes.

> [!WARNING]
> Loop is pre-2.0 software. Expect bugs and artifact-format changes. The latest
> stable release represented by this distribution commit is v1.4.1.

## Plan, Build, and Review

Loop defines each mode's protocol, context, artifacts, validation, and UI. The
selected provider owns the work inside the run, including native subagents or
parallel workflows when supported. Loop does not maintain a separate hidden
task scheduler.

- **Plan** explores the repository, interviews you, asks for confirmation, and
  writes a decision-complete Markdown plan. Loop validates the file after a
  write and can request one structural repair.
- **Build** runs a full plan, selected work items, or a custom slice through one
  visible coordinator turn. It verifies the work and writes a validated report;
  branch, commit, push, prevent-sleep, network, and stop options remain
  Loop-controlled.
- **Review** performs a read-only review over the selected scope and checks.
  Substantive reviews can use provider-native specialists and return one
  consolidated result.

New plans and reports are inspectable Markdown under the project-local `.loop/`
directory. `.planner` remains read-only legacy input and can be migrated
non-destructively.

## Install

1. Download the latest macOS `.dmg` from the
   [Releases page](https://github.com/olekristianbe/loop/releases/latest).
2. Open the DMG and drag Loop to Applications.
3. Launch Loop.

## Requirements

Loop v1.4.1 requires an Apple silicon Mac running macOS 15 or newer. Install and
authenticate at least one supported local provider runtime:

- **Claude Code** — install the `claude` CLI and authenticate once.
- **Codex** — install the `codex` CLI and sign in.
- **Cursor** — install a current Cursor Agent CLI with ACP support.

Provider executable paths can be changed in **Settings → Providers**.

## Updates

Loop checks for stable updates in the background and shows an update prompt when
a newer release is available. Downloads and installation remain user initiated.
You can also use **Loop → Check for Updates…** from the macOS app menu.

## Support

- [Report issues](https://github.com/olekristianbe/loop/issues)
- [Discussions](https://github.com/olekristianbe/loop/discussions)

## License

Copyright 2026 Lytic AS. All rights reserved. Source code is not included in
this distribution.
