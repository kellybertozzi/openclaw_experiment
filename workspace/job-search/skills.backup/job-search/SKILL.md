---
name: job-search
description: Search, evaluate, rank, research, and prepare technology job applications and recruiter/networking outreach for Kelly.
---

# Job Search Skill

Use this skill whenever Kelly asks to:

- find jobs
- search jobs
- look for jobs
- research companies
- compare jobs
- evaluate a job
- tailor a resume
- write a cover letter
- prepare an application
- track applications
- find more opportunities
- identify good entry-level roles
- find systems analyst or business systems roles
- identify recruiters
- prepare recruiter/networking outreach
- research people or companies for networking

## Core Goal

Help Kelly transition from her current cannabis-industry role and Computer Science background into a professional technology, information-systems, or other CS-adjacent career.

Do not assume that "technology job" means software engineering.

Kelly should be considered for both technical and technical-business roles.

## IMPORTANT: LIVE JOB SEARCH REQUIREMENT

When Kelly asks for CURRENT, ACTIVE, LIVE, or NEW job listings:

- Use the available live browser/web capability.
- Browser automation may be used to search public job boards and employer websites.
- The live browser is the source of truth for current job listings.
- Do NOT use jobs_found.md, previous search results, workspace job lists, memory, or previously collected listings as the source of current job listings.
- Workspace files may be used to understand Kelly's background and preferences, but not to claim that a job is currently open.
- Do not fabricate current jobs from remembered information.
- Do not claim a job is active unless the live search provides evidence.
- If live browsing is unavailable, say so rather than pretending the search was live.

### Search strategy

Use multiple searches rather than relying on one query.

Search across several job categories and title variants.

At minimum consider:

1. Web/front-end development
2. Software engineering
3. AI/automation
4. QA/testing
5. Application support
6. Systems analyst
7. Business systems analyst
8. Applications analyst
9. Information systems analyst
10. Technical business analyst
11. Implementation specialist
12. Implementation analyst
13. Technical operations
14. Technical support
15. Product/technical support
16. Data/reporting analyst
17. Other CS-adjacent technical roles

Use synonyms and related titles.

Do not require a job title to contain:
- developer
- engineer
- software

A strong technology opportunity may use terminology such as:
- analyst
- applications
- systems
- implementation
- operations
- support
- platform
- business systems
- information systems
- technical specialist

## PRIORITY FOR KELLY

Give meaningful consideration to roles that bridge technical and business responsibilities.

Particularly prioritize:

- Systems Analyst
- Business Systems Analyst
- Applications Analyst
- Information Systems Analyst
- Technical Business Analyst
- Application Support Analyst
- IT Analyst
- Implementation Specialist
- Implementation Analyst
- Technical Operations Analyst
- Product Support Engineer
- Technical Support Engineer
- Junior Software Engineer
- Software Engineer I
- Front-End Developer
- Web Developer
- QA Analyst
- QA Engineer
- Automation/QA Engineer
- Data/Reporting Analyst

Do not automatically rank software engineering above analyst or implementation roles.

## LOCATION

Prioritize:

- Boston
- Cambridge
- Waltham
- Greater Boston
- nearby communities within reasonable commuting distance

Do not silently expand the search to distant Massachusetts locations.

If a role is remote or hybrid, clearly identify that.

## EXPERIENCE LEVEL

Kelly graduated with a BS in Computer Science in May 2025.

Prioritize:
- entry-level
- associate
- junior
- early-career
- 0-2 years
- 1-3 years when the requirements are otherwise reasonable

Do not automatically exclude a role because it asks for more experience.

However, clearly label substantial-experience roles as long shots.

Do not recommend senior, staff, lead, principal, or management positions merely because they appear in a search.

## LIVE JOB VERIFICATION

For promising jobs, verify as much as possible:

- exact job title
- employer
- exact location
- remote/hybrid/on-site arrangement
- salary or compensation range
- posting date
- experience requirements
- relevant qualifications
- current/open status
- direct application URL
- source website

### DIRECT URL REQUIREMENT

The URL reported for a job MUST point to the specific individual job posting.

This is a hard validation requirement, not a preference.

Before reporting a URL, verify ALL of the following:

1. The URL identifies the individual job posting, not a search-results page.
2. The page title/job title matches the job being reported.
3. The employer/company matches the job being reported.
4. The location is consistent with the job being reported.
5. The posting is still active/current.
6. The URL is usable by Kelly without requiring the agent's current browser session.

### URL EXTRACTION RULES

When using LinkedIn:

- Prefer a URL matching:
  `https://www.linkedin.com/jobs/view/<JOB_ID>/`
- A LinkedIn `/jobs/view/` URL is an individual posting URL.
- A URL containing `/jobs/search/` is NEVER an individual posting URL.
- A URL containing `/company/` is NEVER an individual posting URL.
- A URL containing `/in/` is NEVER an individual posting URL.
- Do not report a URL merely because it is the page currently visible in the browser.
- Do not report the URL of a parent search page when the job was discovered from that search.
- If the browser opens intermediate tracking, authentication, consent, iframe, analytics, or redirect pages, follow the navigation until the actual job posting URL is identified.

When extracting a URL from a job card:

- Inspect the actual job-card link/href.
- Do not infer the URL from the search URL.
- Do not construct a posting URL from the job title unless the actual job ID was observed.
- If multiple links exist, select the link whose destination is the individual job posting.
- Ignore company-logo links, company-page links, recruiter/profile links, tracking links, and search-page links.

For other job boards:

- Prefer the site's individual job-detail URL.
- Prefer the employer's direct application page when it is available and clearly corresponds to the exact job.
- Do not substitute a generic search-results URL.
- Do not substitute a company page.
- Do not substitute a recruiter/profile page.

### URL VALIDATION GATE

Before putting a job URL in the final answer, explicitly perform this check:

`JOB TITLE + COMPANY + LOCATION + DIRECT POSTING URL`

All four must correspond to the same job.

If the URL cannot be verified as the individual posting:

- Do NOT call it an "exact posting URL."
- Do NOT invent or reconstruct a URL.
- Do NOT substitute a search URL or company URL.
- Continue searching for the actual posting.
- If no direct posting URL can be obtained, report that the direct URL could not be verified and do not present another URL as the posting URL.

For a request for exactly one job, it is better to return one verified job than one unverified job.

### DISCORD / CHAT OUTPUT URL RULE

When responding to a Discord request asking for an exact posting URL:

- Return the verified individual posting URL directly.
- Do not wrap a search URL in a Markdown link and label it as the posting.
- Do not return a company LinkedIn URL.
- Do not return a generic job-search URL.
- The displayed link text and destination must both correspond to the actual job posting.

If the exact posting URL cannot be verified, say so rather than giving the user a misleading URL.

Prefer direct employer application pages when available.

## SEARCH EFFICIENCY

Avoid wasting model tokens.

Use a two-stage process:

### Stage 1 — Discovery

Search broadly and identify promising candidates.

Do not deeply research every result.

### Stage 2 — Verification

Only deeply inspect the strongest candidates.

For a request for 5 jobs:

- discover more than 5 candidates
- eliminate obvious poor fits
- deduplicate
- deeply verify the strongest 5
- return the final 5

Do not repeatedly search the same query unless the results are insufficient.

Do not spend excessive time researching jobs that are clearly senior or poor matches.

## FIT SCORING

Assign a 0-100 fit score:

Technical fit: 25
Entry-level accessibility: 20
Compensation: 15
Location: 15
Career growth: 10
Work arrangement: 5
Company quality: 5
Application effort: 5

Classify:

A = Strong match
B = Worth applying
C = Long shot / lower priority

A role should not receive a high fit score merely because it is a technology job.

## OUTPUT FOR JOB SEARCHES

When reporting search results use:

| Rank | Company | Role | Location | Salary | Arrangement | Fit | Recommendation |
|---|---|---|---|---|---|---|---|

Then provide brief reasoning and the direct application URL.

For current/live searches, also state:

- that a live search was performed
- which browser/web capability was used
- which source websites were searched

Do not claim a capability was used if it was not actually used.

## JOB DEDUPLICATION

Check existing job tracking information when appropriate to avoid repeatedly recommending the same jobs.

However, existing workspace information must NOT replace live verification.

A previously known job must be re-verified before being described as currently active.

## APPLICATION PREPARATION

For A-level jobs:

- identify relevant resume keywords
- propose resume adjustments
- draft a cover letter when useful
- prepare screening answers
- identify questions requiring Kelly's input

Never invent:
- experience
- employment history
- skills
- credentials
- project details
- screening answers

If information is missing, ask Kelly.

## APPLICATION APPROVAL

Never submit an application without Kelly's explicit approval.

If Kelly says:

"Apply to #2, #3, and #5"

that is explicit approval to apply to those specific jobs.

Do not interpret general statements such as:
- "I want to find a job"
- "these look good"
- "help me apply"
- "I'd like this job"

as authorization to submit.

## APPLICATION WORKFLOW

When authorized to apply:

1. Open the verified job posting.
2. Confirm the job is still active.
3. Review the application requirements.
4. Prepare truthful application materials.
5. Use Kelly's existing resume/profile information where appropriate.
6. Ask Kelly only when an answer genuinely cannot be determined from known information.
7. Never fabricate screening answers.
8. Submit only after the job-specific authorization exists.
9. Report the result.

If the application requires CAPTCHA, MFA, identity verification, or another security challenge:

- do not bypass it
- do not attempt to defeat it
- stop at the challenge
- report exactly where the application stopped
- allow Kelly to continue manually

## RECRUITER / NETWORKING WORKFLOW

Recruiter and networking outreach is an important part of Kelly's job search.

When Kelly asks about recruiters or networking:

1. Identify relevant recruiters when possible.
2. Prefer recruiters who appear connected to:
   - technology
   - information systems
   - IT
   - software
   - business systems
   - technical recruiting
   - Boston-area hiring
3. Consider Kelly's existing LinkedIn connections when Kelly provides or identifies them.
4. Help Kelly write personalized outreach.
5. Do not send recruiter messages without Kelly's explicit approval.

Recruiter outreach should normally be conversational rather than asking bluntly:

"Do you have a job for me?"

Good outreach should briefly explain:

- who Kelly is
- her Computer Science degree
- that she is looking to transition into technology/information systems
- the types of roles she is targeting
- why she is contacting that particular recruiter/person
- an easy invitation to continue the conversation

If appropriate, suggest offering to send a resume.

## RECRUITER OUTREACH PRIORITY

When relevant, prioritize recruiters and connections associated with:

- systems analyst
- business systems analyst
- applications analyst
- information systems
- IT
- implementation
- technical operations
- software
- QA
- technical support
- data/reporting

Networking is not limited to people whose current job title says "recruiter."

Hiring managers, technical leads, alumni, former classmates, and professional connections may also be useful networking contacts.

## COMPANY RESEARCH

When researching companies:

- use live web information for current hiring information
- distinguish company facts from assumptions
- identify relevant open roles
- identify recruiting contacts when publicly available
- summarize why the company may be a good target for Kelly

Do not imply a company is hiring unless live evidence supports that claim.

## TRUTHFULNESS

Never fabricate information.

Never claim professional experience that does not exist.

Never invent salary ranges.

Never invent posting dates.

Never invent application URLs.

Never claim that a job is active without verification.

Never claim to have browsed a website unless the browser actually accessed it.

If information is unavailable, say:

"Not available from the source I could access."

## GENERAL PRINCIPLE

Optimize for getting Kelly into a good technology career, not merely maximizing the number of software-engineering applications.

A systems analyst or business-systems role that strongly fits Kelly may be more valuable than a software-engineering role that expects several years of experience.

Use judgment and prioritize realistic opportunities.
EOF



