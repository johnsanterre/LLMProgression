# SCRIPT — *Managing the Context Window*

*Formalized narrative draft (~30 min). Persona: the "Trusted Senior Colleague" — matter-of-fact, authoritative, deep pedagogical warmth, no fluff or forced excitement. Keynote length retained. Anthropomorphism softened (one deliberate "junior engineer" metaphor kept; casual "the model decides/knows" phrasing removed in favor of mechanical/structural verbs). `[Beat]` marks an intentional pause at points of intellectual tension. The legato performance pass (forward-slash pauses / breath anchors / actable phrases) is still separate.*

**Slides:** `assets/context-evolution.png` (the staircase) · `assets/harness-stack.png` (the three control bands).

---

## OPENING — The Trend Hiding in Plain Sight

It's good to be here with you. The transition we're moving through together is one I've learned to recognize — mostly because I've moved through a few of them myself, and each was difficult to distinguish from ordinary noise until it had already reshaped the field.

From where I sit, artificial intelligence is driving a transition across an enormous range of ecosystems. But I want to be precise with you up front: for me, this is at least the *third* one. As a high schooler in the 1990s, I worked in film and video. I studied it as an undergraduate, and I became a still photographer in the early 2000s — just in time to watch my entire field get dismantled, and then rebuilt, by digital cameras. So I moved from photography into artificial intelligence in the late aughts, before "data science" was a phrase anyone used.

Watching the origins of data science, and then its almost uncontrolled growth, taught me how these shifts actually behave. And I'll be direct: the disruption I'm watching today from large language models is only comparable to that earlier, genuinely confusing period. Before scikit-learn existed. Before Kaggle competitions existed. When the open question was simply *which* algorithm, and *how* you should even approach an analysis at all.

This is more than a history lesson. I'm telling you this because there's a single mechanism underneath all three transitions, and I want you to see it clearly. The progression of the last two and a half decades — from bulletin board systems and dial-up modems through to LLMs — was never really about the technology. Underneath each step was something slower and more human: a negotiated agreement about *trust*. There was a time, and some of you remember it, when typing a credit card number into a strange new company called Amazon felt reckless.

My work has been about that exact thing: identifying the opportunity a technology opens up, and then doing the patient work of aligning the people — executives, stakeholders, skeptics — required to go explore it. So let me name the trend we're here to examine.

We have moved through three eras. First, we built **models**. Then we practiced **prompt engineering** — phrasing the input to the model precisely. And now the center of gravity has shifted again, to what we're calling **context engineering**. The work is no longer the model itself. The model is, increasingly, a commodity. The work is *what you place in front of it — and what you keep out.*

**[SLIDE — "The Road to Context Engineering" (the staircase)]**

Here is the road that produced that shift. And notice one thing before I describe it: there are no dates on this slide. That's deliberate, and I'll explain why in a moment.

At the bottom is the **single prompt** — you sat down and *fixed* the entire context by hand. Everything available to the model in that moment was whatever you typed. Then came **RAG**, retrieval — instead of typing everything, a pipeline retrieves the relevant documents and assembles the context for you. Then **tool calling** — the model issues calls that pull additional context at runtime. Then **agentic flows** — where the output of one call becomes the input context for the next.

Here is the question that unifies every one of those rungs. Each era is just a new answer to one question: **what is in the window when the model runs — and who put it there?**

[Beat]

Underneath that question are two axes. First: is the context **static** — fixed ahead of time — or **dynamic** — assembled at runtime? Second: who assembles it — a **human**, or the **system** itself? Track it across the slide. The single prompt: static, human-authored. RAG: dynamic, but a human built the pipeline. Tool calling: dynamic, and the call originates from the model. Agentic flows: dynamic, composed across many calls.

And then something unexpected happens at the top of the slide. We return to *static* — to durable context files, the rules and instructions you declare once and reuse on every run. So if you're looking at this thinking, "we ended up back where we started" — you're reading it correctly. But it isn't a circle. It's the most important structural point I'll make this morning.

These techniques **did not replace one another. They became layers.** The modern stack *fixes* the parts that must be stable, and *manages* the parts that must vary. That orchestration — static and dynamic, composed together — is what context engineering *is*. Which, if you sit with it, is precisely how the best architect you know already operates: pin what must hold still, govern what must move.

So here is the through-line for the next half hour. The discipline this entire industry is racing toward is the one this room already practices. You have spent your careers deciding what is admissible and what is not. That instinct isn't behind the curve. Structurally, it *is* the curve.

---

## MOVEMENT I — Context Is the New Unit of Trust

Let me ground this in the world you actually operate in: a regulated one. We tend to discuss regulation as a burden — a checklist, a tax, something the compliance team applies to us. I want to offer a more precise definition.

A regulated space is *codified trust.* It is a group of people who came together and agreed, in writing, on what information may enter a decision, and under what conditions. Strip away the binders and the audits, and regulation is *governance over what context is admissible.* Which means — and this is the part worth sitting with — you have been doing context engineering for your entire careers. You did it for human decision-makers instead of for a model.

Here is a concrete case from my own work. The Hubble Space Telescope has three rotors. Two operate well. One is failing. The group I work with was asked a simple, high-stakes question: can machine learning compensate for that failing rotor?

Now, here is the structural point. There is no regulatory board for Hubble. No committee hands us a document dictating how we may analyze it, or how we may perturb an instrument hundreds of miles above the Earth. And yet it is one of the most *heavily* regulated environments I have worked in — because it is regulated by physics, by reality, and by the researchers. People who have spent their *entire professional lives* on this one instrument, who know its every quirk, and who will accept a solution only if we can justify, in their terms, how it fits.

That is not a fast environment, and it is not an agile one. But it is governed *completely* by human trust — by our ability to transfer understanding back and forth until the people who own the risk are confident the system will hold. The context that model is permitted to operate inside is bounded by physics and by a lifetime of human knowledge. Our entire job is to earn our way inside that boundary.

I saw the same structure, in a very different setting, during my recent work at a bank in Silicon Valley. There, the risk-model framework was explicit: a proposal is made, a committee accepts it, an auditor reviews it, a compliance check closes the loop. Propose, accept, audit, comply. Notice the shape — that is a *context pipeline.* A series of gates governing what information enters a decision and who has signed off. The objective, exactly as with Hubble, is trust. But here is the part most people miss, and it's the exact mechanism that trips teams up: the *pipeline was never the trust itself.* A checklist does not produce confidence. A formula does not produce safety. The artifact is the *residue* of trust that people built — not the source of it.

This is why context engineering should feel familiar to you, not foreign. The industry is now racing to do, for models, what you already do for people. When an enterprise stands up RAG, or builds a walled garden, or adopts **MCP** — a standard governing which tools and data a model may access — it is doing one thing: constraining what context the model is permitted to use. Governing admissibility.

So the landing is this. Trust was *always* about governing context. That did not change. We simply have a new window to govern — and you already know the work.

---

## MOVEMENT II — The Ecology That Regulates Context

When I get frustrated — and I do — with a stakeholder who won't bring in something I find obviously valuable, I make myself recall an example Steven Strogatz, the Cornell mathematician, once described.

It concerns how bees hold a hive at a stable temperature. The counterintuitive part is that they do *not* do it by converging on a single set point. Some bees run cold their whole lives — so they vibrate their flight muscles to generate heat. Some of you run cold; you're the ones with a space heater under the desk. Other bees run hot, sit near the hive's ideal temperature, and spend most of their time outside it. And only a small number hold that optimal temperature as their natural set point.

What Strogatz examined was how that *distribution* — the full spread of set points across the colony — is exactly what produces a stable temperature *inside* the hive. Sit with that for a second. It was not uniformity that produced stability. It was the *ecology* of difference.

Now make the structural transfer. The skeptics in your organization — the cautious architects, the ones who run cold on every new tool — are not blockers. They are the cold bees. They are *regulating* the organization's context. They are load-bearing in keeping the hive from overheating and pivoting itself off a cliff. I'll be honest about my own bias: I am an early adopter to a fault. I see the conclusion and I want to sprint to it. And if everyone shared my temperature, the organization would oscillate violently and tear itself apart. Reluctance is not the pathology. The only real pathology is being shown clear evidence and still refusing to move.

Let me make this concrete. In my current role as CTO, I hired a chief architect I trust deeply — and he is *vehemently* opposed to "vibe coding." For a while that frustrated me. But that frustration turned out to be the most productive thing that happened to me last year, because it forced me to do something more useful than argue. It forced me to *build.* It forced me to construct software that genuinely answered his objections — which, I should say plainly, were entirely valid. What came out of it was a deterministic **agentic harness** that reduced the model's output variability to a small fraction of what it had been. Individual runs became stable. Reproducible. And his bar for production-grade work became something the system could clear. I didn't change his temperature — let me put that more precisely, because the distinction is the whole point — I built the engineering that made the variability low enough for him to trust the output.

**[SLIDE — "The Agentic Harness Stack" (three control bands)]**

This is the shape of what I built, and increasingly the shape of the frontier. I won't walk all seven layers; I want you to see the three *bands.*

At the **bottom**, in blue, is the **static control plane** — persistent context files, grounding to your real code and schemas, versioned and shareable. This is where you *pin what must hold still.* In the **middle**, in teal, is **the doorway** — your governed connections to tools and data, the standard now called MCP: one audited interface to the outside world. At the **top**, in orange, is the **agentic harness** — skills loaded only when relevant, automated hooks that fire at defined moments, and parallel sub-agents that isolate context and vote out failure. This is where you *govern what must move.*

This picture matters to a room of architects because it's written in your native language. It's a control plane. So let me be exact about the three layers, because they get blurred together and they shouldn't.

The **static control plane** is declarative governance. Fixed, versioned, auditable — rules, policies, schemas, parameter-locked infrastructure. It does not vary run to run. It answers: *what is permitted?*

The **agentic harness** is the dynamic control plane. It is the orchestration layer that runs on every request and resolves — within those rules — what context to assemble, which tools to call, how the calls compose, and when to halt. It answers: *given the rules, what gets executed this run?*

And **MCP** is the doorway — the standardized protocol connecting the model to the outside world. The static plane governs *which* doors may exist; the harness routes calls *through* them at runtime. Its real contribution to a regulated enterprise is that it collapses a thousand bespoke, unauditable integrations into one governed doorway. It answers: *how does context move in and out — safely, and uniformly?*

So the line to carry out of this section: the static control plane sets the rules, the agentic harness operates within them, and MCP is the governed doorway both rely on. **Pin what's stable. Govern what moves. Standardize the doorway.**

And the deeper point: you don't *convert* a skeptic by winning the argument. You engineer the context that earns their trust — and in the process, they make the system safer than you would have made it alone.

---

## MOVEMENT III — We Trust the System Around the Window

Let me get technical for a few minutes, because I know some of you are carrying a specific, legitimate grievance, and I want to name it precisely.

You miss transparency. Many of us, especially in regulated finance, reached for logistic regression for years *because* every coefficient told a story you could put in front of an auditor. That was not naïve — it was a brilliant fit for the constraint. So I want to honor why it worked before I complicate it. [Beat] And here is the complication: the certainty you miss rested, in large part, on assumptions we already knew were false. The IID assumption is rarely strictly true. And in Naive Bayes, the naïveté is stated *in the name* — conditional independence is violated by real enterprise data, continuously.

So what we traded was the *appearance* of transparency — let me be precise, because the distinction carries the weight — we traded the *appearance* of transparency for *stability at scale.* I first felt this at Argonne National Laboratory, working alongside MDs through a national research center. The question they put to me was, "How can we trust a model with the word *random* in its name?"

[Beat]

I wasn't ready for it — because the random forest had already proven itself, asymptotically, across a wide range of problems, to be more dependable than any single brittle, "explainable" algorithm. We did not lose transparency in that trade. We relocated it — up a scale — from tracing a single drop of water to characterizing the reproducible fluid dynamics of the whole ocean. That is the same trade we are making again now, with large language models.

So how do you trust a system you cannot fully trace? The same way engineers always have. You stop trying to trust the *component*, and you engineer a trustworthy *system* around it.

Start with what code actually is. Code was always meant to be human-readable — there is a reason we distinguish *machine code* from the code we write. Your codebase is not for the computer. It is human-to-human communication — *context* — specifying what a machine should do. The computer is the execution layer. An LLM is simply a more capable, far less deterministic execution layer. The cleanest way I can frame it: it is *like* adding a fast, capable, but unreliable junior engineer to the conversation — and I mean that as a deliberate analogy, not a claim that the system reasons. The question is not "do we trust it?" The question is "what system do we build around it?"

The industry is answering that right now, in ways this room will recognize. JPMorgan built its LLM Suite as a walled garden — constraining the context the model can reach. Healthcare teams run evaluation loops, where a second, specialized model checks a clinical draft against defined criteria *before* a human reviews it. Wells Fargo runs what it calls a "Golden Set" — a hard halt that stops the system the moment a confidence measure drifts off a verified baseline. And the FDA gave us the most elegant pattern of all: Predetermined Change Control Plans. They do not pretend the model won't change. They *specify, in advance, the precise boundaries within which it is permitted to change.*

That, incidentally, is the future of your craft. We are moving from Test-Driven Development to **Eval-Driven Development** — from testing whether code does what we wrote, to continuously testing whether the *system* still operates within the boundaries we agreed to trust.

So the landing of this movement is the core of the talk. Trust was never about the component. It was never a single sensor on the shuttle, or one tool, or one model. It is the *system* — the system that governs what context flows in, what flows out, and when to halt. That is what you build. That is what you have always built.

---

## MOVEMENT IV — Managing Your Own Context Window

Now bring it all the way down — from the model, past the organization, to *you.* Because the most consequential context window in this room is not the model's. It's yours.

A contrast. When I was young and wanted to learn something, I wrote a letter to Nebraska to request a book. I waited two weeks for it to arrive. Then I had perhaps three months to extract everything I could before I had to return it. My context was *scarce*, and *slow.* The students I teach now live in the inverse — context is abundant and instant. So I run a small experiment with them. I ask a lecture hall of undergraduates, "How many of you use AI to write code?" Every hand goes up. Then I ask them to lower their hands, and I ask, "How many of you believe you are *better off* for it?" Almost none rise. Sometimes none.

So with one especially capable, especially perfectionist student, I prescribed something specific — and I'd prescribe the same to the skeptics here. Set a timer. Spend exactly two hours building a solution with the model. When the timer ends, close the laptop. Without exception. Mid-function if necessary.

I call that a **temporal interlock**, and it is context management for *humans.* Your attention is the scarce window. The two-hour bound caps the blast radius of your own failure. And — this is the operative move — it changes the success metric. You are no longer trying to "deliver a perfect product." You are trying to *map where the model fails.* Instead of grinding fifteen hours to force one application across the line, she now selects an idea, probes it, observes precisely how the system breaks, and stops. Selects the next idea, probes it, stops. In two-hour increments, she is building something more valuable than an application. She is building a map of the boundaries.

And my deeper objective for her is the one I hold for everyone in this division, at every level. I want her to stop being responsible only for the components she personally writes — and to start developing calibrated trust in *which* of those components she can delegate to the software, so she can move up the stack. So here is the directive I'll give you. Look at your manager. Use the model to take on some of what your *manager* does that you currently don't. Give yourself a promotion. Manage the model the way you would manage a report.

Because the moment you do, the question changes. You stop asking, "How do I use this tool to finish my task?" and you begin asking, "How do I see the problem the way my manager sees it?" You move from **author** — the individual contributor producing syntax — to **director** — curating intent and context across many contributors, and tracking exactly where the system succeeds and where it fails. That work — orchestrating context rather than producing it by hand — *is* the context-engineering job.

So the landing here is simple. The discipline we applied to the model, and to the organization, scales down to you. Decide, deliberately, what is admitted into your window.

---

## CLOSING — The Cautious Architect Is the Context Engineer

Let me close.

The fears about where these tools will fail are real. I won't wave them away — and I wouldn't want to, because those fears are doing structural work. But I need you to see what they point at. The entire industry is converging on a single job: deciding what context is admissible. What is pinned. What is governed. What is permitted through the door. And the cautious architect — the person who instinctively thinks in constraints, boundaries, and what-belongs-where — is not behind this moment. That person is its native. Your caution is the capability this era requires.

So I'll end where I began, with the bees. The skeptics among you are not blockers. You are the cold bees. You are the reason the hive holds its temperature instead of cooking itself — no less essential than the early adopters, and no more. But there is one thing the cold bees have to do. You have to grant *yourselves* permission to build — to step outside the lines, inside a boundary you have engineered, and explore.

The window is yours to govern. It always was. Now go and engineer it.
