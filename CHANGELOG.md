# Changelog

## 0.1.6 — 2026-10-22

### Improved
- License checks go through proxyport.pymodel.com, which signs Polar's answers so a fake license server can't unlock the app

## 0.1.5 — 2026-10-22

### Highlights
- Updates show in Settings → General with real download progress, release notes and Install and Relaunch
- The popover and the menu bar icon's menu show an update as soon as the daily check finds one

### Fixed
- The popover stays under the icon when the count goes, and Quit no longer takes focus from a stopped server's row
- The menu bar icon keeps its place when the server count appears or goes

### Improved
- Sparkle 2.9.5, with its symlink security fix

## 0.1.4 — 2026-10-22

### Highlights
- About links to ProxyPort on GitHub and to report an issue there
- Onboarding asks for notifications as its alerts step opens, so alerts are on by default
- Settings → Alerts shows where macOS lets alerts appear, as System Settings does

### Improved
- Notification Settings buttons open ProxyPort's own page in System Settings

## 0.1.3 — 2026-10-21

### Fixed
- The terminal's Keys page lists L for Show log
- One-line rows show which agent started each server
- CPU alerts count one full core as 100%, as the list does, not the whole Mac
- Stops that leave processes running, and windows that can't open, say so
- Open uses https and the server's own address, and is off for databases
- Restart logs stop growing past 10 MB
- The app and proxyport never stop or restart one server at the same time
- CPU alerts wait 5 minutes, so a long build doesn't set one off

### Highlights
- proxyport restart, stop --dry-run, clearer exit codes and richer JSON
- proxyport wait for a server to answer, and next for a free port
- proxyport logs prints or follows what a server writes
- proxyport list --json --watch prints a line each time the list changes
- Ports can be named, from a row's menu or proxyport name
- proxyport install hooks stops a Claude session's servers when it exits
- proxyport mcp gives coding agents ProxyPort's tools over MCP
- Containers show a failing health check and how often Docker restarted them
- Open uses portless's .localhost name for a server portless routes
- One project's servers sit together; the same app run twice says so
- proxyport completion for zsh, bash and fish; clearer, grouped help

### Improved
- Better with Increase Contrast and Differentiate Without Color on
- Scans slow down while the popover is closed and pause while the Mac sleeps

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
