# Changelog

All notable changes to Loop will be documented in this file.

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

[0.1.1]: https://github.com/olekristianbe/loop/releases/tag/v0.1.1
[0.1.0]: https://github.com/olekristianbe/loop/releases/tag/v0.1.0
