# README.md — Bugged (TryHackMe)

## 👀Quick summary
This repo contains a short writeup and screenshots for the **Bugged** room on TryHackMe. The challenge involved an MQTT broker (port `1883`) that accepts commands via a topic and publishes responses on another topic. I subscribed, decoded base64 messages, published `CMD`, and exfiltrated `flag.txt`.

## Files
- `WriteUp.md` — detailed steps & notes  
- `screenshots/` — evidence & command outputs

## Quickstart 
1. Install MQTT clients:
```bash
sudo apt update
sudo apt install mosquitto mosquitto-clients -y
````

2. Subscribe to all topics:

```bash
mosquitto_sub -h <IP> -p 1883 -t '#' -v
```

3. Publish crafted messages using `mosquitto_pub` (see `WriteUp.md` for examples).
4. Decode any base64 responses to reveal the flag.

## Disclaimer

For educational & lab purposes only. Don’t test this against infrastructure you don’t own or have permission to audit.

---
