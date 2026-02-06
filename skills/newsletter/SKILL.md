---
name: newsletter
version: 1.0.0
description: When the user wants to create, draft, or work on a monthly product update newsletter. Also use when the user mentions "newsletter," "monthly update," "product newsletter," "what's new email," or "monthly summary for customers."
---

# Monthly Newsletter Skill

This skill helps draft monthly product update newsletters by gathering updates, asking contextual questions, and creating a newsletter draft in Peter's voice that gets published to Confluence.

## Overview

The newsletter workflow:
1. Gather updates from accoil.com/whatsnew
2. Ask Q&A questions to add context and voice
3. Draft the newsletter in Peter's casual, first-person style
4. Create a Confluence page in Marketing and Sales space

## Step 1: Load Context

Before starting, read Peter's product marketing context to understand Accoil's positioning, voice, and messaging:

```
~/.claude/skills/newsletter/context/product-marketing-context.md
```

Also read the voice guide and template references:
- `~/.claude/skills/newsletter/references/voice-guide.md`
- `~/.claude/skills/newsletter/references/newsletter-template.md`

## Step 2: Gather Updates

Ask the user:
1. **Which month is this newsletter for?** (e.g., "February 2026")
2. **Paste the updates from https://www.accoil.com/whatsnew** - Ask them to copy and paste the content from the What's New page

The pasted content will typically include:
- Update titles/headlines
- Brief descriptions of each feature or improvement
- Dates when updates were released

Parse this content to extract individual updates. Group them by significance (major features vs. smaller improvements).

## Step 3: Q&A Framework

Ask the following questions to gather context and voice:

### Main Highlights
**Question:** "Which updates would you consider the main highlights for this month? (1-2 features that deserve their own section)"

Use the user's response to identify which updates get full feature sections.

### For Each Major Feature
For each highlight feature identified, ask:

**Questions:**
1. "Who is [feature name] for? What's the target audience or use case?"
2. "Why does [feature name] matter? What problem does it solve or value does it unlock?"
3. "Any additional context to include? (early access info, calls to action, links, etc.)"

### Smaller Updates
**Question:** "Looking at the remaining updates, which ones should go into the 'A few smaller things' section?"

### What's Next (Optional)
**Question:** "What's coming next month or in the pipeline? (This section is optional — leave blank if nothing to share)"

### Founder's Note (Optional)
**Question:** "Do you want to include a founder's note or personal message? (Optional — can be about team updates, company milestones, reflections, etc.)"

## Step 4: Voice Guidelines

Peter's newsletter voice is:
- **Casual and friendly** - "Howdy y'all", conversational tone
- **First person from Peter** - "I'm excited to share", personal perspective
- **Clear and helpful** - Explains what features are and why they matter
- **Organized and scannable** - Clear sections, bullets for minor items
- **Action-oriented** - Includes CTAs where appropriate (sign up, book demo, try feature)

**Style patterns from Peter's writing:**
- Opens with warm greeting: "Howdy y'all 👋"
- Sets context for the month: "[Month] is [nearly a wrap/here/etc]"
- Teases highlights: "including [exciting feature]"
- Uses subheadings for each major feature
- Includes "Who's this for?" sections to clarify target audience
- Groups minor updates under "A few smaller things"
- Ends with "What's next" preview and personal sign-off
- Signs as "Peter" on behalf of the Accoil team

**What to avoid:**
- Press release language or corporate jargon
- Buzzwords and marketing-speak
- Overly technical explanations
- Impersonal third-person voice

## Step 5: Newsletter Structure

Use this template structure:

```
Howdy y'all 👋

[Month YYYY] is [nearly a wrap / here / etc]. Here's what landed in [Month], including [teaser for 1-2 highlight features].

[Major Feature 1 Headline]
[1-2 paragraph description of what it is and what it does. Make it conversational and clear. Explain the context and value.]

Who's this for?
[Target audience and specific use cases. Be concrete about who benefits and how they'd use it.]

[Any additional context: early access info, how to enable it, call to action, relevant links]

[Major Feature 2 Headline]
[Same pattern as Feature 1]

Who's this for?
[Target audience and use cases]

[Additional context]

A few smaller things
- [Minor update 1 - one line description]
- [Minor update 2 - one line description]
- [Minor update 3 - one line description]
- [Continue for all smaller updates]

What's next
[1-2 paragraphs about upcoming work, areas of focus, things in the pipeline. This section can be skipped if nothing to share.]

[FOUNDER'S NOTE - OPTIONAL]
[If provided, include personal note from Peter here - could be about team, company milestones, reflections, etc.]

On behalf of the whole Accoil team: [closing message thanking readers, encouraging feedback, expressing excitement, etc.]

Peter
```

## Step 6: Draft the Newsletter

Using all the gathered information:
1. Follow the template structure above
2. Write in Peter's casual, first-person voice
3. Make sure each major feature has:
   - Clear headline
   - Description of what it is/does
   - "Who's this for?" section
   - Any relevant context or CTAs
4. Include all minor updates in bulleted list
5. Add "What's next" if content was provided
6. Include founder's note if provided
7. Write a warm closing message

**Important:** The newsletter should feel personal and conversational, not like marketing copy. Write as if Peter is directly emailing customers with updates.

## Step 7: Create Confluence Page

After drafting the newsletter and showing it to the user for review, create a Confluence page with:

- **Space:** Marketing and Sales
- **Parent page:** Product Update Emails
- **Page title:** Newsletter Draft - [Month Year]
  - Example: "Newsletter Draft - February 2026"
- **Content:** The full newsletter content

Use available Confluence MCP tools to create the page. The Atlassian Rovo MCP Server is configured and available.

After creating the page, provide the user with:
1. Confirmation that the page was created
2. Link to the Confluence page
3. Next steps (review, edit, send)

## Tips for Success

- **Read the context files first** - Understanding Peter's voice and Accoil's positioning is critical
- **Ask clarifying questions** - Better to ask than guess about which features are highlights
- **Keep it conversational** - This is Peter talking to customers, not a corporate announcement
- **Be specific in "Who's this for?"** - Concrete use cases are more helpful than vague audience descriptions
- **Don't overthink minor updates** - One line per item is fine for the "smaller things" section
- **Respect optional sections** - If there's no "What's next" or founder's note, that's fine

## Example Flow

1. User runs `/newsletter`
2. Skill asks: "Which month is this newsletter for?"
3. User: "February 2026"
4. Skill asks: "Please paste the updates from https://www.accoil.com/whatsnew"
5. User pastes content
6. Skill parses updates, asks: "Which updates are the main highlights?"
7. User identifies 2 major features
8. Skill asks detail questions about each major feature
9. Skill asks about minor updates, what's next, founder's note
10. Skill drafts newsletter in Peter's voice
11. Skill shows draft to user for review
12. Skill creates Confluence page in Marketing and Sales > Product Update Emails
13. Skill provides link and next steps
