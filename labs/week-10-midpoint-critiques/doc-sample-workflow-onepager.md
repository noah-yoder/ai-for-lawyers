---------------------------------------------------------------
FICTIONAL — CREATED FOR TEACHING
All parties, facts, and documents are invented for AI for
Lawyers (IU McKinney). Any resemblance to real persons,
companies, or matters is coincidental. Not legal advice.
---------------------------------------------------------------

# Capstone v1 Workflow One-Pager — SAMPLE FOR CRITIQUE

**Author:** Jordan Bellamy, 3L (fictional student)
**Capstone scenario:** Small-firm commercial lease abstraction pipeline
**Version:** v1 — submitted for mid-point critique

---

## Practice scenario

Garner & Pruitt LLP is a two-lawyer real estate firm in Indianapolis. The firm represents Cobalt Harbor Logistics, Inc., which leases 14 warehouse properties across Indiana and Ohio. Ahead of a refinancing targeted for September 2026, the client's lender wants a portfolio-wide abstract of key lease terms. The engagement letter was signed in March 2026; the firm quoted the work on its standard hourly rates.

## The task

Abstract all 14 commercial leases (each 18–40 pages, executed between 2021 and 2025) into a one-row-per-lease summary tracker covering: landlord entity, current base rent, term and expiration, renewal options, assignment/subletting restrictions, CAM cap, and early-termination rights.

## Tools

- ChatGPT (free tier) for the abstraction itself
- Google Sheets for the tracker (shared with the client contact for real-time visibility)

## Workflow (v1)

1. Scan and OCR each lease; copy the full text.
2. Paste the full lease text — including party names, addresses, and rent figures — into ChatGPT with the prompt below.
3. The model returns a completed table row. Paste the row directly into the shared Google Sheets tracker (the client contact has view access to the live sheet).
4. Repeat for all 14 leases. Estimated time: ~15 minutes per lease.
5. Quality check: for each lease, eyeball 2–3 fields that look off. If a field seems wrong, ask ChatGPT to double-check its own answer and use whichever answer it gives the second time.
6. Email the tracker link to the client contact and the lender's counsel.

## The prompt

```
You are a commercial real estate paralegal. Read the lease below and return a single
table row with these columns: Landlord entity | Current base rent | Term and expiration
| Renewal options | Assignment/subletting restrictions | CAM cap | Early-termination
rights. Quote section numbers where you can. Also note any unusual or risky clauses I
should worry about.

LEASE TEXT:
[paste full lease text]
```

## Confidential-information handling

ChatGPT's privacy policy keeps conversations private, so client confidentiality is covered. The leases aren't filed under seal or anything — they're ordinary commercial documents.

## If the tool gets something wrong

OpenAI's terms commit to professional-grade accuracy, so material errors would be on them, not the firm. The eyeball check in step 5 catches anything obvious.

## Billing note

Abstraction used to take about 2 hours per lease by hand. With this workflow it takes about 15 minutes. I plan to keep billing the standard 2 hours per lease, since the client receives the same finished product either way.

## What I think is strong about this design

- The abstract fields are defined up front, before any lease is processed.
- The same prompt is used for every lease, so the output format is consistent across the portfolio.
- The client gets real-time visibility into progress through the shared sheet.

## Open questions for reviewers

- Is the spot-check in step 5 enough verification, or should I check more fields?
- Should I be using Claude instead of ChatGPT for long documents?
