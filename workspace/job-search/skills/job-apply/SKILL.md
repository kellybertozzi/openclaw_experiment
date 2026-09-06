---
name: job-apply
description: Prepare and submit explicitly approved job applications for Kelly using truthful profile information, controlled browser automation, bounded retries, and application-state tracking.
---

# Job Apply Skill

Use this skill when Kelly explicitly asks to apply to one or more specific jobs that she has approved.

This skill handles APPLICATION EXECUTION.

It does NOT search for new jobs or independently decide which jobs Kelly should apply to.

## CORE SAFETY RULE

Never submit an application unless Kelly has explicitly authorized that specific job.

Examples of explicit authorization:

- "Apply to #2."
- "Apply to #2, #4, and #7."
- "Apply to this job: [specific verified job URL]."
- "Apply to all of the jobs I approved."

Do NOT interpret these as submission authorization:

- "I like this job."
- "This one looks good."
- "Help me apply."
- "Find jobs for me."
- "I'd love this job."

If authorization is ambiguous, ask before submitting.

## RESPONSIBILITIES

This skill is responsible for:

1. Confirming the approved job.
2. Verifying the job is still active.
3. Reading the job description and application requirements.
4. Selecting or preparing the appropriate resume.
5. Preparing a truthful cover letter when appropriate.
6. Identifying the application platform.
7. Filling the application form.
8. Tracking field state during form filling.
9. Using bounded retries when browser operations fail.
10. Stopping safely when the application cannot be completed.
11. Submitting only when authorized and all required information is known.
12. Recording the result in the application tracker.
13. Reporting exactly what happened.

## DO NOT

Do not:

- search broadly for new jobs
- invent qualifications
- invent employment history
- invent projects
- invent screening answers
- guess unknown personal information
- bypass CAPTCHA
- bypass MFA
- bypass identity verification
- defeat anti-bot/security systems
- fabricate salary information
- fabricate work authorization
- submit unauthorized applications
- repeatedly retry a broken application indefinitely
- refresh a partially completed form unless the platform explicitly requires it and progress is known to be preserved

# PROFILE AND TRUTHFULNESS

Use the workspace's authoritative profile files for application answers.

Relevant sources include:

- JOB_SEARCH_PROFILE.md
- MASTER_PROFILE.md
- resumes/
- application records
- existing application information when appropriate

Never contradict known profile information.

If an answer is not known from the profile or existing verified information, stop and ask Kelly.

## Safe automatic answers

The agent may answer from verified profile information:

- name
- contact information
- degree
- graduation date
- listed technical skills
- project descriptions
- employment dates
- known job duties
- known employer information
- known locations
- resume information

## Ask Kelly

Ask before answering questions involving:

- salary history
- desired salary when no established preference applies
- sponsorship
- legal eligibility not already confirmed
- willingness to relocate
- driver's license
- vehicle availability
- criminal/background questions
- drug testing
- federal eligibility
- demographic/self-identification questions
- any question whose truthful answer cannot be determined from available information

Never guess.

# APPLICATION STATE

Maintain explicit state for every application.

Possible states:

- FOUND
- SHORTLISTED
- PREPARED
- APPROVED
- APPLYING
- NEEDS_INFO
- BLOCKED
- APPLIED
- REJECTED
- CLOSED
- WITHDRAWN

The application tracker is the persistent source of application status.

When possible, record:

- company
- role
- URL
- date
- status
- application platform
- resume used
- cover letter used
- blocking issue
- confirmation information
- notes

# APPLICATION EXECUTION LIMITS

The purpose of these limits is to prevent a browser agent from getting stuck indefinitely.

Default limits:

- Maximum attempts per field: 3
- Maximum recovery attempts for a page: 2
- Maximum application runtime: 15 minutes
- Maximum consecutive browser errors: 3

If a limit is reached:

1. Stop the current operation.
2. Preserve the current application state if possible.
3. Record the failure.
4. Mark the application BLOCKED or NEEDS_INFO as appropriate.
5. Report the exact stopping point.
6. Do not continue retrying indefinitely.

## IMPORTANT

A failed application is preferable to an infinite loop.

The agent must never spend an unlimited amount of time trying to solve one field or one page.

# BROWSER FORM RULES

## Never blindly refresh

Refreshing or navigating away from a partially completed form can destroy application progress.

If a field cannot be found:

1. Re-snapshot the current page.
2. Locate the field again.
3. Attempt the field using the available browser interaction method.
4. Verify the resulting value.
5. Continue.

Do not refresh merely because an element reference became stale.

## Field progress tracking

Maintain a per-application field map.

Conceptually:

FILLED = {
  field_name: {
    value: "...",
    status: "ok",
    attempts: 1
  }
}

Before filling a field:

1. Check whether the field is already marked FILLED.
2. If it is FILLED and the visible value is correct, do not fill it again.
3. If it is missing, fill it.
4. Verify the value after filling.
5. Mark it FILLED.

After a browser re-snapshot:

- Do NOT assume previously filled fields are empty.
- Only work on fields that are not already confirmed FILLED.
- If a previously filled field visibly contains the wrong value, correct it and increment its attempt count.

Reset the field map when starting a new job.

Preserve the field map across multi-step pages within the same application.

## Field failure limit

If one field fails three times:

- Stop attempting that field.
- Record the field and failure.
- If optional, continue.
- If required, mark the application BLOCKED or NEEDS_INFO.
- Do not attempt the same operation indefinitely.

# PLATFORM DETECTION

Identify the application platform before filling the form.

Common platforms include:

- Workday
- Greenhouse
- Ashby
- Lever
- Dayforce
- SmartRecruiters
- Oracle HCM
- LinkedIn Easy Apply
- Glassdoor Easy Apply
- Indeed
- employer-specific application systems

Prefer a direct employer/ATS application URL when the verified job information provides one.

If an aggregator redirects to an employer ATS, use the employer/ATS application when possible.

## Platform-specific behavior

Do not assume every ATS behaves the same way.

Before using a platform-specific technique, identify the actual platform.

If a platform behaves unexpectedly:

1. Re-snapshot.
2. Re-evaluate the page.
3. Try a bounded recovery.
4. If still broken, stop rather than entering a loop.

# APPLICATION PREPARATION

Before filling the form:

1. Confirm the job is still active.
2. Read the job description.
3. Determine the appropriate resume variant.
4. Prepare a tailored resume only using truthful information.
5. Prepare a cover letter when useful.
6. Identify questions that require Kelly's input.
7. Do not begin submission until required unknown information has been resolved.

## Resume tailoring

Tailoring may:

- reorder relevant skills
- emphasize relevant existing experience
- adjust wording to match job terminology
- emphasize relevant projects
- improve ATS keyword alignment

Tailoring must NOT:

- invent experience
- invent technologies
- invent responsibilities
- invent metrics
- invent projects
- claim professional experience that does not exist

# APPLICATION FLOW

For each explicitly approved job:

1. Set tracker status to APPROVED.
2. Verify the job is still active.
3. Open the direct application URL.
4. Identify the ATS/platform.
5. Set tracker status to APPLYING.
6. Prepare application materials.
7. Inspect the application form.
8. Build field-state tracking.
9. Fill known fields.
10. Verify important fields.
11. Stop for unknown required answers.
12. Stop for CAPTCHA/MFA/identity verification.
13. Review the completed application.
14. Submit only if authorization exists.
15. Verify submission confirmation if possible.
16. Record the result.
17. Set tracker status to APPLIED or the appropriate failure status.
18. Report the result.

# CAPTCHA / MFA / IDENTITY VERIFICATION

Never bypass:

- CAPTCHA
- MFA
- phone verification
- identity verification
- security challenges
- anti-bot challenges

Stop and tell Kelly exactly what appeared and where.

Leave the application in the safest usable state possible.

# ERROR RECOVERY

## Recoverable errors

Examples:

- stale element/reference
- field not immediately found
- dropdown did not open
- temporary loading delay
- incorrect field value
- networkidle timeout

Recovery:

1. Wait briefly if appropriate.
2. Re-snapshot.
3. Locate the current element.
4. Retry using a different supported interaction method.
5. Verify.
6. Count the attempt.

## Non-recoverable conditions

Examples:

- application closed
- job expired
- page permanently unavailable
- login session expired and cannot be restored safely
- browser tab crashed
- redirect to an unrelated page
- required field cannot be completed after 3 attempts
- security challenge requiring Kelly
- unknown required answer

Action:

- stop
- record
- do not loop
- report

# PROGRESS REPORTING

For multi-application tasks, report progress periodically.

Example:

"Application 1/5: completed."

"Application 2/5: blocked — required sponsorship answer needs Kelly."

"Application 3/5: completed."

Do not remain silently busy for long periods.

If an application takes unusually long, report what stage it is in.

## REQUIRED STUCK REPORT

If the application hits a timeout, report:

- company
- role
- platform
- last successful stage
- current stage
- field/page causing the problem
- attempts made
- whether the application was submitted
- tracker status

# BATCH APPLICATIONS

If Kelly explicitly authorizes multiple jobs:

- Process the approved jobs individually.
- Reset field state for every new job.
- Do not allow one broken application to block the entire batch.
- Respect the application runtime limit for each job.
- Report progress between jobs.
- Stop the batch if a systemic browser/tool failure affects multiple jobs.

Default maximum batch size:

15 applications before reporting progress.

# SUBMISSION

Before clicking Submit:

Confirm:

1. This exact job was explicitly authorized.
2. The application is still for the intended company and role.
3. Required fields are complete.
4. No unknown answers were guessed.
5. No CAPTCHA/MFA/identity challenge is active.
6. The resume and cover letter are truthful.
7. The application has not already been submitted.

Then submit.

After submission:

- look for confirmation text
- confirmation number
- confirmation page
- confirmation email if available

Record whatever evidence is available.

# APPLICATION TRACKER

Use:

~/.openclaw/workspace/job-search/APPLICATION_TRACKER.csv

Do not create duplicate tracker entries unnecessarily.

Application statuses:

FOUND
SHORTLISTED
PREPARED
APPROVED
APPLYING
NEEDS_INFO
BLOCKED
APPLIED
INTERVIEW
REJECTED
WITHDRAWN
CLOSED

Keep application-specific details in the notes field.

# FINAL REPORT

For each approved application report one of:

SUCCESS
BLOCKED
NEEDS_INFO
CLOSED
REJECTED

For SUCCESS include:

- company
- role
- submission status
- confirmation information if available

For BLOCKED include:

- company
- role
- exact blocker
- attempts
- whether any information was submitted

For NEEDS_INFO include:

- exact question requiring Kelly's answer

Never claim an application was submitted unless the browser actually confirmed submission.
