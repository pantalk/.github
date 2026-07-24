<p align="center">
  <img src="https://pantalk.dev/icon.svg" alt="Pantalk" width="100" height="100" />
</p>

<h1 align="center">Pantalk</h1>

<p align="center">
  <strong>Any agent, any chat.</strong><br/>
  Put the coding agent you already run into the chat apps your team already uses.
</p>

<p align="center">
  <a href="https://pantalk.dev">Website</a> · <a href="https://github.com/pantalk/pantalk">Documentation</a> · <a href="https://github.com/pantalk/station">Station</a> · <a href="https://github.com/pantalk/skills">Skills</a>
</p>

---

**Claude Code**, **Codex**, **Copilot**, **Gemini CLI**, **Goose**, **OpenCode**, **Aider** - Pantalk puts the harness you already run into **Slack**, **Discord**, **Mattermost**, **Telegram**, **WhatsApp**, **IRC**, **Matrix**, **Twilio/SMS**, and **Zulip**.

You get what a Claude tag in Slack or Block's Buzz gives you - an agent that is a real participant in the conversation, mentionable, threaded, with history - except nothing is paired. Those products pick the harness _and_ the platform for you. Pantalk keeps both ends pluggable: harnesses attach on one edge, platforms on the other, and swapping either is a line of YAML.

One daemon handles auth, sessions, and reconnects. Your harness talks through simple CLI commands or a Unix domain socket with a JSON protocol. No SDKs, no libraries - just shell commands that work with any language.

```bash
# Send a message to any platform
pantalk send --bot ops-bot --channel C0123456789 --text "Deploy complete ✅"

# Check what needs the harness's attention
pantalk notifications --bot ops-bot --unseen

# Read conversation history
pantalk history --bot ops-bot --channel C0123456789 --limit 20

# Stream events in real-time
pantalk stream --bot ops-bot --notify
```

### What people use it for

| Use case                         | What it looks like                                                                                                                                       |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ship code from a chat thread** | Claude Code or Codex opens PRs, fixes failing tests, and reviews diffs in the thread that asked for it - with your repo, sandbox, and approval settings. |
| **Agents that act on incidents** | Triage alerts, work the runbook, and report back in the channel your on-call already watches - or over SMS to a phone with nothing installed on it.      |
| **One subscription, whole team** | Run **one** authenticated Claude or Codex install and let everyone reach it by DM. No seat per person, no local setup, sessions isolated per teammate.   |

### See it working

[**Pantalk Station**](https://github.com/pantalk/station) is the showcase. A browser-accessible Linux desktop with Pantalk, Codex, and Claude Code already installed and registered as agents, plus one-command deployments that stand up a real Mattermost or IRC server next to it:

```bash
docker run --detach --name pantalk-station --shm-size 1g \
  --publish 127.0.0.1:6902:6901 ghcr.io/pantalk/station:latest
```

Open <http://127.0.0.1:6902>, log into a harness, and it is in chat. Changing which harness answers is one line of config.

### Repositories

| Repo                                          | Description                                            |
| --------------------------------------------- | ------------------------------------------------------ |
| [pantalk](https://github.com/pantalk/pantalk) | Daemon, CLI, and documentation                         |
| [station](https://github.com/pantalk/station) | Prebuilt desktop showcasing harness-to-platform wiring |
| [skills](https://github.com/pantalk/skills)   | Skill definitions any agentic harness can consume      |

### Companion Projects

| Repo                                          | Description                                  |
| --------------------------------------------- | -------------------------------------------- |
| [MCPShim](https://github.com/mcpshim/mcpshim) | Use any MCP server as a standard CLI command |
| [crmkit](https://github.com/crmkit/crmkit)    | An agent-first CRM your AI drives directly   |

Pantalk plugs your harness into the platforms people talk on. [MCPShim](https://mcpshim.dev) plugs tools into the harness. Together they form a complete agent infrastructure stack.

### Get Started

```bash
# Download the latest release
curl -sL https://github.com/pantalk/pantalk/releases/latest/download/pantalk-$(uname -s | tr A-Z a-z)-$(uname -m | sed 's/x86_64/amd64/;s/aarch64/arm64/').tar.gz | tar xz
sudo mv pantalk*/pantalk pantalk*/pantalkd /usr/local/bin/

# Install skills for your harness
pantalk skill install
```

<p align="center">
  <sub>Any agent, any chat. → <a href="https://pantalk.dev">pantalk.dev</a></sub>
</p>
