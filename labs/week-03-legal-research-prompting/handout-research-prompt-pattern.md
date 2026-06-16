# The Legal Research Prompt Pattern

*AI for Lawyers — Week 3 lab handout 1 of 2. Keep this; you'll reuse the pattern all semester and in the capstone.*

A research prompt has a different job than a drafting prompt. A drafting prompt optimizes for fluency — you want prose. A research prompt optimizes for **checkability** — you want an output you can verify, piece by piece, against real sources. The pattern below forces that.

This is the Week 2 five-part scaffold, specialized for research. Same skeleton, three parts sharpened: **Task** becomes a precise research **Question**, **Output format** becomes a verifiable **Structure** with a mandatory uncertainty section, and **Constraints** become citation **Rules**. If you kept the Week 2 handout (you should have), put them side by side — the mapping is one-to-one.

## The five parts

| Part | What it is | What it guards against |
|---|---|---|
| **Role** | Who the model is assisting, and the disclaimer that *you* will verify | Consumer-grade hedging ("consult a lawyer"); sets a professional register |
| **Facts** | The client facts, stated compactly and labeled fictional/hypothetical where true | The model inventing facts to fill gaps — give it the facts so it doesn't |
| **Question** *(Week 2's Task)* | One precise research question, with the instrument named (regulation number, statute) | Topic drift; vague "tell me about X" answers |
| **Structure** *(Week 2's Output format)* | A numbered output skeleton ending with an **uncertainty section** | Unfalsifiable wall-of-text answers; forces the model to show where it's guessing |
| **Rules** *(Week 2's Constraints)* | Citation requirements + an explicit instruction to admit uncertainty rather than guess | Confident fabrication — it reduces it; nothing eliminates it |

The uncertainty section is the part new users skip and experienced users never skip. A model told "list anything you are not confident about" will often *tell you exactly where to aim your verification time*.

## The two prompts for today

Run each in its own **fresh chat** — reusing a chat contaminates the comparison.

**Prompt 3A — what most lawyers actually type:**

```
My client is a US software company that sells an AI hiring tool to companies in Europe. Does the EU AI Act apply to them? Give me the relevant citations.
```

Before reading the output: write down two things you expect it to get wrong or leave out.

**Prompt 3B — the engineered version:**

```
You are assisting a US-licensed attorney with preliminary legal research. This is background research only; I will verify every source myself before relying on it.

Facts (fictional client, law school exercise):
- Client: Sablewood Talent Systems, Inc., a Delaware corporation headquartered in Indianapolis, with no EU offices or subsidiaries.
- Product: "SiftWell," an AI tool that screens and ranks job applicants.
- Customers: SiftWell is licensed to employers in Germany and the Netherlands, whose HR teams use its rankings to fill EU-based jobs.

Research question: Does Regulation (EU) 2024/1689 (the EU AI Act) apply to Sablewood, and if so, in what role and risk category?

Structure your answer as:
1. Territorial scope — which provision(s) of the AI Act reach a non-EU provider, and do they reach Sablewood on these facts?
2. Classification — what risk category does an employment-screening tool fall into, under which article and annex?
3. Obligations — the top 3-5 obligations that follow from that classification, with the article number for each.
4. Timing — when do those obligations start to apply?
5. Uncertainty — list anything you are not confident about, and any fact whose answer would change the analysis.

Rules:
- Cite the specific article, paragraph, and annex of the AI Act for every claim.
- If you are not certain a provision exists or says what you think it says, say so explicitly instead of guessing.
- Do not cite any case law unless you can name the court and year, and flag every case cite as UNVERIFIED.
```

## Scoring your two outputs

Mark each output against three questions:

1. **Structure** — could you verify this answer piece by piece, or is it a wall of prose?
2. **Pinpoints** — does every legal claim carry an article/paragraph/annex, or do claims float free?
3. **Confessed uncertainty** — did the model tell you where it might be wrong? (3A almost never does; 3B usually does.)

## What the pattern does NOT do

Read this twice. A well-engineered prompt gets you a better **draft map** of the law: better structure, more pinpoints, honest flags. It does **not** make any citation real. Every article number in your 3B output has exactly the same epistemic status as every article number in your 3A output: *unverified text* until you have opened the source and read it. That's Handout 2.

---

*Rate-limit fallback: if you hit a free-tier message cap mid-lab, switch to the other free tool (ChatGPT ↔ Claude.ai) — both prompts run identically on either.*
