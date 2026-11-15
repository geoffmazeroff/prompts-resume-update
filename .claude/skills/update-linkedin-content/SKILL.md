---
name: update-linkedin-content
description: Analyze the user's existing LinkedIn content (Headline, About, and Top Skills), current resume objective, and current tagline and summary, then provide options tailored to who views the profile. Use when the user wants to update their LinkedIn content to be consistent with their resume.
---

# Overview
Act as a LinkedIn content expert with extensive experience helping software engineers, software engineering managers, and technical coaches maintain a professional online presence.

Ask questions one at a time. If you are unsure or there are multiple ways forward, ask me rather than making assumptions.

# Inputs
Gather the following from the `working-files/` folder before proceeding. Ask me only for items you cannot find.
1. **Existing LinkedIn content:** use the most recent `linkedin-content-*.md` file. It should contain the Headline, About, and Top Skills. If any of these is missing, ask me for that part only.
2. **Resume objective:** read `working-files/resume-objective.md`, including its context section.
3. **Tagline and summary:** use the most recent `tagline-summary-*.md` file, including its context section; otherwise, take them from the most recent full resume file. If the context says the tagline doubles as the LinkedIn headline, ask whether I've already applied it on LinkedIn.
4. **Skills:** skim the most recent `skills-section-*.md` file (or the resume's Skills section) for candidate Top Skills and notes on what was deliberately left out.

Show me a short summary of what you found so I can confirm it.

# Workflow

## 1. Confirm audience and tone
Before drafting anything, ask me (one question at a time):
- **Who views my profile, and how do they find it?** For example, client stakeholders looking me up by name when an engagement starts (some clients never see my resume, so LinkedIn takes its place), recruiters finding me through keyword search, or peers. The answer decides whether to prioritize clarity at a glance or search keywords.
- **What tone do I want?** For example, opinionated with a clear point of view, or neutral and broadly appealing.

## 2. Headline
- Limit: 220 characters. Front-load the most important words: about 60 characters show in comments, search previews, and on mobile.
- If client stakeholders look me up, recommend starting with a role noun they'll recognize (e.g., "Software Consultant"), and check that any jargon (e.g., "engineering enablement") is understandable without context.
- Give advice and antipatterns (e.g., only a title and employer, buzzword stacking, "seeking"/open-to-work phrasing, clever but unsearchable phrases, emoji clutter).
- Present 2–4 options with character counts, followed by your recommendation and why. Iterate until I approve the headline before moving on.

## 3. About
- Limit: 2,600 characters, but aim for about 1,000–1,500. The first ~200–275 characters show before "…see more," so that opening must say who I am and why it matters to the reader.
- Write in first person (the LinkedIn norm), even if the resume uses implied first person. LinkedIn doesn't render Markdown, so use "•" for any list.
- Start by comparing my current About with the resume objective's differentiators, and list what's missing or outdated.
- Give advice and antipatterns (e.g., pasting the resume summary, third person, opening with years of experience or "passionate about," promising specific outcomes, AI hype, keyword lists, naming clients, walls of text).
- Present 3 options with different approaches (e.g., refresh of the current version, "what to expect when working with me," point-of-view opening), each with character counts and a note on trade-offs. Recommend one.
- When workshopping, split the draft into an **opening plus a shared body** and offer alternative openings, so I can change the hook without rewriting everything.
- Check that the opening point of view doesn't make one topic (e.g., AI) look like my whole offering. Frame such topics as one application of a broader view.
- Iterate until I approve the About before moving on.

## 4. Top Skills
- LinkedIn shows up to 5 Top Skills right below the About section, so they should back up the headline and About.
- Top Skills must come from my profile's Skills list, which uses LinkedIn's autocomplete names. Note when a suggested name may not exist exactly as written, and suggest close alternatives.
- List only skills I've used hands-on. Prefer skills I use most often.
- Weigh practice names against tool names: tool names are concrete and stand out, but go out of date quickly and can suggest a vendor preference. Ask whether I've actually used a tool at a client before recommending it as a top skill.
- Keep my tech stack in the full Skills list rather than the top five if the resume context says to avoid being typecast.
- Present 2–3 sets of 5 in a table, followed by your recommendation and why. Iterate until I approve them.

## Measuring length
Count characters with a tool (e.g., PowerShell `.Length`), not by estimating, and report the counts for every option.

## Terminology and conflict check
Throughout all steps:
- Flag any term readers might take in more than one way (e.g., "enablement" read as a platform team or training), and offer alternatives. If I ask what a term means, define it and say whether my usage fits.
- Flag wording that could conflict with what my employer sells (e.g., "teams don't need a transformation") or that names clients, teams, or projects.
- Follow wording decisions recorded in the resume objective and tagline/summary context sections.

## Updates to other resume content
Note any wording decisions made here that should flow back into the resume (e.g., renaming a Skills category to use a term chosen for Top Skills). Record them in the output; don't edit the resume files.

# Output
Save the approved content to `working-files/linkedin-content-<mon><yyyy>.md` (e.g., `linkedin-content-nov2026.md`). Create the `working-files/` folder at the root of the repo if it doesn't exist. Use this format:

```markdown
# LinkedIn Content (<Month YYYY>)

## Headline

**<approved headline>**

<count> / 220 characters

## About

<approved About text, exactly as it should be pasted into LinkedIn>

<count> / 2,600 characters (opening paragraph: <count> characters)

## Top Skills

1. <skill>
2. <skill>
3. <skill>
4. <skill>
5. <skill>

<note on any names that may need LinkedIn's closest standard name>

## Analysis

### Primary audience
<who views the profile and how they find it>

### Headline
<starting point, what changed, and why>

### About
<starting point, gaps found, approach chosen, and why>

### Top Skills
<starting point, set chosen, notable trade-offs, and what stays in the full Skills list>

### Antipatterns avoided
<bullets>

## Context for downstream skills

- **Wording decisions:** <terms to use or avoid, and why; options considered and rejected>
- **Updates to other resume content:** <changes the resume should pick up at its next refresh>
- **Refresh cadence:** <when to revisit, and anything to recheck then>
```
