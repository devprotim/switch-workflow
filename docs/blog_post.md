# How I Turned an AI Coding Agent into a Collaborative DevOps Teammate in 3 Days

*Built with Switch AI and Wispr Flow for the Flip the Switch Hackathon (WeMakeDevs & DevTools Academy).*

---

## The Problem: The "Solo Agent" Isolation Trap

Over the past year, AI coding agents like Claude Code, OpenCode, and Codex have revolutionized how individual engineers write software. But they created an unexpected bottleneck: **isolation**.

When an engineer uses an AI agent in their local terminal, all of that reasoning, root-cause diagnosis, and context happens in a private silo. If production goes down or a critical bug appears:
- Only the person sitting at that terminal sees the AI's hypothesis.
- Other on-call engineers are left in the dark.
- Junior developers miss out on seeing how seniors and AI diagnose issues together.

I wanted to change that. What if, instead of keeping the AI locked inside a private terminal, we brought it directly into our team chat as an active DevOps teammate?

Enter **SwitchOps**.

---

## The Solution: SwitchOps

**SwitchOps** is an autonomous bug triage and incident-response teammate that lives inside team chat channels (powered by Mattermost and Switch AI). 

When a developer shares an error log, stack trace, or incident alert in `#bug-triage`:
1. **SwitchOps reads the context instantly** via the Switch chat bridge.
2. **It assigns an urgency rating** (`🔴 P0 - Critical`, `🟠 P1 - High`, `🟡 P2 - Medium`, `🟢 P3 - Low`).
3. **It formulates a root cause hypothesis** based on logs, recent changes, and stack traces.
4. **It posts structured next steps and code fixes** right in the public thread for everyone on the team to collaborate on.

---

## How It Works Under the Hood

The architecture leverages three key developer technologies:

```
[Developer Speaks via Wispr Flow]
             │
             ▼
    [Mattermost #bug-triage]
             │
             ▼
    [Switch Console Bridge]
             │
             ▼
      [SwitchOps Agent]
             │
             ▼
    [Triage Thread Reply]
```

### 1. Switch AI: The Agent-to-Chat Bridge
Rather than writing brittle webhooks, managing Slack OAuth tokens, and paying per-token API charges, **Switch** runs local agents in the background and bridges them directly to chat platforms. Switch Console spins up a bundled Mattermost instance locally inside Docker, creating an instant collaboration sandbox.

### 2. Voice-First Incident Response with Wispr Flow
During high-pressure incidents, typing long stack traces or explaining symptoms is slow. Using **Wispr Flow**, I was able to push-to-talk dictate bug reports directly into chat at 96 words per minute. Wispr Flow’s auto-formatting accurately captured technical tokens like `JWT`, `OAuth`, `500 HTTP`, and `connection pool` without voice typos.

---

## The Build Journey: Overcoming Real-World Bugs

Building SwitchOps wasn't without hurdles. On Day 1, while connecting Switch Console to our local environment, we encountered a port configuration mismatch: the native Switch Core was failing to register the local server on custom ports. 

Instead of working around it silently, we documented the bug, identified the root cause in `ports.json`, and submitted an official issue ([#1482](https://github.com/sandbox-quantum/switch/issues/1482)) to the open-source Switch repository to help other developers running the native toolchain.

---

## Live Triage in Action

Here is what the workflow looks like in real engineering scenarios:

### Scenario 1: Production Checkout Outage (P0)
A developer dictates via Wispr Flow:
> *"Team, production checkout is completely down after the v2.4 deployment. Getting HTTP 500 database connection pool exhausted. Users cannot place any orders."*

Within seconds, SwitchOps replies:
- **Severity:** 🔴 P0 — Critical (service blocked)
- **Affected Area:** Backend / Database
- **Root Cause:** Connection pool leak correlated with v2.4 deployment
- **Action:** Initiate rollback, check unclosed connections, and monitor pool recovery.

### Scenario 2: Broken Google OAuth Logins (P1)
When users experience `JWT signature validation failed`, SwitchOps points the team toward Google's public key rotation and verifier caching rather than rolling back unrelated services.

### Scenario 3: CSS Layout Collision on Mobile (P3)
Even for minor visual glitches, SwitchOps suggests exact CSS media query solutions for screens under 375px.

---

## What I Learned

1. **AI Belongs in the Room Where It Happens:** Moving an AI agent from a personal shell into a team chat channel turns AI assistance into team knowledge.
2. **Voice Dictation Speeds Up Operations:** Wispr Flow makes incident reporting tactile and fast. Speaking a 50-word bug report takes 15 seconds.
3. **Local-First Architecture Wins:** With Switch, all execution happens on your machine. You don't leak private incident data or internal error traces to third-party cloud bridges.

---

## Try It Out

Check out the full open-source project and step-by-step setup guide:
- **GitHub Repository:** [https://github.com/devprotim/switch-workflow](https://github.com/devprotim/switch-workflow)
- **Built for:** Flip the Switch Hackathon (Nov 2026)

