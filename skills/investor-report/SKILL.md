---
name: investor-report
version: 1.0.0
description: When the user wants to create, draft, or work on a quarterly investor report or investor update. Also use when the user mentions "investor report," "investor update," "quarterly update," "board update," "investor highlights," "investor lowlights," or "quarterly report for investors."
---

# Quarterly Investor Report Skill

This skill helps draft quarterly investor reports by walking Peter through a structured Q&A across key business areas, then producing a polished report ready to send to investors.

## Overview

The investor report workflow:
1. Confirm which quarter and year the report covers
2. Walk through product Q&A
3. Walk through sales/marketing/growth Q&A
4. Gather highlights and lowlights
5. Gather next quarter plans
6. Gather support needed and specific asks of investors
7. Draft the full investor report
8. Optionally save to Confluence

## Step 1: Load Context

Before starting, read Peter's product marketing context to understand Accoil's positioning, product, and business model:

```
~/.claude/skills/newsletter/context/product-marketing-context.md
```

Also read the report template reference:
```
~/.claude/skills/investor-report/references/report-template.md
```

## Step 2: Set the Quarter

Ask the user:
- **Which quarter and year is this report for?** (e.g., "Q1 2026")

Use this to frame all questions and the final report.

## Step 3: Product Q&A

Walk through the product side of the business. Ask these questions one section at a time — don't dump them all at once. Wait for answers before moving to the next question.

### 3a. Product Progress
**Question:** "Let's start with the product side. What were the major product milestones or releases this quarter?"

Follow-up based on their answer:
- "Which of these had the biggest impact on customers or the business?"
- "Were there any releases that didn't land as expected or that you'd do differently?"

### 3b. Product Metrics
**Question:** "Any product metrics worth sharing? Things like: active accounts, feature adoption, engagement trends, activation rates, time-to-value improvements?"

Only ask for what's relevant — don't force metrics that don't exist yet.

### 3c. Technical & Infrastructure
**Question:** "Anything notable on the technical/infrastructure side? Platform improvements, scalability, integrations, reliability?"

This is optional — skip if there's nothing meaningful to share.

## Step 4: Sales / Marketing / Growth Q&A

Now shift to the go-to-market side. Same approach — one section at a time.

### 4a. Revenue & Pipeline
**Question:** "Let's talk about sales and growth. How did revenue and pipeline look this quarter? Any notable wins, losses, or changes in deal dynamics?"

Follow-ups based on their answer:
- "What's driving the wins? Any patterns in who's buying and why?"
- "Any deals lost or stalled? What were the reasons?"

### 4b. Customer Traction
**Question:** "How's customer traction looking? New logos, expansions, churn, retention — what's the story this quarter?"

### 4c. Marketing & Demand Gen
**Question:** "What about marketing and demand generation? What's working, what's not? Any channel or strategy shifts?"

### 4d. Key Metrics
**Question:** "Any key business metrics to include? Things like: MRR/ARR, growth rate, customer count, pipeline value, CAC, LTV, burn rate — whatever you're tracking and comfortable sharing."

## Step 5: Highlights & Lowlights

### 5a. Highlights
**Question:** "What are the top 3-5 highlights for the quarter? These are the wins you're most proud of — could be product, sales, team, partnerships, anything."

### 5b. Lowlights
**Question:** "Now the honest part — what are the top 2-3 lowlights? Things that didn't go as planned, missed targets, setbacks, lessons learned."

Encourage honesty here. Investors respect transparency over spin.

## Step 6: Next Quarter Plans

### 6a. Strategic Direction
**Question:** "Looking ahead to next quarter — are there any major pivots, strategic shifts, or changes in direction?"

### 6b. Key Priorities
**Question:** "What are the top 3-5 priorities for next quarter? What's the team going to be focused on?"

### 6c. Risks & Concerns
**Question:** "Any risks or concerns you're watching heading into next quarter?"

## Step 7: Investor Support & Asks

### 7a. Areas of Support
**Question:** "Where could your investors be most helpful right now? Common areas: introductions to potential customers, hiring, strategic advice, industry connections, follow-on funding."

### 7b. Specific Asks
**Question:** "Do you have any specific, concrete asks of your investors this quarter? The more specific, the better — investors can act on 'introduce me to [type of person] at [type of company]' much more than 'help with sales.'"

## Step 8: Draft the Report

Using all the gathered information, draft the investor report following the template in `references/report-template.md`.

### Voice Guidelines

The investor report voice should be:
- **Direct and honest** — No fluff, no spin. State facts clearly.
- **Confident but grounded** — Celebrate wins without overselling. Acknowledge challenges without catastrophizing.
- **Data-informed** — Include numbers where available. Investors want signal, not noise.
- **Action-oriented** — Especially in the "asks" section. Make it easy for investors to help.
- **Concise** — Investors read many updates. Respect their time. The full report should be readable in 5-10 minutes.

**What to avoid:**
- Corporate jargon or buzzwords
- Burying bad news or avoiding hard truths
- Vague asks ("help with growth" instead of specific requests)
- Overly long narratives when bullets would do
- Metrics without context (always include direction and why it matters)

### Report Structure

Follow the template structure from `references/report-template.md`. Key sections:

1. **TL;DR** — 3-4 bullet summary of the quarter
2. **Highlights** — Top wins
3. **Lowlights** — Honest setbacks
4. **Product Update** — What shipped, what's working, metrics
5. **Sales & Growth Update** — Revenue, pipeline, traction, marketing
6. **Key Metrics** — Dashboard-style numbers (if available)
7. **Next Quarter** — Priorities, direction, risks
8. **Support & Asks** — How investors can help + specific requests
9. **Closing** — Brief personal note

## Step 9: Review & Save

After drafting:
1. Present the full report to Peter for review
2. Ask if anything needs to be adjusted, added, or removed
3. Once approved, offer to create a Confluence page:
   - **Space:** Marketing and Sales
   - **Page title:** Investor Update - [Quarter] [Year]
   - Example: "Investor Update - Q1 2026"

## Tips for Success

- **Ask one section at a time** — Don't overwhelm with all questions at once. Work through each area conversationally.
- **Follow up on interesting threads** — If Peter mentions something notable, dig deeper before moving on.
- **Encourage specificity** — Push for concrete numbers, names, and examples over generalities.
- **Normalize lowlights** — Remind Peter that investors value transparency. Lowlights with lessons learned build trust.
- **Make asks actionable** — Help Peter refine vague requests into specific, actionable asks.
- **Keep the draft tight** — Investors skim. Every sentence should earn its place.
- **Use the product context** — Reference Accoil's positioning and business model from the product marketing context file to frame updates accurately.

## Example Flow

1. User runs `/investor-report`
2. Skill asks: "Which quarter and year is this report for?"
3. User: "Q1 2026"
4. Skill walks through product Q&A (milestones, metrics, tech)
5. Skill walks through sales/marketing/growth Q&A (revenue, traction, marketing, metrics)
6. Skill asks for highlights (3-5 wins)
7. Skill asks for lowlights (2-3 setbacks)
8. Skill asks about next quarter (direction, priorities, risks)
9. Skill asks about investor support and specific asks
10. Skill drafts the full investor report
11. Peter reviews and provides feedback
12. Skill revises if needed
13. Skill offers to save to Confluence
