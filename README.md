# Wavendis — MQTT Client

A lightweight, single-file browser-based MQTT client built as an alternative to the unstable HiveMQ demo client. Connects directly to any MQTT broker via WebSocket — no installation, no backend required. Made as a school project because I hate the default Hive client dashboard.

---

## Features

- **Connect** to any MQTT broker over WebSocket (TLS on port 8884 / 443)
- **Auto-generated Client ID** on every session
- **Subscribe** to topics with wildcard support (`#`, `+`)
- **Color-coded subscriptions** — assign a custom color to each topic, reflected across all log views
- **Publish** messages with configurable QoS (0/1/2) and retain flag
- **Message log** with five views:
  - **All** — every event
  - **Incoming** — received messages only
  - **Outgoing** — sent messages only
  - **⇅ Merged** — incoming and outgoing in a single stream with direction arrows
  - **System** — connection events, subscribe/unsubscribe, errors
- **Ctrl+Enter** shortcut to publish
- Zero dependencies beyond Paho MQTT JS (loaded via CDN)

---

## Usage

Just open `mqtt-client.html` in any modern browser. No build step, no server needed.

```
git clone https://github.com/<your-username>/wavendis-mqtt-client.git
cd wavendis-mqtt-client
open mqtt-client.html
```

Or use it directly via **GitHub Pages**:
```
https://<your-username>.github.io/wavendis-mqtt-client/mqtt-client.html
```

---

## Configuration

| Field | Default | Description |
|---|---|---|
| Host | `broker.hivemq.com` | MQTT broker hostname |
| Port | `8884` | WebSocket port (8884 = TLS, 8083 = plain) |
| Client ID | auto-generated | Unique per session |
| Username | — | Optional, required for private brokers |
| Password | — | Optional, required for private brokers |

To use a private HiveMQ Cloud broker, replace the host with your cluster URL and enter your credentials.

---

## Tech Stack

| | |
|---|---|
| Protocol | MQTT 3.1 over WebSocket |
| Library | [Paho MQTT JS](https://www.eclipse.org/paho/clients/js/) via CDN |
| Fonts | JetBrains Mono, Syne (Google Fonts) |
| Dependencies | None (single HTML file) |

---

## Project Structure

```
wavendis-mqtt-client/
└── mqtt-client.html    # Complete client — HTML, CSS, JS in one file
```

---

## License

MIT

