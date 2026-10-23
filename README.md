# funnel-watchdog

Checks the @vektor.fm Instagram funnel worker (`vektor-ig-dm`) every 30 minutes via its `/health` endpoint.
A failed run means the funnel is down or degraded; GitHub emails the account that last edited the schedule.

- Workflow: `.github/workflows/funnel-health.yml`
- Secret: `REPORT_KEY` (the worker's report key; never printed in logs)
- A monthly keepalive job re-enables the workflow so GitHub's 60-day inactivity pause never stops it silently.
- Run it by hand: Actions → funnel-health → Run workflow.

Public so Actions minutes are free. The workflow holds no secret values.
