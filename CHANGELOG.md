# Changelog

## 0.1.2 — 2026-10-20

### Fixed
- Settings choices no longer cover their text; the top bar is frosted glass

## 0.1.1 — 2026-10-20

### Highlights
- ProxyPort asks once whether to open at login
- Servers started by Cursor, Kiro, Antigravity, Copilot CLI, Amp, Goose, Qwen Code, Cline, Kimi Code, Droid, Auggie or Kilo Code link to that agent; agents that aren't on this Mac start off in Settings → Integrations
- Welcome lists every coding agent found and leads with monitoring ports
- Settings has a system sidebar with colored pane icons

## 0.1.0 — 2026-10-20

- The first release: every server listening on your Mac, in the menu bar, with its port, project, git branch and framework.
- Memory, CPU, network traffic and open connections for each server, set against the whole Mac.
- Alerts when a server passes your memory limit or keeps climbing, with Restart, Stop and Snooze in the notification.
- Each server is linked to the Claude Code, Codex, Pi or OpenCode session that started it.
- Stop ends the whole dev server and nothing respawns it; your agent and shell are never touched. Restart reruns the original command.
- Clean Up finds servers you forgot: deleted worktrees, idle servers, orphans and long runners. Databases are never suggested.
- Containers from OrbStack, Docker Desktop, Colima and Podman show up as servers, with Stop, Restart and Show Log.
- `proxyport` in your terminal: a keyboard-driven list, `proxyport list --json` for agents, and `proxyport stop` for scripts.
- Updates download and install when you say so.
- A license is $5 a year for one Mac. ProxyPort keeps working offline for 30 days. macOS 14 or later.
