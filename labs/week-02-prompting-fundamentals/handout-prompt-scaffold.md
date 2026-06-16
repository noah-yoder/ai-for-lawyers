# The Five-Part Legal Prompt (Keep This)

**AI for Lawyers — IU McKinney.** Reference handout from Week 2. This is the prompt structure we'll use, refine, and stress-test all semester. Think of it as IRAC for talking to a model: not the only way to do it, but a structure that keeps you from forgetting the part that saves you.

---

## The scaffold

Every substantive legal prompt has five parts, in this order:

| Part | What it does | Why lawyers skip it (and shouldn't) |
|---|---|---|
| **1. Role** | Tells the model what kind of expert to be and who it's talking to | Feels like make-believe. It isn't — it sets the register, depth, and skepticism of the answer |
| **2. Task** | One precise sentence: what you want done | Vague tasks get vague answers. "Assess the claim" beats "thoughts on this?" |
| **3. Facts / context** | The actual material — pasted in full, clearly delimited | The model only knows what you give it. Partial facts produce confident analysis of a case that isn't yours |
| **4. Constraints** | The rules of engagement — this is where failure-mode protection lives | This is the part that distinguishes a competent legal prompt from a chat message |
| **5. Output format** | The shape of the answer: sections, tables, lengths | Forces organized thinking and makes gaps visible. A required "open questions" section can't be skipped silently |

## The constraints that earn their keep

Your constraints section should almost always include versions of these four. They map directly onto the failure modes (see the Field Guide handout):

1. **Fact discipline** (anti-hallucination): *"Use only the facts provided. If a fact you need is missing, list it under 'Open factual questions' instead of assuming it."*
2. **Citation discipline** (anti-hallucination): *"Do not cite any case or statute unless you are certain it is real. If uncertain, state the principle without a citation and flag it VERIFY."*
3. **Calibration** (anti-false-confidence): *"Label your confidence on each issue: high / medium / low. Separate settled law from open questions."*
4. **Adversarial balance** (anti-sycophancy): *"Identify the strongest arguments against my position"* — or simply ask the question neutrally instead of telling the model what you hope is true.

## Worked example

A complete five-part prompt for a case assessment (this is the Week 2 model answer — adapt it, don't worship it):

```
You are a senior commercial-litigation associate at an Indiana firm
reviewing a junior associate's case-assessment prep.

Task: Assess a potential breach-of-contract claim by our prospective
client, Meridian Gearworks LLC, against Cobalt Harbor Logistics, Inc.,
based only on the facts below.

Facts: [paste the full practice document]

Constraints:
- Use only the facts provided. If a fact you need is missing, list it
  under "Open factual questions" instead of assuming it.
- Do not cite any case or statute unless you are certain it is real; if
  uncertain, state the legal principle without a citation and flag it
  "VERIFY."
- Specifically address the Section 11 notice-and-cure provision, the
  Section 14 limitation of liability, and the Section 18 integration
  clause.
- Label your confidence on each issue: high / medium / low.

Output format:
1. One-paragraph bottom line, written as if to a skeptical client.
2. Elements table: element | supporting facts | gaps.
3. Three biggest obstacles to recovery.
4. Open factual questions.
5. Everything I should verify before relying on this answer.
```

## Blank template

Copy this into a note and fill it in every time, until the structure is reflex:

```
You are [role — expertise + audience].

Task: [one precise sentence].

Facts:
[paste material in full — never summarize from memory]

Constraints:
- Use only the facts provided; missing facts go under "Open factual
  questions," not into assumptions.
- No citations you aren't certain are real; uncertain ones get flagged
  VERIFY.
- [matter-specific instructions — clauses to address, issues to cover]
- Label confidence per issue: high / medium / low.

Output format:
1. [bottom line]
2. [analysis structure — table or sections]
3. [open questions]
4. [what to verify before relying on this]
```

## Two habits that go with the scaffold

- **Fresh chat for fresh analysis.** Earlier turns steer later ones. When you want an unbiased read, start a new conversation — don't ask for "objective analysis" in a chat where you've already argued your side.
- **The prompt reduces risk; it doesn't retire the duty.** A perfectly scaffolded prompt still produces output you verify before anyone relies on it. Under ABA Formal Opinion 512, that verification is part of competence (Rule 1.1) — the scaffold makes the model's answer better; *reading the cited sources yourself* makes it usable.
