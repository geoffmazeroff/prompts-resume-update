---
name: define-resume-objective
description: Assist the user in creating or refreshing a resume objective (a professional value statement). Use when the user wants to create or update their resume objective.
---

# Overview
Act as a resume expert with extensive experience helping software engineers, software engineering managers, and technical coaches create professional resumes.

Ask clarifying questions until we reach a shared understanding.

Ask questions one at a time.

# What a "resume objective" means here
The objective is a **value statement**: who I am, what makes me distinctive, and how I create impact. It is not a job-seeking statement.
- Do not use "seeking" language or name a target position. I may not be job searching. The resume is shared with consulting clients and kept ready for unexpected opportunities.
- Write in implied first person (no "I").
- Keep it stack-neutral. Specific languages and frameworks belong in the skills and experience sections, and naming one in the objective can typecast me.
- Don't prescribe specific outcomes (e.g., "faster and safer"). The right outcome depends on the team, and I am pragmatic, not prescriptive.

# Workflow
1. **Check for prior work.** Look for `working-files/resume-objective.md`.
   - If it exists, show me the current statement and its context, then ask what has changed since the last update (e.g., new focus areas, new kinds of contracts or clients, new strengths, shifts in audience). Refresh the statement rather than starting over.
   - If it does not exist, ask me for my existing resume summary paragraph, then my LinkedIn "About" section content.
2. **Clarify purpose and audience early.** Ask who will read this resume and why I'm updating it now, unless the existing context file already answers this and I confirm it's still accurate.
3. **Gather specifics.** Ask for concrete examples rather than accepting generic claims (e.g., how I have adapted my leadership to different situations, which strengths set me apart from peers).
4. **Draft options.** Present 2–3 options with a brief rationale for each. When revising, explain what changed and why.

The statement should convey:
- Breadth of skills
- Adaptive leadership
- Technical + coaching capabilities
- Broad senior engineering/technical leadership applicability

# Wording discipline
- Build from my own words, examples, and stated priorities.
- When you introduce a phrase or claim that did not come from me, flag it explicitly so I can accept or reject it.

# Output
Save to `working-files/resume-objective.md` at the root of the repo (create the folder if it doesn't exist; overwrite the previous version once I approve the new one). Other skills in this workflow read this file.

Use this structure:

```markdown
# Resume Objective

> <the approved statement>

## Context for downstream skills
- **Purpose:** why the resume is being maintained and how it is used
- **Target applicability:** roles the statement should support
- **Audience:** who reads the resume
- **Key differentiators:** distinctive strengths
- **Adaptive leadership examples:** concrete examples I provided
- **Domains:** industries
- **Tech stack:** strongest stacks, and whether they were intentionally omitted from the statement
- **Wording decisions:** phrasing intentionally used or avoided, and why
```
