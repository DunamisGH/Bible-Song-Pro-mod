# Bible Song Pro Mod

A community-maintained fork of [Bible Song Pro](https://github.com/Johnbatey/bible-song-pro) for presenting Bible passages, song lyrics, and on-screen overlays. This fork adds LAN display support and workflow improvements for setlists and overlays.

[Download the project ZIP](https://github.com/DunamisGH/Bible-Song-Pro-mod/archive/refs/heads/setlisting-overlays.zip) · [View the upstream project](https://github.com/Johnbatey/bible-song-pro)

## What’s in this fork

- Sync the control panel and display over a local network.
- Use Tailscale Funnel for remote access when needed.
- Add ticker, text, media, and logo overlays to setlists.
- Use right-sidebar menus with clearer theme-aware styling and accordion behavior.
- Keep Bible passages, songs, and overlay sets together in one service setlist.

## Quick start

1. Download and extract the ZIP.
2. On Windows, run `start_lan.bat`, or start the server manually with `py -3 lan_server.py`.

3. Open the control panel and display on the same computer or another device on your network. Replace `<your-lan-ip>` with the server computer’s LAN address:

	- Control panel: `http://<your-lan-ip>:8000/Bible%20Song%20Pro%20panel.html`
	- Display: `http://<your-lan-ip>:8000/BSP_display.html`

The display connects to the relay at `ws://<your-lan-ip>:5511`. For same-computer use, `localhost` is also available.

## Remote access with Tailscale Funnel

Run `start_funnel.bat` on Windows, or start the server manually with:

```bat
py -3 lan_server_funnel.py
```

The Funnel setup uses HTTPS port `443` and relay port `10000`. Enter those ports in Remote Show settings. Stopping the launcher stops the local server but may leave Funnel routes configured; turn them off with:

```bat
tailscale funnel --https=443 off
tailscale funnel --https=10000 off
```

## Fork and attribution

This fork is independently maintained by **DunamisGH**. DunamisGH’s work here covers the fork’s additional features and modifications; it does not claim ownership of the original project or its code.

The upstream project is copyright © 2026 Johnson Olakotan and is licensed under the GNU General Public License, version 3.0 (GPL-3.0). See the upstream [copyright notice](https://github.com/Johnbatey/bible-song-pro/blob/main/COPYRIGHT.md) and [license](https://github.com/Johnbatey/bible-song-pro/blob/main/LICENSE) for the original notices and license terms.
