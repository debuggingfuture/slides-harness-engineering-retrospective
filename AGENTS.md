# Agent Instructions

Overall flow for Presentations
- We will share our journey adapting to agentic development and Harness Engineering
- Introduce Stripe & OpenAI as reference
- Base on 8 perspectives
  - talk about each experiments / learnings we have
- Outro - "FOMO" and ares to explore

Top Banner
- Always show which section you're in, and support navigation to corresponding section.
- For Section 2, the top banner should show "Framework"
- For Section 3, the top banner should show 2 rows of 8 perspectives
-    highlight which part of perspective it is talking about


## Table of Contents


### Section 1: Background
- **Engineering Harness on the fly** (title)
  - Title slide, "Adapting to Harness Engineering in a startup"

- **WTF is Harness Engineering** (quote)
  - Mitchell Hashimoto quote on what is harness Engineering
  - "It is the idea that anytime you find an agent makes a mistake, you take the time to engineer a solution such that the agent never makes that mistake again. "

- **Background**
  - **Project Nature**
    - Widget at Media site of 150M+ Global Monthly Visits
    - High Compliance+Security Requirement
    - Scalability & Performance 
   - **Tech Stack**
    - Edge: CF Workers, D1, Durable Objects, Queues
    - DevOps: Pulumi, Github Actions, Nx CLoud
    - Backend: PostgreSQL, Kafka, Flink
    - Application: TypeScript, Effect-TS
    - Data: Rudderstack, PostHog
    - CQRS architecture
    - Monorepo
    - effect-ts powered strong types, OTel observability, DI via Layers


- **Project Timeline**
  - 6 milestones (3 click groups): Sonnet 4.5 (Sep 25) → Kickoff (Oct 25) → Prototyping (Jan 26) → Opus 4.6 (Feb 26) → Pivot/Integrations (Feb 26) → Production/Beta (Mar 26)
  - Claude Code usage: Pro Plan → Premium Seat → AWS Bedrock
  - Team: 1 Designer, 3 Principal Dev (12yr+), 1 Senior FE
  - Vincent: somehow taken PM+DevSecOps+Tech Lead role, ~30-50 PRs / week  | ~100 messages/day to Claude
  - [commits.jpg](commits.jpg)


- **Different Mental Models**
  - Two-column with images: Individual (steering the car) vs Team (steering the factory)
  - Personal workflow with Claude Code vs assembly line with swarm of agents

### Section 2: Framework


- **Stripe's Coding Agent Workflow - Minions**
  - Source: [https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents)
  - Flow: Slack prompt → Slackbot triage → CF Sandbox → GitHub Actions → Job completes → Slackbot responds with PR
  - [minion.png](minion.png)

- **OpenAI's Approach: Harness Engineering**
  - Source: openai.com/index/harness-engineering
  - 0 lines manually written, AGENTS.md as map, enforce invariants not implementations
  - ~1M LOC in 5 months, 3 engineers, 1,500+ PRs, 6+ hour agent runs

- **Framework: 6+2 Perspectives of Harness Engineering**
  - 2 rows of 6 perspectives with colored cards, progressive v-click reveal
  - Architecture & Taste, Agent Legibility, Repo as System of Record, Application Legibility, Increasing Autonomy, Entropy & Garbage Collection
  - extra row of 7. human legibility and 8.agility


### Section 3: Our Take

- **Where Do We Stand?**
  - Tag: Increasing Autonomy
  - Spectrum bar: Human-assisted → Fully autonomous
  - Markers: Stripe (~15%, agent as assistant), Us (~35%, humans write code with agents), OpenAI (~85%, agent as engineer)


- Human-first
  - Design
  - Analytics Dashboard
  

- **Perspective 1: Architecture & Taste**
  - On Architecture
    - Great ROI - Team spent 1st month on discussions and write them down
    - Footer links to GitHub Spec Kit
    - opionionated and mostly NOT from agents - cqrs, effect-ts, changeset, signoz etc

 - Style Guide
   - Took multiple iterations to promot (correct) effect-ts usage
   - `._tag`
   - simple pre-pr lint hook (biome) work best, keep agent loop fast
 - At early phrase (4.5) and limited implementation, Not holistic enough to follow the DDD, CQRS patterns
 - Hallucination: unused OR non-isomorphic packages

- **Perspective 2: Agent Legibility**

  - Content: TODO

- **Perspective 3: Repo as System of Record**
  - We started out with Github SpecKit
  - Github issues - Created by Human
  - Content: TODO
  - Git based


 - specs become executable, multi-step refinement, clarify before building


- **Perspective 4: Application Legibility**
  - Template: badge + subtitle + two-column (What We Did / Learnings)
  - Content: TODO

  - Designer Developer commiting at storybook
    - Challenges: 
      - Git branch conflicts
      - Lack of Source of truth at Figma


- **Perspective 5: Increasing Autonomy**
  - Template: badge + subtitle + two-column (What We Did / Learnings)
  - We don't want full autonomy, but direct scarce human attention to focus what matters
- - **Autonomy**
  - Gatekeep for compliance and stakeholders requirement take human to digets
  - We Did
    - CI self-heal
    - Monitoring
    - self-status update

    <!--- Perf Trigger-->


- **Perspective 6: Entropy & Garbage Collection**
  - Problem: AI slop is real
  - Passing zero-shot output with no review & 15 action items to your colleague
  - Learnings
    - Architecture audit & review
  - Learning: Firewall not working
    - Original: Start with firewall - Notion by Human, Spec by Agents
    - Reality: 
      - Notion & Notion AI are both pretty crap 
      - Everything is written by Agent anyway
      - Github based specs written by Agent are much better actualyl  
      - Lack of Sourth of truth (Internal & External)
      - Talk to codebase: Active Gap analysis / Ask for metric definition 
    
  - Learning: Remove Dead code is important to avoid hallucination
    - `gh` cli is subpar


- **Perspective 7: Human Legibility**


  - **Know what your ship**?
    - Tech: Gaps in architecture, mock implementations
    - Discussion on prototype 


- **Perspective 8: Agility**
  - Be Agile / No best practices / everyone is learning
  - Tags: Application Legibility, Entropy & Garbage Collection
  - Back to basics: Quote agile manifesto
  - Stay True: Need of Deep Think. Tailor Featureset
  - What we did: Spawn Opencode/Slackbot next day after reading Stripe articles

- **Known Miss Out**
 
  - UX QA: No agentic workflow to do QA on CLS, speed, reproduce & record bugs etc
  - SLO: setup SLO (stub)





- **Create Custom CLI**
  - deterministic, better interpolation vs Bash
  - effect-ts based cli
    - cicd (workaround GH action YAML)
    - access provision
  
## Section 4: 

  - High level "Known miss outs" for things to experiment
  - "Unknown missouts" to highlights things we're not sure if industry has an answer

  - For more market operations
  - Lean4 spec  
  



- Challenge: AI Sandbox
  - Dagger - slow
  - ~ application legibility

- Agent to consolidate specs



- Human as bottleneck
  - less familar with browser testing stack
  
  
  

- **Unknown Miss Out**
  - Local-first Notion alternative for collaboration?
  - Sandbox environment (stub)
  
  - Type systems 


- **Case Study: CI Pipeline**
  - Two-column: Human (deploy staging, verify health, update arch diagrams) vs Agent (create pre-prod branch, run tests, deploy, merge PR)
  - Human = taste & verification, Agent = execution & mechanics

- **Reflection: How Much Do I Know About the Systems?**
  - Less Familiar Stacks: CF Queues, Effect-TS patterns, SigNoz, CF Durable Objects
  - Code Paths I Didn't Know Existed: Kafka rebalance, Flink checkpoint recovery, D1 batch transactions, Pulumi dynamic providers

- **Improving with Claude Code**
  - Tags: Entropy & Garbage Collection, Repo as System of Record
  - Personal: `/insights` command for usage patterns, habits, productivity
  - Team: hard to aggregate, sensitive data, no safe sharing, manual knowledge sharing gap

## Appendixx

- **Datadog: Deterministic Simulation Testing**
  - Source: datadoghq.com/blog/ai/harness-first-agents
  - Verify invariants not lines, DST catches bugs in ~5s, verification pyramid (TLA+ → DST → model checking → proofs → telemetry)
  - Scalability inversion: agents generate specs/harnesses/proofs
  - Results: redis-rust 87% mem reduction, Helix 93% disk throughput, 5x lower latency vs Kafka



### Application Legibility

- Huge unlock

### Section 4: Personal Reflection

- In vs out of loop
  - reactive
  -  
  
  
- can't stop working
  -  must be dumb
  
  
  
  ccli
  
  projects skills
  - cli


- Ownership-first
  - AI Slop is very real
- Concensus
  - Meetings notes v Signoffs
  
  
- **When autonomy is desired**



- **Overall**
  - Human drives architecture, agents excel at implementation
  - Architecture held up as complexity grew
  - Harness engineering amplifies human intent, doesn't replace it

- **Stay in the Flow** (quote)
  - Mitchell Hashimoto quote on letting agents work while you do other tasks
  - Disable notifications, stay in deep work, invest mistakes into guardrails


## Slidev Conventions

- Slides are separated by `---`
- Frontmatter at top of file configures theme, transitions, etc.
- `v-click` / `<v-clicks>` — progressive reveal on click
- We should limit each slides to have usually only 2 clicks, at most 3
- `v-click="N"` — group elements to reveal together on click N
- Two-column layouts use `<div class="grid grid-cols-2 gap-8">` with Tailwind



## Slide Template

The presentation follows a consistent template for perspective slides:

1. Title heading
2. Colored badge (`<span>` with border/bg classes)
3. Subtitle line (`.text-sm.opacity-60`)
4. Two-column grid with section headings and `<v-clicks>` lists

## Commands

- `pnpm dev` — start dev server with live reload
- `pnpm build` — build static SPA
- `pnpm export` — export to PDF

## Relevant Links

The presentation quote and link to below

- https://mitchellh.com/writing/my-ai-adoption-journey#step-2-reproduce-your-own-work
- https://mitchellh.com/writing/my-ai-adoption-journey#step-5-engineer-the-harness
- [Minions: Stripe’s one-shot, end-to-end coding agents](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents)
- [OpenAI: Harness Engineering](https://openai.com/index/harness-engineering/)
- [GitHub Spec Kit](https://github.com/github/spec-kit)
- [Datadog: Harness-first Agents](https://www.datadoghq.com/blog/ai/harness-first-agents/)
- Agile Manifesto: https://agilemanifesto.org/
