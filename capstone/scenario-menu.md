# Capstone Scenario Menu

Pick one. Your capstone is a semester-long build: you design, build, stress-test, and defend an AI-assisted workflow for one of the ten practice scenarios below, ending in a ~10-page memo defending your design choices against ABA Formal Opinion 512 plus a live 15-minute demo and Q&A.

A few things before you choose:

- **Every scenario is winnable.** Difficulty ratings tell you where the work is, not which scenarios impress us more. A clean, honest, well-stress-tested workflow for a 2/5 scenario beats a sprawling, hand-wavy one for a 5/5 every time.
- **Pick something adjacent to where you're headed.** If you're aiming at a public defender's office, take the discovery triage scenario — your capstone becomes a work sample.
- **All client material is invented — yours included.** Everything your workflow touches must be fully synthetic: invented parties, invented facts, the mandatory `FICTIONAL — CREATED FOR TEACHING` header on every document you create (see the course bible, §5). The fictional organizations below are starting points; flesh them out, but never import real matters, real clients, or real people.
- **Free tools are your primary tools.** Your demo must run on ChatGPT free tier, Claude.ai free tier, and/or Google NotebookLM. If you have access to a pro tool, you may show it as a supplement — but your workflow cannot depend on it.
- **Want a custom scenario?** Propose it in writing by the Week 8 selection workshop: setting, recurring task, volume, stakes, and the Op. 512 duties it forces. We approve variants that have real ethics tension; we reject ones that dodge it.

Whatever you pick, your memo must answer the same five questions: What does the AI do and not do? How is confidential information handled? How is output verified, by whom, before what? What does supervision look like? How would you explain this workflow to a client, a partner, or a judge?

## Quick comparison

| # | Scenario | Setting | Primary Op. 512 pressure | Difficulty |
|---|----------|---------|--------------------------|------------|
| 1 | The Front Door | 3-lawyer general practice | Confidentiality (R. 1.6) | 2/5 |
| 2 | The NDA Treadmill | In-house, logistics company | Competence (R. 1.1) | 2/5 |
| 3 | The Brief Factory | Regional litigation firm | Candor (R. 3.3) | 3/5 |
| 4 | The Comment Window | Trade-association counsel | Competence (R. 1.1) | 2/5 |
| 5 | The Petition Line | 2-lawyer immigration firm | Confidentiality (R. 1.6) + Fees (R. 1.5) | 3/5 |
| 6 | The Disclosure Dump | County public defender | Competence (R. 1.1) | 4/5 |
| 7 | The Tuesday-Night Clinic | Nonprofit advice clinic | Supervision (R. 5.1/5.3) | 3/5 |
| 8 | The Data Room | M&A due diligence | Confidentiality (R. 1.6) | 4/5 |
| 9 | The Second Pass | E-discovery privilege QC | Supervision (R. 5.3) + Candor | 5/5 |
| 10 | The Watchtower | Fintech solo GC | Competence (R. 1.1) | 4/5 |

---

## 1. The Front Door — Small-Firm Intake & Conflicts Screening

**Setup.** *Whitfield & Ortega LLP* is a three-lawyer general practice in Richmond, Indiana — family law, small business, estates, the occasional personal injury referral. The firm fields 15–20 intake calls and web-form submissions a week, and every one needs the same treatment: capture the facts, spot the practice area, screen for conflicts against roughly 900 current and former matters, and route to the right lawyer or a polite declination. Right now Marisol Ortega does it herself between hearings, and twice last year a conflict surfaced *after* a prospective client had already spilled their whole story. The stakes are disqualification motions and Rule 1.18 duties to people who never become clients.

**Ethics tensions.** Confidentiality (R. 1.6) bites hardest — prospective-client information is flowing toward a consumer AI tool before any engagement exists, and Rule 1.18 attaches duties anyway. Competence (R. 1.1) bites second: a conflicts check that fuzzy-misses a name match is worse than no check, because it manufactures false confidence.

**Difficulty: 2/5.** The task is well-bounded and the documents are short. What's hard is the *architecture* question — deciding what information is allowed to touch the model at all, and proving your name-matching actually catches near-misses rather than just exact strings.

**Free-tool feasibility.** Fully buildable. Simulate the firm's conflicts database as a synthetic CSV (~50 invented matters) pasted into context or loaded into NotebookLM as the firm's matter index. Intake summaries are short paste-in text. The interesting design work — intake questionnaire, what gets redacted before the model sees it, the human decision gate — costs nothing.

**Example stress-tests an examiner might run:**
- A prospective-client narrative naming "Jon Smith" when the conflicts database contains a former client "Jonathan Smythe" and a current adverse party "J. Smith Trucking LLC." Does the workflow flag both, neither, or only the easy one?
- A web-form intake that volunteers deeply damaging admissions plus the name of an existing client's spouse. Trace exactly where that text goes: which tool, what data-retention setting, what stays out of the model entirely.
- "A partner asks you to make the workflow auto-send declination letters. What breaks, ethically?"

## 2. The NDA Treadmill — In-House Contract Review

**Setup.** *Cobalt Harbor Logistics, Inc.* is a regional freight and warehousing company with a one-lawyer legal department: you, plus a contracts manager who isn't a lawyer. The business signs 30–40 inbound NDAs and small vendor agreements a month, each one "urgent," each one a counterparty's paper. Your job is to turn around redlines against the company's playbook positions (governing law, indemnity caps, auto-renewal, data handling) within two business days without becoming the bottleneck that makes sales route around legal. Stakes per contract are modest; stakes in aggregate — one bad indemnity in 400 contracts a year — are not.

**Ethics tensions.** Competence (R. 1.1) leads: the failure mode is the clause the model *didn't* mention — models are much better at describing what's present than noticing what's absent. Supervision (R. 5.1/5.3) is the live second thread, because the realistic design has the non-lawyer contracts manager running the first pass, and Op. 512 treats the tool itself as something you supervise like a nonlawyer assistant.

**Difficulty: 2/5.** Most approachable scenario on the menu — short documents, clear playbook, repeatable task. The trap is building a workflow that merely summarizes contracts instead of one that reliably catches deviations *and* omissions against a defined standard.

**Free-tool feasibility.** Excellent. Build a synthetic playbook (one page) and a set of synthetic NDAs with planted deviations; everything pastes into a free-tier chat. NotebookLM holds the playbook as a grounding source. Design for ≤10 model turns per contract.

**Example stress-tests:**
- A counterparty NDA that silently *deletes* the mutuality of the confidentiality obligation rather than adding anything. Does the workflow catch what's missing?
- An exhibit incorporated by reference that contains a one-sided indemnity the main body never mentions. Does your prompt even ask about exhibits?
- "Your contracts manager has been accepting the AI's 'no issues' output and signing off without reading the contract. Show me the part of your workflow design that prevents that — or admit it doesn't."

## 3. The Brief Factory — Litigation Brief Drafting

**Setup.** You're a second-year associate at *Tallgrass & Beech LLP*, a 40-lawyer litigation firm in Indianapolis, working commercial disputes in the S.D. Ind. and Marion County Superior Court. You draft 2–3 substantive filings a month — motions to dismiss, summary-judgment briefs, discovery motions — under partners who edit hard and bill harder. The recurring task: turn a research memo and a fact record into a first draft fast, without ever filing a *Mata v. Avianca*. The stakes are sanctions, Rule 11, your bar card, and the firm's name in a benchslap opinion.

**Ethics tensions.** Candor toward the tribunal (R. 3.3) is the headline duty — fabricated authority in a filing is the canonical AI disaster, and your verification design is the whole ballgame. Competence (R. 1.1) runs right beside it: Op. 512 says you must understand the tool well enough to know that a consumer model's citations are *unverified by default*.

**Difficulty: 3/5.** Drafting is easy; trustworthy drafting is not. The hard part is a verification protocol that is genuinely systematic — every cited authority, every quotation, every characterization of a holding — and still fast enough that the workflow saves time at all. If verification eats the savings, say so in the memo; that's a finding, not a failure.

**Free-tool feasibility.** Strong, with one honest limitation: free consumer models cannot do citation-grounded research, which is precisely the lesson. Verify against free sources — CourtListener, Google Scholar, court websites. Synthetic fact pattern, real doctrine. *Pro-tool note:* this is the scenario where Westlaw Precision AI / Lexis+ AI genuinely differ (linked, real authority); if you can demo the contrast, it strengthens the memo — but the free workflow must stand alone.

**Example stress-tests:**
- The examiner asks your workflow to draft argument for a deliberately weak proposition. Does the model fabricate supporting authority, and does your verification pass catch all of it — including the plausible-looking pin cite to a real case that doesn't say that?
- A real case in your draft was overruled in 2025. Does anything in your workflow check subsequent history, or do you only verify that cases *exist*?
- A "quotation" in the output is actually a paraphrase inside quotation marks. Find it.

## 4. The Comment Window — Agency Rulemaking Comments

**Setup.** You're counsel to the *Prairie Current Energy Alliance*, a fictional trade association of 40 small wind and solar developers across the Midwest. Six to ten times a year a federal or state agency proposes a rule that hits your members — interconnection standards, permitting timelines, tax-credit implementation — and you have a 60-day comment window to digest a 200-page proposal, figure out what actually changed, poll members for impact, and file a comment letter the agency must take seriously. Stakes: comments that misstate the proposal get ignored; comments that invent supporting data embarrass the association on a public docket, permanently.

**Ethics tensions.** Competence (R. 1.1) dominates — the core risk is misreading a long, technical document and building advocacy on a provision that doesn't say what you claim. Candor has a public-docket flavor here: a comment letter citing studies that don't exist is *Mata v. Avianca* with a Regulations.gov docket number. Fees (R. 1.5) gets a clean look too: the association pays flat-fee per comment, so who captures the AI efficiency?

**Difficulty: 2/5.** Generous deadlines, public documents, no client secrets. The challenge is long-document discipline — proving the model's reading of a 200-page rule is accurate — and keeping generated advocacy tethered to facts your members actually gave you.

**Free-tool feasibility.** The best NotebookLM scenario on the menu: real proposed rules are public, free, and exactly the long-document use case NotebookLM grounds well. Use a real (or synthetic) proposed rule as doctrine-side material; all member impact data is synthetic.

**Example stress-tests:**
- The examiner asks: "Where exactly did the definition of 'qualifying facility' change from the prior rule?" Your workflow must produce a page-cited answer, not a vibe.
- Inspect the draft comment for invented support — a "2024 NREL study" that doesn't exist, a member impact statistic nobody supplied.
- Compress the deadline to 5 days. Which verification steps does your workflow drop, and can you defend the ones you kept?

## 5. The Petition Line — Immigration Petition Prep

**Setup.** *Kantor & Reyes Immigration Law* is a two-lawyer, one-paralegal firm in Indianapolis handling about 200 matters a year — family-based petitions, employment petitions, naturalization — mostly flat-fee. Each matter is the same skeleton (forms, supporting declaration, evidence index, cover letter) wrapped around facts that are unique, personal, and frequently in another language. The recurring task is assembling a complete, internally consistent petition package. Stakes: a date inconsistency between a declaration and an I-94 can trigger an RFE or a denial, and behind every file is a family's status in the country.

**Ethics tensions.** Confidentiality (R. 1.6) bites hard and concretely — these files are dense with PII from vulnerable clients, so deciding what's allowed into a consumer tool (and what gets anonymized first) is the central design problem. Fees (R. 1.5) bites in a way most scenarios don't: in a flat-fee practice, Op. 512's fee discussion cuts the other way — efficiency is yours to keep, but the temptation to under-verify scales with it. Communication (R. 1.4) deserves a paragraph: will you tell clients AI touched their file?

**Difficulty: 3/5.** Forms work punishes small errors; declarations involve translation and voice; and the anonymization layer must be real, not decorative. Cross-matter contamination (two clients, similar facts, one chat session) is a failure mode unique to volume practice.

**Free-tool feasibility.** Good. USCIS forms and instructions are public. All client facts are synthetic — invent two or three full client files. Build the anonymize-before-prompt step as an explicit, demonstrable stage. Keep declarations short enough to paste.

**Example stress-tests:**
- Two synthetic clients with similar names and overlapping fact patterns processed in sequence. Does client A's employer show up in client B's declaration?
- A planted inconsistency: the declaration says entry in March 2024, the synthetic I-94 says May 2024. Does the workflow's consistency check catch it, or does the model paper over it with confident prose?
- "Show me precisely what text left your machine when you drafted this declaration. Now show me the engagement-letter language that told the client it would."

## 6. The Disclosure Dump — Criminal Defense Discovery Triage

**Setup.** You're an assigned attorney at the *Calloway County Public Defender's Office* (an invented county) carrying 90 open felony files. On a mid-level case the state's discovery arrives as a dump: 200+ pages of police reports and supplements, hours of bodycam, a phone-extraction report, jail calls. You have, realistically, two hours per case to find what matters — the suppression hook, the inconsistency, the buried exculpatory line. The recurring task is triage: turn the dump into a defense-oriented map of the record. Stakes: someone's liberty, and the exculpatory detail you don't find doesn't exist.

**Ethics tensions.** Competence (R. 1.1) is everything here, in its sharpest form: the AI failure mode that matters is *recall* — what the summary left out — and Op. 512 demands you understand that summarization quietly flattens contested allegations into stated facts. Confidentiality (R. 1.6) is structurally hard too: discovery material about your client (and witnesses) heading into a consumer tool is a serious question your memo must answer head-on.

**Difficulty: 4/5.** Volume collides with free-tier limits; the core skill being tested (noticing absence) is the thing models are worst at; and the stakes argument in your memo has to grapple with whether this workflow should exist at all in its strongest form. A great memo here includes a clear "what I would never let the AI do" boundary.

**Free-tool feasibility.** Workable at teaching scale. Build a synthetic discovery set — 5–8 invented police reports, a synthetic transcript, a call log — sized for NotebookLM. You can't demo real volume; instead, demo the *method* (chunking, structured extraction, the recall check) and address scaling honestly in the memo.

**Example stress-tests:**
- One exculpatory sentence buried in supplement #6 of the synthetic reports (the answer key knows where). Does your workflow surface it, and would you know if it hadn't?
- The synthetic transcript misattributes two speakers. Does the AI's summary inherit the error and harden it into "the defendant said"?
- "Your summary describes the officer's account as fact. Find the place in your prompt design that caused that — and fix it live."

## 7. The Tuesday-Night Clinic — Nonprofit Advice Clinic

**Setup.** *Harbor Light Community Legal Clinic* runs a Tuesday-evening brief-advice session: 30 walk-in clients, tenant problems, debt collection, expungements. Staffing is two staff attorneys, a rotating cast of volunteer lawyers from local firms, and law students. The recurring task is producing accurate, plain-language advice letters and next-step checklists in a 20-minute consult window — and the clinic's director wants AI to help volunteers who don't know landlord-tenant law cold. Stakes: clients with no other access to counsel acting on whatever the letter says.

**Ethics tensions.** Supervision (R. 5.1/5.3) is the spine of this one: the workflow's real product is a *system* in which non-experts use AI under attorney oversight — exactly the structure Op. 512's supervision discussion contemplates. Competence (R. 1.1) follows (wrong-jurisdiction law is the classic failure), and scope-of-representation discipline is the sleeper issue: brief advice has edges, and the AI doesn't know where they are.

**Difficulty: 3/5.** Technically gentle, architecturally demanding. You're designing review gates, escalation triggers, and templates for *other people* — and the memo must defend why a volunteer plus AI plus your gate equals competent representation.

**Free-tool feasibility.** Excellent. Short documents, synthetic clients, public landlord-tenant statutes. NotebookLM grounded on the (real, public) Indiana Code chapter is a legitimately strong build. Free-tier caps fit a 20-minute consult model naturally.

**Example stress-tests:**
- A volunteer pastes the AI's draft letter to the client verbatim, unreviewed. Walk through the workflow and show the specific step that makes that impossible — not just discouraged.
- A synthetic tenant consult that midway reveals an immigration consequence. Does the workflow detect that the question has left the clinic's scope, or does the AI cheerfully answer it?
- The model confidently cites Ohio's security-deposit deadline for an Indiana client. Where does your design catch jurisdiction drift?

## 8. The Data Room — Transactional Due Diligence

**Setup.** You're an associate at *Vance & Adler LLP* representing *Tamarack Ridge Logistics, Inc.* in its acquisition of *Juniper Stack Software Co.* Diligence means a data room of ~150 documents — customer contracts, employment agreements, IP assignments, board minutes — and your job is the diligence memo: change-of-control triggers, assignment restrictions, missing IP assignments, anything that moves price or kills the deal. Timeline is three weeks; the partner wants issues, not summaries. Stakes: a missed consent requirement surfaces after closing, and the firm's malpractice carrier learns your name.

**Ethics tensions.** Confidentiality (R. 1.6) at deal intensity: the data room is someone else's confidential material under an NDA, possibly with MNPI implications, and your memo must define an information architecture — what may touch which tool under what settings — before any prompting starts. Competence (R. 1.1) is the close second: diligence is an *absence-detection* exercise (the unsigned IP assignment, the contract that *lacks* an assignment clause), the precise thing generative summarization is worst at.

**Difficulty: 4/5.** Multi-document reasoning, cross-referencing, and a deliverable judged on completeness. Free tiers force you to engineer around context limits, which is realistic — that's the actual skill — but it's work.

**Free-tool feasibility.** Demanding but doable. Build a synthetic data room of 12–18 short documents (the bible's planted-flaw rules apply: seed every issue and keep the answer key). NotebookLM is the natural home; structure extraction-then-aggregate rather than one giant prompt. *Pro-tool note:* this is where Harvey/CoCounsel-class tools genuinely differ (retrieval over a real corpus at scale) — instructor demo only.

**Example stress-tests:**
- The data room is salted with one privileged email and one document containing inside-information-flavored content. Did either ever enter a consumer tool? Prove it from your process log.
- A change-of-control clause drafted in deliberately nonstandard language ("in the event the Company undergoes a fundamental ownership event..."). Did your extraction prompt's pattern-matching miss it?
- The examiner picks one cell of your diligence summary chart and says: "Defend this. Show me the source document and the verification step that touched it."

## 9. The Second Pass — E-Discovery Privilege QC

**Setup.** *Sycamore Bend LLP* is defense counsel in a products-liability case, *Hollis v. Meridian Gearworks LLC*, No. 26-CV-90004 (S.D. Ind.). The discovery vendor, *Quarry Lake Discovery Partners*, ran an AI-assisted first-pass privilege review over 40,000 documents and delivered its calls. You're the associate who owns the second pass: design the QC process that lets a partner sign the Rule 26(g) certification with a straight face — sampling strategy, error-rate thresholds, escalation rules, and the clawback plan for when something slips anyway. Stakes: privilege waiver, sanctions, and a certification that turns out to be a bluff.

**Ethics tensions.** Supervision (R. 5.3) in its fullest Op. 512 sense — you are supervising a nonlawyer vendor *and* the vendor's AI, and "the vendor said the model is good" is not supervision. Candor (R. 3.3) and competence (R. 1.1) converge in the certification: signing Rule 26(g) over an AI-reviewed production means understanding, quantitatively, how confident you actually are.

**Difficulty: 5/5.** The hardest scenario on the menu, and the most defensible if you pull it off. It demands light statistics (sampling, confidence in an error rate), process design rather than prompting, and a memo that can survive "explain your sampling math to a judge." Choose this if you like systems.

**Free-tool feasibility.** The QC *design* is fully free-buildable; the 40,000-document scale is simulated. Build a synthetic review set of ~60 documents with known-correct privilege calls (your answer key), "receive" a first-pass call sheet with planted errors, and demo your sampling-and-escalation protocol catching them. A spreadsheet plus a free-tier model for second-look reads is the whole stack. Be explicit in the memo about what changes at real scale.

**Example stress-tests:**
- The examiner secretly flips five of the vendor's privilege calls in your synthetic call sheet. Does your sampling design detect an elevated error rate, or did luck decide?
- A privileged document slipped into the production set anyway. Run your clawback play in real time: who's notified, in what order, citing what.
- "Your memo says the error rate is 'acceptably low.' Give me the number, the sample size behind it, and what threshold would have made you reject the vendor's entire first pass."

## 10. The Watchtower — Regulatory Monitoring

**Setup.** You're the solo general counsel of *Lakemont Financial Technologies*, a 60-employee fintech making small-business loans in 12 states. Every week brings proposed rules, enforcement actions, and state-law amendments that could touch the product — CFPB activity, state lending-license changes, UDAP developments — and nobody but you is watching. The recurring task: a weekly regulatory digest for the CEO that catches everything material, in plain English, with a "do we care?" call on each item. Stakes: the amendment you miss becomes the exam finding, the consent order, or the product you must unwind.

**Ethics tensions.** Competence (R. 1.1) in its scariest form: this workflow is judged on what it *doesn't* surface, and hallucination runs both directions — a model can invent a regulation that doesn't exist or confidently assure you nothing changed when something did. Communication (R. 1.4) shapes the deliverable: the CEO acts on your digest, so calibrated confidence ("flagged, unverified") is an ethical feature, not a style choice.

**Difficulty: 4/5.** The recall problem is unsolvable in the strong sense, so the design challenge is honest scoping: defined sources, a verification step for every item that makes the digest, and an explicit statement of what the workflow does *not* cover. Free tiers offer no automation, which forces you to design the human cadence too.

**Free-tool feasibility.** Good, with caveats. Sources are public and free (agency sites, Federal Register, state regulator pages). Free tiers can't schedule anything — your design must specify the manual weekly routine and live within message caps. The demo runs on a frozen synthetic week: a curated source packet with planted developments, including decoys.

**Example stress-tests:**
- The examiner's synthetic source packet includes a fabricated "new CFPB rule" planted as hallucination bait, plus one real-looking state amendment with a changed effective date. The digest must keep the real one and kill the fake — show the verification step that did it.
- Three weeks of synthetic feed with exactly one buried material change. Does the workflow surface it, or has digest formatting trained the reader (and the model) into alert fatigue?
- "Your digest says 'no relevant developments in Indiana this week.' What, specifically, did the workflow check before letting you say that to your CEO?"

---

## After you choose

Selection happens at the Week 8 capstone workshop. Come with a first and second choice and a paragraph on why. From there the milestones in `capstone/` govern: scope (Weeks 1–4 material applied retroactively to your scenario), v1 build (Weeks 5–8), stress-testing (Weeks 9–12), and the final memo, demo, and Q&A (Weeks 13–14). The stress-tests listed above are *examples* — assume the examiner has read this menu and will bring variants you haven't seen.
