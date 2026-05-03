# Changelog

All notable changes to Loop will be documented in this file.

## [0.2.0] - 2026-05-03

Major release. Loop v0.2 is a near-rewrite of the v0.1 workflow around a JSON
planner, multi-provider execution, and a sidebar workspace for tasks, builds,
and human checks.

### Added
- **Codex provider** alongside Claude. Pick a provider/model from a single
  dropdown; build orchestration runs through a shared provider abstraction.
- **JSON planner** — structured tasks with explicit dependencies, scoped state,
  and validation. Replaces the v0.1 markdown `.planner/` format. v0.1 plans
  are detected and offered an upgrade path.
- **Build orchestrator** — sequential dependency scheduling, per-task scope,
  one commit per task, no auto-archive on completion.
- **Human-check queue** — inline notes on tasks, feedback drafts, plan-
  next-round drafts, and upgrade-fix drafts.
- **In-app web preview** (`WebContentsView`) for the thing you're building,
  with browser automation hooks.
- **Monaco editor takeover** in the center pane, with light/dark themes that
  follow the app theme.
- **Generate-then-edit UX** for commit messages and PR titles — agent drafts,
  you edit, you ship.
- **Queue-first messaging** with editable queued cards and an explicit
  "steer" action that kills and resumes the active response.
- **TodoWrite list** rendered above the input field while the agent works.
- **Per-project sidebar** with unified project switcher, files panel, and
  diffs view.
- **Status dot indicators** (green / blue / orange) on tabs and the
  segmented control.
- **Cmd+P fuzzy file search** with exact-match prioritization.
- **Manual git refresh** button in the Changes panel.
- **Test execution and lint enforcement** in the build system.
- **Stable-only update channel** — rejects nightly-shaped versions at runtime
  so installed Loops only see stable v0.2+ updates.

### Changed
- **Workflow** is now Plan → Build → Review, with chat as the primary surface
  for clarifying questions. The v0.1 separate Research phase is gone.
- **Plan tab** redesigned as a sidebar workspace with Tasks, Builds, Human
  checks, legacy upgrade, and explicit archive actions.
- **Build composer** UX: compact visible prompt, default-ready tasks, stable
  branch validation, review checks, and new-chat handling.
- **Plan and Build prompts** rewritten around native Loop behavior, structured
  decisions, references, agent verification, and strict human-check
  boundaries.
- **Branding** refreshed end to end — logos, app icon, and web surfaces all
  updated to the v0.2 Loop identity.
- **Update experience** moved into the sidebar with improved changelog
  display.
- **Per-project state** restored on switch (input persistence, terminal
  state, scroll position).
- **Tab navigation** reworked: mode-aware "+" button, actions dropdown,
  reopen recently closed.

### Removed
- Menu bar tray icon and tray-based status surface.
- Intel macOS builds. Loop ships **arm64-only**.

### Fixed
- PTY SIGABRT crash on app quit and on update.
- CLI not-found errors for installed users (added fallback paths and dynamic
  install suggestions).
- Image attachments persisting on tab switch; non-image file display.
- AskUserQuestion "Other" input clearing on Enter (now guards against IME
  composition).
- Plan task auto-checkoff reliability.
- Native browser/image-preview overlay suspension while blocking overlays
  are open.
- Terminal OSC and replay leakage across projects.
- Scroll jump when the agent completes a response.
- Git commits no longer time out on large diffs (output streams instead).
- Accessibility issues surfaced by the React Doctor pass.

## [0.1.1] - 2026-03-27

### Fixed
- Terminal duplication, scroll jumps, and auto-scroll rewrite
- Terminal light mode support and input field contrast
- Stale Claude sessions when switching projects
- Unstaging files, planner file detection, clickable file paths in messages
- Plan sort order (newest first)

### Changed
- Migrated from npm to bun
- Modularized IPC handlers with URL validation
- Decomposed large UI components into focused modules
- Message queuing during streaming for multi-project support

### Added
- Changelog modal and distribution pipeline
- UI polish and cleanup

## [0.1.0] - 2026-03-27

Initial release.

### Features
- 4-phase workflow: Plan, Research, Build, Review
- Loop-based execution with configurable iteration counts
- Real-time streaming output with tabbed interface
- Multi-project management with drag-and-drop
- Session history with git diffs and commit summaries
- Chat input for sending messages to Claude during sessions
- Image attachment support (drag-drop, paste, file picker)
- Commit generation with AI-powered messages
- Pull request creation and preview
- Menu bar integration with status indicator
- Terminal integration with multi-session support
- Auto-update support
- Light and dark theme
- Code signed and notarized by Apple

[0.2.0]: https://github.com/olekristianbe/loop/releases/tag/v0.2.0
[0.1.1]: https://github.com/olekristianbe/loop/releases/tag/v0.1.1
[0.1.0]: https://github.com/olekristianbe/loop/releases/tag/v0.1.0
