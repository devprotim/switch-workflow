# 2-Minute Demo Video Script: SwitchOps

> **Target Length:** 2 minutes to 2 minutes 30 seconds  
> **Tools:** Loom or QuickTime Screen Recording + Microphone

---

## ⏱️ Timeline & Talking Points

### 0:00 – 0:30 | The Hook & The Problem
- **What to show on screen:** [README.md](file:///Users/devprotimsikdar/Projects/switch-workflow/README.md) with the Mermaid architecture diagram.
- **What to say:**
  > *"Hey everyone! Welcome to SwitchOps. Today, millions of developers use AI coding agents, but those agents live in private terminal windows. When an incident or bug hits production, nobody on the team sees the AI's diagnostic reasoning.*
  > *With SwitchOps, we bring our AI agent directly into our team chat channels using Switch AI, making bug triage collaborative, instant, and transparent."*

### 0:30 – 1:00 | The Architecture & Wispr Flow
- **What to show on screen:** Switch Console showing the active Mattermost room and SwitchOps agent, then switch to Wispr Flow.
- **What to say:**
  > *"Here in Switch Console, we connected a local Mattermost chat channel called `#bug-triage` to our custom SwitchOps agent.*
  > *To make incident reporting lightning fast, we use Wispr Flow for voice dictation so engineers can speak bug reports hands-free at nearly 100 words per minute."*

### 1:00 – 1:50 | Live Triage Demo
- **What to show on screen:** Mattermost `#bug-triage` channel.
- **What to say & show:**
  > *"Let's look at `#bug-triage` in action. Here, an engineer reported a critical checkout outage after a release.*
  > *SwitchOps immediately stepped into the thread, rated it 🔴 P0 Critical, isolated the database connection pool exhaustion, and gave the team step-by-step rollback and mitigation instructions.*
  > *In another report, a team member flagged a Google OAuth authentication issue. SwitchOps immediately classified it as 🟠 P1 High, identified public key rotation caching, and provided verification checks.*
  > *The entire team can see the diagnosis, review recommended fixes, and collaborate in the open."*

### 1:50 – 2:15 | Wrap-Up & Submission
- **What to show on screen:** GitHub repository [devprotimsikdar/switch-workflow](https://github.com/devprotimsikdar/switch-workflow) and DEVLOG.
- **What to say:**
  > *"SwitchOps is completely open source, preserves data privacy with local execution, and eliminates expensive API keys.*
  > *Thanks to Switch AI, WeMakeDevs, DevTools Academy, and Wispr Flow for hosting the Flip the Switch hackathon!"*

