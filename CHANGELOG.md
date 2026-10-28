# Changelog

All notable changes to FlowCharge are recorded here.

The format follows Keep a Changelog, with one deliberate deviation: a release heading is
written as `## X.Y.Z - YYYY-MM-DD`, with no brackets around the version. This matches the
FlowCharge Core repository. Nothing in this repository reads that heading today. Do not
add the brackets.

Versions follow Semantic Versioning.

## 0.5.0 - 2026-10-28

### Added

- The board has a Now running panel. It lists each FlowCharge Core run working in the
  project, with its task, its IDs, its place in the task list and a timer. Several runs
  list together, a stalled run shows in grey, and the collapsed bar moves through the
  runs. A Now running pill in the project row opens the panel as a pop-down, and its pin
  key fixes the panel above the find toolbar. A run opens its detail on the Tasks tab.
- A Health button in the project row opens the workstream, open issue and task
  completion figures. Its pin key fixes them as a band under the project row.
- The board shows the git branch on a row of its own, with a branch glyph.
- Add project has a Choose folder button on macOS that opens the system folder picker.
- Any column collapses to a narrow rail, and the choice is remembered. On a phone, a
  status strip switches between the columns.

### Changed

- The top of the board is rebuilt. A brand bar, a project row with the breadcrumb, live
  state and the Now running, Health, Core, update and More controls, a branch row and
  the find toolbar replace the old stack of bands. The first card now starts about 220 px
  from the top at 1280 by 800, where it started about 400 px down before.
- Core settings and the missing-install warning moved into a FlowCharge Core popover.
  Theme and version moved into the More menu. The update notice is a pill with a popover.
- The board fits the window. Columns share the width, each column scrolls, and the board
  keeps its scroll position and focus when its data refreshes.
- Sort is one menu at every width, and the result count shows only while filtering.
- Cards show one updated date and their first three tags.
- Every popover and sheet now has a clear edge. Backdrops darken the page in both
  themes. Every tappable control on a phone is at least 36 px square.
- The home page opens the Add project form from a button, and each project tile has one
  menu. "Delete" now reads "Remove from list", and long paths shorten.

### Fixed

- Pop-downs no longer run off the screen at tablet widths. The Now running pop-down opens
  centred under the project row.
- Walking a project folder no longer fails when a file disappears during the scan.
- The word and value pairs on the Core control, the column heads and the Now running
  pill now sit on one line.
- The task completion line reads "1 task list" for a single list.
- Search, filter, sort and view controls are labelled for assistive technology, and the
  theme toggle reports its pressed state.

### Internal

- Internal test, CI and documentation maintenance.

## 0.4.0 - 2026-10-15

### Added

- Manage Integrations is now split by scope. The home page opens a global dialog,
  and each project's board has its own briefcase button that installs FlowCharge Core
  for that project only. Both dialogs are titled "Manage FlowCharge Core" and carry a
  badge that names the scope, "Global" or "Project: <name>".
- A board shows a red warning when FlowCharge Core is installed neither in the
  project nor globally.
- The board has a "Core settings" row that shows the project's default agent, task
  list mode, prompts and validate settings, and marks each as set or default.
- FlowCharge now checks GitHub for a newer release. When one exists, a small warning
  icon appears in the breadcrumb row, and pressing it shows the new version. The
  banner has a button that turns update checks off.
- Project tiles on the home page can be dragged into a new order by their grip, and
  the order is saved in the project list.
- The board remembers its sort choice between sessions.

### Changed

- A path with no `flowcharge/` folder now opens a dialog that asks to create the
  folder, in place of a message under the Add Project field.
- FlowCharge now requires Node 22 or newer when it is built from source. The release
  binaries are unaffected.

### Fixed

- The Manage Integrations button is now disabled, with a tooltip that says why, when
  the board is opened over the network instead of on the machine running FlowCharge.
- On narrow phone screens the Manage Integrations button is now an icon, so all four
  toolbar buttons fit, and the toolbar no longer overflows.
- An open workstream detail modal now refreshes its plan, task list and issue list in
  place when the underlying files change.
- The board search box now also finds a workstream by the ID of its plan, task list,
  issue list or any of its issues.
- The board no longer shows extra space under its information strip.

### Internal

- Internal test, CI and documentation maintenance.

## 0.3.2 - 2026-10-15

### Changed

- Manage Integrations is now disabled, with a tooltip that says why, when the board is
  opened over the network instead of on the machine running FlowCharge. The server
  already refused every integrations action from another machine, so the button no longer
  leads to a dead end.
- On narrow phone screens the Manage Integrations button is now a briefcase icon, so all
  four toolbar buttons fit.

### Fixed

- An open workstream detail modal now refreshes its plan, task list and issue list in
  place when the underlying files change, with no need to close and reopen it.
- The board search box now also finds a workstream by the ID of its plan, task list,
  issue list or any of its issues.
- The toolbar no longer overflows on screens 360 pixels wide or narrower.

### Internal

- Internal test and CI maintenance.

## 0.3.1 - 2026-09-28

### Fixed

- The macOS binaries now carry a valid code signature. The 0.3.0 macOS builds failed
  macOS's own signature check. On a fresh Homebrew install, the first run could exit to
  the prompt with no message and no server, and only a second run started FlowCharge.

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
