# Capstone Scoping Worksheet (Weeks 1–4)

This worksheet is how your capstone starts. You'll fill it in across the first four weeks of the course and submit it at the **Week 4 milestone gate**. A good scope is the single best predictor of a good capstone — the projects that struggle in November are almost always the ones that were fuzzy in September.

What you're scoping: one defined legal practice scenario — picked from `capstone/scenario-menu.md` (or a custom scenario you've proposed in writing) — and the AI-assisted workflow you'll design for it. Pick your scenario early; your selection is confirmed at the Week 4 gate along with this worksheet, and everything from Week 5 on builds on it. Over the semester you'll build that workflow (weeks 5–8), stress-test it (weeks 9–12), and defend it in a 10-page memo, a 15-minute live demo, and Q&A (weeks 13–14). The capstone is 35% of your grade. This worksheet is the foundation under all of it.

Work in this file (or a copy). Short, specific answers beat long, hedged ones everywhere below.

## Ground rules before you write anything

1. **Your scenario must be fully synthetic.** Invented client, invented parties, invented facts. If you worked or interned somewhere — a firm, a clinic, a company, a court — you may borrow the *shape* of a task you saw ("intake screening at a small plaintiff's firm"), but never the facts, names, documents, or anything traceable to a real matter. When in doubt, invent more.
2. **Name fictional parties so they're obviously fictional.** Two-word invented company names (*Cobalt Harbor Logistics*), common-but-invented people (*Dana Whitfield*), real jurisdictions but fake docket numbers in the `26-CV-9000x` series. Quick-search any company name to make sure it doesn't collide with a real one.
3. **Free tools are your primary path.** Your workflow must run end-to-end on ChatGPT free tier, Claude.ai free tier, and/or Google NotebookLM. You may *also* design a pro-tool variant (Westlaw Precision AI, Lexis+ AI, CoCounsel) if you have access — but the graded demo must never depend on a paid tool working.
4. **Scope small.** A narrow workflow you can actually defend beats an ambitious one you can't. "AI-assisted first-pass review of NDAs against a 6-point checklist" is a great capstone. "AI for contracts" is not a capstone; it's a mood.

## Pacing: how this maps to weeks 1–4

| Week | After that week's lab, you can fill in... |
|---|---|
| 1 (tool tour) | Scenario picked from `capstone/scenario-menu.md`; Part 1 first draft; Part 4 candidate-tool list |
| 2 (prompting & failure modes) | Part 2; first pass at Part 6 (you now know how these tools fail) |
| 3 (research & verification) | Part 5 (success criteria need verification steps — you just learned them) |
| 4 (confidentiality workflows) | Part 3, especially the confidentiality row; final polish; submit |

Don't wait until week 4 to start. The worksheet is designed so each lab hands you the next section.

## Part 1 — The scenario

**1.1 The client (invented).** Who is the lawyer in your scenario, and who do they serve? One short paragraph: practice setting (small firm / in-house / clinic / agency / solo), the fictional client or client type, and what's at stake for them.

**1.2 The task.** What specific legal task does your workflow assist? One sentence, starting with a verb. ("Screen incoming intake forms for conflicts and statute-of-limitations red flags before a human reviews them.")

**1.3 The "before" picture.** How does a lawyer do this task today, without AI? Walk it in 3–6 steps. If you can't describe the manual version, you don't understand the task well enough to automate any of it.

**1.4 Why this task is a good fit for AI assistance — and where it isn't.** Two or three sentences each way. The "where it isn't" half is not optional; it becomes the seed of your stress-test plan in weeks 9–12.

## Part 2 — Task decomposition: the AI's job vs. the lawyer's job

Fill in the table. Every row of your workflow goes in one column or the other — nothing is "the system handles it."

| Step | Who does it (AI / lawyer) | What exactly happens | What can go wrong here |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| ... | | | |

Then answer: **2.1 Where is the human checkpoint?** Name the step(s) where a lawyer reviews AI output before anything leaves the workflow. A workflow with no human checkpoint will not pass the Week 4 gate.

## Part 3 — Ethical duties implicated (the Op. 512 map)

ABA Formal Opinion 512 organizes a lawyer's AI obligations under five duties. Your final memo must defend your workflow against all five; start the map now. For each duty, write 1–3 sentences on how *your specific workflow* implicates it — or, if a duty genuinely barely applies, say why in one honest sentence (don't force it).

| Duty | Rule | How my workflow implicates it |
|---|---|---|
| Competence | 1.1 | |
| Confidentiality | 1.6 | |
| Supervision | 5.1/5.3 | |
| Fees | 1.5 | |
| Candor | 3.3 | |

**3.1 The hard one.** Which duty is the biggest problem for your design? (Every design has one. Confidentiality if client data touches a consumer tool; candor if the output goes near a court; supervision if a non-lawyer runs the workflow.) Name it and write 3–4 sentences on your current thinking. "I don't have a solution yet" is an acceptable answer at week 4 — pretending the problem doesn't exist is not.

## Part 4 — Candidate tools

| Tool | Free? | What I'd use it for in this workflow | Known limitation that matters here |
|---|---|---|---|
| | | | |
| | | | |

Requirements: at least two free tools in the table (your workflow's prompts should run on either ChatGPT or Claude.ai so a rate limit never strands you), and NotebookLM if your scenario involves long documents. Pro tools are welcome as an extra row marked clearly as the **optional pro-tool variant** — describe what genuinely changes (e.g., citation-grounded retrieval), not just "nicer interface."

**4.1 What no tool does.** Name one part of the task you've concluded should *not* use AI at all, and why. Knowing when not to use the tool is a graded skill in this course.

## Part 5 — Success criteria

**5.1 Definition of working.** Complete this sentence: "My workflow works if, given ____________, it produces ____________, and a reviewing lawyer can verify that output by ____________ in roughly ____ minutes."

**5.2 Verification steps.** List the concrete checks a lawyer performs on the AI's output before relying on it (e.g., "confirm every cited authority exists and says what the output claims, via a second independent source"). Each check should be something you can demonstrate live in your week 14 demo.

**5.3 The money shot.** Describe the one moment where your workflow visibly *catches a problem* — a planted bad input, a fabricated citation, a privileged document that shouldn't be there. If your demo can't show the workflow catching something, your verification steps are decoration. You'll plant this flaw yourself in your synthetic test documents; that's by design.

**5.4 Test materials plan.** What synthetic documents will you create to build and test against? List them (e.g., "8 invented intake forms, 2 with planted conflicts; 1 invented NDA with an ambiguous indemnity clause"). Every one must carry the course's FICTIONAL header block.

## Part 6 — What could go wrong (stress-test preview)

List 3–5 ways your workflow could fail *in practice* — not "the AI might be wrong" but specific scenarios: a hallucinated case in a client letter, an intake form containing privileged material from the other side, an output that's confidently wrong in a way your verification step wouldn't catch. For each: which Op. 512 duty it implicates. This list becomes your weeks 9–12 stress-test agenda, so make it adversarial now.

If you want a structured push, run Prompt S1 on your draft scope:

```
You are a skeptical supervising partner. A law student proposes the
following AI-assisted legal workflow as a semester project. Read the
scope below and answer three things, bluntly:

1. Is the task specific enough to build and test in 8 weeks, or is it
   really several tasks wearing a trench coat? If the latter, name the
   one task they should keep.
2. What are the three most likely ways this workflow fails in real
   practice? For each, name the professional duty implicated
   (competence, confidentiality, supervision, fees, or candor).
3. What is the single question about this design the student appears
   not to have asked yet?

PROPOSED SCOPE:
[paste your Parts 1, 2, and 5 here]
```

The model's critique is input, not gospel — you've seen by now how confidently these tools can be wrong. Keep what survives your own judgment; note in your submission one critique you *rejected* and why. That rejection, well-reasoned, is worth more at the gate than ten accepted suggestions.

## Worked example (for calibration — do not reuse this scenario)

```
---------------------------------------------------------------
FICTIONAL — CREATED FOR TEACHING
All parties, facts, and documents are invented for AI for
Lawyers (IU McKinney). Any resemblance to real persons,
companies, or matters is coincidental. Not legal advice.
---------------------------------------------------------------
```

*Scenario:* Imani Brooks is a solo practitioner in Indianapolis handling residential landlord-tenant defense. Her invented client base is low-income tenants; intake arrives as free-text web forms. *Task:* Screen each intake form to flag (a) imminent deadlines (hearing dates, notice periods), (b) potential conflicts against a 40-name fictional prior-client list, and (c) facts suggesting an emergency (lockout, utility shutoff) — producing a one-paragraph triage summary a human reads before anyone is contacted. *Human checkpoint:* Imani reads every triage summary against the raw form before acting; the AI never communicates with a tenant. *The hard duty:* confidentiality — intake facts are sensitive, so the workflow strips names and addresses to placeholders before anything touches a consumer model, and the worked test set is 10 invented intake forms, 3 with planted flaws (one buried hearing date, one conflict hit, one form that's actually from a landlord). *Money shot:* the demo shows the workflow flagging the landlord-side form as a conflict the model initially summarized as routine.

Notice what makes this scope work: one task, a named human checkpoint, a confidentiality answer that's a *design feature* rather than a disclaimer, and planted flaws decided up front. Yours should feel like this — in a different scenario.

## What you submit at the Week 4 gate

- Your scenario selection (menu number, or your approved custom proposal) — locked at this gate.
- This worksheet, every part filled in (Part 6 may be a working list).
- One paragraph: the Prompt S1 critique you rejected, and why.
- Nothing polished. The gate grades thinking, not formatting — see `capstone/milestone-rubrics.md` for exactly what "on track" looks like.
