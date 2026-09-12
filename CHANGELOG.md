# Changelog

All notable changes to FlowCharge are recorded here.

The format follows Keep a Changelog, with one deliberate deviation: a release heading is
written as `## X.Y.Z - YYYY-MM-DD`, with no brackets around the version. This matches the
FlowCharge Core repository. Nothing in this repository reads that heading today. Do not
add the brackets.

Versions follow Semantic Versioning.

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
