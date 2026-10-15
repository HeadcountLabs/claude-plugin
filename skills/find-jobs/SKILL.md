---
name: find-jobs
description: Find, count or look up open job postings with the Headcount Labs tools. Use when the user asks who is hiring, how many jobs match a role or place, or for job listings with apply links.
---

# Find jobs with Headcount Labs

1. If you are unsure which filter fits (pay, work arrangement, seniority, dates), call `list_fields` with a keyword first.
2. When the user asks how many jobs match, call `count_jobs`. Counts don't use the user's monthly jobs.
3. When the user wants listings, call `search_jobs` with the narrowest filters that fit the request and a small `limit`
   (5 to 10) unless they ask for more.
4. For one job's full record, call `get_job` with its `job_id`.
5. In the answer, give each job's title, employer, location, pay as the employer published it (say when none is
   listed), and the posting link from `postings[].posting_url`, so the user can check the original and apply there.
6. These tools only read job data. They can't apply to jobs or contact employers. Say so if the user asks for that.
