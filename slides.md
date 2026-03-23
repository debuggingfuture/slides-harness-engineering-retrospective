---
theme: default
title: Engineering Harness on the Fly
info: |
  Adapting to Harness Engineering in a Startup
class: text-center
drawings:
  persist: false
transition: slide-left
---

# Engineering Harness on the Fly

Adapting to Harness Engineering in a Startup

<div class="mt-4 flex justify-center">
  <video src="/ar_bo.mp4" autoplay loop muted playsinline class="h-48 rounded-lg shadow-lg" />
</div>

<div class="abs-br m-6 flex gap-2">
  <span class="text-sm opacity-50">2026</span>
</div>

---
layout: quote
---

# WTF is Harness Engineering

<div style="max-width: 60%;">

> "It is the idea that anytime you find an agent makes a mistake,
> you take the time to **engineer a solution**
> such that the agent **never makes that mistake again**."

— Mitchell Hashimoto, [*My AI Adoption Journey*](https://mitchellh.com/writing/my-ai-adoption-journey#step-2-reproduce-your-own-work)

</div>

---

# Background

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### Project Nature

<v-clicks>

- **High Compliance + Security Requirement**
- **Scalability & Performance**
- **150M+ Global Monthly Visits**

</v-clicks>

</div>

<div>

### Tech Stack

<div class="flex flex-wrap gap-1.5 mt-2">
  <span class="border border-orange-400/40 bg-orange-500/10 text-orange-300 rounded px-1.5 py-0.5 text-xs font-mono">CF Workers</span>
  <span class="border border-orange-400/40 bg-orange-500/10 text-orange-300 rounded px-1.5 py-0.5 text-xs font-mono">D1</span>
  <span class="border border-orange-400/40 bg-orange-500/10 text-orange-300 rounded px-1.5 py-0.5 text-xs font-mono">Durable Objects</span>
  <span class="border border-orange-400/40 bg-orange-500/10 text-orange-300 rounded px-1.5 py-0.5 text-xs font-mono">Queues</span>
  <span class="border border-gray-400/40 bg-gray-500/10 text-gray-300 rounded px-1.5 py-0.5 text-xs font-mono">Pulumi</span>
  <span class="border border-gray-400/40 bg-gray-500/10 text-gray-300 rounded px-1.5 py-0.5 text-xs font-mono">GitHub Actions</span>
  <span class="border border-gray-400/40 bg-gray-500/10 text-gray-300 rounded px-1.5 py-0.5 text-xs font-mono">Nx Cloud</span>
  <span class="border border-blue-400/40 bg-blue-500/10 text-blue-300 rounded px-1.5 py-0.5 text-xs font-mono">PostgreSQL</span>
  <span class="border border-blue-400/40 bg-blue-500/10 text-blue-300 rounded px-1.5 py-0.5 text-xs font-mono">Kafka</span>
  <span class="border border-blue-400/40 bg-blue-500/10 text-blue-300 rounded px-1.5 py-0.5 text-xs font-mono">Flink</span>
  <span class="border border-emerald-400/40 bg-emerald-500/10 text-emerald-300 rounded px-1.5 py-0.5 text-xs font-mono">TypeScript</span>
  <span class="border border-emerald-400/40 bg-emerald-500/10 text-emerald-300 rounded px-1.5 py-0.5 text-xs font-mono">Effect-TS</span>
  <span class="border border-pink-400/40 bg-pink-500/10 text-pink-300 rounded px-1.5 py-0.5 text-xs font-mono">Rudderstack</span>
  <span class="border border-pink-400/40 bg-pink-500/10 text-pink-300 rounded px-1.5 py-0.5 text-xs font-mono">PostHog</span>
</div>

<div class="mt-2 text-xs opacity-60">CQRS architecture · Effect-TS typed errors · DI via Layers</div>

</div>

</div>

---

# Project Timeline

<div class="flex items-end gap-0 mt-2 px-2" style="height: 120px;">
  <div v-click="1" class="flex-1 text-center">
    <div class="bg-violet-500/20 border border-violet-400 rounded px-1 py-0.5 text-xs text-violet-300 mb-1">Sonnet 4.5</div>
    <div class="w-3 h-3 rounded-full bg-violet-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Sep 25</div>
  </div>
  <div v-click="1" class="flex-1 border-t border-gray-600 self-center"></div>
  <div v-click="1" class="flex-1 text-center">
    <div class="bg-emerald-500/20 border border-emerald-400 rounded px-1 py-0.5 text-xs text-emerald-300 mb-1">Kickoff · Arch</div>
    <div class="w-3 h-3 rounded-full bg-emerald-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Oct 25</div>
  </div>
  <div v-click="2" class="flex-1 border-t border-gray-600 self-center"></div>
  <div v-click="2" class="flex-1 text-center">
    <div class="bg-emerald-500/20 border border-emerald-400 rounded px-1 py-0.5 text-xs text-emerald-300 mb-1">Prototyping · Pivot</div>
    <div class="w-3 h-3 rounded-full bg-emerald-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Jan 26</div>
  </div>
  <div v-click="2" class="flex-1 border-t border-gray-600 self-center"></div>
  <div v-click="2" class="flex-1 text-center">
    <div class="bg-violet-500/20 border border-violet-400 rounded px-1 py-0.5 text-xs text-violet-300 mb-1">Opus 4.6</div>
    <div class="w-3 h-3 rounded-full bg-violet-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Feb 26</div>
  </div>
  <div v-click="2" class="flex-1 border-t border-gray-600 self-center"></div>
  <div v-click="2" class="flex-1 text-center">
    <div class="bg-emerald-500/20 border border-emerald-400 rounded px-1 py-0.5 text-xs text-emerald-300 mb-1">Integrations, CI</div>
    <div class="w-3 h-3 rounded-full bg-emerald-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Feb 26</div>
  </div>
  <div v-click="2" class="flex-1 border-t border-gray-600 self-center"></div>
  <div v-click="2" class="flex-1 text-center">
    <div class="bg-violet-500/20 border border-violet-400 rounded px-1 py-0.5 text-xs text-violet-300 mb-1">OpenCode</div>
    <div class="w-3 h-3 rounded-full bg-violet-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Mar 26</div>
  </div>
  <div v-click="2" class="flex-1 border-t border-gray-600 self-center"></div>
  <div v-click="2" class="flex-1 text-center">
    <div class="bg-violet-500/20 border border-violet-400 rounded px-1 py-0.5 text-xs text-violet-300 mb-1">Opus 4.6 1M</div>
    <div class="w-3 h-3 rounded-full bg-violet-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Mar 26</div>
  </div>
  <div v-click="2" class="flex-1 border-t border-gray-600 self-center"></div>
  <div v-click="2" class="flex-1 text-center">
    <div class="bg-emerald-500/20 border border-emerald-400 rounded px-1 py-0.5 text-xs text-emerald-300 mb-1">Production · Beta</div>
    <div class="w-3 h-3 rounded-full bg-emerald-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Mar 26</div>
  </div>
</div>
<div class="flex gap-4 mt-1 ml-2 text-xs">
  <span class="flex items-center gap-1"><span class="w-2 h-2 rounded-full bg-violet-400 inline-block"></span> Claude / Tools</span>
  <span class="flex items-center gap-1"><span class="w-2 h-2 rounded-full bg-emerald-400 inline-block"></span> Project</span>
</div>

<div v-click="3" class="grid grid-cols-2 gap-8 mt-4">
<div>

- **Team**: 1 Designer, 3 Principal Devs (12yr+ experience), 1 Senior FE Dev
- **Vincent**: PM + Security + Tech Lead role, ~30-50 PRs/week | ~100 messages/day to Claude
- **Claude Code**: Pro Plan → Premium Seat → AWS Bedrock. Token efficieny not (yet) a priority


</div>
<div>

<img src="/commits.png" class="h-48 rounded-lg shadow" />

</div>
</div>

---

# Mental Model Shift

<div class="grid grid-cols-2 gap-8 mt-6">

<div class="text-center">

<img src="/mental1.png" class="h-48 mx-auto rounded-lg shadow" />

**Individual** — Steering the Car

Working with Claude Code with Personalized workflow

</div>

<div class="text-center">

<img src="/mental2.png" class="h-48 mx-auto rounded-lg shadow" />

**Team** — Steering the Factory

Assembly Line, with eveyone commanding swarm of agents

</div>

</div>

---
layout: references
---

# Stripe's Coding Agent Workflow — Minions

One-shot end-to-end coding agents — [stripe.dev/blog/minions](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents)

1. 💬 **Human prompt at Slack** — Engineer describes a task or question
2. 🤖 **Slackbot triages** — Identifies whether it's a question or an actionable task
3. ☁️ **Cloudflare Sandbox** — Spins up isolated sandbox environment if needed
4. ⚙️ **GitHub Actions** — Builds, analyzes, and validates the codebase
5. ✅ **Job completes** — CI pipeline finishes execution
6. 📬 **Slackbot responds** — Returns results or drafts a PR for review

<img src="/minion.png" class="mt-4 mx-auto h-36 rounded-lg shadow" />

---
layout: references
---

# OpenAI's Approach: Harness Engineering

0 lines of manually-written code — [openai.com/index/harness-engineering](https://openai.com/index/harness-engineering/)

- **Humans steer. Agents execute.** — no human-written code, ever
- **Repo as single source of truth** — `AGENTS.md` as map, not manual
- **Enforce invariants, not implementations** — rigid architecture, flexible expression
- ~1M LOC in 5 months, 3 engineers, 1,500+ PRs merged
- Agent-to-agent code review, single runs working 6+ hours

---
layout: references
---

# Framework: 6+2 Perspectives of Harness Engineering

Adapted from [OpenAI's Harness Engineering](https://openai.com/index/harness-engineering/)

<div class="grid grid-cols-4 gap-3 mt-6">

<div v-click="1" class="border border-amber-400/40 bg-amber-500/10 rounded-lg p-3">
<div class="text-amber-300 font-bold text-sm">1. Architecture & Taste</div>
<div class="text-xs mt-1 opacity-70">Enforce invariants, not implementations. Rigid boundaries, flexible expression.</div>
</div>

<div v-click="1" class="border border-green-400/40 bg-green-500/10 rounded-lg p-3">
<div class="text-green-300 font-bold text-sm">2. Repo as System of Record</div>
<div class="text-xs mt-1 opacity-70">If it's not in the repo, it doesn't exist. Docs, plans, specs — all versioned.</div>
</div>

<div v-click="1" class="border border-cyan-400/40 bg-cyan-500/10 rounded-lg p-3">
<div class="text-cyan-300 font-bold text-sm">3. Agent Legibility</div>
<div class="text-xs mt-1 opacity-70">Optimize for the agent's ability to reason — not just human readability.</div>
</div>

<div v-click="1" class="border border-blue-400/40 bg-blue-500/10 rounded-lg p-3">
<div class="text-blue-300 font-bold text-sm">4. Application Legibility</div>
<div class="text-xs mt-1 opacity-70">Agents can drive the app, read logs, take screenshots, query metrics.</div>
</div>

<div v-click="1" class="border border-purple-400/40 bg-purple-500/10 rounded-lg p-3">
<div class="text-purple-300 font-bold text-sm">5. Increasing Autonomy</div>
<div class="text-xs mt-1 opacity-70">From human-assisted to agent-driven. Each capability unlocks the next level.</div>
</div>

<div v-click="1" class="border border-rose-400/40 bg-rose-500/10 rounded-lg p-3">
<div class="text-rose-300 font-bold text-sm">6. Entropy & Garbage Collection</div>
<div class="text-xs mt-1 opacity-70">Agents replicate patterns — even bad ones. Continuous cleanup prevents drift.</div>
</div>

</div>

<div v-click="2" class="flex justify-end items-center gap-3 mt-2">

<div class="text-xs opacity-50">+ Added by Vincent</div>

<div class="border border-teal-400/40 bg-teal-500/10 rounded-lg p-3" style="width: calc(25% - 0.5rem);">
<div class="text-teal-300 font-bold text-sm">7. Human Legibility</div>
<div class="text-xs mt-1 opacity-70">Optimize for human understanding — clear specs, readable code, maintainable context.</div>
</div>

<div class="border border-orange-400/40 bg-orange-500/10 rounded-lg p-3" style="width: calc(25% - 0.5rem);">
<div class="text-orange-300 font-bold text-sm">8. Agility</div>
<div class="text-xs mt-1 opacity-70">Individuals over processes. Working software over documentation. Respond to change.</div>
</div>

</div>

---
layout: perspective
active: 1
---

# Perspective 1: Architecture & Taste

<div class="text-sm opacity-60 mt-1">Enforce invariants, not implementations. Rigid boundaries, flexible expression.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### What We Did

<v-clicks>

- <!-- TODO: add points -->

</v-clicks>

</div>

<div>

### Learnings

<v-clicks>

- <!-- TODO: add points -->

</v-clicks>

</div>

</div>

---
layout: perspective
active: 2
---

# Perspective 2: Repo as System of Record

<div class="text-sm opacity-60 mt-1">If it's not in the repo, it doesn't exist. Docs, plans, specs — all versioned.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### What We Did

<v-clicks>

- **Git-based** everything — specs, architecture decisions, runbooks all live in the repo
- Agent to consolidate specs from scattered sources

</v-clicks>

</div>

<div>

### Learnings

<v-clicks>

- **Notion is pretty crap** for agent-readable context — not versioned, not grep-able, not in the repo
- Moving documentation into the repo made agents dramatically more effective

</v-clicks>

</div>

</div>

<div class="mt-4 border-t border-green-400/20 pt-3">

**See also:** [GitHub Spec Kit](https://github.com/github/spec-kit) — structured specs as a harness that constrains agent interpretation before any code is written.

</div>

---
layout: perspective
active: 2
---

# The Monolithic Manual Problem

---
layout: perspective
active: 3
---

# Perspective 3: Agent Legibility

<div class="text-sm opacity-60 mt-1">Optimize for the agent's ability to reason — not just human readability.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### What We Did

<v-clicks>

- <!-- TODO: add points -->

</v-clicks>

</div>

<div>

### Learnings

<v-clicks>

- <!-- TODO: add points -->

</v-clicks>

</div>

</div>

<div class="mt-6 border-l-4 border-red-400/60 pl-4 py-2 bg-red-500/5 rounded-r">

> "It rots instantly. A monolithic manual turns into a graveyard of stale rules. Agents can't tell what's still true, humans stop maintaining it, and the file quietly becomes an attractive nuisance."

</div>

<div class="mt-4 border-l-4 border-red-400/60 pl-4 py-2 bg-red-500/5 rounded-r">

> "It's hard to verify. A single blob doesn't lend itself to mechanical checks (coverage, freshness, ownership, cross-links), so drift is inevitable."

</div>

<div class="text-sm opacity-50 mt-3">— OpenAI, <a href="https://openai.com/index/harness-engineering/">Harness Engineering</a></div>

<v-clicks>

- **CLAUDE.md / AGENTS.md** are system of record — but they must be **modular, verifiable, and maintained**
- Stale instructions are worse than no instructions — agents follow them blindly
- Invest in **freshness checks**: ownership per section, last-updated dates, CI lint for dead references

</v-clicks>

---
layout: perspective
active: 4
---

# Perspective 4: Application Legibility

<div class="text-sm opacity-60 mt-1">Agents can drive the app, read logs, take screenshots, query metrics.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### What We Did

<v-clicks>

- **Designer + Developer committing at Storybook** — shared component development workflow

</v-clicks>

</div>

<div>

### Challenges

<v-clicks>

- **Git branch conflicts** — designer and developer stepping on each other's changes
- **Lack of source of truth at Figma** — Storybook diverges from design, no single canonical reference

</v-clicks>

</div>

</div>

---
layout: perspective
active: 4
---

# Custom CLI for Application Legibility

<div class="text-sm opacity-60 mt-1">Give agents eyes into your systems — not just the codebase.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### What We Built — `ccli`

- **GitHub**: read issues, PRs, comments, CI run status
- **SigNoz**: query logs, traces, alerts, service health
- **AWS**: tail CloudWatch logs, inspect ECS deployments
- **Slack**: post status updates, alert notifications

</div>

<div v-click>

### Why It Matters

- Agents can **diagnose production issues** by reading real logs and traces
- **Closes the feedback loop** — agent reads issue, checks logs, proposes fix
- Deterministic, typed CLI > fragile Bash pipelines with `jq`
- Caching + analytics built in — know what your agents are actually querying

</div>

</div>

---
layout: perspective
active: 5
---

# Perspective 5: Increasing Autonomy

<div class="text-sm opacity-60 mt-1">From human-assisted to agent-driven. Each capability unlocks the next level.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### What We Did

<v-clicks>

- <!-- TODO: add points -->

</v-clicks>

</div>

<div>

### Learnings

<v-clicks>

- <!-- TODO: add points -->

</v-clicks>

</div>

</div>

---
layout: perspective
active: 6
---

# Perspective 6: Entropy & Garbage Collection

<div class="text-sm opacity-60 mt-1">Agents replicate patterns — even bad ones. The "No Look Pass"&trade;</div>

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### What We Did

- **Architecture audit & review** — periodic review of agent-generated code for drift

### The "No Look Pass"

<img src="/ronaldinho-no-look-pass.gif" class="h-32 rounded-lg shadow-lg mt-2" />

</div>

<div v-click>

### Learnings

- **Start with firewall** human vs agent → then accept agent context as it matures
- **2nd Law of Thermodynamics** — without active effort, codebases decay toward disorder
- **Zero-shot prompting** — agents with no context produce plausible but drifting code
- Merging agent PRs without reading the diff — it looks cool, until it doesn't
- **Every "no look pass" is a bet** that your harness catches what your eyes didn't


</div>

</div>

---
layout: perspective
active: 7
---

# Perspective 7: Human Legibility

<div class="text-sm opacity-60 mt-1">Optimize for human understanding — clear specs, readable code, maintainable context.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div v-click="1">

### What We Did

- **Custom CLI (`ccli`)** — deterministic, typed wrapper over GitHub, AWS, Pulumi, Slack, and network tools
- **Effect-TS based CLI** — CI/CD orchestration as a workaround for GitHub Actions YAML fragility
- **Access provisioning** — codified in tooling, not ad-hoc shell scripts

</div>

<div v-click="2">

### Learnings

- **Better interpolation than Bash** — structured args prevent injection and quoting nightmares
- Agents produce more reliable output when calling typed CLIs vs composing raw shell
- Wrapping existing tools (gh, aws) gives you **caching, logging, analytics** for free

</div>

</div>

---
layout: perspective
active: 8
---

# Perspective 8: Agility

<div class="mt-6 space-y-3">

<div v-click="1" class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Individuals and interactions</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">processes and tools</span>
</div>

<div v-click="1" class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Working software</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">comprehensive documentation</span>
</div>

<div v-click="1" class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Customer collaboration</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">contract negotiation</span>
</div>

<div v-click="1" class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Responding to change</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">following a plan</span>
</div>

</div>

<div v-click="2" class="mt-6 text-sm opacity-60 text-center italic">

"That is, while there is value in the items on the right, we value the items on the left more."

</div>

---
layout: perspective
active: 5
---

# Where Do We Stand?

<div class="mt-6 relative">

<!-- Spectrum bar -->
<div class="h-3 rounded-full bg-gradient-to-r from-green-400 via-blue-400 to-purple-500 mx-8" />

<!-- Labels on the spectrum -->
<div class="flex justify-between mx-8 mt-1">
  <span class="text-xs opacity-50">Human-assisted</span>
  <span class="text-xs opacity-50">Fully autonomous</span>
</div>

<!-- Marker positions -->
<div class="relative mx-8 mt-6" style="height: 120px;">

  <!-- Stripe marker ~15% -->
  <div class="absolute text-center" style="left: 15%; transform: translateX(-50%);">
    <div class="w-4 h-4 rounded-full bg-green-400 border-2 border-white mx-auto" />
    <div class="mt-2 text-sm font-bold opacity-60">Stripe</div>
    <div class="text-xs opacity-40">Agent as assistant</div>
  </div>

  <!-- Us marker ~35% — slightly closer to Stripe -->
  <div class="absolute text-center" style="left: 35%; transform: translateX(-50%);">
    <div class="w-5 h-5 rounded-full bg-blue-500 border-2 border-white mx-auto ring-4 ring-blue-500/30" />
    <div class="mt-2 text-sm font-bold text-blue-400">We're here</div>
    <div class="text-xs opacity-60">Humans write code <b>with</b> agents</div>
  </div>

  <!-- OpenAI marker ~85% -->
  <div class="absolute text-center" style="left: 85%; transform: translateX(-50%);">
    <div class="w-4 h-4 rounded-full bg-purple-500 border-2 border-white mx-auto" />
    <div class="mt-2 text-sm font-bold opacity-60">OpenAI</div>
    <div class="text-xs opacity-40">Agent as engineer</div>
  </div>

</div>

</div>

---
layout: perspective
active: "4,6"
---

# Known Miss Out

### UX QA

- **No agentic workflow** to do QA on CLS, speed, reproduce & record bugs etc
- **Layout bugs slip through** — CSS issues, overflow, z-index, responsive breakpoints go unnoticed
- **Design-to-implementation gap** — agents can match specs structurally but miss visual polish

### SLO

- Setup SLO

<div class="mt-6 text-sm opacity-60">

Agents excel at logic and integration — but UX quality still requires human eyes.

</div>

---
layout: perspective
active: 5
---

# Autonomy

<div class="text-sm opacity-60 mt-1">Gatekeeping for compliance and stakeholder requirements takes human judgement to digest.</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div v-click="1">

### What We Did

- **CI self-heal** — agent detects and fixes broken builds autonomously
- **Monitoring** — agent-driven observability setup and alert response
- **Self-status update** — agent posts progress to PRs and Slack without prompting

</div>

<div v-click="2">

### Agent to Consolidate Specs

- Agent reads scattered requirements and produces unified spec documents
- Reduces human overhead in cross-referencing multiple sources

</div>

</div>

---
layout: perspective
active: "5"
---

# Unknown Miss Out

<v-clicks>

- **Local-first Notion alternative** for collaboration?
- **Sandbox environment** — isolated agent execution for safe experimentation
- **Type systems** — can richer type systems serve as a better harness for agent-generated code?

</v-clicks>

---
layout: perspective
active: 3
---

# Gap Analysis / Hallucination

<div class="text-sm opacity-60 mt-1">When agents confidently produce wrong answers — how do you catch it?</div>

<v-clicks>

- **Specs: Internal vs External** — agent-generated specs can drift from actual requirements if not grounded
- **Remove dead code** — agents generate code that references removed functions; stale code accumulates fast
- **Hallucination is the default** — without strong context, agents fill gaps with plausible fiction

</v-clicks>

---
layout: perspective
active: 4
---

# Challenge: AI Sandbox

<div class="text-sm opacity-60 mt-1">Isolated execution environments for safe agent experimentation.</div>

<v-clicks>

- **Dagger** — explored for containerized agent sandboxing, but **too slow** for interactive workflows
- Closely tied to **Application Legibility** — agents need to run, observe, and iterate on the app
- No great solution yet — sandboxing adds latency that breaks the agent feedback loop

</v-clicks>

---
layout: perspective
active: "4"
---

# Human as Bottleneck

<v-clicks>

- **Less familiar with browser testing stack** — Playwright, Cypress, visual regression tooling
- When the human doesn't know the domain, agents can't be effectively supervised
- The bottleneck isn't the agent — it's the human's ability to evaluate agent output in unfamiliar territory

</v-clicks>

---
layout: perspective
active: 6
---

# Style Guide

<v-clicks>

- **Took multiple iterations** to prompt correct Effect-TS usage
- Avoiding `._tag` direct access — enforced via CLAUDE.md rules
- **Simple pre-PR lint hook** (Biome) catches common agent mistakes before review

</v-clicks>

---
layout: perspective
active: "5"
---

# Case Study: CI Pipeline

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### 1. Human — Deploy & Document

<div class="mt-3 space-y-2">

<div v-click="1" class="flex items-start gap-2">
  <span class="text-emerald-400 mt-0.5">&#10148;</span>
  <span>Deploy feature branch to <strong>staging</strong></span>
</div>

<div v-click="1" class="flex items-start gap-2">
  <span class="text-emerald-400 mt-0.5">&#10148;</span>
  <span>Verify deployment health manually</span>
</div>

<div v-click="1" class="flex items-start gap-2">
  <span class="text-emerald-400 mt-0.5">&#10148;</span>
  <span>Update <strong>architecture diagrams</strong> to reflect changes</span>
</div>

</div>

<div class="mt-4 text-xs opacity-50">Human handles taste decisions — staging validation, documentation accuracy</div>

</div>

<div v-click="2">

### 2. Agent — Pre-prod → Prod

<div class="mt-3 space-y-2">

<div class="flex items-start gap-2">
  <span class="text-blue-400 mt-0.5">&#10148;</span>
  <span>Create <strong>pre-prod branch</strong> from staging</span>
</div>

<div class="flex items-start gap-2">
  <span class="text-blue-400 mt-0.5">&#10148;</span>
  <span>Claude runs <strong>test suite</strong> against pre-prod</span>
</div>

<div class="flex items-start gap-2">
  <span class="text-blue-400 mt-0.5">&#10148;</span>
  <span>Claude <strong>deploys</strong> and validates health checks</span>
</div>

<div class="flex items-start gap-2">
  <span class="text-blue-400 mt-0.5">&#10148;</span>
  <span>Claude <strong>merges</strong> PR on success</span>
</div>

</div>

<div class="mt-4 text-xs opacity-50">Agent handles mechanical steps — branching, testing, deploying, merging</div>

</div>

</div>

<div class="mt-6 flex items-center justify-center gap-2 text-sm">
  <span class="bg-emerald-500/20 border border-emerald-400/40 text-emerald-300 rounded px-2 py-0.5">Human: taste & verification</span>
  <span class="opacity-40">→</span>
  <span class="bg-blue-500/20 border border-blue-400/40 text-blue-300 rounded px-2 py-0.5">Agent: execution & mechanics</span>
</div>

---
layout: perspective
active: "1"
---

# Reflection: How Much Do I Know About the Systems?

<div class="grid grid-cols-2 gap-6 mt-4">
<div>

### Less Familiar Stacks

- **CF Queues** — message batching, retry semantics, dead-letter handling
- **Effect-TS patterns** — Layer composition, `Effect.gen` generators, `Schema.TaggedError` for typed failures
- **SigNoz** — trace correlation, custom dashboards, alert rule authoring
- **Cloudflare Durable Objects** — actor model, hibernation lifecycle, alarm scheduling

</div>
<div v-click>

### Code Paths I Didn't Know Existed

- Kafka consumer rebalance & offset commit logic
- Flink checkpoint/savepoint recovery flow
- D1 batch transaction boundaries in Workers
- Pulumi dynamic providers and component resources


</div>
</div>

---
layout: perspective
active: "2,6"
---

# Improving with Claude Code

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### Personal Level — `/insights`

- Built-in Claude Code command to review your own usage patterns
- Surfaces habits, common mistakes, and productivity trends
- Helps you iterate on your personal harness — CLAUDE.md, hooks, workflows
- Low friction: just run `/insights` in your terminal

</div>

<div v-click>

### Team Level — The Hard Part

- Aggregating insights across a team is **much harder**
- Agent sessions contain **sensitive data** — proprietary code, credentials, internal context
- No safe way to share raw session data across team members today
- Current gap: team-level harness improvement requires manual knowledge sharing

</div>

</div>

---
layout: perspective
active: "6"
---

# Datadog: Deterministic Simulation Testing

Harness-first engineering — [datadoghq.com/blog/ai/harness-first-agents](https://www.datadoghq.com/blog/ai/harness-first-agents/)

<v-clicks>

- **Don't review every line — verify every invariant** — invest in automated checks, not manual diffs
- **DST as the workhorse** — deterministic simulation + fault injection catches bugs in ~5s that code review misses
- **Verification pyramid**: TLA+ specs → DST (500+ seeds) → model checking → bounded proofs → telemetry

</v-clicks>

<div v-click class="mt-2">

- **Scalability inversion** — formal methods used to be expensive; agents now generate specs, harnesses, and proofs automatically
- **Results**: redis-rust 87% memory reduction; Helix ~93% peak disk throughput, 5x lower produce latency vs Kafka

<div class="mt-2 text-sm opacity-60">

"The harness compounds in a way that code review cannot. Every invariant catches an entire class of bugs across future iterations."

</div>

</div>

---

# In vs Out of the Loop

<v-clicks>

- **Reactive mode** — responding to agent output after the fact
- Tension between staying informed and staying productive
- When to review every diff vs when to trust the harness

</v-clicks>

---

# Can't Stop Working

<v-clicks>

- Agents **must be dumb** — if you can't step away, your harness isn't working
- Built `ccli` — a custom CLI wrapping GitHub, AWS, Pulumi, Slack, and network tools

</v-clicks>

<div v-click>

- Invested in **project skills** — reusable Claude Code slash commands for common workflows
- The goal: fire-and-forget tasks that don't need you watching

</div>

---

# Ownership-first

<v-clicks>

- **AI Slop is very real** — agent-generated code that works but nobody understands or owns
- Every PR still needs a human who takes responsibility for what ships
- Ownership means you can explain *why* it's built this way, not just *that* it works

</v-clicks>

---

# Consensus

<v-clicks>

- **Meeting notes vs Signoffs** — agents can summarize, but decisions need human commitment
- Async signoffs in PRs > meeting minutes that nobody reads
- The repo becomes the consensus mechanism — if it's merged, it's agreed upon

</v-clicks>

---

# When Autonomy Is Desired

<v-clicks>

- Repetitive mechanical tasks — CI fixes, dependency updates, boilerplate
- Well-defined scope with clear success criteria
- Strong harness in place — tests, lints, type checks catch regressions

</v-clicks>

---

# Know Your Ship?

<v-clicks>

- Discussion on prototype — how much do you need to understand code you didn't write?
- Agent-generated code can outpace your mental model
- Balance: trust the harness, but maintain architectural awareness

</v-clicks>

---

# GitHub Spec Kit: Spec-Driven Development

<div class="text-sm opacity-60 mt-1">[github/spec-kit](https://github.com/github/spec-kit) — Specs as the source of truth, not code</div>

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

### How It Works

- **Specs become executable** — define the *what* and *why*; agents handle the *how*
- **Multi-step refinement** — constitution → specify → plan → tasks → implement
- **Clarify before building** — `/speckit.clarify` catches ambiguity before it becomes wrong code

</div>

<div v-click>

### Why It Matters

- **Agent-agnostic** — works with Claude Code, Copilot, Cursor, Codex, Gemini, 20+ agents
- **Extensible harness** — presets enforce org standards; extensions add domain-specific workflows
- Structured specs **constrain the agent's interpretation space** before any code is written

</div>

</div>

---

# Overall

<v-clicks>

- **Human drives architecture** — the high-level design, system boundaries, and key trade-offs were all human decisions
- Agents excel at implementation, but the structural choices that make or break a project still need human judgement

</v-clicks>

<div v-click>

- This worked pretty well in the end — the architecture held up as complexity grew
- Harness engineering is about **amplifying human intent**, not replacing it

</div>

---
layout: quote
---

# Stay in the Flow

> "Let agents do all of that work while I worked on other tasks."

— Mitchell Hashimoto, [*My AI Adoption Journey*](https://mitchellh.com/writing/my-ai-adoption-journey#step-5-engineer-the-harness)

Disable notifications, stay in deep work, and invest every agent mistake into guardrails so it never happens again.
