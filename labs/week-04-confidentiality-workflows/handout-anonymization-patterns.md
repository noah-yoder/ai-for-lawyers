# Anonymization Patterns: Sanitizing Client Facts for Consumer AI Tools

*AI for Lawyers — Week 4 handout. Use with the Data Triage Guide: these patterns are how YELLOW-tier work gets done.*

Sanitization is not "delete the names." Names are the easiest identifiers to remove and the least important. What identifies a client in practice is the *combination* of ordinary details — industry plus city plus headcount plus a newsworthy event will out your client faster than a surname. Sanitizing well means controlling identifiers *and* combinations, while keeping the facts that make the legal analysis work.

## The three patterns

Work down this list. Each pattern is safer than the one above it; use the safest one that still leaves the task doable.

### Pattern 1 — Redaction (weakest)

Strike the identifier and leave a placeholder: "[CLIENT]," "[EMPLOYEE A]," "[CITY]."

- **Use for:** names of people and entities, email addresses, account or docket numbers.
- **Why it's weak:** redaction removes the label but keeps every contextual clue around it. "[CLIENT], the largest gear manufacturer in [CITY]" is not anonymous.
- **Habit:** redact *consistently* — if "Dana" survives in paragraph four after you redacted "Dana Whitfield" in paragraph one, you've sanitized nothing.

### Pattern 2 — Aliasing / substitution (better)

Replace specifics with same-shaped substitutes: real-feeling but false names, rounded or shifted numbers, a comparable-but-different jurisdiction *where jurisdiction doesn't drive the analysis*.

- **Use for:** facts where the *shape* matters but the *value* doesn't. "About 340 employees" → "several hundred employees." "$86M revenue" → "a mid-eight-figure manufacturer." "May 12 demand letter" → "a recent demand letter."
- **Watch out:** don't alias facts that are legally operative. If the claim arises under Illinois law, moving the plant to Ohio breaks the analysis. Alias around the operative facts, not through them.
- **Watch out:** highly specific numbers are fingerprints. An $11.9M demand is searchable; "an eight-figure opening demand" is not.

### Pattern 3 — Abstraction (strongest)

Restate the situation as a generic hypothetical at the highest level of generality that still supports the analysis: "An employer collected employee fingerprints for timekeeping without written releases."

- **Use for:** the legal-analysis core of almost any question. Most doctrinal asks — elements, exposure frameworks, what-to-ask-next — need *category* facts, not *client* facts.
- **The test:** if a fully abstract hypothetical gets you a useful answer, you never needed the client's facts in the tool at all. Try abstraction *first*; descend to aliasing only for facts the analysis genuinely turns on.
- **The trade-off:** over-abstract and the output goes generic or wrong. "An employer had a compliance issue" is safe and useless. Calibrating this trade-off is the skill.

## Quasi-identifiers: the leaks that get people caught

A *quasi-identifier* is a detail that's harmless alone but identifying in combination. After sanitizing, hunt for these:

| Leak type | Example | Fix |
|---|---|---|
| Industry + geography | "a gear manufacturer with a northern-Illinois plant" | Keep only the one that's legally operative |
| Unique events | "the audit was covered in the trade press" | Omit, or abstract past it ("a publicly reported investigation") |
| Precise numbers | exact headcount, revenue, demand amounts, dates | Round, band, or relativize ("several hundred," "recent") |
| Named third parties | vendors, products, opposing firms | Vendors and products identify clients too — alias them |
| Insider details | who-said-what-internally, named whistleblowers | Abstract to role only if operative ("a manager raised the issue internally") — and ask whether it belongs in the prompt at all |
| Procedural posture | court + county + claim type + timing | Keep the claim type; drop venue specifics unless operative |
| Sensitive personal details | a claimant's medical condition | Include only if legally operative, and only as a category ("a medical condition affecting scan reliability") |

## The re-identification audit

Never grade your own sanitization. Before sanitized text leaves your hands, run an adversarial pass — ideally a colleague's eyes, and (today's lab trick) the model itself in a *fresh* chat: paste only the sanitized text and ask what it can infer about the real parties. If a model with no context can shortlist your client, so can opposing counsel, a journalist, or the client's competitor.

A sanitized summary **passes** when: a motivated stranger reading it could not shortlist the client; every legally operative fact survived; and you can say which pattern you applied to each removed detail and why.

## Worked micro-example

**Raw:** "Our client, Juniper Stack Software Co. of Carmel, Indiana, fired its only DevOps engineer, Theo Brandvold, two days after he emailed the CEO about unpaid overtime."

**Bad sanitization (redaction only):** "Our client, [COMPANY] of Carmel, Indiana, fired its only DevOps engineer two days after he emailed the CEO about unpaid overtime." — *Town + "only DevOps engineer" + event is a fingerprint.*

**Good sanitization (abstraction + aliasing):** "A small software company terminated an employee shortly after he complained in writing to senior management about unpaid overtime." — *Everything the retaliation analysis needs; nothing a stranger can search.*

## One more thing the patterns can't fix

Sanitization manages the *identification* risk. It does not convert a consumer tool into an approved one for material you've promised to protect in specific ways — protective-order designations, litigation-hold material, data a client's outside counsel guidelines fence off. For those, the answer isn't better anonymization; it's a different tier of tool, or none. Triage first, sanitize second.
