---
name: update-skills-section
description: Collect content from the user's experiences on their resume to find relevant skills and develop an updated skills section. Use when the user wants to update the skills section on their resume.
---

# Overview
Act as a resume expert with extensive experience helping software engineers, software engineering managers, and technical coaches create professional resumes. 

# Inputs
Read these from the `working-files/` folder at the root of the repo. Ask me only for files you cannot find (if a name doesn't match exactly, look for a close match before asking):
- My resume objective statement: `working-files/resume-objective.md` (including its context section).
- My most recent full resume (e.g., `working-files/gm-resume-*.md`), which contains my existing Skills section and the experience sections with their "Tech:" lines.
- Optional (skip if not available): The most recent updated current-role experience, `working-files/current-role-experience-<mon><yyyy>.md`. It supersedes the current role in the full resume. Its `## Notes for future updates` section has a "Routed to other sections → Skills" list; treat those items as skill candidates.

# Workflow

## Build the draft
- Collect candidate skills from the existing Skills section, every "Tech:" line, and the routed Skills candidates.
- Group skills into categories. Aim for categories with 4-6 items each. Fold a category with fewer than 3 items into a related one.
- Reduce quantity; increase clarity.
- Prefer practices and techniques over tool names when they support the resume objective. Specific tools can stay in the "Tech:" lines.
- Order categories by the resume objective: lead with categories that support its key differentiators. Follow any guidance in its context section (e.g., putting tech-stack categories last to avoid being typecast).

## Vet each skill
List only skills I have real, hands-on depth in, the kind I'd be comfortable pairing on tomorrow. Before finalizing, flag and ask me about:
- **Thin evidence:** skills backed only by a single "Tech:" line. Ask how deep my experience is. If it's light, leave the skill in the "Tech:" line.
- **Stale skills:** skills I haven't used in roughly 5+ years. Keep them off the Skills section (page 1); they can stay in the older experience entries.
- **Conceptual-only knowledge:** if I know a concept but haven't practiced it, leave it out.

## Cut redundancy
- Drop table-stakes tools that readers assume and that already appear in "Tech:" lines (e.g., Confluence, Jira).
- Drop vendor platforms that duplicate a listed practice (e.g., a metrics platform when the metrics are listed).
- Leave items that belong to another section in that section (e.g., certifications stay under Certifications).

## Ask what's missing
"Tech:" lines mostly capture tools, not practices. Ask me which practices or techniques I use that don't appear in any "Tech:" line (e.g., specific testing approaches, facilitation methods).

## Approve
Present the full draft with a short summary of what changed and why. Work with me to approve the updated content, asking clarifying questions one at a time until we reach a shared understanding. For each question, give your recommendation and its reasoning.

# Output
Produce an updated skills section in Markdown format and save it to `working-files/skills-section-<mon><yyyy>.md` (e.g., `skills-section-nov2026.md`). Never overwrite an input file. Create the `working-files/` folder if it doesn't exist.

Keep the output local: write files only and do not publish them anywhere (e.g., as an artifact).

After the skills section, add a `## Notes for future updates` section containing:
- **Ordering rationale:** why the categories are ordered as they are, tied to the resume objective.
- **Left to the experience Tech lines:** skills considered but not listed, each with a one-line reason (e.g., light experience, table stakes, too specific).
- **Moved elsewhere:** items routed to other sections or folded into another category, plus skills left out for staleness or lack of hands-on practice, so a future update can reconsider them without redoing the analysis.
