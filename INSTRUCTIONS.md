# INSTRUCTIONS.md — fork owner preferences

This is a personal fork of the public herdr-web-ui project. This file records the
fork owner's preferences, corrections and standing instructions. It is not part of
the upstream project: never drop, revert or "clean up" this file when merging or
restacking on upstream changes.

## Agent rules

- Read this file at the start of every session, before doing any work.
- Whenever you learn a new preference, correction or standing instruction from the
  owner, add it here in the same session. If an existing entry already covers the
  topic, update that entry instead of adding a duplicate.
- Keep entries short, factual and dated (YYYY-MM-DD). Add new entries at the bottom
  of the matching section, or a new section at the bottom of the file.
- Never delete an entry unless the owner asks. Mark a replaced entry as
  `(superseded YYYY-MM-DD: reason)` instead.
- Record durable preferences only — not session-specific task details.

## Preferences

<!-- Agents: append dated entries below. Newest last. -->

- 2026-10-13 — Commit frequently as work progresses, so each meaningful step lands as a commit. NEVER push — not to any branch, remote or fork — unless the owner explicitly asks for a push in that instance.
- 2026-10-29 — The app must NOT be run by hand with `bun run start` in a terminal. It runs as the macOS LaunchAgent `dev.keremini.herdr-web-ui` (`~/Library/LaunchAgents/dev.keremini.herdr-web-ui.plist`): RunAtLoad + KeepAlive, `bun run start` in this checkout at login/after reboot, starts headless `herdr server` first when `~/.config/herdr/herdr.sock` is missing. Logs: `~/Library/Logs/herdr-web-ui/`. After a codebase change, release with `launchctl kickstart -k gui/$(id -u)/dev.keremini.herdr-web-ui` (do not start a manual instance next to it). Modelled on the owner's `dev.local-studio.web` plist.
