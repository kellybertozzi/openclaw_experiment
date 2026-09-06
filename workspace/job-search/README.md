# Job Search Agent Setup

Copy all files in this directory into:

`~/.openclaw/workspace/job-search/`

OpenClaw loads `AGENTS.md`, `SOUL.md`, `IDENTITY.md`, and `USER.md` from the agent workspace. The job-search profile and tracker are additional working files.

After copying, restart the Gateway and verify the agent.

Suggested verification:
```bash
openclaw agents list
openclaw agents list --bindings
openclaw gateway restart
```

For a direct test:
```bash
openclaw agent --agent job-search --message "Read my job-search profile and give me a 10-job search plan. Do not apply to anything."
```
