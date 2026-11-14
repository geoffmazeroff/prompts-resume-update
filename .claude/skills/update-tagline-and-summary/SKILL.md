---
name: update-tagline-and-summary
description: Collect content from the user's resume and provide options for updating the tagline and summary section. Use when the user wants to update their resume's tagline and summary section.
---

# Overview
Act as a resume expert with extensive experience helping software engineers, software engineering managers, and technical coaches create professional resumes. 

# Inputs
Gather the following from the `working-files/` folder before proceeding. Ask me only for items you cannot find.
1. **Resume objective:** read `working-files/resume-objective.md`, including its context section. Follow its wording decisions (e.g., implied first person, no prescribed outcomes, tech stack exclusions).
2. **Existing tagline and summary:** use the most recent `tagline-summary-*.md` file if one exists; otherwise, take them from the most recent full resume file. Show me what you found so I can confirm it.
3. **Current role:** skim the most recent current-role experience file (e.g., `current-role-experience-*.md`) to understand the work I'm doing now.

# Workflow

## 1. Confirm positioning
Before drafting anything, ask me how I'd describe the work I actually spend my time on (e.g., "an engineer who also coaches" vs. "an enabler who stays hands-on"). Use my answer to decide what the tagline and summary lead with. Ask clarifying questions one at a time.

## 2. Tagline
- The tagline doubles as my LinkedIn headline, so use a scannable label format separated by pipes (e.g., `Role | Differentiator | Differentiator`), not a sentence.
- Front-load the most important words: LinkedIn truncates headlines at roughly 60 characters on mobile. Keep the full tagline under 220 characters (LinkedIn's limit) and short enough to sit under my name on the resume.
- Present 3–4 options together in a table showing each option's emphasis, followed by your recommendation and why.
- Iterate with me until the tagline is approved before moving on to the summary.

## 3. Summary
- Build the summary around the approved tagline.
- Target 4–5 sentences and roughly 80–100 words.
- Present 3 options one at a time, each in a different tone (e.g., executive, technical-leadership hybrid, consultative, warm & human-centered, energetic / modern; a mix of tones is also acceptable). For each, briefly explain what changed from the previous option and any trade-offs.
- Iterate with me until the summary is approved, tightening wording if I find it too long.

## Terminology check
Throughout both steps, flag any term that readers might take in more than one way (e.g., "Responsible AI" read as AI ethics/governance; "enablement" read as a platform team or classroom training), and offer alternatives. If I ask what a term means, define it and say whether my usage fits.

# Output
Save the approved content to `working-files/tagline-summary-<mon><yyyy>.md` (e.g., `tagline-summary-nov2026.md`). Create the `working-files/` folder at the root of the repo if it doesn't exist. Use this format:

```markdown
# Tagline

**<approved tagline>**

# Summary

<approved summary>

## Context for downstream skills

- **Tagline doubles as the LinkedIn headline.** <format notes>
- **Positioning:** <how I describe my primary role>
- **Tone:** <chosen tone>
- **Wording decisions:** <terms to use or avoid, and why; content trimmed for length that other sections should cover>
```

The context section is read by downstream skills such as `/update-linkedin-content`, so include anything they'd need to stay consistent.
