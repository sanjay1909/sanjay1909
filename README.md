# I build developer abstractions that make AI systems explainable by construction.

By day, **Senior Engineer at AWS**, building production generative AI applications.
Outside work, I create open-source frameworks and write about the hard problems most teams skip when shipping enterprise AI.

---

## 10+ years on one problem

> Making the internal state of complex systems legible — first to humans, now to AI.

```
Weave  ─►  StateTree  ─►  FootPrint  ─►  agentfootprint  ─►  hcifootprint
(data vis  (state         (execution    (context            (same
 sessions)  diffing)       graphs +       engineering,        legibility,
                           causal         abstracted;         pointed at the
                           traces)        decision            interaction
                                          evidence            surface — apps
                                          as a cache)         agents can
                                                              operate)
```

Each step abstracted one more thing the previous step did by hand.

---

## What I'm building

### [FootPrint](https://github.com/footprintjs/footPrint) — *The flowchart pattern for backend code*

Business logic becomes a directed graph that produces **causal traces an LLM can reason over**.

- 7 flow patterns · transactional state · PII redaction · auto-generated tool descriptions
- 6 modular libraries: `memory` · `builder` · `scope` · `engine` · `runner` · `contract`
- Parallel fork/join · streaming · patch-based state · time-travel replay
- **Variable-first backward slicing** — ask *"why is score N?"* and walk the variable back to its birth · pause/resume checkpoints across servers

```bash
npm install footprintjs
```

### [agentfootprint](https://github.com/footprintjs/agentfootprint) — *Context engineering, abstracted*

The autograd-shaped abstraction for LLM apps. Built on FootPrint. You describe injections; the framework evaluates triggers, composes slots, and observes every decision as a typed event.

- **2 primitives** (`LLMCall` · `Agent`) + **4 compositions** (`Sequence` · `Parallel` · `Conditional` · `Loop`)
- **1 Injection primitive**, 4 typed factories (`defineSkill` · `defineSteering` · `defineInstruction` · `defineFact`) targeting 3 slots (system · messages · tools) under 4 triggers (always / rule / on-tool-return / llm-activated)
- **1 Memory factory** — 4 types × 7 strategies, including **Causal** (decision-evidence snapshots → cross-run replay, cheap-model triage, training data — three uses of the same recording)
- **47 typed observability events** across 13 domains · pause/resume across servers · multi-tenant identity · MCP integration
- **$0 dev** via `mock()` · 6 LLM providers (Anthropic · OpenAI · Bedrock · Ollama · Browser variants)
- **Context-bug localization** — when an agent answers wrong, pinpoint *which* injected context caused it (walk the trajectory, shortlist early culprits, confirm by replay) · a **"why this tool?"** scorer over every tool it could have picked
- [Live Playground](https://footprintjs.github.io/agent-playground/) — paste a trace, drag the time-travel slider

```bash
npm install agentfootprint
```

### [hcifootprint](https://github.com/footprintjs/hcifootprint) — *Apps agents can operate*

Turns a web app's interaction surface into a **typed, traversable skill graph** an LLM agent can plan over and act on — served over MCP, so the agent acts as the signed-in user through the app's own handlers.

- Adoption ladder starts **read-only** ("guide mode") — the agent observes before it acts
- Ships `llms.txt` for agent consumers · 281 tests
- A vanilla dress-shop becomes **agent-operable in three commits** ([demo repo](https://github.com/footprintjs/hcifootprint-demo))

**▶ [Watch the 37-second demo](https://youtu.be/vx5amF94ipI)**

```bash
npm install hcifootprint
```

### The ecosystem — six packages, all on npm

| Package | One line |
|---|---|
| `footprintjs` | Self-explaining flowchart engine for backend logic |
| `agentfootprint` | Context engineering + agent framework, built on FootPrint |
| `hcifootprint` | Web apps as typed skill graphs agents can operate |
| `footprint-explainable-ui` | Flowchart + time-travel + causal rewind on one timeline |
| `agentfootprint-lens` | Agent debugging with one time cursor |
| `agentthinkingui` | Scrubbable story replay + the why-this-tool rack |

Full graph → **[footprintjs.github.io](https://footprintjs.github.io/)**

---

## Visible Reasoning — the research thesis behind it

A framework for deterministic LLM-agent transparency. A **third paradigm** distinct from:

- **Chain-of-thought** — the agent narrates its own thinking (unverifiable; the narration is more LLM output)
- **LLM-as-judge** — a second agent grades the first (recursive trust problem)
- **Recorded decision evidence** — *the framework owns the trace*. Every decision the flowchart makes is a typed event; humans, cheaper LLMs, and training pipelines all consume the same recording.

*Visible Reasoning: User-Facing Decision Transparency for Generative AI Systems* — published at **HCI International 2026** · LNCS 16745, pp. 3–21 · Springer, Cham · [doi:10.1007/978-3-032-30849-8_1](https://doi.org/10.1007/978-3-032-30849-8_1).
Earlier work — *Bridging UI Design and Chatbot Interactions* (form-based principles → conversational agents) — published at **HCII 2025**.

---

## Writing

**[Enterprise Gen AI Application](https://www.linkedin.com/newsletters/enterprise-gen-ai-application-7270536688406802432/)** — LinkedIn newsletter, 320+ subscribers · **[The Trail Pattern](https://footprintjs.github.io/blog/)** — the footprintjs ecosystem blog.

| # | Post | Core idea |
|---|------|-----------|
| 1 | From Supply-Driven to Demand-Driven | The chatbot should drive UX, not assist it |
| 2 | Make Search the First Tool | STAY/SWITCH + Focus Token protocol |
| 3 | The Flowchart Pattern | Making backend code self-explainable for AI |

---

**PhD in Computer Science, UMass Lowell** · Dallas, TX
[LinkedIn](https://linkedin.com/in/sanjay1909) · [Medium](https://medium.com/@sanjay1909) · 
