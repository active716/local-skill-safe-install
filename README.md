# Local Skill Safe Install

A Codex-compatible skill for safely inspecting, freezing, installing, updating, and uninstalling local Skill or Agent instruction files.

## Files

- `SKILL.md` - the installable skill.

## Safety Notes

This repository is intended to keep a fixed local copy of the skill text. Do not add local backups, tokens, API keys, OAuth credentials, or personal workspace paths.

The skill itself emphasizes:

- inspect before installing
- avoid automatic remote updates
- require explicit approval before network, command, or global-setting changes
- keep backups before modifying user-level Agent configuration
- verify installed content with hashes
