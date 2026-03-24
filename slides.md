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

# Engineering Harness on the fly

Adapting to Harness Engineering in a Startup (While shipping)

<div class="mt-4 flex justify-center">
  <video src="/ar_bo.mp4" autoplay loop muted playsinline class="h-48 rounded-lg shadow-lg" />
</div>

<div class="abs-br m-6 flex gap-2 items-center">
  <a href="https://github.com/debuggingfuture/slides-harness-engineering-retrospective/" target="_blank" class="text-sm opacity-50 hover:opacity-100">by @debuggingfuture</a>
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

- **High Compliance + Security Requirement**
- **Scalability & Performance**
- **150M+ Global Monthly Visits**

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

<div class="mt-2 text-xs opacity-60">Monorepo · CQRS architecture · Effect-TS typed errors · OTel observability · DI via Layers</div>

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
    <div class="bg-violet-500/20 border border-violet-400 rounded px-1 py-0.5 text-xs text-violet-300 mb-1">OpenCode @ GHA</div>
    <div class="w-3 h-3 rounded-full bg-violet-400 mx-auto"></div>
    <div class="text-xs text-gray-400 mt-1">Feb 26</div>
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
- **Vincent (me)**: PM + Security/Data Privacy + Tech Lead role <br /> ~30-50 PRs/week | ~120 msg/day to Claude | <br /> 0 LoC manually-written
- **Claude Code**: Pro → Team | Premium → AWS Bedrock. Token efficieny not (yet) a priority


</div>
<div>

<img src="/commits.png" class="h-64 rounded-lg shadow" />

</div>
</div>

---

# Mental Model Shift

<div class="grid grid-cols-2 gap-8 mt-6">

<div class="text-center">

<img src="/mental1.png" class="h-48 mx-auto rounded-lg shadow" />

**Individual** — Steering the Car

Personal workflow, keep prompting & customizing

</div>

<div class="text-center">

<img src="/mental2.png" class="h-48 mx-auto rounded-lg shadow" />

**Team** — Steering the Factory

Ensure product is legit & aligned when evyeryone commanding swarm of agents

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

[openai.com/index/harness-engineering](https://openai.com/index/harness-engineering/)

- **Internal tool** built by Codex — greenfield, empty repo
- **0 lines manually written** — humans steer, agents execute
- ~1M LOC in 5 months · 3 engineers · 1,500+ PRs · 6+ hour agent runs

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

  <!-- Us marker ~40% -->
  <div class="absolute text-center" style="left: 40%; transform: translateX(-50%);">
    <div class="w-5 h-5 rounded-full bg-blue-500 border-2 border-white mx-auto ring-4 ring-blue-500/30" />
    <div class="mt-2 text-sm font-bold text-blue-400">We're here</div>
    <div class="text-xs opacity-60">Human prompt & review</div>
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
layout: references
---

# Framework: 6+2 Perspectives of Harness Engineering

Adapted from [OpenAI's Harness Engineering](https://openai.com/index/harness-engineering/)

<div class="grid grid-cols-4 gap-3 mt-6">

<div v-click="1" class="border border-green-400/40 bg-green-500/10 rounded-lg p-3">
<div class="text-green-300 font-bold text-sm">1. Repo as System of Record</div>
<div class="text-xs mt-1 opacity-70">If it's not in the repo, it doesn't exist. Docs, plans, specs — all versioned.</div>
</div>

<div v-click="1" class="border border-amber-400/40 bg-amber-500/10 rounded-lg p-3">
<div class="text-amber-300 font-bold text-sm">2. Architecture & Taste</div>
<div class="text-xs mt-1 opacity-70">Enforce invariants, not implementations. Rigid boundaries, flexible expression.</div>
</div>

<div v-click="1" class="border border-cyan-400/40 bg-cyan-500/10 rounded-lg p-3">
<div class="text-cyan-300 font-bold text-sm">3. Agent Legibility</div>
<div class="text-xs mt-1 opacity-70">Optimize for the agent's ability to reason — not just human readability.</div>
</div>

<div v-click="1" class="border border-rose-400/40 bg-rose-500/10 rounded-lg p-3">
<div class="text-rose-300 font-bold text-sm">4. Entropy & Garbage Collection</div>
<div class="text-xs mt-1 opacity-70">Agents replicate patterns — even bad ones. Continuous cleanup prevents drift.</div>
</div>

<div v-click="1" class="border border-blue-400/40 bg-blue-500/10 rounded-lg p-3">
<div class="text-blue-300 font-bold text-sm">5. Application Legibility</div>
<div class="text-xs mt-1 opacity-70">Agents can drive the app, read logs, take screenshots, query metrics.</div>
</div>

<div v-click="1" class="border border-purple-400/40 bg-purple-500/10 rounded-lg p-3">
<div class="text-purple-300 font-bold text-sm">6. Increasing Autonomy</div>
<div class="text-xs mt-1 opacity-70">From human-assisted to agent-driven. Each capability unlocks the next level.</div>
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
<div class="text-xs mt-1 opacity-70">Ship, learn, adapt — value responsiveness over rigid plans.</div>
</div>

</div>


---
layout: perspective
active: 1
---

<div class="grid grid-cols-2 gap-8 text-sm h-full">

<div>

# Executable Spec in Repo

<div class="text-sm opacity-60 mb-4">If it's not in the repo, it doesn't exist.</div>

<div class="mb-4">

> "Give Codex a map, not a 1,000-page instruction manual."

</div>
<div class="mb-4">

> "It rots instantly. It's hard to verify."

</div>

- Started with **[GitHub Spec Kit](https://github.com/github/spec-kit)** — `/clarify` prompts me to think.
- **Wordy, Context drift** → dropped Spec Kit, consolidated into markdown by design, workflow, runbook (Still ~27k lines)
- **Git(Hub)-based collab**
  - Solved Sync. Local lightweight markdown = Fast
  - both humans & agents create issues
- **Notion (& AI) = subpar** — Expensive, Slow, Dumb, Drifted

</div>

<div class="h-full">
  <img src="/constitution.png" class="rounded-lg shadow h-full w-full object-cover" />
</div>

</div>

---
layout: perspective
active: 1
---

<div class="col-span-2 mb-2">

# Omniscient Agents who can time travel

<div class="text-sm opacity-60">If it's not in the repo, it doesn't exist.</div>

</div>

<div class="grid grid-cols-2 gap-8 text-sm" style="height: calc(100% - 5rem)">

<div>

- **Knowing in-and-out of the codebase**
  - *"PR#123 tried A but failed, let's dig deeper"*
  - *"This bug is on master too — not due to our changes"*
  - *"Refactor these patterns for files changed since v1.0.3"*
  - *These are the pre-requisites. Add these secrets first.*
- **Parallelized: 6+ worktress, rebase & cherry-pick**
- **Classic Best Practices: Keep PR Small, Keep master Pretty**
  - 1 lint error taxes 15 agents
- **Out of repo:** custom scrapers + indexed docs, custom CLAUDE.md / skills

</div>

<div class="h-full flex flex-col justify-center">
  <img src="/pr.png" class="rounded-lg shadow w-full object-contain" />
</div>

</div>

---
layout: perspective
active: 2
---

# As usual, Don't f**k up the architecture

<div class="text-sm opacity-60">Enforce invariants, not implementations.</div>

- **Kickstart** — 1st month on discussions, wrote them down (great ROI)
- **Opinionated, NOT from agents** — monorepo, Saga, Effect-TS, changeset, SigNoz etc (NO Supabase!)
- Hexagonal, CQRS, DDD → strict boundary & predictable structure
- **Early Phase** — bootstrapping Harness
  - Prototyping → add "Constitution" (invariants)
  - Naming conventions → type-based Schema & Interfaces
- **Later Phase** — entrust agents on design (CI pipelines, Kafka schemas, data pipelines, marketing stack, tests3)

---
layout: perspective
active: 2
---

# Took us a while to get right

<div class="text-sm opacity-60">Enforce invariants, not implementations.</div>

- Multiple iterations to promote idiomitic Effect-TS usage (e.g. `Option` not `._tag`)
- Concise, Concrete examples work best
- Simple pre-PR lint hook (Biome) — keep agent loop fast
- Early phase (Sonnet 4.5): not holistic enough for DDD/CQRS
- **Hallucination**: unused or non-isomorphic packages

---
layout: perspective
active: 3
---

# What Do Agents See?

<div class="text-sm opacity-60">Optimize for the agent's ability to reason.</div>

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

- **Setup**: Slack, Notion MCP, Figma MCP (kind of works), Granola (Meetings)
- **Feed context**: org chart, contacts to agent
- **Lack of source of truth** — internal & external outside Git
- We want only **curated** context — not everything
- Support Prompting Slackbot to create draft PR (via OpenCode)
- **Security** is the hard part!

</div>

<div class="flex items-center justify-center h-full">
  <img src="/slackbot.png" class="rounded-lg shadow w-4/5 object-contain" />
</div>

</div>

---
layout: perspective
active: 3
---

# Firewall didn't work

<div class="text-sm opacity-60">Optimize for the agent's ability to reason.</div>

- **Agents are writing everything**
  - Plan: Notion by human, specs by agent
  - Reality: 
    - Unmaintained AI Slop (Notion & Notion AI both quite useless)
    - GitHub-based specs written by agents outperforming
- **Confirmation bias** — agents reinforce what you already believe
- **CLAUDE.md / AGENTS.md** must be modular, verifiable, maintained — stale instructions are worse than none
- Open Stacks really help

---
layout: perspective
active: 4
---

# The "No Look Pass"™

<div class="text-sm opacity-60">Continuous cleanup prevents drift.</div>

- **AI slop is real** — zero-shot prompts passing around -> Entropy 
- **Mistakes Made**:
  - Merging agent PRs without reading the diff, forgot to `git add`
  - Agents merging to `master` with `--admin`

<img src="/ronaldinho-no-look-pass.gif" class="h-32 rounded-lg shadow-lg mt-2" />

---
layout: perspective
active: 4
---

# Fighting 2nd law of thermodynamics

<div class="text-sm opacity-60">Continuous cleanup prevents drift.</div>

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### Auto (OpenCode @ GHA)

- Daily update on `STATUS.md`
- PR to issue and PR reviews
- Weekly architecture audit
- Comment to agentic scrum master on Slack

</div>

<div>

### Manual

- Architecture audit & review — talk to codebase
- Spec rewrite, active gap analysis
- **Remove dead code** — stale code is a hallucination magnet

</div>

</div>

---
layout: perspective
active: 5
---

# Observability to Agent = Step Function for Productivity

<div class="text-sm opacity-60">Agents can drive the app, read logs, query metrics.</div>

- **Our CI Complexity** - 3 Env x 7-9 Components x Secret Management.
  - IaC (Pulumi), GitHub Actions — circular deps, state drift, IAM
- **Deployment as Case Study**
  - Staging: point agent to failing build, fix & add guidelines, e2e, soak tests
  - Prod: `pre-prod` branch → agent PR → merge → deploy → validate

- **Production Monitoring** — via Pulumi ESC (read-only), k6 perf test suite
  - SigNoz, PostHog: iterate metrics, alerts, dashboards with agents
  - Claude Skill to troubleshoot / Scheduled OpenCode@GHA → Slack

<img src="/perf_chokepoint.png" class="mt-4 mx-auto h-36 rounded-lg shadow" />

---
layout: perspective
active: 5
---

# Utilities, Guardrails and TODOs

<div class="text-sm opacity-60">Agents can drive the app, read logs, query metrics.</div>

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### Custom CLI

- **Deterministic, better interpolation** vs Bash
- Effect-TS based CLI
  - CICD (workaround GH Action YAML)
  - Access provision

</div>

<div>

### What We Missed

- **Dagger** for sandboxing — too slow
- **No agentic UX QA** — CLS, speed, layout bugs
- No Chrome Dev Tools via CDP/MCP
- **SLO** — not set up yet

</div>

</div>

---
layout: perspective
active: 6
---

# Becareful what you wish for

<div class="text-sm opacity-60">Each capability unlocks the next level.</div>

- **Not full autonomy** — gatekeep for compliance & stakeholder requirements that take human to digest
- **What we want** — direct scarce human attention to what matters (a.k.a. stay in the flow), avoid human being the bottleneck

<div class="grid grid-cols-3 gap-6 mt-4">

<div>

### We have

- Auto PR Reviews
- CI self-heal
- Monitoring
- Self-status update

</div>

<div>

### We struggle

- Auto sprint planning
- Piping all Slack convo as context
- **Human as blocker**
  - Misunderstanding in Pulumi stack wasted agent cycles
  - Dev not familiar with latest browser stack

</div>

<div>

### We don't have

- Auto-merge PRs
- CD to prod
- Auto features from PostHog usage

</div>

</div>

---
layout: perspective
active: 7
---

# Novel problem - Know What you shi(*)?

<div class="text-sm opacity-60">Optimize for human understanding.</div>

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### Background

- Pace **faster than ever**
- Agent shipped with stack you're unfamiliar with

### Challenges

- Gaps in architecture
- Mock implementations

</div>

<div>

### What matters

- Branch convention, code ownership still matters
- Custom CLI helped
- Yes I still have to learn!
- Conscious on what I can live with

</div>

</div>

---
layout: perspective
active: 7
---

# Improving with Agents

<div class="text-sm opacity-60">Optimize for human understanding.</div>

- **Document and challenge** both thinking process and solution
- Create **well-defined skills** and high signal-to-noise CLIs
- **Personal**: `/insights` command for usage patterns, habits, productivity
- **Team visibility**
  - reviews on PR, prompting agents on slack together
  - conventional commits / PR templates 
  - aggregate insights is hard: sensitive data
---
layout: perspective
active: 8
---

# Everyone Is Learning

<div class="text-sm opacity-60">Back to Agile Manifesto. Bias towards shipping.</div>

<div class="mt-6 space-y-3">

<div class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Individuals and interactions</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">processes and tools</span>
</div>

<div class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Working software</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">comprehensive documentation</span>
</div>

<div class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Customer collaboration</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">contract negotiation</span>
</div>

<div class="flex items-center gap-3">
  <span class="text-orange-300 font-bold text-lg flex-1 text-right">Responding to change</span>
  <span class="opacity-40 text-sm">over</span>
  <span class="opacity-50 text-lg flex-1">following a plan</span>
</div>

</div>

<div class="mt-6 text-sm opacity-60 text-center italic">

"That is, while there is value in the items on the right, we value the items on the left more."

</div>

- **Go fast, Go Slow** — Different landscape every week 
- **Need of deep think** — tailor featureset, don't just ship what agents suggest
- **What we did**: spawned Opencode/Slackbot the next day after reading the Stripe article

---

# Mixed Feelings

<div class="grid grid-cols-4 gap-4 mt-6">

<div class="border border-emerald-400/40 bg-emerald-500/10 rounded-lg p-4 text-center">
<div class="text-2xl mb-2">&#9889;</div>
<div class="text-emerald-300 font-bold">Excited</div>
</div>

<div class="border border-amber-400/40 bg-amber-500/10 rounded-lg p-4 text-center">
<div class="text-2xl mb-2">&#127754;</div>
<div class="text-amber-300 font-bold">Overwhelmed</div>
</div>

<div class="border border-rose-400/40 bg-rose-500/10 rounded-lg p-4 text-center">
<div class="text-2xl mb-2">&#128293;</div>
<div class="text-rose-300 font-bold">Burnout</div>
</div>

<div class="border border-purple-400/40 bg-purple-500/10 rounded-lg p-4 text-center">
<div class="text-2xl mb-2">&#10067;</div>
<div class="text-purple-300 font-bold">Confused</div>
</div>

</div>

<div v-click="1" class="mt-8 space-y-3">

- When is **autonomy desired** — and when does it hurt?
- When to **remove the human as bottleneck** — and when to stay in the loop?
- Which parts of software are **[malleable](https://www.inkandswitch.com/essay/malleable-software/)**?
- How to be **ownership-first** for each role? PM, Designer, Engineer
- Agent boosted my productivity but **I'm not sleeping**.. What's wrong?
- Tools are free. **What should I build next?**

</div>

---

# FOMO

Things we haven't tried yet — but want to.

<div class="grid grid-cols-2 gap-6 mt-6">

<div class="border border-gray-400/30 bg-gray-500/10 rounded-lg p-4">
<div class="font-bold text-sm">Local-first Notion alternative</div>
<div class="text-xs mt-1 opacity-60">Mission control that's versioned, grep-able, and agent-friendly</div>
</div>

<div class="border border-gray-400/30 bg-gray-500/10 rounded-lg p-4">
<div class="font-bold text-sm">Best Sandbox Environment</div>
<div class="text-xs mt-1 opacity-60">Isolated, reproducible dev environments for agents</div>
</div>

<div class="border border-gray-400/30 bg-gray-500/10 rounded-lg p-4">
<div class="font-bold text-sm">Formal Verifiable & Executable Spec</div>
<div class="text-xs mt-1 opacity-60">Lean4 — proofs as harness, not just tests</div>
</div>

<div class="border border-gray-400/30 bg-gray-500/10 rounded-lg p-4">
<div class="font-bold text-sm">Zero-trust Context Management</div>
<div class="text-xs mt-1 opacity-60">Fine-grained control over what agents can see and access</div>
</div>

</div>

---
layout: quote
---

# You Still Need the Creative Part

> "The best buildings result from the symbiotic relationship between the architect and the engineer
> where the engineer is the **objective inventor** and the architect the **creative input**."

— Peter Rice
