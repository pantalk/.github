<p align="center">
  <img src="https://pantalk.dev/icon.svg" alt="Pantalk" width="100" height="100" />
</p>

<h1 align="center">Pantalk</h1>

<p align="center">
  <strong>Give your AI agent a voice on every chat platform.</strong>
</p>

<p align="center">
  <a href="https://pantalk.dev">Website</a> · <a href="https://github.com/pantalk/pantalk">Documentation</a> · <a href="https://github.com/pantalk/skills">Skills</a>
</p>

---

Pantalk is a lightweight daemon + CLI that lets AI agents send, receive, and stream messages across **Slack**, **Discord**, **Mattermost**, **Telegram**, **WhatsApp**, **IRC**, **Matrix**, **Twilio**, and **Zulip** through a single interface.

One daemon handles auth, sessions, and reconnects. Your agent talks through simple CLI commands or a Unix domain socket with a JSON protocol. No SDKs, no libraries — just shell commands that work with any language.

```bash
# Send a message to any platform
pantalk send --bot ops-bot --channel C0123456789 --text "Deploy complete ✅"

# Check what needs your agent's attention
pantalk notifications --bot ops-bot --unseen

# Read conversation history
pantalk history --bot ops-bot --channel C0123456789 --limit 20

# Stream events in real-time
pantalk stream --bot ops-bot --notify
```

### Repositories

| Repo                                          | Description                                  |
| --------------------------------------------- | -------------------------------------------- |
| [pantalk](https://github.com/pantalk/pantalk) | Daemon, CLI, and documentation               |
| [skills](https://github.com/pantalk/skills)   | Agent skill definitions for AI coding agents |

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=pantalk/pantalk&type=date&legend=top-left)](https://www.star-history.com/#pantalk/pantalk&type=date&legend=top-left)

### Get Started

```bash
# Download the latest release
curl -sL https://github.com/pantalk/pantalk/releases/latest/download/pantalk-$(uname -s | tr A-Z a-z)-$(uname -m | sed 's/x86_64/amd64/;s/aarch64/arm64/').tar.gz | tar xz
sudo mv pantalk*/pantalk pantalk*/pantalkd /usr/local/bin/

# Install skills for your AI agent
pantalk skill install
```

<p align="center">
  <sub>Built for AI agents that need to talk. → <a href="https://pantalk.dev">pantalk.dev</a></sub>
</p>
