# Lab 0 Handout: The AI Tool Landscape — A Hands-On Tour

*AI for Lawyers — Week 1. Bring this sheet and your laptop to every lab.*

You're a junior associate at the firm representing **Cobalt Harbor Logistics, Inc.** A demand letter just landed (it's in the course materials: `doc-demand-letter-meridian-cobalt.md` — everything in it is fictional, invented for this course). You have three free AI tools and 40 minutes. Your job today isn't to answer the letter — it's to find out what each tool is actually for.

**House rule, starting now and for the whole semester:** nothing real ever goes into a consumer AI tool — no real client, employer, or personal-legal-matter facts. In this course you will only ever paste documents we invented. Why this rule exists is Week 4.

## The map: three tiers of legal AI

| Tier | Tools | What it's connected to | When it cites authority... |
|---|---|---|---|
| **1. Consumer chatbots** | ChatGPT, Claude, Gemini | Nothing — open generation from training | ...it's generating text that *looks like* authority. Verify everything. |
| **2. Grounded notebooks** | NotebookLM | Only the sources you upload | ...it cites back into *your* documents — and can't see past them. |
| **3. Professional legal AI** | Westlaw Precision AI, Lexis+ AI, CoCounsel, Harvey | Real legal corpora + your documents | ...citations are real and linked. Judgment is still yours. |

Same engine family throughout. What differs is what each tool is **connected to** and what it's **allowed to say**.

## The exercise

Fill in your scorecard **immediately after each step** — specifics, not vibes. Quote the output. If you hit a rate limit in one chatbot, switch to the other; the prompts work in both.

### Step 1 — Same prompt, two engines (~10 min)

Run Prompt 1A in **ChatGPT**, then the identical prompt in a fresh **Claude** chat. Paste the full demand letter where indicated.

Prompt 1A:

```
I'm a junior associate at a firm that represents Cobalt Harbor Logistics, Inc.
Below is a demand letter our client just received. In plain English:
(1) summarize what the sender is claiming and demanding,
(2) identify the sender's strongest point, and
(3) identify the weakest point or anything in the letter that looks off.
Keep it under 250 words.

[PASTE THE FULL DEMAND LETTER HERE]
```

Compare the two outputs: structure, tone, hedging, what each flagged as "off." Did either tool notice anything wrong with the *numbers* in the letter? The *dates*?

### Step 2 — Ask for authority (~10 min)

In the **same chats** (both tools), run Prompt 1B:

```
What Indiana cases support or undercut the claims in this demand letter?
Give me 3 cases with full citations and one sentence each on why each matters.
```

Note how confident each tool sounds. Then, when prompted, **compare citation lists with your neighbor**: same prompt, same letter — did any two of you get the same cases?

### Step 3 — The grounded tool (~10 min)

Open **NotebookLM** (use a *personal* Google account — university accounts may be blocked). Create a notebook, choose **"Copied text"** as the source type, and paste the demand letter. Then ask, in the notebook chat:

Prompt 1C:

```
Summarize this demand letter in plain English. Then list three specific facts
a defense lawyer would want to know that the letter does NOT provide.
```

Prompt 1D:

```
What Indiana cases support the sender's legal position?
```

Watch two things: the inline citations on the summary (click one), and what the tool does when asked for case law it doesn't have. Compare that to Step 2.

### Step 4 — Pro-tool demo (~6 min)

Eyes on the screen — your instructor will run the same task in a professional legal tool. Fill in row 4 of the scorecard from what you observe: what did it do that your free tools didn't? What did it still leave for the lawyer?

### Finished early?

Run this in either chatbot and compare its self-assessment against your scorecard:

```
What kinds of legal tasks should I NOT rely on you for, and why?
Be specific and honest about your own limitations.
```

## Scorecard *(this is your graded lab artifact — be specific, quote the output)*

| Tool | What it did well (quote/specifics) | Where it wobbled or failed | Citations: did it give any? Could you verify them? | Hand to a partner as-is? (Y/N — why) |
|---|---|---|---|---|
| ChatGPT | | | | |
| Claude | | | | |
| NotebookLM | | | | |
| Pro tool (demo): ____________ | | | | |

## Before you leave: the Op. 512 line

ABA Formal Opinion 512 (2024) says competent use of generative AI — a duty under Model Rule 1.1 — requires "a reasonable understanding of the capabilities and limitations" of the specific tool you're using. You can't get that understanding from a headline or a vendor demo. You just got 40 minutes of it firsthand.

**In two sentences, in your own words:** one capability and one limitation you observed today that you couldn't have described this morning.

&nbsp;

&nbsp;

*Turn in this sheet (or a photo of it) before you leave. Next week: prompting fundamentals and failure modes — including where those Step 2 citations actually came from.*
