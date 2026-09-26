# Changelog

All notable changes to FlowCharge are recorded here.

The format follows Keep a Changelog, with one deliberate deviation: a release heading is
written as `## X.Y.Z - YYYY-MM-DD`, with no brackets around the version. This matches the
FlowCharge Core repository. Nothing in this repository reads that heading today. Do not
add the brackets.

Versions follow Semantic Versioning.

## 0.3.0 - 2026-09-26

### Added

- Add Project can now create a project's `flowcharge/` folder automatically when one
  doesn't already exist, so a brand-new project can be added straight from the home
  page without first installing FlowCharge Core in a coding harness.
- Manage Integrations can now install FlowCharge Core into OpenAI Codex, alongside
  Claude Code, OpenCode, Cursor and Windsurf.
- The board's filter panel now has a searchable "More tags…" list holding every tag
  on the project, so a tag past the fast-path row's cap is still reachable. The
  fast-path row now also labels how many tags it is showing out of the full count.

### Fixed

- The board's sort control no longer overflows the screen at mobile widths, where it
  previously pushed the page wider than the viewport and left the sort-direction
  button unreachable.
- The sort and filter buttons now expose their active state to screen readers.
- The filter panel's tag list no longer stays empty on a small project: the rule
  that decided which tags qualify for a chip could never be satisfied below seven
  workstreams.
- A task or issue item's attached data block is now recognized whether it is fenced
  with the standard three backticks or with a longer or tilde fence, matching normal
  Markdown behavior instead of only the exact three-backtick form.
- The web app, CLI binary and Electron build now compute the location of FlowCharge's
  own data files (such as the skill-install registry) the same way. One of the three
  had drifted onto its own logic that ignored the shared data-directory setting, which
  would have broken inside a packaged Electron build. The Electron build itself is not
  part of this release; this keeps it correct for when it returns.

## 0.2.1 - 2026-09-15

### Fixed

- Installing or updating the FlowCharge Core skill suite no longer strips the YAML
  frontmatter from installed skill files. Installed files are now byte-for-byte
  identical to the published release, and the installed version is read from those
  files directly instead of from an internal record.
- An install that is missing skills, or whose files disagree with each other on
  version, is now detected and reported, with a one-click repair.
- A Manage Integrations row now reflects the result of an install or update
  immediately, instead of showing its state from before the click.
- Clicking Install or Update now shows a small in-progress spinner in place of the
  button, instead of no feedback at all.

### Changed

- Manage Integrations rows now show one clear status per harness (not detected, not
  installed, installed, needs repair, or up to date) instead of overlapping, and
  sometimes contradictory, labels.
- Each row's Install, Update and Remove controls are icon-only with consistent
  tooltips, and Install is now available per row instead of via a shared checkbox
  and a separate button.

## 0.2.0 - 2026-09-14

### Added

- A home-page project tile's folder path can now be edited in place, and the tile shows
  when the project was last modified.
- Editing a project tile now opens a dedicated, labeled form instead of editing the tile
  in place.
- Cursor and Windsurf now support installing the FlowCharge Core skill suite at global
  (user-level) scope, using each tool's own native Skills format, alongside the existing
  project-scope support.

### Fixed

- The home page's Delete button no longer silently does nothing. Deleting a project now
  always works, confirmed with an in-page control instead of a native dialog that could
  go unnoticed.
- Corrected several install-engine defects, including a presence-check gap for
  OpenCode's legacy skill-folder layout and a stale release-fetch host.

## 0.1.2 - 2026-09-13

### Fixed

- Corrected two internal test fixtures for the Manage Integrations installer that named
  the FlowCharge Core skill suite's old release-asset name and old skill-folder layout.
  No user-facing behavior changed.

## 0.1.1 - 2026-09-12

### Added

- A Remove button for each installed integration in Manage Integrations, with a
  confirmation before it deletes any files.
- A warning before Update overwrites an integration's skill files when FlowCharge did not
  perform that install itself.

### Fixed

- Manage Integrations no longer shows "Missing skills" for a tool that has the full skill
  suite installed.
- Manage Integrations now shows the real installed version instead of "Version unknown",
  and hides the version and update chips for a tool with nothing installed.
- OpenCode installs made before OpenCode's own folder-naming change are now correctly
  recognized as installed.
- Installing skills now includes every file a skill ships with, not just its main file.
- The release banner in Manage Integrations no longer shows the version number twice.

## 0.1.0 - 2026-09-07

### Added

- The public FlowCharge repository was scaffolded with its README, its changelog and its
  security policy.
