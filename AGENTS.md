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


For Section 3
When we talk about each perspective, shows the relevant principle from openai

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
  - Claude Code usage: Pro → Team x Premium → AWS Bedrock
  - Team: 1 Designer, 3 Principal Dev (12yr+), 1 Senior FE
  - Vincent: somehow taken PM+DevSecOps+Tech Lead role, ~30-50 PRs / week  | ~100 messages/day to Claude
  - [commits.jpg](commits.jpg)


- **Different Mental Models**
  - Two-column with images: Individual (steering the car) vs Team (steering the factory)
  - Personal workflow
    - Keep prompting & customizing
  - Assembly line 
    - Legit, aligned product when evyeryone commanding swarm of agents

### Section 2: Framework


- **Stripe's Coding Agent Workflow - Minions**
  - Source: [https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents)
  - Flow: Slack prompt → Slackbot triage → CF Sandbox → GitHub Actions → Job completes → Slackbot responds with PR
  - [minion.png](minion.png)

- **OpenAI's Approach: Harness Engineering**
  - Source: openai.com/index/harness-engineering
  - Internal Tool build by Codex
  - Greenfield (empty repo)
  - Humans steer. Agents execute - 0 lines manually written
  - ~1M LOC in 5 months, 3 engineers, 1,500+ PRs, 6+ hour agent runs

- **Framework: 6+2 Perspectives of Harness Engineering**
  - 2 rows of 6 perspectives with colored cards, progressive v-click reveal
  - Architecture & Taste, Agent Legibility, Repo as System of Record, Application Legibility, Increasing Autonomy, Entropy & Garbage Collection
  - extra row of 7. human legibility and 8.agility


### Section 3: Our Take

- **Where Do We Stand?**
  - Spectrum bar: Human-assisted → Fully autonomous
  - Markers: Stripe (~15%, agent as assistant), Us (~40%, Human prompt & review), OpenAI (~85%, agent as engineer)


- Human-first
  - Design
  - Analytics Dashboard
  

- **Perspective 1: Repo as System of Record**
  - "Executable Spec in Repo"
  - We started out with Github Spec-Kit
     - specs lives in repo. executable, multi-step refinement
     - `/clarify` is interesting & prompt you to think
  - > It rots instantly. It's hard to verify
  - > give Codex a map, not a 1,000-page instruction manual
    - Context problem & Drift -> Drop SpecKit, consolidate into markdowns
  - Git(Hub) based sync & collab
    - lightweight local markdown files
    - Both Human & Agents create Github issues for tracking
  - Omniscient Agents who can Time travel  
    - "PR#123 tried A but failed, lets dig deeper"
    - "This bug is on master too not due to our changes"
    - "Fix these patterns for files we changed since v1.0.3"
  - Prefer small PRs, pretty master
    - 1 lint error taxing 15 agents
  - Out of Repo
    - Custom scrappers + Indexed docs 
    - custom CLAUDE.md / skills

- **Perspective 2: Architecture & Taste**
  - On Architecture
    - Early Phrase
      - Team spent 1st month on discussions and write them down (Great ROI)
      - opionionated and mostly NOT from agents -  monorepo, effect-ts, changeset, signoz etc
      - hexagonal, CQRS, DDD -> strict boundary & predictable structure 
      - Prototype -> Add "Constitution" (Invariant)
      - Naming convention -> Type-based Schema & Interfaces, working code
    - Later phrase
      - Consoldiate docs 
      - Agents come up with design for pipeliness
 - Style Guide
   - Took multiple iterations to promot (correct) effect-ts usage e.g. `._tag`
   - Concrete Examples to follow through
   - Limiting Hooks:  keep agent loop fast e.g. simple pre-pr lint hook (biome) 
 - At early phrase (Sonnet 4.5) and limited implementation, Not holistic enough to follow the DDD, CQRS patterns
 - Hallucination: unused OR non-isomorphic packages
 
   - What's in:
     - saga / cqrs patterns, kafka schemas state diagram 
     - data pipeline, marketing stack


- **Perspective 3: Agent Legibility**
  - Setup: Slack, Notion MCP, Figma, Granola (Meetings)
  - What we tried
    - Figma MCP (Kind of work)
    - Designer Developer commiting at storybook
      - Challenges: 
        - Git branch conflicts
        - Lack of Source of truth at Figma
    - Feed "Org Chart" / Contacts to Agent
  - We (I) want only **curated** context for agent
  - Support Tagging Slackbot to create draft PR (via OpenCode)
  
  - Learnings: Firewall not working
    - Original: Notion by Human, Spec by Agents
    - Reality: 
      - Notion & Notion AI are both pretty useless 
      - Everything is written by Agent anyway
      - Github based specs written by Agent are much better actualyl  
      - Lack of Sourth of truth (Internal & External)
  - Confirmation bias


- **Perspective 4: Entropy & Garbage Collection**
  - Problem: AI slop is real
  - Passing zero-shot action items to your colleague
  - Measures
    - [Auto] Daily update on `STATUS.md` (OpenCode@GHA)
    - [Auto] PR to issue and PR Reviews  (OpenCode@GHA)
    - [Auto] Weekly Architecture Audit  (OpenCode@GHA)
    - Comment to Agentic scrum master on Slack
  
    - [Manual] Scheduled Agentic Architecture audit & review on Github Action
      - Talk to codebase: Active Gap analysis / Ask for metric definition 
    - Spec Reviews and Rewrite    
  - Learning: Remove Dead code is important to avoid hallucination



- **Perspective 5: Application Legibility**
  - Provide Observability to Agent = Step Function increae in productivity

  - **Deployment CI Pipeline**
    - (Typical Challenges)
      - Complexity: 3 Env x 7-9 Components (AWS ECS, Kafka connectors) x Secret Management
      - IaC (Pulumi), Github Acitons - Circular Dependencies, State drift, IAM design etc
    - Agents to the rescue
      - Deploy to Staging -> Point agent to failing build, fix manually & add Guidelines, e2e, deployment (soak), acceptance Tests
      - Deploy to prod -> Create `pre-prod` branch, agent PR, merge, deploy, validate CI

 - **Production Validations/Monitoring**
   - Provision Pulumi ESC for Read-only environment
   - Agent: build out k6 test suite
   - SigNoz, PostHog: iterate metrics, alerts, dashboard with agents
   - Claude Skill to torubleshoot / Scheduled OpenCode@GHA -> Slack 


  - **Custom CLI Helped**
    - deterministic, better interpolation vs Bash
    - effect-ts based cli
      - cicd (workaround GH action YAML)
      - access provision
    
  - **#Missout**
    - Integration Tests/ Local Dev**
      - Challenge:
        - Dagger - slow & not really helping
    - UX QA: No agentic workflow to do QA on CLS, speed, reproduce & record bugs etc
    - (Did not use Chrome Dev Tools via CDP/MCP/agent-use )
    - SLO: setup SLO (stub)
    
    
- **Perspective 6: Increasing Autonomy**  
  - We don't want full autonomy
      - Gatekeep for compliance and stakeholders requirement take human to digest
  - What we want
    - direct scarce human attention to focus what matters (a.k.a stay in the flow)
    - Avoid human being the bottleneck  
  - We Do have
    - Auto PR Reviews 
    - CI self-heal
    - Monitoring
    - self-status update
  - We struggle
    - Auto sprint planning
    - Piping all Slack convo as context
    - Human being blocker 
      - my misunderstadning in pulumi stack wasted agent cycles 
      - Dev not familar with latest Browser stack
  - We don't have
    - Auto-merge PRs 
    - CD to prod 
    - Auto Feature base on PostHog usages

 
  
- **Perspective 7: Human Legibility**

  - **Novel problem: Know what you ship**?
    - Background
      - Pace Faster than ever
      - Agent shipped with stack you unfamilar with
    - Challenges
      - Gaps in architecture, mock implementations
    - **What matters**
      - Branch convention, Code Ownership still matters 
      - Custom CLI helped 
      - Yes I still have to learn!
      - Conscious on what I can live with

  - **Improving with Agents**     
    - Document and Challenge both thinking process and solution
    - high signal-to-noise Prompt Templates (e.g. PR review)
    - Create well-defined skills and prettified CLIs 
    - Personal: `/insights` command for usage patterns, habits, productivity
    - Team:
       - Challenges: Limited tools (e.g. Claude). Involves sensitive data
       

- **Perspective 8: Agility**
  - Tagline
    - "Everyone is learning. Ship Working software and respond to change."
  - Be Agile / No best practices
  - Back to basics: Quote agile manifesto
    - Individuals and interactions over processes and tools
    - Working software over comprehensive documentation
    - Customer collaboration over contract negotiation
    - Responding to change over following a plan
  - Stay True: Need of Deep Think. Tailor Featureset
  - What we did: Spawn Opencode/Slackbot next day after reading Stripe articles


## Section 4: Reflections & Outro

 - **Excited, Overwhelmed, Burn out, Confused**
 
  - When is Autonomy Desired?
  
  - When to remove human as bottleneck?
 
  - Which part of software are "malleable"? 
   
  - How to be Ownership-first for each role? PM, Designer
  
  - Agent boosted my productivity but I'm not sleeping.. What's wrong?

  - Tools are free. What Next should I build?
    
  
  - **FOMO**
    - Local-first Notion alternative for mission control?
    - Best Sandbox Environment
    - Formal Verifiable & Executable Spec (Lean4)
    - Zero-trust context management?

  
- **That's the Engineering part**

  - You still need the creative part

  - Quote from Peter Rice

    >  best buildings result from the symbiotic relationship between the architect and the engineer where the engineer is the objective inventor and the architect the creative input.
  


## Appendix

- **Datadog: Deterministic Simulation Testing**
  - Source: datadoghq.com/blog/ai/harness-first-agents
  - Verify invariants not lines, DST catches bugs in ~5s, verification pyramid (TLA+ → DST → model checking → proofs → telemetry)
  - Scalability inversion: agents generate specs/harnesses/proofs
  - Results: redis-rust 87% mem reduction, Helix 93% disk throughput, 5x lower latency vs Kafka



---

## Slidev Conventions

- Slides are separated by `---`
- Frontmatter at top of file configures theme, transitions, etc.
- `v-click` / `<v-clicks>` — progressive reveal on click
- For animation, We should limit each slides to have usually only 1 clicks, at most 3
- `v-click="N"` — group elements to reveal together on click N
- Two-column layouts use `<div class="grid grid-cols-2 gap-8">` with Tailwind
- Quotes (`>`) should be plain markdown blockquotes — never wrap them in colored boxes (`border-*`, `bg-*`). Ensure enough gap between quotes
- Avoid repeating the same or similar phrases twice on one slide — if the title says it, the bullets shouldn't restate it



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
- [Malleable Softare](https://www.inkandswitch.com/essay/malleable-software/#our-goal-malleable-software)



---
  - Metaphor: Architect vs Structural Engineer
  

Destination
