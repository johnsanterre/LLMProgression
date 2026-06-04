# KEYNOTE INDEX — *Managing the Context Window* (Restructured)

**Working Title options:** *"Context Is the New Contract"* · *"Engineering the Window"* · *"What You Feed the Machine"* · *"The Context Engineers"*

**Central trend (the talk's spine):** The industry has moved from **model-building → prompt engineering → context engineering.** The center of gravity is no longer the model — it's *what context you put in front of it, and what you keep out.* Managing the context window is the defining discipline of this era.

**The thesis that ties it to the old notions:** *Managing context IS engineering trust.* And the cautious architect — who already thinks in constraints, boundaries, and what-belongs-where — is the person this era was built for.

**Through-line (one sentence):** Context is the new bottleneck; whoever engineers it — at the model, the self, and the organization — engineers trust, and your caution is the exact superpower that discipline rewards.

**Speaker:** PhD in AI · NASA scientist · UC Berkeley professor. Tone = engineering authority + warm peer.

**Audience:** CTO/CIO division of 600+ in regulated, zero-margin enterprise Architecture/Data/Engineering, paralyzed by "fear of doing something wrong."

**Mission:** Permission to innovate — by showing the whole industry is converging on context management, and that their architectural discipline is the native skill of that convergence.

> **CENTRAL NOTIONS WE KEEP** (re-skinned through the context lens): regulation = codified trust · the bee ecology / cold bees · the anti-vibe-coding architect + agentic harness · trust the system not the machine · the 2-hour sandbox / temporal interlock · author → director · the cautious architect is the superpower.

> **THE ORGANIZING METAPHOR — context at three scales:**
> 1. **The model's** context window (technical: RAG, MCP, harnesses, guardrails, evals)
> 2. **The engineer's** context window (cognitive: attention, timeboxing, up the stack)
> 3. **The organization's** context window (cultural: codified trust, the ecology of skeptics)

---

## OPENING — The Trend Hiding in Plain Sight — *~3.5 min*
- Personal arc, compressed: film/video → digital photography → AI before "data science" existed. Every transition was learning to trust a new kind of context (the Amazon credit-card moment).
- **Name the trend out loud:** we went model-building → prompt engineering → **context engineering**. The window — not the model — is where the work now lives.
- **HERO VISUAL — "The Road to Context Engineering" (`assets/context-evolution.png`):** a clean vertical stack (no dates — the axis is *control*, not time), each rung tagged STATIC or DYNAMIC — Single Prompt [STATIC] → RAG/Retrieval [DYNAMIC] → Tool Calling [DYNAMIC] → Agentic Flows [DYNAMIC] → Context Engineering [STATIC + DYNAMIC]. *(No hard years on purpose: the progression overlaps and static context bookends the whole story — it's both the oldest move and the foundation of the frontier synthesis, so a strict timeline would mislead.)*
- **THE RECONCILIATION (the key beat — frame it as one question):** every era is just a new answer to *"what's in the window when the model runs, and who put it there?"* Two axes underneath:
  - **Static vs. Dynamic** — is the context *fixed* ahead of time, or *assembled* at runtime?
  - **Human- vs. Model-controlled** — who decides what goes in?
  - Walk it: (1) **Single call** — you *fix* the context by hand [static/human]. (2) **RAG** — a pipeline retrieves docs to *build* it [dynamic/human-built]. (3) **Tool calling** — the *model* fetches its own context mid-flight [dynamic/model]. (4) **Agentic flows** — agents' *responses become context* for the next step [dynamic/multi-agent]. (5) **Static context files** (CLAUDE.md, skills) — *declare* durable context once, reused every run [static again, but declarative + reusable].
  - **The punchline:** the journey loops back to static on purpose — because these techniques **didn't replace each other, they became LAYERS.** The frontier stack *fixes* the stable parts and *manages* the volatile parts.
- **THE BRIDGE to Movement II:** the staircase (the trend over *time*) and the harness pyramid (the trend as *architecture*) are the **same story from two angles** — durable static context at the foundation, dynamic tools/agents above. "Context engineering" = orchestrating static + dynamic together — which is exactly how a cautious architect already thinks: *pin what must be stable, govern what must adapt.*
- **Promise:** the discipline this era rewards is the one you already have — bounding what's admissible.

---

## MOVEMENT I — Context Is the New Unit of Trust *(org-scale context)* — *~6 min*
- **Reframe regulation:** a regulated space is just *governance over what context is admissible* — codified trust about what information may enter a decision.
- **Hero story — Hubble:** the model's "context" is bounded by physics and the researchers' lifetime of knowledge; trust is earned by fitting *their* context, not by speed. "Not regulated by a board — regulated by physics and a lifetime of work."
- **Aside (SVB):** propose → committee → auditor → compliance is a *context pipeline*; the checklist alone never was the trust.
- **Trend tie-in:** enterprises moving to RAG, walled gardens, and **MCP** — all the same move: controlling what context the model can see.
- **Landing:** Trust was always about governing context. We just have a new window to govern now.

---

## MOVEMENT II — The Ecology That Regulates Context *(the bees + the architect)* — *~7 min*
- **Bee ecology / cold bees (Strogatz):** the hive holds a stable internal context (temperature) through a *distribution* of set points. Cold bees are regulators, not failures.
- **The flip:** skeptics & architects = the regulators of your *organizational* context window — load-bearing, not blockers.
- **Personal hero story — the anti-vibe-coding architect:** his resistance forced me to build a deterministic **agentic harness** — literally context-window management: cut output variability to a fraction by controlling what the model sees and how its calls compose.
- **HERO VISUAL — "The Agentic Harness Stack" (`assets/harness-stack.png`, vendor-neutral):** a 7-layer vertical stack grouped into the **three control bands** (see KEY DISTINCTION below). *Show it, name the three bands, move on* (keep the movement light):
  - **Bottom band = Static Control Plane** (blue): persistent context files · symbol-level grounding · shareable setups → *pin what's stable.*
  - **Middle band = The Doorway** (teal): governed tool & data connections / **MCP** → *standardize access.*
  - **Top band = Agentic Harness** (orange): on-demand skills · hooks & triggers · parallel sub-agents → *govern what adapts.*
  - **The arc it makes visual:** beginners use the raw model; power users engineer the context around it = the **Author → Director** shift.
  - **Seeds a callback:** every Movement III guardrail (Wells Fargo Golden Set, FDA PCCP) is just an enterprise version of one of these bands.
- **Trend tie-in:** agentic harnesses, sub-agents, and context compaction are the cutting edge *beyond* raw prompting — layers of logic that curate context across many LLM calls.
- **Landing:** You don't convert skeptics — you engineer the context that earns their trust.
- *(REST BEAT after this story-driven movement.)*

> **KEY DISTINCTION — three layers of context control (borrow the architects' own control-plane mental model):**
> 1. **Static control plane = declarative governance ("fix").** Fixed, versioned, auditable: context files (CLAUDE.md), rules, policies, schemas, parameter-locked Terraform, guardrail/eval definitions. Doesn't change per run. *Defines the boundaries the system may operate within.* (This is what FDA PCCP is.) → *"What is permitted?"*
> 2. **Agentic harness = dynamic control plane ("manage").** Runtime orchestration around the model: per request, decides what context to assemble, which tools fire, how calls compose, when to retry/halt. *Manages the volatile context.* (This is what cut the architect's variability.) → *"Given the rules, what do we do this run?"*
> 3. **MCP = the connection protocol ("doorway").** Standardized interface between models and tools/data; the bus both planes rely on. Static plane governs *which* servers are allowed; the harness *uses* them at runtime. Collapses bespoke integrations into one governed, auditable doorway. → *"How does context get in/out, safely and uniformly?"*
>
> **The one-liner:** static control plane sets the rules → agentic harness acts within them → MCP is the governed doorway both rely on. In thesis language: **pin what's stable, govern what adapts, standardize the doorway.**
> **Maps to both visuals:** pyramid → context files (static plane) at the foundation, MCP servers (doorway) in the middle, hooks/skills/sub-agents (harness) at the top. Staircase → the STATIC rungs vs. DYNAMIC rungs, with MCP making the dynamic ones *governable* instead of chaotic.

> **ASSET NOTE:** final vendor-neutral slide = `assets/harness-stack.png` (7 layers grouped into 3 control bands). Source reference was the "Claude Code Harness Stack" (`assets/image-ea6b1d32-...png`), kept for provenance only.

---

## MOVEMENT III — We Trust the System Around the Window *(model-scale context)* — *~7.5 min (the spine)*
- **Brief bridge (the old Movement III, compressed to ~90 sec):** we already made this trade once — from the traceable single drop (logistic regression, IID, Naive Bayes — comforting fictions) to the **asymptotic stability of the whole ocean** (Argonne / "a model with 'random' in its name"). We didn't lose transparency; we moved it up a scale.
- **Reframe code:** code is *human-to-human context* about what a machine will do; the computer is the execution layer, and the LLM is a more capable, less deterministic one.
- **Industry guardrails as context engineering (brisk, not a lecture):** JPMorgan LLM Suite (walled-garden context) · healthcare auditor-agent eval loops (a second model checking the context) · Wells Fargo "Golden Set" (hard-halt on confidence drift) · FDA **Predetermined Change Control Plans** (bounding *permitted change*). → **TDD → Eval-Driven Development.**
- **Landing:** Trust was never about the component — it's the system that decides what context flows in, out, and when to stop.

---

## MOVEMENT IV — Managing Your Own Context Window *(self-scale context)* — *~5 min*
- **Generational contrast:** writing to Nebraska for a book (scarce context, slow) vs. today's infinite-context undergrads — every hand up for "using AI," almost none for "better off."
- **Hero story + prescription — the 2-hour sandbox:** the **temporal interlock** is context management for *humans* — your attention is the scarce window; timebox it, cap the blast radius, and change the metric from "perfect product" to "map where the model fails."
- **The promotion move:** stop owning components; develop trust in *which* context to hand to software → manage the LLM as your employee → shift from **Author** (syntax) to **Director** (curating intent and context). That *is* the context-engineering job.
- **Landing:** The same discipline scales down to you: decide what deserves your window.

---

## THE CLOSING — The Cautious Architect Is the Context Engineer — *~2 min*
- The whole industry is converging on one job: deciding what context is admissible. The cautious architect already thinks in constraints, boundaries, and what-belongs-where — that *is* context engineering.
- **Cold-bee callback:** skeptics aren't blockers; they're why the hive's context stays stable.
- **Final turn:** grant yourselves permission to build — the window is yours to engineer.

---

**Total target: ~31 min of content → ~30 delivered with pauses honored.** *(Four movements instead of six = cleaner climbs, fewer transitions.)*

---

## WHAT CHANGED IN THIS RESTRUCTURE
- **New spine:** the industry trend toward **context-window management**, framed at three scales (model / self / org).
- **Six movements → four:** old III (transparency) demoted to a 90-sec bridge inside the new Movement III; old IV (system) + the math now share one movement; old V/VI folded into the new Movement IV.
- **Every central notion kept** but re-skinned as a context-management story (regulation, bees, architect/harness, guardrails, sandbox, author→director, cautious architect).
- **New trend anchors added:** RAG · MCP · agentic harnesses / sub-agents · context compaction · Eval-Driven Development — alongside the existing JPMorgan / Wells Fargo / FDA guardrail set.

## STILL CUT (do not reintroduce)
- Robinson Track Circuit (1870s) · the explicit "Three Tiers of Leadership" list · the "Four Executive Skills" list · standalone Movement VI.
