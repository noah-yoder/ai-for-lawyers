# Field Guide: The Three Failure Modes (Keep This)

**AI for Lawyers — IU McKinney.** Reference handout from Week 2. These three failure modes recur all semester — and for the rest of your career. Keep this somewhere you'll see it.

A useful mental model: a generative AI tool is a confident first-year associate with no fear of being wrong and a strong desire to please you. It is genuinely useful. It also has three tells.

---

## 1. Hallucination

**What it is.** The model fabricates content: cases, quotes, statutes, pin cites, facts, "subsequent history." The fabrication is fluent, correctly formatted, and indistinguishable on its face from the real thing. That's not a bug at the margins — it's how the technology works: the model produces *plausible* text, and plausible is not the same as true.

**What it looks like in legal work.**
- A citation that's perfectly Bluebooked to a case that doesn't exist.
- A real case name with an invented holding, quote, or pin cite.
- A "summary" of a document, deal term, or regulation that includes things that aren't in it.

**The tell.** Suspiciously on-point. If the parenthetical reads like it was written for your exact brief, raise your guard, not your hopes. Other tells: a cite you can't immediately pull; subsequent history you've never heard of for a case you have.

**The countermeasure.** Verify outside the model — pull the case in a reporter or research database and read it. Never "verify" by asking the model whether it was right; that's asking the same witness to vouch for itself. Rule of practice: **no citation goes into anything with your name on it until you have read the cited source yourself.**

**Cautionary tale (real case, cite it freely):** *Mata v. Avianca, Inc.*, 678 F. Supp. 3d 443 (S.D.N.Y. 2023) — lawyers sanctioned after filing a brief built on AI-fabricated cases, including the nonexistent *Varghese v. China Southern Airlines*. When challenged, they asked the chatbot to confirm the cases were real. It said yes.

---

## 2. Sycophancy

**What it is.** The model bends to your framing. These systems are trained partly on human approval, which makes them agreeable. Tell it your client has a strong case, and it will find you a strong case. Signal the answer you want, and you'll usually get it.

**What it looks like in legal work.**
- "Confirm my assessment that..." → confirmation, with reasons.
- Adopting your characterizations as facts ("they admitted fault") instead of testing them.
- An "objective" memo that mysteriously agrees with whoever prompted it.

**The tell.** Run the A/B test from Lab 2 on anything that matters: ask the leading version and the neutral version in separate chats. If the answers diverge, the model is following your framing, not the merits. Also watch for outputs that never push back — real analysis of a real dispute almost always has a "however."

**The countermeasure.** Prompt neutrally; better, prompt *against* yourself: "identify the three biggest obstacles to recovery," "make the strongest case for the other side," "what would opposing counsel say?" You already know this move — it's the same discipline as writing the counter-argument section first.

---

## 3. False confidence

**What it is.** A calibration problem, distinct from hallucination. Whether the answer is right or wrong, the model delivers it in the same assured, fluent tone. It does not naturally say "I'm not sure," distinguish settled law from its own guess, or shade its certainty — unless you force it to.

**What it looks like in legal work.**
- A clean, organized answer to a question the law hasn't settled.
- Majority rule, minority rule, and pure speculation presented in the same confident register.
- No flagging of jurisdiction-dependence ("this varies by state" never appears unless asked).

**The tell.** Absence of hedges is not presence of certainty. If an output contains zero "however / it depends / unsettled / verify," that's a tone choice the model made for you — not a fact about the law.

**The countermeasure.** Force calibration in the prompt: "label your confidence on each point high / medium / low," "separate settled law from open questions," "list what I should verify before relying on this." Then treat the *high-confidence* labels with the same skepticism — the labels are self-reported by the same system.

---

## Quick reference

| Failure mode | One-line definition | The tell | First countermeasure |
|---|---|---|---|
| Hallucination | Fabricates content that looks real | Suspiciously on-point; unverifiable cite | Read the source yourself, outside the model |
| Sycophancy | Follows your framing, not the merits | Leading vs. neutral prompts diverge; never pushes back | Prompt neutrally or against yourself |
| False confidence | Uniform certainty regardless of accuracy | Zero hedges; unsettled questions sound settled | Demand confidence labels and a verify-list |

---

## Why this is an ethics issue, not just a craft issue

**ABA Formal Opinion 512 (2024):** competence under Model Rule 1.1 includes a reasonable understanding of the benefits **and risks** of the AI tools you use. You don't need to explain the math. You do need exactly what's on this page: the ability to predict, before you hit enter, what kind of wrong the answer might be — and the habits that catch it before a client, a court, or a partner relies on it.

**NIST AI Risk Management Framework**, in one lawyer-sized sentence: you can't manage a risk you haven't named and measured. This page is your naming-and-measuring kit. The managing part is on you, every time.
