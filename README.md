# I build provenance-native systems for human–agent software.

Software that records evidence as it runs — so humans and agents can **inspect, replay, challenge, and safely act on what happened**.

By day, I am a **Senior Engineer at AWS**, building production generative AI applications. Outside work, I create open-source frameworks and research a question I have followed throughout my career:

> How can a complex system make its internal state and decisions legible by construction?

My current answer is one design rule:

> **Record the path at the moment it happens. Never reconstruct it afterward.**

**[Explore the ecosystem](https://footprintjs.github.io/)** · [Product view](https://footprintjs.github.io/?view=product) · [Technical view](https://footprintjs.github.io/?view=technical)

---

## What I am building now

The [footprintjs ecosystem](https://footprintjs.github.io/) applies the same recording rule to four different journeys.

| Journey | System | What becomes legible |
|---|---|---|
| Backend execution | [FootPrint](https://github.com/footprintjs/footPrint) | Reads, writes, branches, state changes, and the cause of any output |
| Agent reasoning | [AgentFootprint](https://github.com/footprintjs/agentfootprint) | Context injections, model calls, tool decisions, cost, and failure causes |
| Application interaction | [HACI Footprint](https://github.com/footprintjs/hcifootprint) | The capabilities an agent can currently use, through the signed-in user's real application boundary |
| Exploratory analysis | [VizFootprint](https://github.com/footprintjs/vizfootprint) | Every human and agent path, including abandoned branches and statistical obligations |

Six ecosystem packages are published on npm; VizFootprint is the pre-alpha research system extending the same idea to mixed human–agent visual analysis.

---

## The systems

### [FootPrint](https://github.com/footprintjs/footPrint) — execution provenance

Business logic becomes a directed graph whose execution record is created inline as the graph runs.

- Transactional and patch-based state, parallel fork/join, streaming, checkpoints, and time-travel replay
- Variable-first backward slicing: ask why a value exists and walk it back to the reads, writes, and decisions that produced it
- Auto-generated tool descriptions and causal traces an LLM can reason over

**npm:** [footprintjs](https://www.npmjs.com/package/footprintjs)

### [AgentFootprint](https://github.com/footprintjs/agentfootprint) — context provenance

An agent framework that treats context assembly and every model or tool decision as typed, inspectable evidence.

- Two primitives and four compositions for building agent workflows
- Typed context injections across system, message, and tool slots
- Context-bug localization: shortlist the context that changed an answer, remove it, replay, and confirm the cause
- Causal memory, multi-provider support, MCP integration, pause/resume, and a scored “why this tool?” view

**npm:** [agentfootprint](https://www.npmjs.com/package/agentfootprint) · [Live playground](https://footprintjs.github.io/agent-playground/)

### [HACI Footprint](https://github.com/footprintjs/hcifootprint) — human and agent computer interaction

Turns a web application's interaction surface into a typed, traversable skill graph an agent can plan over and use through MCP.

- Starts read-only in guide mode: the agent observes before it acts
- Preserves permissions, preconditions, confirmation gates, and the signed-in user's boundary
- Makes an existing application agent-operable incrementally rather than replacing its UI

**npm:** [hcifootprint](https://www.npmjs.com/package/hcifootprint) · [Watch the 37-second demo](https://youtu.be/vx5amF94ipI)

### [VizFootprint](https://github.com/footprintjs/vizfootprint) — exploration provenance · pre-alpha

Records exploratory visual analysis as an append-only, parent-linked trail shared by humans and agents.

- Every interaction becomes a cause-tagged commit; moving back and acting creates a branch without erasing the old future
- Named paths can be compared, replayed, adopted, archived, and restored
- Statistical memory remains attached to the complete analysis history, including abandoned paths

**Read:** [The Trail Pattern](https://footprintjs.github.io/blog/the-trail-pattern/)

### Evidence lenses

| Lens | Purpose |
|---|---|
| [Explainable UI](https://github.com/footprintjs/explainable-ui) | Flowchart traversal, time travel, and causal rewind for FootPrint |
| [AgentFootprint Lens](https://github.com/footprintjs/agentfootprint-lens) | Messages, prompts, tools, decisions, and cost on one execution cursor |
| [Thinking UI](https://github.com/footprintjs/agentThinkingUI) | Scrubbable replay of an agent's reasoning, evidence, and tool alternatives |

---

## Research

### Visible Reasoning

My research thesis is that reliable agent transparency should come from **recorded decision evidence owned by the framework**, not from asking a model to narrate or judge its own reasoning.

- **Chain-of-thought:** another model-generated claim about what happened
- **LLM-as-judge:** a second model introduces another trust boundary
- **Recorded decision evidence:** the runtime owns the trace; humans, smaller models, debuggers, and training pipelines consume the same evidence

*Visible Reasoning: User-Facing Decision Transparency for Generative AI Systems* — **HCI International 2026**, LNCS 16745, pp. 3–21, Springer · [DOI](https://doi.org/10.1007/978-3-032-30849-8_1)

Earlier work: *Bridging UI Design and Chatbot Interactions* — **HCI International 2025**.

---

## Writing

- [Enterprise Gen AI Application](https://www.linkedin.com/newsletters/enterprise-gen-ai-application-7270536688406802432/) — practical patterns for production generative AI
- [The Flowchart Pattern](https://footprintjs.github.io/blog/the-flowchart-pattern/) — when the drawing becomes the program
- [The Trail Pattern](https://footprintjs.github.io/blog/the-trail-pattern/) — when the record becomes the map
- [Visible Reasoning](https://footprintjs.github.io/blog/visible-reasoning/) — deterministic evidence for human-facing agent transparency

---

## How I got here

| Stage | What changed |
|---|---|
| **HCI and visual analytics** | Through my PhD work and [Weave](https://github.com/sanjay1909/WeaveCoreJS), I focused on making complex data-visualization sessions understandable to people. |
| **State architecture** | StateTree moved the question underneath the interface: if state changes drive the experience, those transitions should be inspectable, comparable, and reversible. |
| **Production engineering** | Building large software systems made the same problem operational: logs describe fragments, but they rarely preserve the causal structure needed to explain a result. |
| **Execution provenance · 2025** | FootPrint made backend code the graph itself, so execution could record its own reads, writes, branches, and causes. |
| **Agent context provenance · 2026** | AgentFootprint and Visible Reasoning extended that structure to context assembly, model calls, tool choices, and counterfactual replay. |
| **Human–agent application interaction · 2026** | HACI Footprint moved from explaining an agent to defining what it can safely see and do inside a real application. |
| **Exploration provenance · 2026** | VizFootprint broadened the work from planned execution to open-ended human and agent exploration, where the record becomes the map. |
| **Now** | I am focused on **provenance-native human–agent systems**: software that creates trustworthy evidence during execution and interaction, then exposes the right lens for the person or agent examining it. |

The projects changed. The underlying question did not:

> **How can software make what happened — and why — available as trustworthy evidence?**

---

**PhD in Computer Science, UMass Lowell** · **Senior Engineer at AWS** · Dallas, TX

[LinkedIn](https://linkedin.com/in/sanjay1909) · [Medium](https://medium.com/@sanjay1909) · [GitHub organization](https://github.com/footprintjs)
