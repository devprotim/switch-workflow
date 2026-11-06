# SwitchOps — Live Demo Video Script

> **Format:** Walkthrough Demo  
> **Length:** ~2 minutes  
> **Style:** Natural, engaging live product demonstration ("Let me show you my screen...")

---

## 🎬 Demo Walkthrough

### 0:00 – 0:25 | Welcome & The Quick Pitch
**On Screen:** Start on your GitHub repo [devprotim/switch-workflow](https://github.com/devprotim/switch-workflow).

> *"Hey everyone, welcome to the demo of **SwitchOps**!*
>
> *Today, I'm excited to show you how we took an AI coding agent out of the private terminal and put it directly into our team chat to triage bugs alongside humans in real time.*
>
> *Let's jump right into the demo."*

---

### 0:25 – 0:50 | The Setup & Wispr Flow
**On Screen:** Switch to **Switch Console** and show the `#bug-triage` room, then glance at Wispr Flow.

> *"Here in Switch Console, we've connected our local Mattermost workspace to a custom agent named SwitchOps.*
>
> *We also hooked up **Wispr Flow** so that during high-pressure incidents, on-call engineers don't even have to type out long, tedious error messages—they can just speak naturally hands-free. Let's see how that looks."*

---

### 0:50 – 1:35 | The Live Triage in Action
**On Screen:** Switch to the **Mattermost `#bug-triage` channel** and zoom in on the thread.

> *"So picture this scenario: our team just shipped release v2.4, and suddenly checkout breaks.*
>
> *I used Wispr Flow to speak the alert straight into chat: 'Team, production checkout is completely down after the v2.4 deployment. Getting 500 HTTP database connection pool exhausted errors.'*
>
> *Now watch what SwitchOps does right here in the thread. Within seconds, it replies with a structured summary:*
> - *It automatically flags it as **🔴 P0 Critical**.*
> - *It isolates the root cause to database connection exhaustion linked to the recent v2.4 release.*
> - *And most importantly, it gives our on-call team clear next steps: pause rollout, roll back, and verify the connection pool.*
>
> *Down here, we tested another scenario with Google OAuth login failures. SwitchOps immediately caught that it was a **🟠 P1** issue caused by JWT key rotation caching, and told us exactly what verifier settings to check.*
>
> *Even for small CSS bugs like text overlap in dark mode, it gives a **🟢 P3** rating with the exact code fix."*

---

### 1:35 – 2:00 | Why It Matters & Wrap-Up
**On Screen:** Return to the GitHub repo / architecture diagram.

> *"What makes this so powerful is that nobody is stuck debugging alone in a private shell anymore. The entire team sees the triage, learns from the diagnosis, and collaborates out in the open.*
>
> *Because Switch runs locally on our machine, our codebase and incident data stay 100% private.*
>
> *That’s SwitchOps! Thanks so much for checking out the demo."*
