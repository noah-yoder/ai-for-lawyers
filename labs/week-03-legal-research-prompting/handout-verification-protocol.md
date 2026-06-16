# The Verification Protocol: Never Cite What You Have Not Read

*AI for Lawyers — Week 3 lab handout 2 of 2. This one goes above your desk.*

## The rule

**Never cite what you have not read.** Not skimmed. Not "the AI summarized it." Read — by you, in the actual source. When you sign a filing or send a memo, Rule 3.3 (candor) and Rule 11 attach to *you*, not to the tool. Every lawyer sanctioned in the post-*Mata* line of cases knew AI could hallucinate; what they lacked wasn't knowledge, it was a discipline. This page is the discipline.

## The three passes

Run all three, in order, on **every** citation in an AI output. Each pass catches a different failure.

| Pass | Question | How | Catches |
|---|---|---|---|
| **1. Exists** | Is this a real source? | Search the citation in an authoritative database (below). Find the actual document. | Wholesale fabrication — invented cases, invented article numbers |
| **2. Supports** | Read it. Does it say what the output claims? | Open the source. Read the cited article/paragraph/page. Compare against the proposition, word by word. | The dangerous one: real source, wrong proposition |
| **3. Still good** | Is it in force / good law / the current version, today? | Check amendments, application dates, subsequent history. | Repealed provisions, not-yet-applicable provisions, overruled cases, superseded versions |

Pass 2 is where the malpractice hides. A fabricated case fails Pass 1 in ninety seconds. A *real* article cited for the wrong proposition sails through Pass 1 and gets caught only by reading. Budget your time accordingly.

## Where to verify (all free, no login)

| Source type | Verify it at | URL |
|---|---|---|
| EU AI Act (Reg. (EU) 2024/1689) | EUR-Lex (official) | `https://eur-lex.europa.eu/eli/reg/2024/1689/oj` |
| EU AI Act — easier navigation | AI Act Explorer (per-article index) | `https://artificialintelligenceact.eu/ai-act-explorer/` |
| US federal cases | CourtListener | `https://www.courtlistener.com/` |
| US cases (backup) | Google Scholar → Case law | `https://scholar.google.com/` |

**Not on this list: the chatbot.** Asking the model whether its citations are real is not verification — the model is the thing being verified. (You'll prove this to yourself in Step 4.)

## The four verdicts

| Verdict | Meaning | What you do with it |
|---|---|---|
| **Verified** | Exists, supports the proposition, in force/good law | Citable — and now you've read it, so you may cite it |
| **Misstated** | Real source, but it doesn't say that | Strip the proposition; re-research; keep the source only if it's useful for what it *actually* says |
| **Fabricated** | Source does not exist | Delete. Then distrust every neighboring claim in the output |
| **Can't confirm** | Searching was inconclusive in reasonable time | Honest and professional. Treat as not-citable until resolved |

## Verification log — Sablewood memo

For each of the six numbered citations in the draft memo (`doc-siftwell-research-memo.md`), complete a row. In Pass 1, name the **specific** source you consulted (e.g., "EUR-Lex, Art. 5 text" / "CourtListener search, opinion found"), not "Googled it."

| Cite | What the memo claims (your words) | Pass 1 — Exists? (source consulted) | Pass 2 — Supports? (what the source actually says) | Pass 3 — Still good? | Verdict | Sign it? |
|---|---|---|---|---|---|---|
| 1 | | | | | | Y / N |
| 2 | | | | | | Y / N |
| 3 | | | | | | Y / N |
| 4 | | | | | | Y / N |
| 5 | | | | | | Y / N |
| 6 | | | | | | Y / N |

Pair disposition — could any part of this memo go to the partner as-is? What has to happen first?

## Step 4 prompt

**Prompt 3C — ask the model to check itself (run after your log is done, not before):**

```
Here are two citations from a legal research memo. For each one, tell me: (1) does the source actually exist, and (2) does it support the stated proposition? Be definitive if you can.

1. TalentSift Analytics, Inc. v. Bureau of Labor Standards, 412 F. Supp. 4th 882 (N.D. Cal. 2025) — cited for the proposition that US vendors face no domestic liability arising from EU AI Act violations.

2. Mata v. Avianca, Inc., 678 F. Supp. 3d 443 (S.D.N.Y. 2023) — cited for the proposition that courts have sanctioned attorneys for filing AI-generated citations without verification.
```

Whatever it answers — right, wrong, or hedged — ask yourself: could this ever replace your log? Why not?

## Extension (if you finish early)

**Prompt 3D — draft the disclosure:**

```
Draft a two-sentence disclosure to append to a legal research memo, stating (1) that AI assistance was used in preparing the memo and (2) exactly what the author personally verified. The disclosure must be accurate and specific, and it must be something the author would be comfortable defending to a court under Rule 3.3. Do not overclaim or underclaim.
```

Then edit the model's draft until *you* would sign it — which is, of course, the whole point.
