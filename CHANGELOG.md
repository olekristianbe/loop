# Changelog

All notable changes to Loop will be documented in this file.

## v1.4.1 - 2026-07-15 — Performance and execution reliability

Loop 1.4.1 improves responsiveness in terminals, streamed code responses, and
large files while strengthening the contract between the web app and native
daemon.

- Added WebGL terminal rendering with automatic DOM fallback.
- Throttled syntax highlighting during streamed code responses while
  preserving an exact final highlight.
- Added a read-only preview for text files over 2 MiB or 100,000 lines.
- Made the daemon authoritative for temporary worktree names, project-terminal
  execution context, model metadata, effort capabilities, and ultrathink
  prompting.
- Reconciled optimistic settings changes to the complete state persisted by the
  daemon.
- Added GitHub Enterprise and self-hosted GitLab remote recognition.
- Added typed native command decoding, development ingress validation, and an
  automated TypeScript/Rust drift gate covering 14 schemas and 23 RPC methods.

Full notes: [docs/releases/v1.4.1.md](docs/releases/v1.4.1.md).

## v1.4.0 - 2026-07-14 — Provider-native Plan, Build, and Review

Loop 1.4.0 makes the provider the execution engine for every formal mode. Loop
keeps the mode UX, project context, artifact contracts, deterministic
validation, repair boundary, and live activity surface; Claude Code, Codex, or
Cursor handles the work and any internal agent orchestration. This release also
includes the v1.3.1-era work that was never published as a stable release.

- Rebuilt Plan as a provider-native conversation and Build/Deep Review as one
  visible provider-native coordinator turn each, then removed the custom
  Workflow Engine, hidden stage/task children, and Loop-owned build scheduler.
- Made `.loop` Markdown the source of truth for new work: validated plans,
  build reports, review reports, durable run state, and report-derived
  summaries. `.planner` remains read-only legacy input and migrates
  non-destructively.
- Added deterministic plan and build-report validation with exactly one repair
  request after an invalid write.
- Added normalized native-agent and tool activity for Claude, Codex, and Cursor
  with grouped agent progress in the timeline.
- Made every Build option functional: branch preparation, scoped work items,
  source-only auto-commit safety, push-after-commit, prevent sleep, advisory
  network access, and interrupt-backed Stop with a cancelled summary.
- Expanded daily workflows with context notes, unified verification and human
  checks, responsive preview presets, desktop notifications, per-mode model
  overrides, and project-path changes that preserve history.
- Added Claude image attachments and built-in selections for Claude Fable 5,
  Cursor Grok 4.5, and the Codex GPT-5.6 variants.
- Removed Loop's managed Skills settings and automatic host-folder projection.
  Formal Plan, Build, and Review behavior now comes from each mode's
  provider-native protocol.
- Fixed build draft promotion, stale cross-thread completion panels, build
  stop/restart races, terminal remounts and focus loss during streaming,
  provider activity noise, UI render loops, project-terminal bootstrap
  retention, and empty run cards.
- Fixed the Servers tab so project-scoped HTTP listeners open in Loop's browser
  and stop actions revalidate project ownership before signaling.
- Fixed untracked-only commit drafts, kept Loop-owned `.loop` artifacts out of
  Git actions, and made exact-file commits preserve unrelated staged work
  through an atomic transaction.
- Preserved unique Build/Review run history per thread with restart recovery,
  enforced read-only Review at every provider boundary, validated reports
  before successful completion, and rejected unsafe `.loop` artifact paths.
- Removed React Compiler bailouts affecting UI stability, strengthened native
  code quality gates, resolved the dependency audit, and extended stable macOS
  updater metadata with final-DMG notarization and verification.

Full notes: [docs/releases/v1.4.0.md](docs/releases/v1.4.0.md).

## v1.3.0 - 2026-06-18

Loop 1.3.0 moves the desktop app to Tauri with a bundled native backend and
also includes broad workflow updates across chat and composer, preview,
terminal, Git, project navigation, settings, provider handling, and release
packaging.

- Added the Tauri desktop shell and bundled native backend.
- Moved auth, Git, terminal, orchestration, local server discovery, provider
  routing, editor reads, and workspace access into the native runtime.
- Improved chat and composer flows with image drops, preserved pending input,
  cleaner provider/model state, and split Markdown rendering.
- Reworked project sidebar, live project context, branch/status display, and
  local server management.
- Added desktop preview sessions, native preview screenshots, better preview
  URL resolution, and scoped server discovery.
- Expanded Git workflows with branch merge dialogs, Merge PR actions, and
  generated commit/PR text using the configured model.
- Stabilized terminal, editor, packaged UI styling, theme tokens, Cursor
  provider support, provider auth fallback, and desktop update handling.
- Hardened the stable macOS release path for compatibility with both older
  Electron installations and current Tauri installations.

Full notes: [docs/releases/v1.3.0.md](docs/releases/v1.3.0.md).

## [0.2.1] - 2026-05-07

Stability and workflow release for the v0.2 line. Loop remains macOS
arm64-only and continues to publish updates through the stable `latest`
channel.

### Added
- **Persistent planner workspace state** across navigation, including selected
  plan, selected task, comments, review notes, and build-start repair drafts.
- **Skills settings foundation** for Codex and Claude skill presentation,
  duplicate detection, and repair metadata.
- **Clearer update entry points** from Settings, the sidebar update pill, and
  the app menu.

### Changed
- **Right sidebar workspace** is more practical for Plan, Files, Browser, Git,
  and build context handoff.
- **Browser preview annotation flow** now uses a single-mode interaction model
  with visible send notes and steadier preview overlay behavior.
- **Git handoff controls** are clearer and refresh project state more
  predictably.
- **macOS icon release path** is documented around the bundle-driven `.icon`
  asset, with `.icns` kept as a local tooling fallback.

### Fixed
- Browser preview detach/reattach behavior during chat and overlays.
- Build review notes and human-check state being lost in planner workflows.
- Build-start repair drafts not guiding the agent with enough context.
- Local environment target injection for desktop startup.
- Provider skill registry handling when registry data is unavailable.

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

[0.2.1]: https://github.com/olekristianbe/loop/releases/tag/v0.2.1
[0.2.0]: https://github.com/olekristianbe/loop/releases/tag/v0.2.0
[0.1.1]: https://github.com/olekristianbe/loop/releases/tag/v0.1.1
[0.1.0]: https://github.com/olekristianbe/loop/releases/tag/v0.1.0
