# I build developer abstractions that make enterprise systems AI-readable.

By day, I'm a **Senior Engineer at AWS** building production generative AI applications.  
Outside work, I create open-source tools and write about the hard problems most teams skip when shipping enterprise AI.

---

## What I'm building

### [FootPrint](https://github.com/footprintjs/footPrint) — *The flowchart pattern for backend code*

Business logic becomes a directed graph that produces **causal traces an LLM can reason over**.

- 7 flow patterns · transactional state · PII redaction · auto-generated tool descriptions
- 6 modular libraries: `memory` · `builder` · `scope` · `engine` · `runner` · `contract`
- Parallel fork/join · streaming · patch-based state · time-travel replay

```
npm install footprintjs
```

### [agentfootprint](https://github.com/footprintjs/agentfootprint) — *The explainable agent framework*

Built on FootPrint. Design your agent, watch it run, verify it wasn't hallucinating.

- 6 agent patterns: LLM Call · Agent (ReAct) · RAG · Sequential · Parallel · Routing
- **Per-iteration evaluation**: `obs.explain()` → connected context + decisions + sources + claims
- Conditional behavior that activates based on accumulated state — not hardcoded if/else
- $0 test suite via `mock()` adapter · Anthropic · OpenAI · Bedrock · Ollama
- [Live Playground](https://footprintjs.github.io/agent-playground/) with time-travel across all observability tabs

```
npm install agentfootprint
```

---

## What I write about

**[Enterprise Gen AI Application](https://www.linkedin.com/newsletters/enterprise-gen-ai-application-7270536688406802432/)** — LinkedIn newsletter (320+ subscribers)

| # | Post | Core idea |
|---|------|-----------|
| 1 | **From Supply-Driven to Demand-Driven** | The chatbot should drive UX, not assist it |
| 2 | **Make Search the First Tool** | STAY/SWITCH + Focus Token protocol |
| 3 | **The Flowchart Pattern** | Making backend code self-explainable for AI |

---

## Research

**Bridging UI Design and Chatbot Interactions**  
Applying form-based principles (Submit/Reset → STAY/SWITCH) to conversational agents.  
Published at **HCI International 2025** · [Springer proceedings](https://scholar.google.com/citations?user=YOUR_ID)

**Visible Reasoning**  
A framework for deterministic LLM agent transparency — a "third paradigm" distinct from chain-of-thought and LLM-as-judge.  
Accepted at **HCII 2026** · Springer proceedings

---

## The thread connecting all of it

```
Weave (data vis sessions)
  → StateTree (state diffing)
    → FootPrint (execution graphs + causal traces)
      → agentfootprint (explainable agents — design, evaluate, monitor)
```

10+ years on one problem: **making the internal state of complex systems legible** to whoever needs to understand them — first humans, now AI.

---

**PhD in Computer Science, UMass Lowell** · Dallas, TX  
[LinkedIn](https://linkedin.com/in/sanjay1909) · [Medium](https://medium.com/@sanjay1909) · [Google Scholar](https://scholar.google.com/citations?user=YOUR_ID)
