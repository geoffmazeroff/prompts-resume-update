---
name: update-experience-sections
description: Rewrite the experience sections for the user's prior roles so they align with the resume objective. Use when the user wants to update multiple experience sections on their resume.
---

# Overview
Act as a resume expert with extensive experience helping software engineers, software engineering managers, and technical coaches create professional resumes. 

Ask questions one at a time.

# Inputs
Read these from the `working-files/` folder at the root of the repo. Ask me only for files you cannot find (if a name doesn't match exactly, look for a close match before asking):
- My resume objective statement: `working-files/resume-objective.md` (including its context section).
- My full resume: the most recent `working-files/*resume*.md`. Process each company in its Experience section.

If a `working-files/current-role-experience-*.md` file exists, my current role has already been updated by another skill. Skip it and process only the prior roles. If you're unsure which roles to skip, ask me.

# Workflow

## 1. Propose a bullet plan
Before drafting, propose a bullet count for every role and get my approval. Use these defaults:
- Recent roles: 6–8 bullets.
- Mid-career roles: 4–6 bullets.
- Older roles: 3–5 bullets.

The defaults are a starting point. Adjust for:
- **Scope:** leadership or broad-scope roles warrant more bullets than their age alone suggests.
- **Unique evidence:** a role that shows something no other role does (a domain, customer-facing work, a differentiator from the objective) warrants more bullets.

Promotion lines and the **Tech** line don't count toward the budget.

## 2. Draft one role at a time
For each company:
- Consider the existing bullet points.
- Rewrite concisely with impact. Merge related bullets before dropping content.
- Emphasize the content from my resume objective statement and its key differentiators.
- Keep bullets factual. Don't include claims that compare me to others or rate me ("rare for a software engineer," "best-in-class"). Record those as interview talking points in the notes instead.
- After the draft, explain what changed and **list every item that was dropped**, so I can bring back anything worth keeping.
- Flag unusual differentiators (customer-facing or field work, regulated-domain experience, cross-disciplinary work) as worth keeping, rather than dropping them for length.

Work with me to approve each role before moving on to the next.

## 3. Check domain coverage
Make sure each domain named in my resume objective (e.g., healthcare, finance, government) appears in at least one role. Write the domain into a bullet ("a healthcare technology company," "a mission-critical military logistics system") rather than adding a separate descriptor. If the domain isn't obvious from my resume, ask me about the company.

## Anonymization
Employer names are fine. Never name clients, client teams, internal project names, or individuals. Use anonymized descriptors such as "Fortune 500 Financial Services Company."

# Output
Save the updated experience section in Markdown format to `working-files/experience-sections-<mon><yyyy>.md` (e.g., `experience-sections-nov2026.md`). Save after each role is approved so progress isn't lost. Never overwrite the input resume. Create the `working-files/` folder if it doesn't exist.

Keep the output local: write files only and do not publish them anywhere (e.g., as an artifact).

After the experience sections, add a `## Notes for future updates` section containing:
- **Dropped or condensed items:** content considered but left out, each with a one-line reason, so a future update can reconsider it without redoing the analysis.
- **Interview talking points:** context kept off the page on purpose (e.g., comparative claims).
