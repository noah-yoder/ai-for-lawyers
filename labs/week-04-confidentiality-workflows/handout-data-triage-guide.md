# Data Triage Guide: Can This Touch That Tool?

*AI for Lawyers — Week 4 handout. Keep this; you'll use it every week for the rest of the semester, and then for the rest of your career.*

Rule 1.6(a) protects **all information relating to the representation of a client** — not just secrets, not just privileged material, not just things marked confidential. The client's name can be confidential. The fact that the client called you can be confidential. Rule 1.6(c) then requires you to make *reasonable efforts* to prevent unauthorized disclosure. ABA Formal Opinion 512 applies that duty directly to generative AI: before any client information goes into a tool, you must understand what the tool does with what you type.

So the question is never "is AI allowed?" It's: **what is this data, what does this tool do with inputs, and what have we promised?** Run those three questions every time. They take thirty seconds once they're habit.

## The three triage questions

### Question 1 — What is this data?

| Tier | What it covers | Examples |
|---|---|---|
| **Public** | Information from public sources, with no client connection revealed by your use of it | A published opinion, a statute, a filed (unsealed) complaint, a doctrine question |
| **Client-related** | Anything relating to a representation — even if it seems harmless | Client identity, matter existence, facts from intake, draft documents, strategy |
| **Heightened** | Client-related *plus* an extra legal or ethical overlay | Health information, biometric data, trade secrets, material nonpublic information, anything under a protective order or litigation hold |

Notice the overlap with the privacy law you're studying on the doctrinal side: the categories regulators treat as most sensitive (GDPR special categories, state-law sensitive data, biometric identifiers) sit in the Heightened tier here too. The regulatory map and the ethics map point the same direction.

### Question 2 — What does this tool do with inputs?

Five things to find out about *any* AI tool before client data touches it. The answers live in the terms of service, privacy policy, and (for paid tools) the data-processing or enterprise agreement:

1. **Training.** Are your inputs used to train or improve the models? By default, or only if you opt in? Can you opt out, and did you?
2. **Human review.** Can the provider's employees or contractors read your conversations (e.g., for safety or abuse review)?
3. **Retention.** How long are your inputs kept? Can you delete them, and does deletion actually purge them?
4. **Confidentiality & security commitments.** Does the provider make contractual confidentiality promises to *you*? Any security certifications? Or is it "as-is," consumer-grade?
5. **Who's the counterparty?** Is the agreement between the provider and *you personally* (consumer account) or between the provider and *your firm/client* (enterprise agreement)? Where is the data processed?

**Typical answers as of early 2026** — and this snapshot *will* expire; checking the current terms is the skill, not memorizing this table:

| | Free consumer tier (ChatGPT, Claude.ai) | Enterprise / firm-approved (incl. legal AI platforms) |
|---|---|---|
| Training on inputs | Commonly yes by default or by retained setting; opt-outs exist but you must find and use them | Contractually off |
| Human review | Possible (safety/abuse review) | Restricted by contract |
| Retention | Provider-controlled; deletion terms vary | Negotiated; often customer-controlled |
| Confidentiality promises | Essentially none to you | Yes — that's much of what's being bought |
| Counterparty | You, personally | The firm or client |

### Question 3 — What have we promised, and what else applies?

Beyond the tool's terms, check for obligations that override everything:

- **Outside counsel guidelines / engagement letters.** Many clients now restrict or prohibit AI use on their matters. Read yours.
- **Protective orders and confidentiality agreements.** A stipulated protective order limiting who may access designated material is a court order. A consumer AI provider is not on the approved list.
- **Litigation holds.** Hold material has preservation and handling rules of its own.
- **Privilege.** Disclosure to a third party can waive attorney-client privilege. Whether pasting into an AI tool is a waiving disclosure is unsettled — which is exactly why you don't want to be the test case.

## The four output tiers

Combine the three questions and every task lands in one of four tiers:

| Tier | Meaning | Rule of thumb |
|---|---|---|
| **GREEN** | Free consumer tool, as-is | Public-tier data only; nothing reveals a client connection |
| **YELLOW** | Consumer tool, **only after sanitization** | Client-related data, but the task survives anonymization (see the Anonymization Patterns handout) — and the sanitized version passes a re-identification audit |
| **RED** | Enterprise / firm-approved tool only, or informed client consent | Data that can't be meaningfully sanitized without gutting the task, or Heightened-tier data |
| **BLACK** | No AI tool, any tier | Protective-order material on unapproved systems; client instructions prohibit it; data whose mere submission breaches an obligation |

Two traps the tiers don't solve for you:

- **"The client said it's fine."** Consent helps only if it's *informed* — Op. 512's discussion of consent means the client understood what the tool does with inputs (Question 2). "Go ahead, use the AI thing" is not informed consent to training, retention, and human review on a consumer tier. And consent doesn't relax court orders or third parties' rights.
- **"I didn't use any names."** Rule 1.6 cmt. 4 lets lawyers discuss hypotheticals only when there's *no reasonable likelihood* the listener could identify the client. A unique combination of industry, geography, timing, and event can identify a client as surely as a name. That's what the re-identification audit in today's lab is for.

## The thirty-second version

Before you paste, ask out loud:

1. **What is this?** Public / client-related / heightened?
2. **What does this tool do with it?** Training, human review, retention, promises, counterparty?
3. **What did we promise?** OCGs, orders, holds, privilege?

If you can't answer Question 2 for the tool in front of you, the answer is YELLOW at best — and the homework is reading the terms, not hoping.
