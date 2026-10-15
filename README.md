# Headcount Labs for Claude Code

![Headcount Labs](logo.png)

Headcount Labs collects open job postings from company career sites and job boards, merges duplicates of the same
job, and keeps a link to every source posting. This plugin connects Claude Code to the Headcount Labs job search
server, so you can ask Claude about open jobs in plain language.

## Install

In Claude Code, run:

```
/plugin install headcount-labs --marketplace headcountlabs/claude-plugin
```

Without the plugin, you can add the server yourself:
`claude mcp add --transport http headcount-labs "https://api.headcountlabs.com/mcp?profile=claude"`.

## What you can ask

- "How many data engineer jobs are open in Germany right now?"
- "Find 5 remote software engineer jobs in the US posted in the last week."
- "Find a registered nurse job in Texas that lists pay and show me every source link."

## What the plugin contains

- `.mcp.json` adds one remote MCP server, `https://api.headcountlabs.com/mcp?profile=claude`. Nothing runs on your
  machine.
- `skills/find-jobs` tells Claude which tool fits which question and to show the posting link with each job.

## Sign-in and data

The first time Claude uses the server, Claude Code opens a Headcount Labs sign-in page (OAuth). A free account
includes 1,000 jobs a month, and counts don't use them. Claude sends your search filters and questions to
api.headcountlabs.com and receives job data back. No API key is needed and nothing is stored in this plugin.

The tools read job data, with two exceptions. `set_confirmation_level` changes one account setting, how large a search
can be before Claude must ask you first. `verify_jobs` has the Headcount Labs server re-open a small sample of the
original postings to check that they match. The plugin can't apply to jobs, contact employers or change your plan.

## Links

- Setup and docs: https://headcountlabs.com/mcp/
- Privacy policy: https://headcountlabs.com/privacy/
- Terms: https://headcountlabs.com/terms/
- Support: https://headcountlabs.com/contact/ or support@headcountlabs.com
