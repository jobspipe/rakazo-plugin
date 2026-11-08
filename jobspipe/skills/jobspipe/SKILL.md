---
name: jobspipe
description: Answer questions about who is hiring with live job postings from the JobsPipe MCP server. Use when the user wants open roles, hiring or buying signals, companies hiring for a skill or tool, salary or location data from postings, layoffs, a company's tech stack, or an alert for new postings.
---

# JobsPipe

JobsPipe collects live job postings from 30+ job boards, public employment services
and company career sites (Greenhouse, Lever, Workday, Ashby and more) into one schema.
Use its tools instead of browsing job boards.

## Pick the tool

- **Find postings:** `search` for a role and a place in plain words. Use `search_jobs`
  when the question needs filters: location, remote, salary, seniority, skills,
  employment type, visa stance, language, source or posting age.
- **Read one posting:** `fetch` with an id returned by a search.
- **Unsure what a filter accepts:** `search_documentation`.
- **Companies, not postings:** `search_hiring_companies` (who is hiring for X),
  `search_companies_by_technology` (who uses a tool), `suggest_companies`,
  `resolve_company` and `get_company_profile`.
- **Tech stack:** `get_company_tech_stack`, or `detect_company_tech_stack` to scan a
  domain now. Use `resolve_technologies` to turn tool names into slugs for filters.
- **Layoffs:** `search_layoffs`.
- **Open research questions** ("which fintechs in Singapore are hiring data engineers?"):
  `research_question`.
- **Watch for new postings:** save the search with `create_signal`; manage it with
  `list_signals`, `update_signal` and `delete_signal`. Do not re-run a search on a
  routine to poll; signals fire on new matches and cost no job credits.

## Common jobs to be done

- **Job hunting:** search with the person's role, location, remote preference, salary
  floor and seniority; list the best matches with links; offer a signal for new ones.
- **Recruiting and sourcing:** find companies hiring for a skill in a place
  (`search_hiring_companies`), or recent layoffs (`search_layoffs`) as candidate pools.
- **Sales prospecting:** open roles are buying signals. A company hiring for the job
  a product supports, or using a related tool (`search_companies_by_technology`), is a
  lead. Return company, the posting that signals intent, and why it fits.
- **Competitor and market research:** what a company is hiring for, how many roles,
  in which teams and places, and what the postings reveal about plans and stack.
- **Compensation and skills:** salary ranges and the skills that recur across postings
  for a role and place. Report the sample size; only postings that list pay count.
- **Ongoing monitoring:** for anything the person wants to hear about again, create a
  signal, or pair a signal with a routine that summarizes new matches.

## Answer well

1. Start narrow: a small `limit` and recent postings unless the user asks for more.
   Every job returned spends a credit from the user's JobsPipe plan.
2. Link each posting you mention with the URL the tool returned. Quote company, title,
   location, salary when present and posting date. Never invent postings or salaries.
3. For counts or trends, say how many results matched and over what window.
4. If a result reports a low balance, or a call fails with 402, tell the user and offer
   `upgrade_plan`, which returns a checkout link. It never charges anything itself.
   `get_account_info` shows the plan and remaining credits.
5. If a posting looks closed or wrong, or a search misses something that should exist,
   report it with `give_feedback`.

## Connection

If tools are missing or return 401, ask the user to open **Integrations**, choose
**Sign in** on the JobsPipe server and authorize with their JobsPipe account. The free
plan needs no card. An API key (`jp_live_...` from https://jobspipe.dev/dashboard) also
works as the server's access token under **Advanced**.
