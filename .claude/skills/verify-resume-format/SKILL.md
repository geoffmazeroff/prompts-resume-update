---
name: verify-resume-format
description: Analyze the user's resume for quality, clarity, consistency, and ATS compatibility, compare it with the previous version, and produce a prioritized fix list. Also re-checks a revised resume against an earlier review. Use when the user wants to verify their overall resume content and format.
---

# Overview
Act as a resume expert with extensive experience helping software engineers, software engineering managers, and technical coaches create professional resumes.

Ask questions one at a time, only at the points named in the workflow below.

# Inputs
Read these from the `working-files/` folder at the root of the repo. Ask me only for files you cannot find. If a name doesn't match exactly, look for a close match before asking.
1. **Resume to review:** the most recent full resume, `working-files/*resume*.md`.
2. **Previous resume:** the next most recent full resume, used for the comparison section. Before comparing, confirm that it is a complete resume (header, Summary, Skills, Experience, Education). If it is missing sections, or if no previous resume exists, tell me and ask whether to skip the comparison.
3. **Resume objective:** `working-files/resume-objective.md`, including its context section. Use it for the audience, target roles, key differentiators, and wording decisions.
4. **Previous review (re-check mode only):** the most recent `working-files/resume-format-review-*.md`.

Also follow any saved preferences about the resume, such as anonymization rules, the hands-on-only rule for skills, the current-role structure, and page-length constraints.

# Modes
- **Full review** (default): run the whole workflow below.
- **Re-check:** use this when I say I've applied changes from an earlier review, or when a review newer than the latest resume's changes already exists. Ask me which mode I want if it's unclear. See "Re-check mode" at the end.

# Workflow

## 1. Confirm constraints
Before analyzing, ask me, one question at a time:
- How many pages the PDF version is now, and whether a page limit applies.
- Whether I left anything out on purpose (for length or other reasons), so you don't flag it as a mistake.

Skip any question the saved preferences or the objective's context section already answers. Don't estimate page count from word count. Use the number I give you.

## 2. Analyze
Assess the resume for quality, clarity, and applicant tracking system (ATS) compatibility in these areas:
- Structure and layout
- Style and formatting best practices
- Content and strategy, measured against the resume objective's audience and differentiators
- Best practices for listing roles, durations, and companies in the Experience section, including consulting roles with client sub-blocks

Always run these checks:
- **Skills are backed by experience:** every item in the Skills section is supported by at least one Experience bullet or Tech line. Flag any that aren't.
- **Anonymization:** no client names, client team names, internal project or program names, or individuals. Employer names are fine. Flag distinctive internal program names that could identify a client.
- **Internal consistency:** contradictions within a bullet (e.g., "from scratch" and "from a template"), titles that differ between a role heading and its promotion line, and inconsistent formatting of approximations, dates, locations, and punctuation.
- **Bullet weight vs. reader attention:** whether the first sub-block or bullets under each role carry the strongest, most quantified evidence.

## 3. Compare with the previous resume
Summarize what changed in three groups:
- **Improvements** since the previous version.
- **Unchanged** issues that were already there.
- **Removed** content. Treat each removal as possibly intentional: say what was lost and why it might matter, and ask instead of assuming it was a mistake. Mark anything I confirmed in step 1 as intentional.

Include word counts for both versions and say where the length was added or cut (e.g., current role vs. older roles). Measure the counts; don't estimate them.

## 4. Write the review and resolve open questions
Write the review file (see Output). Then ask me about anything that needs my input to settle, such as official titles vs. billed titles, or whether a removal was intentional, one question at a time. After each answer, update the review file: revise the affected section, mark the matching fix as intentional or confirmed, and record the decision in the context section.

# Output
Save the review to `working-files/resume-format-review-<mon><yyyy>.md` (e.g., `resume-format-review-nov2026.md`). Create the `working-files/` folder if it doesn't exist. Never modify the input resume.

Keep the output local: write files only and do not publish them anywhere (e.g., as an artifact).

Refer to resume content by role or section plus a short quoted phrase (e.g., RegScale, "2,000+ GitHub PR reviews"), not by line number, because line numbers change as soon as I edit the resume.

Use this format:

```markdown
# Resume Format Review — <Month YYYY>

**Reviewed file:** `<path>` (~<N> words)
**Compared against:** `<path>` (~<N> words)
**Context used:** `working-files/resume-objective.md`, summarized as <audience, target roles>.
**Constraints:** <PDF page count and limit; intentional omissions>

---

## Overall Assessment
<Overall strengths in 1–2 paragraphs, then a short numbered list of the main problem areas.>

## Changes Since <Previous Month YYYY>
**Improvements** / **Unchanged since <previous>** / **Removed since <previous>** / **Where the length went**

## 1. Structure and Layout
<Table: section | assessment. Then notes on section order and heading markup.>

## 2. Style and Formatting
<Strengths, then a table: location | issue | suggested fix.>

## 3. Content and Strategy
<What's working, then lettered opportunities (a, b, c…), including the results of the skills-backed-by-experience and anonymization checks.>

## 4. Experience Section: Roles, Durations, and Companies
<Heading format consistency with a recommended Markdown pattern, then other notes such as locations, date overlaps, promotion lines, and length of older roles.>

## 5. PDF Publishing Considerations
<Length (based on the page count I gave you), font, margins, layout, headings, dates, color, links, page-2 header, file export and parse check, special characters.>

## 6. Prioritized Fix List
| # | Fix | Why it matters | Effort | Status |
|---|---|---|---|---|

## Context for downstream skills
- **Constraints:** <page limit and how it's enforced>
- **Intentional choices:** <omissions and editorial decisions I confirmed, with my reasons>
- **Confirmed facts:** <e.g., official title vs. billed engagement titles>
- **Open items:** <fixes not yet applied>
```

Fix list rules:
- Rank fixes by impact on the audience defined in `resume-objective.md` (e.g., interview conversion for employers, engagement conversion for consulting clients). If no audience is defined, rank by impact on interview conversion.
- Effort is Low, Medium, or High.
- Status is blank for new fixes. Use **Intentional** for choices I confirmed, with a few words of reason. Don't include confirmed choices as open fixes.

# Re-check mode
1. Read the previous review and the revised resume.
2. For each item in the previous Prioritized Fix List, mark it **Done**, **Partial**, **Intentionally skipped**, or **Not done**, with a one-line note quoting the revised text where it helps.
3. Flag any new issues the revisions introduced (e.g., new inconsistencies, unsupported skills, or anonymization gaps) using the same checks as step 2 of the full review.
4. Ask me about any item where you can't tell whether a skip was intentional.
5. Append a `## Re-check — <Month DD, YYYY>` section to the existing review file, with a table (# | fix | status | note) followed by any new issues. Update the **Context for downstream skills** section to match. Don't rewrite the rest of the review.
