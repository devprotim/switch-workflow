# 2-Minute Demo Video Script: SwitchOps

> **Target Length:** ~2 minutes  
> **Vibe:** Friendly, casual, and relaxed — like showing a cool project to a developer friend.

---

## ⏱️ Timeline & Script

### 0:00 – 0:30 | The Intro & The Problem
**On Screen:** Show your [GitHub README](https://github.com/devprotim/switch-workflow).

> *"Hey everyone! Quick question: how many times have you used an AI coding tool on your laptop, figured out a bug fix in your private terminal, but your teammates had no clue what was happening?*
>
> *Right now, most of our AI tools are kind of lonely. They sit in our own personal shell, while our team actually hangs out in chat. That's why I built **SwitchOps** for the Flip the Switch hackathon.*
>
> *With Switch AI, we took the AI out of the private terminal and gave it a seat right inside our team chat room."*

---

### 0:30 – 0:55 | The Setup & Wispr Flow
**On Screen:** Switch Console showing the `#bug-triage` room, then quick glance at Wispr Flow.

> *"Here's how simple the setup is. Inside Switch Console, we hooked up a local Mattermost chat channel called `#bug-triage` to our AI teammate.*
>
> *And honestly, typing out long, messy stack traces during an incident is super annoying. So I used **Wispr Flow** to just speak the bugs out loud hands-free at nearly 100 words a minute. Let me show you what happens next."*

---

### 0:55 – 1:45 | Seeing It In Action
**On Screen:** Mattermost `#bug-triage` channel, scrolling through the replies.

> *"Check out `#bug-triage` in action.*
>
> *When our checkout broke right after a new release, I just spoke what was happening into the channel: 'production checkout is down, getting 500 database pool errors.'*
>
> *Within seconds, SwitchOps jumped straight into the thread. It tagged it as a 🔴 P0 Critical emergency, figured out that the new release was hogging database connections, and gave us clear rollback instructions so the whole team knew what to do right away.*
>
> *We also tested it with a broken Google login bug. It immediately recognized that it was a 🟠 P1 authentication issue, pointed out an expired key cache, and told us what to check.*
>
> *Even for small stuff, like text overlapping in dark mode, it gives a friendly 🟢 P3 rating and shares the exact CSS fix."*

---

### 1:45 – 2:05 | Wrap-Up
**On Screen:** GitHub repo and DEVLOG.

> *"The best part? Nobody is debugging alone in the dark anymore. The AI works alongside the whole team out in the open. And because Switch runs locally, our code and incident logs stay private on our machine.*
>
> *Huge shoutout to Switch AI, WeMakeDevs, DevTools Academy, and Wispr Flow for hosting such a fun hackathon. Thanks for watching!"*
