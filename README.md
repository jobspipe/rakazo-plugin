# JobsPipe plugin for Rakazo

Give your [Rakazo](https://rakazo.com) bots live hiring data: job postings from 30+ job
boards, ATS feeds and company career sites, companies hiring for a skill, layoffs,
company tech stacks, and alerts for new postings.

The plugin connects the hosted [JobsPipe MCP server](https://docs.jobspipe.dev/ai-agents/mcp)
(`https://mcp.jobspipe.dev/mcp`) and adds a `jobspipe` skill that teaches bots which
tool to use. No code from this repository runs.

## Install

1. In Rakazo, open **Integrations**, choose **+** → **From GitHub**, paste
   `https://github.com/jobspipe/rakazo-plugin/tree/main/jobspipe`, and choose **Preview**.
2. Choose **Connect**, then **Add skills**.
3. Choose **Sign in** on the JobsPipe server and authorize with your JobsPipe account.
   New accounts start on the free plan (1,000 jobs a month, no card).
4. With a bot selected, choose **Use in this bot**.

### API key instead of OAuth

Create a key at https://jobspipe.dev/dashboard, then open **Integrations** → **+** →
**Manage MCP servers**, edit the JobsPipe server, expand **Advanced**, and paste the key
(`jp_live_...`) into **Access token**.

## Use cases

| Who | What to ask a bot |
| --- | --- |
| **Job seekers** | "Find remote senior React roles in Europe posted this week that pay over €80k." · "Alert me when a new product designer role opens in Singapore." |
| **Recruiters and sourcers** | "Which companies are hiring Kubernetes engineers in Berlin right now?" · "Who just laid off data scientists? I want to reach them." |
| **Sales and GTM teams** | "Find Series B fintechs hiring their first RevOps lead: they need our tool." · "Which companies using Salesforce are hiring SDRs in the US?" |
| **Founders and product teams** | "Which competitors are hiring for AI roles, and what do the postings say they're building?" · "What stack does linear.app run?" |
| **Investors and analysts** | "How fast is this portfolio company hiring compared with last quarter?" · "Which startups in Jakarta doubled engineering openings this month?" |
| **HR and compensation** | "What do data engineer postings in London list as salary ranges?" · "Which skills appear most in staff ML engineer roles?" |
| **Job boards and newsletters** | "Every remote climate-tech job posted today, as a list with links." · "Alert me when a new remote climate-tech role is posted." |

Bots can combine these on a **routine**: for example, a weekly digest of new roles for
a job seeker, or a daily list of companies that started hiring for a role you sell into.

## Tools

`search`, `fetch`, `search_jobs`, `search_documentation`, `search_hiring_companies`,
`search_companies_by_technology`, `suggest_companies`, `resolve_company`,
`get_company_profile`, `get_company_tech_stack`, `detect_company_tech_stack`,
`resolve_technologies`, `search_layoffs`, `research_question`, `create_signal`,
`list_signals`, `update_signal`, `delete_signal`, `get_account_info`, `upgrade_plan`,
`give_feedback`.

Searches draw credits from the connected JobsPipe plan (1 credit = 1 job returned).
Signals cost no job credits. Pricing: https://jobspipe.dev/pricing

## Support

https://jobspipe.dev · https://docs.jobspipe.dev
