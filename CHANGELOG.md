# Changelog

## 0.1.10 — 2026-11-27

### Highlights
- The popover lists Other listeners: every port something listens on that isn't shown as a server, with the reason, including ports outside the scanned range

### Improved
- Servers on ports from 1024 up, such as Hugo's 1313 and Parcel's 1234, show by default; `proxyport next` still suggests ports from 3000
- Each scan takes less work: ProxyPort no longer reads the CPU temperature while the Temperature card is off, works out which app owns a process once instead of every scan, and redraws the menu bar icon once per scan
- After a `gh` pull request lookup times out, ProxyPort waits before trying it again
- Details stays responsive while you hover its charts, and warning amber, the memory chart's alert label and About's copyright line are easier to read

### Fixed
- A license ProxyPort couldn't read from a locked keychain is read again once the keychain opens, instead of asking you to activate
- When the license can't be saved to the keychain, activating again reuses that activation instead of using up another
- A license check that fails is tried again within the hour instead of a day later
- Always show in the terminal UI no longer undoes one made in the app, and the app picks up allowlist and port range changes made from the terminal
- A tool that connects to Keep Awake and sends nothing no longer holds up other tools' requests
- Dev servers run by Xcode's Python, such as `python3 -m http.server`, show in the list instead of being hidden as an app's own backend
- `proxyport next` and the `free_port` MCP tool no longer offer a port another user's process holds on a network address, such as Tailscale's
- A port range saved out of order, such as by `defaults write`, no longer crashes ProxyPort at launch
- Keep Awake works on a desktop Mac plugged into a UPS instead of stopping with "power unknown"
- Stop and Restart say why they did nothing while the port list can't be read, instead of doing nothing silently
- Automatic Clean Up still suggests the containers it never stops on its own
- Servers started from nushell, tcsh, ksh, PowerShell, Elvish or xonsh show up, marked Unlisted
- A debugger port set through `NODE_OPTIONS` or `JAVA_TOOL_OPTIONS` is no longer taken for the server's own port
- A server started by a build daemon, such as a Gradle task, shows as its own server instead of inside the daemon, and a server started by a process ProxyPort doesn't list is no longer hidden with it
- Your own builds left running in the background (`nohup ./server &`) or started from an IDE's debugger show up from their project folder, marked Unlisted
- A container on the host network (`--net host`) shows on the ports it serves instead of only as a background container
- Gradle's build daemon and the Kotlin compile daemon no longer show as servers; they're listed under Other listeners
- Details shows why a Stop or Restart failed, as the list does, and scrolls a long process list instead of pushing its buttons off the screen
- The menu bar icon's tooltip says what's running and whether Keep Awake is on
- Search no longer says "No matches" above background containers, headless browsers or other listeners that match
- A memory bar highlight no longer sticks after the container or app it pointed at goes away, and a new server starting no longer takes keyboard focus off the list
- The CPU chart in Details keeps its bars apart at short scan intervals
- Settings → Ports says what still shows up when no process names are listed
- `proxyport` no longer passes a project's terminal escape codes from a folder, branch or process name through to your terminal
- `proxyport <port>`, `proxyport logs` and the MCP `get_server` and `server_logs` tools name the servers sharing a port instead of picking one
- The MCP server answers a request sent as the last line without a newline, and no longer exits before its replies are written
- MCP `server_logs` includes what a container wrote to stderr
- MCP tools refuse a bad `from`, `count` or `lines` instead of quietly using another value, `awake_acquire` and `awake_renew` accept `seconds: 1`, and a malformed request gets the right JSON-RPC error
- `proxyport` exits with a write error instead of being killed when the reader of its output goes away
- `proxyport list --json --watch` no longer prints an empty list before the first scan
- `proxyport stop` reports a port named twice, or inside a range, once, and `--identity` no longer swallows the option after it
- `proxyport list --json --all` gives headless browsers' start time as a date and rounds their CPU like the rest
- `proxyport wait` says a fractional timeout as given ("after 0.5 s") instead of "after 0 s"

## 0.1.9 — 2026-11-27

### Improved
- The popover, Details, the terminal UI and `proxyport restart` offer the same server actions under the same names, say the same thing about a Restart outside its agent's session, and title a server by its port name when it has one
- Memory by app counts Codex, Pi and other coding agents that run through Node toward the agent, not toward "node"
- The menu bar popover opens fresh every time: on the list, with no search, Clean Up, armed Stop or highlight left from the last visit
- Search matches names without regard to case or accents, and VoiceOver can open a server from its memory bar segment and names Details' More actions menu

### Fixed
- Onboarding counts the tools it checks correctly: "1 of 3 found", not "of 4"
- `proxyport install hooks` leaves Claude Code's settings untouched when it can't save their backup first
- `proxyport next` and the `free_port` MCP tool no longer report ports as free when macOS returns an incomplete socket list
- Allowlist changes made with the `proxyport` command now reach the app
- Restart no longer reads a free port as busy while ProxyPort is starting a helper tool
- `proxyport <port>` shows the Allowlist and Traffic rows Details shows
- Settings → Alerts says why Allow… failed when macOS couldn't ask for notifications
- The menu bar icon's right-click menu no longer offers an empty Open in Browser, and its Settings… opens on License while ProxyPort is locked
- A server appearing no longer takes keyboard focus away from Settings
- A server row with no room for its branch hides it instead of showing a sliver
- Settings → Keep Awake says why a manual timer didn't start, and a failed Show log or Resume no longer greets the next popover
- Pressed buttons darken again; a press looked the same as a hover
- A refused license key stays in the field instead of being cleared
- VoiceOver names the alert threshold fields, the idle clean up picker and agent icons, says whether "more" is expanded, and stops reading decorative icons
- Force Quit After reads "1 second", not "1 seconds"

## 0.1.8 — 2026-11-26

### Highlights
- Keep Awake in Settings → General and the menu bar icon's menu, with manual timers, automatic holds while Claude Code, Codex, Pi or OpenCode is working, and timed holds for `proxyport awake` and MCP clients
- See local headless Chrome browsers, their launchers and resource use in the popover, terminal and `proxyport list --all`.

### Improved
- `proxyport awake status`, `acquire`, `renew` and `release`, plus the `awake_*` MCP tools, let scripts and agents hold a Mac awake without owning an assertion
- Open and Copy URL preserve the listener’s IP address. Use Set Browser URL to remember a page for one service without affecting another service on the same port.

### Fixed
- Keep coding sessions out of server Stop, Restart and Clean Up. Their own ports appear in `proxyport list --all`; dev servers they launch stay independently manageable.
- Stop and Restart are no longer refused as "already stopping or restarting" while ProxyPort is starting one of its helper tools

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
