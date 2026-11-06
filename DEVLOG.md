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

---

## 🗓️ Day 1 — Nov 4, 2026: The Bug Hunter & Core Contribution

### 🎯 Objectives (from Day 0 plan)
- [x] Launch Switch Console and complete the `switch-buddy` onboarding flow
- [x] Spin up the local Mattermost instance and create `#bug-triage` channel
- [ ] Connect our first AI agent and test end-to-end communication loop in chat

### 🛠️ What We Did Today
1. **Launched Switch Console & Completed Onboarding:**
   - Launched Switch Console and began the `switch-buddy` onboarding flow.
   - During onboarding, hit a critical port-mismatch bug (see below) which consumed the session.

2. **Spun Up Local Mattermost Instance:**
   - Started the bundled Mattermost server on `http://localhost:8065` via Docker.
   - Channel creation (`#bug-triage`) deferred — blocked by the port bug below.

3. **Discovered Real Core Bug in Switch Console (v0.40.1):**
   - When connecting an existing Mattermost instance on `http://localhost:8065`, Switch Console's native server ignored the user-specified port and fell back to cached `ports.json` pointing to port `50007`.
   - Identified root cause in `local-switch-server/ports.json` and `native/mattermost-compose.yml`.
   - Fixed local connection so Switch Core and Mattermost communicate properly.

4. **Submitted Official Hackathon Issue for Core Contribution Track:**
   - Opened issue [#1482](https://github.com/sandbox-quantum/switch/issues/1482) on `sandbox-quantum/switch`.
   - Formally requested assignment under the `hackathon` label to compete for the **$100 Best Core Contribution** track.

### ⚠️ Gaps & Carry-Over
- **End-to-end agent ↔ chat test not completed.** The port bug discovery consumed the session. This is the #1 priority for Day 2.
- **`#bug-triage` channel not yet created** in Mattermost — requires stable connection first.

### 🔜 Next Up (Day 2 — Nov 5)
- Create `#bug-triage` channel in local Mattermost.
- Connect the SwitchOps AI agent and verify a full round-trip message in chat.
- Capture first demo screenshot for `demo/screenshots/`.

---

## 🗓️ Day 2 — Nov 5, 2026: Live Triage Loop & Voice-First DevOps with Wispr Flow

### 🎯 Objectives
- [x] Configure Mattermost bridge and verify active connection
- [x] Create `#bug-triage` channel in Mattermost
- [x] Define and deploy `SwitchOps` system prompt in Switch Console
- [x] Connect `SwitchOps` agent to `#bug-triage` room
- [x] Test end-to-end triage loops across P0, P1, and P3 severity scenarios
- [x] Dictate bug reports with Wispr Flow voice dictation (96 WPM)
- [x] Capture visual proof for submission and Wispr Flow bonus track

### 🛠️ What We Did Today
1. **Resolved Native Bridge Connection:**
   - Cleared stale bridge metadata in Switch Console.
   - Connected Switch Console to the local Mattermost service running on port 50100.
   - Initialized the `#bug-triage` channel for real-time collaboration.

2. **Configured SwitchOps Agent Persona:**
   - Authored the production triage system prompt (`agent/system_prompt.md`).
   - Configured structured triage summaries:
     - 🔍 Triage Summary & Issue Title
     - 🔴 / 🟠 / 🟡 / 🟢 Severity rating (P0 to P3)
     - Affected architectural domain (Frontend, Backend, Database, Infra)
     - Potential Root Cause hypothesis
     - Concrete, actionable engineering next steps (immediate check + code fix)

3. **Conducted Live Real-Time Triage Tests:**
   - **Scenario 1 (🔴 P0 Critical Outage):** Dictated production checkout downtime with database connection pool exhaustion. SwitchOps accurately classified it as P0, identified v2.4 rollout correlation, and prescribed immediate rollback and pool monitoring.
   - **Scenario 2 (🟠 P1 High Priority Auth Failure):** Dictated Google OAuth JWT verification failures. SwitchOps flagged key rotation cache issues and supplied verification debugging steps.
   - **Scenario 3 (🟢 P3 Low Priority UI Bug):** Dictated mobile responsiveness text overlap on dark mode toggle button. SwitchOps provided CSS media query adjustments.

4. **Captured Voice-First DevOps Proof (Wispr Flow):**
   - Spoke bug reports hands-free using Wispr Flow push-to-talk.
   - Recorded dictation at 96 words per minute.
   - Captured the floating Wispr waveform UI and official Insights tab proof (176 words spoken today).

### 💡 Learnings & Notes
- Having an AI agent live inside the team chat channel changes the incident response workflow. Instead of one developer sifting through logs in an IDE, the triage analysis is visible to the entire team instantly.
- Wispr Flow voice dictation makes describing complex stack traces and incident symptoms 2-3x faster than typing.

### 🔜 Next Up (Day 3 — Nov 6: Submission Day)
- [x] Record 2-minute walkthrough demo video.
- [x] Publish technical blog post on Dev.to / Hashnode.
- [x] Publish #HowISwitch social post on X / LinkedIn.
- [x] Submit Track 03: Best Core Contribution PR (#833 Canva connector).
- Submit project before Friday EOD!

---

## 🗓️ Day 3 — Nov 6, 2026: Core Contribution & Hackathon Polish

### 🎯 Objectives
- [x] Get assigned to official Track 03 hackathon issue on `sandbox-quantum/switch`
- [x] Implement the Canva Service Connector ([#833](https://github.com/sandbox-quantum/switch/issues/833))
- [x] Submit Pull Request ([#1615](https://github.com/sandbox-quantum/switch/pull/1615)) and sign the CLA
- [x] Verify CI test suite passes 100%
- [x] Update all submission links and assets

### 🛠️ What We Did Today
1. **Track 03 Assignment & Discord Escalation:**
   - Evaluated open hackathon tickets and posted structured proposals for `#833` (Canva) and `#783` (Factory Droid).
   - Coordinated via Discord with Phil Conway to secure official assignment from the maintainer team.
2. **Canva Connector Implementation:**
   - Built full OAuth configuration in `core/switch_core/connections/catalog/canva/connection.yaml` targeting Canva's official remote MCP server (`https://api.canva.com/connect/v1/mcp`).
   - Authored `skill/SKILL.md` specifying Canva's transactional editing lifecycle (`start-editing-transaction` → `perform-editing-operations` → `commit-editing-transaction`) and strict credential hygiene.
   - Added comprehensive test coverage in `test_loader.py`, `test_app_credentials.py`, `test_connector_apps.py`, `test_connection_catalog.py`, and `test_workspace_services.py`.
   - Updated design documentation in `docs/design/service-connections-v2.md`.
3. **Submitted PR #1615 & Passed CI:**
   - Opened PR [#1615](https://github.com/sandbox-quantum/switch/pull/1615) referencing `Closes #833`.
   - Successfully signed the Contributor License Agreement (CLA) with green CI status across CLA Assistant and Socket Security.



