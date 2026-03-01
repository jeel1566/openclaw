---
title: "Use Cases and Project Ideas"
description: "What you can build with OpenClaw — from personal assistants to business automation"
summary: "Practical applications, business project ideas, and automation platforms powered by OpenClaw"
read_when:
  - Exploring what OpenClaw can do
  - Planning a project with OpenClaw
  - Evaluating OpenClaw for a specific use case
  - Looking for business ideas to build on OpenClaw
---

# What You Can Build with OpenClaw

OpenClaw is a multi-channel AI gateway that turns messaging platforms into powerful agent interfaces. This page covers both the technical building blocks and concrete business ideas you can build today.

## Business Project Ideas

These are practical, revenue-generating products you can build on OpenClaw. Each one solves a real problem that businesses already pay to fix.

### Customer Support Agent for Small Businesses

**The problem:** Small businesses (restaurants, clinics, salons, repair shops) lose customers because they can't respond to WhatsApp and Instagram messages fast enough. They can't afford a support team.

**What you build:** A WhatsApp/Telegram bot that answers FAQs, takes bookings, and escalates complex issues to the owner's phone. The agent knows the business hours, menu/price list, and policies from files in its workspace.

**How it works with OpenClaw:**
- Connect WhatsApp via [channel setup](/channels/whatsapp) with `allowFrom` for the business number
- Put business info (hours, pricing, policies) in the agent's [workspace](/concepts/agent-workspace) as markdown files
- Use [cron jobs](/automation/cron-jobs) to send daily summaries of conversations to the owner
- Use [multi-agent routing](/concepts/multi-agent) to run multiple client businesses from one gateway

**Revenue model:** Monthly subscription per business ($50-200/mo).

### Appointment Booking and Scheduling Assistant

**The problem:** Service businesses (dentists, tutors, consultants, hair salons) waste hours every week on back-and-forth scheduling over WhatsApp or phone. No-shows cost them money.

**What you build:** A conversational booking agent on WhatsApp/Telegram that checks availability, books appointments, sends reminders, and handles rescheduling. Connects to Google Calendar or CalDAV.

**How it works with OpenClaw:**
- Install the [CalDAV Calendar skill](https://clawhub.com/skills/caldav-calendar) or build a Google Calendar skill
- Use [cron jobs](/automation/cron-jobs) to send appointment reminders 24h and 1h before
- Use [browser automation](/tools/browser) to sync with booking systems that lack APIs
- Handle multiple businesses with [multi-agent routing](/concepts/multi-agent)

**Revenue model:** Per-booking fee or monthly flat rate per provider.

### E-Commerce Order and Inventory Agent

**The problem:** Small e-commerce sellers on Shopify, WooCommerce, or marketplaces spend hours answering "is this in stock?", "where's my order?", and "can I return this?" on WhatsApp and social media.

**What you build:** An agent that connects to the store backend, answers product questions, tracks orders, processes return requests, and alerts the owner about low stock or new orders.

**How it works with OpenClaw:**
- Use [webhooks](/automation/webhook) to receive new order notifications from Shopify/WooCommerce
- Build a [custom skill](/tools/skills) that queries the store API for order status and inventory
- Connect WhatsApp and Telegram for customer communication
- Use [cron jobs](/automation/cron-jobs) for daily inventory and sales reports

**Revenue model:** Monthly subscription + percentage of recovered abandoned carts.

### Real Estate Lead Response Bot

**The problem:** Real estate agents get leads from multiple portals (Zillow, Realtor, Facebook Ads) and the first agent to respond usually wins the deal. Most agents take hours to reply.

**What you build:** An agent that instantly responds to new leads via WhatsApp or SMS, qualifies them with questions (budget, timeline, area), schedules viewings, and sends property listings with photos.

**How it works with OpenClaw:**
- [Webhooks](/automation/webhook) receive lead notifications from portals and CRMs
- Agent responds within seconds on WhatsApp with property details
- Use [browser automation](/tools/browser) to pull listing details and photos from MLS
- [Cron jobs](/automation/cron-jobs) for follow-up sequences on leads that went cold
- [Multi-agent](/concepts/multi-agent) to handle different agents or regions

**Revenue model:** Per-lead fee or monthly retainer per agent.

### Accounting and Bookkeeping Intake

**The problem:** Small business owners and freelancers dump receipts, invoices, and bank statements in a WhatsApp group for their accountant. The accountant spends hours sorting, categorizing, and chasing missing documents.

**What you build:** A WhatsApp bot where clients forward receipts and invoices. The agent extracts amounts, dates, and vendors from images/PDFs, categorizes them, and produces monthly summaries ready for the accountant.

**How it works with OpenClaw:**
- Clients send photos/PDFs of receipts via WhatsApp — OpenClaw handles [images](/nodes/images) and [audio](/nodes/audio) processing
- Vision models extract data from receipt images
- Agent writes structured records to workspace files or a database
- [Cron jobs](/automation/cron-jobs) generate monthly reports and flag missing documents
- [Gmail Pub/Sub](/automation/gmail-pubsub) automatically processes invoices from email

**Revenue model:** Monthly per-client fee charged to accounting firms.

### Social Media Content Manager

**The problem:** Small businesses know they need to post regularly on social media but don't have time to create content, schedule posts, or respond to comments.

**What you build:** An agent that drafts posts, creates captions, schedules publishing, and monitors engagement — all managed through Telegram or Slack conversation.

**How it works with OpenClaw:**
- Chat with the agent on Telegram/Slack to approve or tweak content
- [Browser automation](/tools/browser) posts to platforms that lack scheduling APIs
- [Cron jobs](/automation/cron-jobs) for scheduled post publishing
- Agent monitors engagement metrics and sends daily performance summaries
- Use [skills](/tools/skills) to integrate with Buffer, Hootsuite, or platform APIs

**Revenue model:** Monthly content management retainer per client.

### Internal Operations Assistant for Teams

**The problem:** Teams waste hours on repetitive internal tasks: status reports, standup summaries, onboarding checklists, PTO tracking, and hunting for information across Slack channels.

**What you build:** A Slack/Discord/Teams bot that automates standups, generates weekly reports from channel activity, handles PTO requests, onboards new hires with checklists, and answers HR/policy questions from company docs.

**How it works with OpenClaw:**
- Connect to Slack or [Microsoft Teams](/channels/msteams) as the team's workspace
- Load company handbook, policies, and procedures into the agent [workspace](/concepts/agent-workspace)
- [Cron jobs](/automation/cron-jobs) for daily standup prompts and weekly report generation
- [Webhooks](/automation/webhook) to integrate with HR systems (BambooHR, Gusto)
- Use [multi-agent](/concepts/multi-agent) for separate HR, engineering, and ops agents

**Revenue model:** Per-seat monthly pricing.

### Restaurant Order-Taking Bot

**The problem:** Restaurants lose delivery and takeout orders because phone lines are busy and third-party delivery apps take 30% commission.

**What you build:** A WhatsApp ordering bot where customers browse the menu, customize orders, and pay — bypassing delivery apps entirely.

**How it works with OpenClaw:**
- Menu and pricing stored in agent [workspace](/concepts/agent-workspace) files
- Customers order via WhatsApp with natural conversation
- Agent confirms orders, calculates totals, and sends payment links
- [Cron jobs](/automation/cron-jobs) for daily revenue summaries
- [Browser automation](/tools/browser) to sync orders with POS systems

**Revenue model:** Small per-order fee (much lower than delivery app commission).

### Competitive Price Monitoring

**The problem:** E-commerce businesses and retailers need to track competitor pricing daily but can't afford enterprise monitoring tools ($500+/mo) and manual checking doesn't scale.

**What you build:** An agent that monitors competitor websites, tracks price changes, and alerts the business via Slack or WhatsApp when competitors change prices on key products.

**How it works with OpenClaw:**
- [Browser automation](/tools/browser) visits competitor product pages on schedule
- [Cron jobs](/automation/cron-jobs) run price checks multiple times per day
- Agent compares prices against your catalog and sends alerts for significant changes
- Weekly trend reports delivered to Slack or Telegram

**Revenue model:** Monthly subscription based on number of products tracked.

### Client Reporting Automation for Agencies

**The problem:** Marketing, SEO, and advertising agencies spend 5-10 hours per client per month manually building performance reports from Google Analytics, ad platforms, and social media.

**What you build:** An agent that pulls data from multiple sources, generates branded reports, and delivers them to clients on schedule — all triggered from a Slack message or automated cron.

**How it works with OpenClaw:**
- [Browser automation](/tools/browser) logs into analytics dashboards and extracts data (check each platform's terms of service before automating; use [browser profiles](/tools/browser-login) for secure credential management)
- [Cron jobs](/automation/cron-jobs) generate reports on the 1st of each month
- Reports delivered to client Telegram/WhatsApp or emailed as PDFs
- Agency staff can request ad-hoc reports via Slack command

**Revenue model:** Per-client monthly fee or bundled into agency retainer.

---

## Technical Building Blocks

The ideas above are built on these OpenClaw capabilities.

### Messaging Channels

Connect to the platforms your users already use:

- WhatsApp, Telegram, Discord, Slack, iMessage, Signal, and [more](/channels/index)
- Microsoft Teams, Matrix, IRC, Mattermost via [plugins](/plugins/community)
- Run multiple accounts per channel with [multi-agent routing](/concepts/multi-agent)

### Automation Primitives

Schedule work and react to external events:

- **Cron jobs** — recurring tasks like daily briefings or report generation ([Cron Jobs](/automation/cron-jobs))
- **Webhooks** — trigger agent actions from CRMs, payment systems, or any HTTP source ([Webhooks](/automation/webhook))
- **Gmail Pub/Sub** — react to incoming emails ([Gmail Pub/Sub](/automation/gmail-pubsub))
- **Hooks** — run custom logic on message lifecycle events ([Hooks](/automation/hooks))

### Browser Automation

Control a dedicated Chromium instance for web tasks that lack APIs:

- Fill forms, click buttons, navigate pages, and extract data
- Log into websites and perform actions on your behalf
- Take screenshots and analyze page content with vision models

See [Browser](/tools/browser) for details.

### Multi-Agent Systems

Run multiple isolated agents from a single gateway:

- Each agent gets its own workspace, sessions, and system prompt
- Route messages by channel, sender, or group via [channel routing](/channels/channel-routing)
- Agents delegate to each other via [agent-send](/tools/agent-send) and [subagents](/tools/subagents)

See [Multi-Agent](/concepts/multi-agent) for the full architecture.

### Skills and Integrations

Wrap any API or tool into a conversational interface:

- Browse and install community skills from [ClawHub](https://clawhub.com)
- Build custom skills that call external APIs, run CLI commands, or query databases
- Share skills with the community

See [Skills](/tools/skills) for details.

### Voice and Media

Build voice-driven interfaces and process media:

- **Voice Wake** — always-on voice activation ([Voice Wake](/nodes/voicewake))
- **Talk Mode** — real-time voice conversations ([Talk](/nodes/talk))
- **Media processing** — handle images, audio, and documents ([Images](/nodes/images), [Audio](/nodes/audio))

### OpenAI API Compatibility

OpenClaw exposes an [OpenAI-compatible HTTP API](/gateway/openai-http-api) so you can integrate with any tool that speaks the OpenAI protocol (LangChain, Vercel AI SDK, n8n, and more).

### Mobile and Companion Apps

Extend to mobile devices with native apps:

- **macOS** — menu bar app with Voice Wake and Canvas ([macOS](/platforms/macos))
- **iOS** — voice, camera, and Canvas surface ([iOS](/platforms/ios))
- **Android** — chat, camera, and Canvas ([Android](/platforms/android))
- **WebChat** — browser-based chat interface ([WebChat](/web/webchat))

### Plugins and Extensions

Extend OpenClaw with [plugins](/tools/plugin) for custom channels, tools, or integrations. See [Community Plugins](/plugins/community) for available extensions.

---

## Next Steps

- [Getting Started](/start/getting-started) — set up your first OpenClaw instance
- [Showcase](/start/showcase) — see real community projects built by the community
- [Features](/concepts/features) — full feature list
- [Skills](/tools/skills) — browse and build skills
- [Multi-Agent](/concepts/multi-agent) — multi-agent architecture guide
