# Bible Song Pro LAN display setup

This project includes a lightweight LAN relay so the control panel and display can sync across devices on the same network.

## Run it

Windows:

```bat
py -3 lan_server.py
```

or:

```bat
py -3 lan_server.py --host 0.0.0.0 --http-port 8000 --relay-port 5511
```

Then open the control panel and display pages on the same machine or another device on the LAN:

- Control panel: http://<your-lan-ip>:8000/Bible%20Song%20Pro%20panel.html
- Display: http://<your-lan-ip>:8000/BSP_display.html

The display page will automatically try to connect to the same host over WebSocket:

- ws://<your-lan-ip>:5511

## Notes

- The relay is intentionally minimal and designed for local network use.
- If you load the display using `localhost`, it will default to `127.0.0.1`, which only works on the same machine.
- To use another device on the LAN, open the page via the server's LAN IP address.
