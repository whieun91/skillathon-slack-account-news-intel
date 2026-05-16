---
name: slack-account-news-intel-demo
description: Demo-safe version of Slack account news intelligence for Skillathon submissions. Use when Codex needs to analyze public company news with mock Slack plan and usage data for upsell, Enterprise+ expansion, renewal risk, attrition prevention, or Slack-ready account briefings. Produces readable Korean Markdown reports and copy-paste-ready Slack summaries while avoiding real customer names, internal usage data, secrets, or private account notes.
---

# Slack Account News Intel Demo

## Overview

Use this skill to turn public customer/prospect news and mock Slack account data into account-level sales intelligence for Slack account executives. Prioritize readable Markdown reports and Slack-ready summary messages over spreadsheets.
This demo version is intended for Skillathon submission, sharing, and reproducible demos. Do not include real customer lists, real Slack usage data, private account notes, API keys, tokens, webhook URLs, or other sensitive data in this skill folder.
For Korean users, write the final report, Slack summary, labels, recommendations, and commentary in Korean unless the user explicitly requests another language.
Keep the intelligence report format, but add pipeline-generation guidance when the user wants outreach timing, hooking points, or weekly pipeline creation.

## Inputs

Ask for missing inputs only when they are necessary for the requested output. Useful inputs include:

- Customer or prospect list, preferably with Korean and English names if available
- Current Slack plan, usage status, renewal timing, owner, segment, and strategic notes
- Licensed users, paid users, active users, monthly active users, workspace count, and Slack Connect usage when available
- Reporting period, defaulting to the last 7 days for weekly reports
- Target outcome: upsell, Enterprise Grid, Enterprise+, new logo, renewal defense, or attrition risk monitoring
- Pipeline target or campaign goal, such as creating 10 qualified pipeline opportunities per week
- Preferred output language, defaulting to Korean when the user writes in Korean

If customer plan data is absent, still analyze news but label plan-based recommendations as assumptions.
If the account list is large, prioritize Enterprise, Business+, strategic accounts, and accounts with severe risk signals before broad Free or Pro coverage.
If the account is already on Enterprise or Enterprise+, do not describe the opportunity as a simple plan upgrade. Frame it as expansion of paid users, workspaces, Slack Connect/external collaboration, AI and Salesforce workflow adoption, governance/compliance value, or renewal protection.

## Workflow

1. Normalize account names and aliases before searching or analyzing. Include Korean corporate names, brand names, app names, and common English names.
   - When the source account name is English only, search both the English name and likely Korean names.
   - If no Korean alias is provided, first identify the Korean company or brand name from official sites, company profiles, app listings, press releases, or reputable Korean business sources.
   - Preserve uncertainty: if a Korean alias is inferred but not confirmed, label it as an assumption.
2. Gather recent, source-linked news for each account. Prefer reputable business, tech, industry, press release, and company newsroom sources. Include article dates.
3. Classify each news item using `references/signal-taxonomy.md`.
4. Map signals to Slack sales implications:
   - Expansion, hiring, funding, IPO, global growth, ecosystem growth, or DX/AX: look for upsell and Enterprise plan opportunities.
   - Google Workspace, Salesforce, Atlassian, ServiceNow, Okta, AWS, or cloud collaboration adoption: treat as possible Slack-compatible digital workplace momentum unless the source says otherwise.
   - Cost cutting, restructuring, layoffs, business contraction, security incidents, regulatory pressure, tool consolidation, or Slack discontinuation: treat as renewal or attrition risk.
5. Apply Slack plan context from `references/slack-plan-context.md` before naming the commercial motion.
6. Combine news signals with usage signals:
   - `active_users > licensed_users`: validate billing definitions, then treat as a strong seat-expansion or true-up conversation.
   - `active_users / licensed_users >= 0.9`: treat as high utilization and renewal-value proof or expansion readiness.
   - `active_users / licensed_users < 0.5`: treat as adoption or attrition risk unless there is a known explanation.
   - Usage unavailable: avoid usage-based claims and ask for usage data if the account is important.
7. Score pipeline fit using `references/pipeline-scoring.md` when pipeline creation or outreach timing matters.
8. Create hook messages using `references/hook-message-template.md` for accounts selected as this-week outreach candidates.
9. Create a Markdown report using `references/report-template.md`.
10. Add readable visuals using `references/visual-summary-template.md` when the report covers more than 3 accounts.
11. Create a concise Slack copy-paste summary using `references/slack-summary-template.md`.
12. Keep recommendations actionable for an AE: next step, reason to engage, suggested talk track, risk owner, and urgency.

## Evidence Rules

- Cite each material claim with source name, date, and URL when available.
- Separate confirmed facts from inference. Use "Inference" or "Assumption" labels when connecting news to Slack opportunity.
- Do not overstate causality. A positive business event is a sales signal, not proof of budget or intent.
- Flag severe risk immediately when a source mentions Slack cancellation, competitor replacement, major cost reduction, legal issues, or layoffs.
- If news is stale, low-quality, duplicate, or only tangentially related, mark it as low confidence or exclude it.

## Output Rules

- Prefer Markdown tables only when they improve scanning. Use short bullets for account narratives.
- Include at least one compact visual summary for weekly reports: priority table, signal distribution chart, urgency matrix, or account heatmap.
- Include usage columns or usage signals when available, especially for Enterprise accounts where seat expansion and renewal defense matter more than plan upgrades.
- If the goal is pipeline creation, include "이번 주 Pipeline 후보 Top 10" near the top while preserving the broader intelligence report sections.
- For Top 10 accounts, include hook point, recommended contact timing, suggested first message, commercial motion, and confidence.
- Keep the Slack summary short enough to paste into a channel without flooding it.
- Order accounts by urgency: severe attrition risk, high-confidence expansion opportunity, medium opportunity, monitor only.
- Include a "No meaningful news found" section only for accounts that were checked and had no useful signals.
- End with AE action items, not generic commentary.

## References

- Read `references/signal-taxonomy.md` when classifying news signals.
- Read `references/report-template.md` when producing the Markdown report.
- Read `references/visual-summary-template.md` when adding charts, tables, or infographic-style summaries.
- Read `references/slack-summary-template.md` when producing a Slack copy-paste message.
- Read `references/customer-data-template.md` when the user needs a format for customer list or Slack plan inputs.
- Read `references/customer-accounts.md` when using the provided customer account and Slack plan list from the source workbook.
- Read `references/slack-plan-context.md` when interpreting Slack plan, upsell, expansion, Enterprise, or Enterprise+ motions.
- Read `references/pipeline-scoring.md` when ranking accounts for weekly pipeline generation.
- Read `references/hook-message-template.md` when producing outreach hooks or first-contact messages.
