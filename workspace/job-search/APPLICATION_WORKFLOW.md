# Job Application Workflow

## Phase A — Discovery

Search multiple sources and collect jobs into `APPLICATION_TRACKER.csv`.

Do not apply during discovery.

For each job capture:
- date found
- company
- title
- URL
- location
- work arrangement
- salary
- commute category
- match score
- status
- notes

## Phase B — Ranking

Use the scoring rules in `AGENTS.md`.

Prioritize roles where Kelly can realistically get an interview, not merely jobs with impressive titles.

## Phase C — Tailoring

Use one of:
- web/front-end
- AI/technical
- general tech
- technical support/operations

Keep all factual claims grounded in `JOB_SEARCH_PROFILE.md`.

## Phase D — Approval

Before the first batch of submissions, present a compact approval list:

| # | Company | Role | Salary | Location | Score | Why |
|---|---|---|---|---|---:|---|

Kelly can approve:
- specific jobs
- all jobs above a score
- a batch by date

## Phase E — Submission

After approval:
1. Open the employer's application.
2. Fill only verified information.
3. Tailor resume/cover letter.
4. Stop for unknown answers.
5. Stop for CAPTCHA/MFA/identity checks.
6. Submit.
7. Record confirmation/status.

## Automatic application limits

Default:
- Do not submit more than 15 applications in one batch without reporting progress.
- Do not repeatedly apply to the same employer for substantially identical roles.
- Do not apply to jobs that clearly violate geography, salary, or eligibility constraints unless Kelly explicitly overrides the filter.

## Application-answer rules

Safe to auto-answer from verified profile:
- degree
- graduation date
- listed skills
- project descriptions
- known employment dates
- known job duties
- known locations

Ask Kelly:
- salary history
- desired salary when not obvious
- sponsorship
- legal eligibility questions not already confirmed
- driver's license/vehicle
- willingness to relocate
- criminal/background questions
- drug-testing questions
- demographic/self-identification questions
- anything not covered by the profile

## Drug testing

Do not proactively disclose drug use or testing concerns.

If an application explicitly asks about drug testing, a background check, or federal eligibility, stop and ask Kelly how to answer. Never lie.

## Federal roles

Filter federal-government jobs out by default.

### Application effort

Consider:
- simplicity of the application
- whether the employer accepts a normal resume upload
- number of required fields
- repeated/duplicative questions
- ATS usability
- presence of anti-bot/security challenges

Do not reject a strong job solely because its application is difficult.

Application friction should affect ranking only when jobs are otherwise
similar.

## Tracker statuses

Use:
- FOUND
- SHORTLISTED
- PREPARED
- APPROVED
- APPLIED
- INTERVIEW
- REJECTED
- WITHDRAWN
- CLOSED
- NEEDS INFO

Keep a `notes` field for application-specific details.
