# SwitchOps — Developer Log & Build Journey

> This log documents the daily progress, challenges, and architectural decisions made while building **SwitchOps** for the **Flip the Switch Hackathon** (WeMakeDevs & DevTools Academy, powered by Switch AI).

---

## 🗓️ Day 0 — Nov 3, 2026: Setup & Foundations

### 🎯 Objectives
- [x] Install and configure Wispr Flow for voice-first agent dictation
- [x] Download and install Switch Console
- [x] Verify Docker Desktop environment
- [x] Initialize Git repository and project structure

### 🛠️ What We Did Today
1. **Installed Wispr Flow:**
   - Configured push-to-talk hotkeys for instant speech-to-text dictation.
   - Tested dictating prompts and notes directly into the terminal and code editor.
   - Ready to capture voice usage metrics in the Insights tab for the *Code with Wispr* bonus track.

2. **Downloaded & Installed Switch Console:**
   - Downloaded latest Switch Console (`v0.40.1` x64 macOS package) from official releases.
   - Verified local Docker Desktop daemon (`Docker v29.8.2`) is running and ready to power the bundled local Mattermost server.

3. **Repository Initialization:**
   - Initialized Git repository with `main` branch.
   - Setup project directories:
     - `agent/`: System prompts, role definitions, and tool logic for our AI triage teammate.
     - `demo/`: Screenshots and video recording assets.
     - `docs/`: Technical notes and architecture details.

### 💡 Learnings & Notes
- Switch's local Mattermost bundle eliminates the overhead of setting up Slack bot tokens and webhooks on external corporate platforms.
- Voice dictation significantly speeds up writing descriptive system instructions and daily logs compared to manual typing.

### 🔜 Next Up (Day 1 — Nov 4)
- Launch Switch Console and complete the `switch-buddy` onboarding flow.
- Spin up the local Mattermost instance and create `#bug-triage` channel.
- Connect our first AI agent and test end-to-end communication loop in chat.
