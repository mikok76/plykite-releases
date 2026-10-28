# Plykite for Windows — User Guide

Version 0.9.37-win.20 (28 October 2026). Russian version: [user-manual-windows.ru.md](user-manual.ru.md).

---

## 1. What Plykite is

Plykite joins all of your computer's internet connections — a cable, Wi-Fi, a phone sharing its
internet over USB or Wi-Fi, a USB modem, up to eight at once — into one. It works for every Windows
program, with nothing to set up in the programs and no server on the internet.

- **Every program, every connection.** Each new connection goes out over the link that suits it best
  right now. Browsers, updates, games, cloud drives and torrents all gain.
- **Big files faster.** Plykite's own downloader fetches one big file in pieces over every link at
  once, so the speeds add up.
- **No drop-outs.** When a link is lost, its connections move to the working links within seconds.
- **Your choice wins.** Drag a program or a site onto a link and it stays there — forever, for an
  hour or for two minutes.
- **Honest figures.** Every link is measured on its own; Plykite shows what each link carries now and
  what it can do.

One connection always uses one link: the packets of a connection are never split. So a program that
downloads over one connection gets no more than one link's speed. Plykite's downloader does: it opens
connections on every link.

## 2. Requirements

- 64-bit Windows 10 22H2 or Windows 11.
- An Intel or AMD processor (setup `…-x64.exe` in [Releases](https://github.com/mikok76/plykite-releases/releases)). The build for ARM (such as Snapdragon) is not published yet.
  Settings → System → About → System type tells which.
- Administrator rights to install (once; Windows asks in its UAC prompt).
- At least two internet links for the speeds to add up. With one link Plykite still works: it measures
  it and keeps statistics.

## 3. What Plykite is made of

| Part | What it does | Rights |
|---|---|---|
| **Tray icon** and **Plykite window** | Menu, window, notifications, updates. | Your user |
| **Controller** | Finds and checks the links, measures them, decides the shares, runs downloads. Starts when you sign in to Windows. | Your user |
| **Engine service** (PlykiteEngine) | Captures the traffic through the virtual adapter "Plykite" and sends each connection over the chosen link. Its guard turns the engine off if it ever gets in the internet's way. | System |

If the engine stops for any reason, the internet keeps working the ordinary way, just without
distribution.

## 4. Installing

1. Download the setup program `Plykite-Setup-<version>-x64.exe` from the latest release (Releases) and run it.
2. The program is not signed yet, so Windows may say "Windows protected your PC". Click **More info →
   Run anyway**.
3. Allow the changes in the UAC prompt and follow the setup's steps.

The setup checks the files, installs the engine service, the controller and the tray icon for the user
signed in to Windows, and checks the internet through Plykite. If that check fails, Plykite gives you
plain internet back by itself in 15 minutes (the "dead-man switch").

If Defender wrongly removes or blocks `plykite.exe` (for example "Bearfoos.A!ml"), install from the zip
package with `install.cmd -DefenderExclusion`: it adds Plykite's folders to Defender's exclusions.

After the install the Plykite icon appears next to the clock (if you do not see it, it may be hidden
under the "^" arrow — drag it onto the taskbar).

## 5. First start

1. Connect your links: a cable, Wi-Fi, a phone by USB cable with its hotspot or USB tethering on, a USB
   modem.
2. Plykite finds each link within seconds and gives it a name, a colour and a kind (cable, Wi-Fi, phone
   over USB, modem). It also recognises the provider.
3. Plykite may ask about a link in the menu and in the window, for example whether a new network is
   metered, or whether two links share one provider. The answers decide whether big downloads may use
   the link.
4. Every link is measured by a short test. Until then its line says "not measured yet".

A disconnected link disappears from the window. When you connect it again, it comes back with its
settings.

## 6. The tray icon and its menu

The icon is the Plykite logo with a coloured dot:

| Dot | Meaning |
|---|---|
| Green | Distribution works. |
| Grey | The internet goes directly (capture paused or the engine off). You have internet, just without distribution. |
| Amber | A warning, for example only one link works. |
| Red | A problem: no link answers, Windows ran out of network ports, or the engine does not answer. |

Point at the icon for a tip that says what is happening. A **click** opens the menu, a **double click**
the Plykite window.

The menu, top to bottom:

- **⬆ Update Plykite to …** — when a new version is out (section 18). As this version's term nears its
  end, the line "This version works until …" is here too.
- **The summary**: what is happening and what to do, with a button when an action helps (for example
  **Switch on now** after a guard pause).
- **Questions about new links**, with their answers.
- **Links** — one line per link: the speed now, what it can do, the delay and the state; **Measure
  speed now**.
- **Downloads**: the running downloads and the downloads list.
- **Active window: <program>** — choose a link for the program that was in front, and for how long:
  forever, 1 hour or 2 minutes (for a speed test).
- **Site in the active tab…** — when a browser is in front (Chrome, Edge, Firefox and others): choose a
  link for the open site.
- **Capture: on — pause it** / **Capture is paused — turn it on**.
- **Default mode** and **Torrents** (sections 9 and 13).
- **Open Plykite…** (the main item), **Settings…**, **Open the dashboard in the browser…**,
  **Statistics…**; the dashboard's addresses for other devices while access is on (a click copies one).
- **Help**: **Check for updates**, **User guide**, **Collect logs for a bug report…**, **About
  Plykite…**.
- **Turn Plykite off (plain internet)** / **Turn Plykite on** — stops or starts the engine service. Off,
  Plykite does not split the internet until you turn it on or restart Windows.
- **Show the tray icon when I sign in to Windows**, **Refresh the figures**, **Quit** (closes only the
  icon; distribution keeps working).

If the controller does not answer, the menu says so and offers **Start the controller**.

## 7. The Plykite window

The rail on the left switches pages: **Overview**, **Links**, **Downloads**, **Apps**, **Sites**,
**Assignments**, **Statistics**; at the bottom **Settings** and **Help**. The window follows Windows'
light or dark theme; pick one in Settings → General → Appearance. The window remembers its size and
place on each monitor.

If the window loses the controller, a notice at the top says "No connection since …": what you see may
be out of date, and every control is off meanwhile.

### 7.1 Overview

The total speed of all links now, a 60-second chart per link, and what all links can do together.
Below is the "thread" drawing: each link is a strand that goes into Plykite and out to the internet as
one thread; the faster the link, the thicker its strand. Point at a strand to highlight it; a click
opens the link on the Links page.

### 7.2 Links

Every connected link: its kind, provider, state (**working**, **primary**, **metered**, **no internet
for 3 min**), its switch and share of the thread. **Measure all** tests every link. A link you switched
off stays in the list as "switched off by you" — turn its switch on to use it again.

A link's card lets you rename it, mark it metered, stop using it, forbid it to be primary, set a data
plan, choose its operator or forget it.

### 7.3 Downloads

Big files over all links at once (section 10). A finished download has **Show in Explorer**.

### 7.4 Apps and Sites

Every program (or site) that uses the network now is a card. The bar at the bottom of a card shows which
links it uses and in what proportion. **Drag a card onto a link** to keep it there; onto **Share between
all** to spread it over every link; onto **Auto** to give it back to the default mode. **New rule…**
assigns a program (an .exe file) or a site that is not open now. **Why this link?** in a card's menu
explains why a program goes the way it does.

When you assign, Plykite asks for how long (forever or for a while) and what to do with connections
already open: **Move at once** (recommended: they reconnect over the new link), **Softly: new
connections only**, or **Forcibly: fragile programs too**.

### 7.5 Assignments

Everything you assigned by hand, running or not: where it goes (in the link's colour) and how long is
left. You can remove an assignment here. Below are the programs that learning marked as "big
downloads", if learning is on.

### 7.6 Statistics

Traffic by hour or by day for today, 7 or 30 days, per link; the programs and sites that used each link
most. Statistics come from the connection history, which stays on this computer only.

### 7.7 Settings

The index is on the left (links at the top in a narrow window). Changes apply at once; what waits for a
controller restart is noted next to it.

| Section | What it sets |
|---|---|
| Main | Scenario, default mode, primary link, fallback order "if the primary link is gone", traffic capture. |
| Saved settings | Your settings under a name, the automatic copies, restore, import and export (section 7.8). |
| Links | Per link: metered, use, may be primary; data plans of metered links. |
| Speed tests | How often each link is measured and how much a metered link may spend a day. |
| Calls and remote access | Where video calls, remote desktop and interactive streams go. |
| Banks and account logins / Government services | Where these sites go and whether they wait for their own link in a failure. |
| DNS | Where name lookups go. |
| Downloads | Default folder, where downloads are split, limits per link. |
| Torrents | How torrents share the links. |
| Rules | Length of new assignments, moving open connections, assignment defaults. |
| Learning | Automatic rules from the statistics. |
| Failures and protection | How fast a failure is noticed, going back after recovery, the penalty for a "flapping" link. |
| Access from other devices | The dashboard on your local network, who may use it, the PIN for control. |
| History and data | Whether to keep the connection history, how much and how long; clear it. |
| Virtual machines | How VM traffic is told apart; the helper inside a VM. |
| Notifications | Which events to tell about (section 17). |
| General | Appearance, language. |
| Advanced | Versions, folders, logs, **Restart the controller**. |

Speed tests, Failures and protection, and Advanced appear when **Show advanced settings** is on
(General). At the bottom of the page is a link to the dashboard in the browser.

### 7.8 Saved settings

Settings → **Saved settings** keeps whole sets of your settings: the mode and scenario, link names and
choices, data plans, assignments, downloads and the rest of the window's settings.

- **Save…** stores the present settings under a name, for example "Home: cable and two phones".
- Plykite also keeps a copy by itself for each day the settings changed, on the first start of a new
  version and before every restore. The 10 newest automatic copies are kept; yours always.
- **Restore** brings a copy back. Plykite saves the present settings first, then restarts the controller
  in a few seconds; the internet keeps working.
- **Rename…**, **Export…** (one file you can take to another computer, a Mac included; it holds no
  passwords, keys, adapters or devices of this computer) and **Delete**. A deleted copy stays in the
  trash for 30 days and can be brought back.
- **Import from a file…** loads an exported file; its links are matched to this computer's links by
  kind.

Measurements, statistics and the connection history are not part of a copy.

### 7.9 Help

The version and build date, the **beta term** (the last day this version works), the update state with
**Check for updates**, the author, the beta licence and third-party licences, **User guide**, **Open the
logs folder**.

## 8. Assigning programs and sites

Four ways:

1. Drag a card on the **Apps** or **Sites** page.
2. Tray menu → **Active window: <program>** or **Site in the active tab…**.
3. **New rule…** on the Apps and Sites pages (for a program that is not running: choose its .exe file).
4. Command line: `plykite override add --app "Speedtest" --mode only-mobile --ttl 2m`.

On Windows a program is assigned by its file name (for example `chrome.exe`), so a rule works also
while the program is not running.

The choices for a link: through it first while it works (the others as standby); only through it (a
connection waits while the link is gone); share across all links; "Auto" (the default mode). The
"2 minutes" length is handy for a speed test of one link.

## 9. Default mode and scenarios

The default mode decides what happens to everything you did not assign.

| Mode | How it works |
|---|---|
| **Everything ordinary over the primary link; only downloads and torrents are shared** (recommended) | Sites, video, calls, remote desktop and VPN go over the primary link for a quick response. Known downloaders, big parallel downloads and torrents are shared over all links. |
| **Share everything across all links** | Each new connection goes to the link that is freer now. Calls, remote desktop, VPN and DNS still stay on the primary link. |
| **Everything over <link>, the others as standby** | One link first; the others only when it fails. |
| **Only <link>** | Everything over one link; while it is down, over the best working one, then back. |

The **primary link** is chosen automatically (the best working one) or pinned by you (Settings → Main).
**Scenarios** set several settings at once.

## 10. Downloading big files over all links

Start a download on the **Downloads** page or on the command line:

```
plykite get https://example.com/big.iso -o %USERPROFILE%\Downloads
plykite get hf://org/model -include "*.safetensors"
```

- The file is cut into 8 MB pieces; the pieces come over every allowed link at once.
- If a link is lost, the others fetch its pieces.
- A download goes on after a network drop, a restart or sleep.
- The file is checked: by the sha256 from Hugging Face or the sum you gave (`-sha256`); without a sum,
  pieces from different links are compared.
- Whole Hugging Face repositories download with `hf://org/model`.
- A download gives way to your calls and remote desktop on the same link.
- Before a big download over a metered link Plykite says how much will go over it.

## 11. Speed tests

Each link is measured by a short test (a few seconds of download and upload with speed.cloudflare.com)
until the speed stops growing. Plykite repeats the tests by itself: more often on an unmetered cable,
rarely on metered links, within a daily budget. **Measure speed now** in the menu or **Measure all** on
the Links page start a test at once.

## 12. Metered links and data plans

Mark a phone's or modem's link as **metered**. Then set its plan (Settings → Links → "Plan…"): gigabytes
a month, the reset day, a daily limit and what to do when the plan is used up: no downloads and
torrents, standby only, or just a warning. Notifications come at 75 % and at 100 %.

## 13. Torrents

Torrent programs are recognised by themselves. **How torrents share the links**:

- **Only what is left: your traffic first** (recommended) — on each link a torrent takes only what is
  free;
- **Over all links by speed, on a par with the rest**;
- **Not on the primary link**.

Each torrent peer stays on one link. For the best result turn µTP off in the torrent program.

## 14. Calls, remote access, banks and government sites

Video calls (Zoom, Teams and others), remote desktop and terminals stay on the primary link by default,
so a switch never drops a call. Banks, account logins (Google, Microsoft, Apple ID) and government sites
of every country keep to one link: such sites sign you out when your address changes. In the settings
each group can go to any link.

## 15. VPN

Plykite recognises connected VPN programs (Tailscale included). A split-tunnel VPN works together with
Plykite. A full-tunnel VPN that takes all traffic makes Plykite step aside while it is connected; the
menu and the window say so.

Two features of the Mac version are not on Windows yet: a VPN as an exit for programs, and "DNS follows
the program".

## 16. Virtual machines and access from other devices

Plykite finds virtual machines (VMware, VirtualBox, Hyper-V, WSL). With a small helper installed inside
a VM (Settings → Virtual machines → VM helper), the VM's own programs appear as separate cards. The
Plykite setup adds one Windows Firewall rule for that, on the VM adapters only.

Settings → Access from other devices shows the Plykite dashboard in the browser of another computer or
phone on your network. Without a PIN guests can only look; with the PIN they can change modes and rules
for 12 hours. On this computer the dashboard opens at `http://127.0.0.1:1081/` or from the menu.

## 17. Notifications

Plykite shows notifications of its tray icon: a link lost or back, a data plan at 75 % or used up,
distribution switched off by itself, the guard stopped the engine. Choose them in Settings →
Notifications. A click on a notification opens the window.

Windows may hide notifications (Do Not Disturb; Settings → System → Notifications). So the most
important ones — a new version and the end of the beta term — Plykite also shows as the first item of
the menu and as a banner in the window.

## 18. Updates and the beta term

This is a beta. Each build works for **70 days** from its build date; the last day is shown in Help.
When the term ends, Plykite stops splitting the internet (the internet stays as usual) until you install
a new version.

Once a day Plykite checks by itself whether a new version is out (it downloads a small signed
description file from github.com). When one is out:

- **⬆ Update Plykite to …** appears first in the menu, and an **Update Plykite** banner in the window;
- 14 and 3 days before the term ends, Plykite reminds you;
- Help → **Check for updates** checks at once.

Click **Update Plykite**: the setup program downloads over the fastest working link, its size and
checksum are verified, then Windows asks for permission once. The setup updates Plykite; your settings
stay, and the internet may drop for a few seconds. Plykite never installs anything by itself — only when
you click.

## 19. Privacy

- Plykite works only on your computer, with no account and no server. Nothing is sent to the developer.
- The connection history stays on this computer only; turn it off, limit it or clear it in Settings →
  History and data.
- External services: speed.cloudflare.com (speed tests), 1.0.0.1 (checking that a link works), Team
  Cymru (the operator from the external address), github.com (once a day, the update check).
- The logs contain site, program and adapter names, Wi-Fi network names and external addresses. Look
  through them before you send them.

## 20. If something is wrong

**Look at the top of the tray menu first** — it says what is happening.

| Message | What to do |
|---|---|
| "The internet goes directly…" | The guard paused the engine, or it is paused. The internet works without distribution; Plykite turns the engine on again by itself after 2, 5 or 15 minutes, or click **Switch on now**. |
| "The Plykite controller is not responding" | Click **Start the controller** in the menu, or in the window Settings → Advanced → **Restart the controller**. |
| "View only" in the window | A controller restart usually fixes it; the internet keeps working meanwhile. |
| "Windows is running out of network ports…" | Quit the named program; ports free up in 30–60 seconds. |
| A link says "no internet" | Check the phone: its hotspot on, mobile data on, a signal. |
| You need plain internet right now | Menu → **Turn Plykite off (plain internet)**. The same item turns it back on. |

**Collect logs for a bug report…** (under Help in the menu) saves a zip with the controller, tray,
setup and service logs and the output of `plykite diag`. It works even when the controller does not
answer. The logs are in `%LOCALAPPDATA%\Plykite\logs` and `C:\ProgramData\Plykite\logs`.

## 21. Command line

Run the commands in PowerShell or the Command Prompt.

| Command | What for |
|---|---|
| `plykite status`, `plykite links` | The links, shares, programs and assignments. |
| `plykite link rename\|metered\|use\|never\|forget ID …` | Change one link. |
| `plykite primary [auto\|ID]`, `plykite mode …`, `plykite p2p-mode …` | Primary link, default mode, torrent mode. |
| `plykite override add\|list\|rm\|clear` | Manual assignments. |
| `plykite measure`, `plykite get …`, `plykite downloads` | Speed test, download, downloads. |
| `plykite config list\|save\|restore\|export\|import` | Saved settings. |
| `plykite diag`, `plykite verify-routing` | Diagnostics and a live check of the links. |
| `plykite pause`, `plykite resume` | Pause capture. |
| `plykite agent start\|stop\|restart\|status\|log` | The controller. |
| `plykite service start\|stop\|status` | The engine service (`stop` gives plain internet). |
| `plykite version`, `plykite help` | — |

## 22. Removing Plykite

Settings → Apps → Installed apps → Plykite → Uninstall (or `uninstall.cmd` from the zip package). The
internet is plain at once. Settings and logs stay; `uninstall.cmd -Purge` removes them too.

## 23. Known limitations

- One connection always uses one link; only downloads with many connections (Plykite's downloader,
  download managers, torrents) add speeds up.
- IPv4 only; IPv6 traffic is not distributed.
- Local networks and multicast bypass Plykite by design.
- No VPN exits for programs and no "DNS follows the program" (both are in the Mac version).
- The program is not signed: Windows SmartScreen and Defender may warn.
- A beta build works for 70 days from its build date (section 18).

## 24. Licences

Plykite uses the mihomo engine (GPL-3.0; its source and patch come with the program), Wintun, the Go and
.NET runtimes and open data. The licence texts are in Help → Third-party licences and in
`C:\Program Files\Plykite Setup\licenses`.
