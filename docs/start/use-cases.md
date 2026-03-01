---
title: "Use Cases"
description: "What you can build with OpenClaw"
summary: "Practical applications, agentic systems, and automation platforms powered by OpenClaw"
read_when:
  - Exploring what OpenClaw can do
  - Planning a project with OpenClaw
  - Evaluating OpenClaw for a specific use case
---

# What You Can Build with OpenClaw

OpenClaw is a multi-channel AI gateway that turns messaging platforms into powerful agent interfaces. Below are the major categories of applications and systems you can build.

## Personal AI Assistant

The most common use case. Connect your messaging apps and get an always-on assistant that can:

- Answer questions and hold conversations across WhatsApp, Telegram, Discord, Slack, iMessage, and more
- Run commands on your machine, read/write files, and manage your workspace
- Send proactive updates via [heartbeats](/start/openclaw#heartbeats-proactive-mode) and [cron jobs](/automation/cron-jobs)
- Process images, audio, and documents you send it

See the [Personal Assistant Setup](/start/openclaw) guide to get started.

## Automation Platforms

OpenClaw's tool ecosystem and scheduling primitives make it a natural fit for building automation workflows.

### Browser Automation

Control a dedicated Chromium instance to automate web tasks that lack APIs:

- Fill forms, click buttons, navigate pages, and extract data
- Log into websites and perform actions on your behalf
- Take screenshots and analyze page content with vision models

See [Browser](/tools/browser) for details.

### Scheduled Tasks and Webhooks

Run recurring jobs or react to external events:

- **Cron jobs** — periodic tasks like daily briefings, report generation, or data syncing ([Cron Jobs](/automation/cron-jobs))
- **Webhooks** — trigger agent actions from external services ([Webhooks](/automation/webhook))
- **Gmail Pub/Sub** — react to incoming emails automatically ([Gmail Pub/Sub](/automation/gmail-pubsub))
- **Hooks** — run custom logic on message events ([Hooks](/automation/hooks))

### Examples from the Community

- **Tesco Shop Autopilot** — weekly meal plan to confirmed grocery order via browser control
- **Accounting Intake** — collect PDFs from email and prep tax documents monthly
- **ParentPay School Meals** — automated school meal booking
- **Padel Court Booking** — check and book sports courts automatically

## Multi-Agent Systems (MAS)

OpenClaw supports multi-agent architectures where specialized agents handle different tasks.

### Agent Routing

Route messages to different agents based on channel, sender, or group:

- Each agent gets an isolated workspace, session, and system prompt
- Agents can delegate work to other agents via [agent-send](/tools/agent-send) and [subagents](/tools/subagents)
- Use [channel routing](/channels/channel-routing) to assign channels to specific agents

See [Multi-Agent](/concepts/multi-agent) for the full architecture.

### Agent Coordination Patterns

- **Orchestrator + Workers** — a primary agent delegates specialized tasks to worker agents
- **Per-Channel Experts** — assign a coding agent to Slack, a research agent to Telegram, a personal assistant to WhatsApp
- **Subagent Delegation** — spawn ephemeral subagents for isolated subtasks like code review or data analysis

### Example from the Community

- **Kev's Dream Team** — 14+ agents under one gateway with an orchestrator delegating to specialized workers for coding, research, DevOps, and more

## Developer Tools and DevOps

Build tools that integrate with your development workflow:

- **PR Review Automation** — review pull requests and post feedback to messaging channels
- **Issue Triage** — monitor GitHub/Jira/Linear issues and respond or categorize them
- **CI/CD Notifications** — get build results and deploy status in your chat
- **Code Generation** — build entire apps or features through conversational chat
- **Skill Builder** — create custom [skills](/tools/skills) that wrap any CLI tool or API

### Example from the Community

- **PR Review to Telegram** — OpenClaw reviews diffs and sends merge verdicts to Telegram
- **iOS App via Telegram** — built a complete iOS app and deployed to TestFlight entirely through Telegram chat
- **Linear CLI** — manage Linear issues and projects from the terminal, integrated with agentic workflows

## Smart Home and IoT Control

Use OpenClaw as a natural language interface for hardware and smart home systems:

- **Home Assistant** — control lights, switches, and sensors via the [Home Assistant skill](https://clawhub.com/skills/homeassistant)
- **Philips Hue** — manage lighting with natural language
- **Sonos** — control speakers and music playback
- **Robot Vacuums** — start cleaning, check status, manage schedules
- **3D Printers** — monitor print jobs, check camera feeds, run calibration
- **Air Purifiers** — automate air quality management

## Voice-First Applications

Build voice-driven interfaces using OpenClaw's audio capabilities:

- **Voice Wake** — always-on voice activation on macOS and iOS ([Voice Wake](/nodes/voicewake))
- **Talk Mode** — real-time voice conversations with your agent ([Talk](/nodes/talk))
- **Phone Bridge** — connect phone calls to your agent via WebRTC or Vapi
- **Audio Transcription** — process voice notes and audio files

## Knowledge Management

Build systems that ingest, index, and query information:

- **Memory** — persistent agent memory with semantic search ([Memory](/concepts/memory))
- **Document Ingestion** — process PDFs, images, and audio into searchable knowledge
- **Transcription Indexing** — transcribe and index voice notes and recordings
- **Learning Systems** — build language learning or study tools with feedback loops

### Example from the Community

- **WhatsApp Memory Vault** — ingested full WhatsApp exports, transcribed 1,000+ voice notes, and output linked markdown reports
- **xuezh Chinese Learning** — pronunciation feedback and study flows via voice

## Custom Skills and Integrations

The [Skills](/tools/skills) system lets you wrap any API or tool into a conversational interface:

- Browse and install community skills from [ClawHub](https://clawhub.com)
- Build custom skills that call external APIs, run CLI commands, or query databases
- Share skills with the community

### What People Have Built

- **Wine Cellar** — local CSV-backed inventory skill built in minutes
- **Job Search Agent** — searches listings and matches against CV keywords
- **TradingView Analysis** — logs into TradingView, screenshots charts, performs technical analysis
- **Todoist Integration** — manage tasks through natural conversation
- **CalDAV Calendar** — self-hosted calendar management

## Mobile and Companion Apps

Extend OpenClaw to mobile devices with native companion apps:

- **macOS** — menu bar app with Voice Wake, Talk Mode overlay, and Canvas ([macOS](/platforms/macos))
- **iOS** — voice, camera, screen recording, and Canvas surface ([iOS](/platforms/ios))
- **Android** — chat, camera, screen recording, and Canvas ([Android](/platforms/android))
- **WebChat** — browser-based chat interface ([WebChat](/web/webchat))

## Plugins and Extensions

Extend OpenClaw with [plugins](/tools/plugin) for custom channels, tools, or integrations:

- Add new messaging channels (Microsoft Teams, Matrix, IRC, and more)
- Build custom extensions that hook into the agent lifecycle
- Use the plugin SDK to create shareable packages

See [Community Plugins](/plugins/community) for available extensions.

---

## Next Steps

- [Getting Started](/start/getting-started) — set up your first OpenClaw instance
- [Showcase](/start/showcase) — see real community projects
- [Features](/concepts/features) — full feature list
- [Skills](/tools/skills) — browse and build skills
- [Multi-Agent](/concepts/multi-agent) — multi-agent architecture guide
