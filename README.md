# MK64 Coop Deluxe

**Online multiplayer for Mario Kart 64: Recompiled: races of up to 8 karts and balloon battles of up to 16, on servers you run.**

[Download](../../releases/latest) · [Report a bug](../../issues/new/choose)

MK64 Coop Deluxe lets players on different PCs race and battle together in
[Mario Kart 64: Recompiled](https://github.com/sonicdcer/MarioKart64Recomp), the PC port of Mario Kart 64. A launcher for Windows, macOS and Linux picks or hosts a
server and starts the game; a mod draws a lobby inside the game and keeps every kart in step. Each PC brings one kart full screen, or two to
four in split screen, and CPU karts fill the empty seats.

**Contents:** [Download](#download) · [What works](#what-works) · [Getting started](#getting-started) · [Playing with friends](#playing-with-friends) ·
[Hosting a server](#hosting-a-server) · [FAQ](#faq) · [Reporting a bug](#reporting-a-bug) · [Notice](#notice)

## Download

Get the latest from **[Releases](../../releases/latest)** and pick the file for your system.

| System | File |
|---|---|
| Windows 10 or 11 (x64) | `Mk64CoopLauncher-<version>-win-x64.exe` |
| macOS (Apple silicon and Intel) | `mk64coop-<version>-osx-universal.dmg`, or `mk64coop-<version>-osx-universal.app.zip` |
| Linux (x64) | `mk64coop-<version>-linux-x64.AppImage`, `.deb` or `.rpm` |

The launcher is one file with the server and the game mod inside. **Windows:** run it from anywhere. **macOS:** drag *MK64 Coop Deluxe* to
Applications; the app is not notarized, so the first time open it with System Settings → Privacy & Security → *Open Anyway*. **Linux:**
`sudo apt install ./mk64coop-<version>-linux-x64.deb` or `sudo dnf install ./mk64coop-<version>-linux-x64.rpm`, or make the AppImage executable
(`chmod +x`) and run it. None of the files are code-signed, so Windows SmartScreen or macOS may ask you to confirm.

**You also need:**

1. **The game: [Mario Kart 64: Recompiled, from the mariomariokt64 fork](https://github.com/mariomariokt64/MarioKart64Recomp/releases/latest)** (Windows zip, macOS zip for Intel and Apple silicon,
   Linux AppImage or tar.gz for x64 and arm64). It is a separate project (GPL-3.0, by sonicdcer and the N64Recomp team); the fork builds its
   multiplayer branch with the Keyboard Players option, which split screen online uses. The official 0.9.2 release does not load the mod.
2. **Your own copy of the US Mario Kart 64 ROM** (`.z64`, `.v64` or `.n64`). Nothing of the game is distributed here, and your ROM never
   leaves your PC.
3. **Windows 10 or 11 (x64), macOS (Apple silicon or Intel), or Linux (x64).** Nothing else to install.

## What works

- **A lobby inside the game:** browse, create and join lobbies, chat, get ready, pick a driver for each seat, choose the course; the host
  starts the match for everyone.
- **Races of up to 8 karts** on any course, in 50cc, 100cc, 150cc or Extra; everyone gets the same results. CPU karts fill the empty seats.
- **Balloon battles of up to 16 karts:** hits, balloons, items, Boo's steals and bomb karts are shared between PCs; karts past the game's
  own eight are drawn by the mod, and CPU karts past the eighth drive with the game's own physics and items.
- **Split screen online:** two or more players on one PC, each with their own device: the game's **Assign players** (in its Controls
  page, once the game is started) gives each player a gamepad, or the keyboard.
- **After a race:** the host's Retry, Course Change and Driver Change act for everyone; a PC can join a battle under way in a CPU kart's place.
- **The launcher:** Play (pick a server, check it, start the game), Status (the game, the mod, the ROM, the server and a tunnel at a
  glance), Live (who is on, the lobbies, the server's log), Host (run a server with one button) and Settings (the game, the ROM, the mod).
  The **?** button at the top right, or F1, walks you through any page.
- **Hosting:** on your PC, for your home network, or for anyone through a temporary Cloudflare tunnel (no port forwarding); join codes
  for a private server; a live leaderboard page for phones.

In the game: **Tab** moves through the lobby panel and **Enter** picks; hold **L and R** together (keyboard: E and R) to open the panel
again. The game's Controls menu rebinds every key.

## Playing with friends

- **Same network:** on the host's PC, Host page, turn on **Allow players on my network**, then **Start server**. Friends type the address
  it shows (for example `192.168.1.20:6464`).
- **Invite a friend** (Host page) copies a message with every address that reaches your server and its join code, ready to paste in a chat.
- **Keep it private:** set a join code before you share a tunnel's address. Players type it on their Play page; the launcher says at once
  whether the server takes it.

## Hosting a server

The launcher hosts a server with one button (Host page); **Start in background** keeps it running after the launcher closes. For a
dedicated host, run the server from the zip:

```
app\mk64coop.exe serve --host 0.0.0.0 --port 6464 --name "My server" --join-code <code> --max-players 16
```

Options: `--host <bind address>` (default `127.0.0.1`, this PC only: a tunnel on the same PC still reaches it; `0.0.0.0` for your network),
`--port` (default 6464), `--advertise <address players use>`, `--name`,
`--motd <line>`, `--max-players <2-16>`, `--join-code <code>`, `--data <folder>`. Everything runs over one HTTP port: the
game's WebSocket, the server's information and the leaderboard at `http://<server>:6464/board/`, so it works behind a Cloudflare Tunnel or
an HTTPS reverse proxy.

## FAQ

**The game says the mod needs another version.** Use the game build from the [releases of the mariomariokt64 fork](https://github.com/mariomariokt64/MarioKart64Recomp/releases/latest). The official
0.9.2 release does not load the mod.

**The game starts but never connects.** Check the server on the Play page first (the dot turns green when it answers). Then open **Game
log** (Play or Status page): it says what the mod tried. A private server needs its join code; a server on another PC needs **Allow players
on my network** on, or a tunnel.

**Can I play split screen online?** Yes: set how many players are on this PC (1 to 4) on the Play page, one gamepad each.
 them. Your saves are the game's own.

## Reporting a bug

Open an issue: **[Report a bug](../../issues/new/choose)**. The form asks for what helps most:

- **The version:** click the version at the bottom of the launcher's sidebar (it copies something like `MK64 Coop Deluxe vX.Y.Z (abc1234)`).
- **How you play:** hosting or joining, how players connect (same PC, same network, a tunnel), how many PCs and players.
- **The game log:** Play or Status page, **Game log**, **Copy**. A host's server log is on the Live page.

Look through a log before you post it: it can show your server address and player names. Please do not attach your ROM or game files.
