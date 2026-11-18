---
name: reper-crm
description: Query B2B leads, ONRC/ANAF company profiles, pipeline deals, and email campaign stats in REPER CRM, or save lead notes via the REPER MCP server.
---

# REPER CRM MCP Usage

Use the `reper` MCP server whenever the user asks about companies, leads, pipeline deals, or email outreach campaigns in their REPER account.

## Workflow

1. **Discover projects first** if the user mentions multiple workspaces/projects or if `project_id` is unknown: call `list_projects`.
2. **Search leads** with `search_leads` (supports free text `query` for company name/CUI/phone/email, plus `county`, `city`, `caen`, `stage`, `has_phone`, `has_email`, `has_website`, `assigned`, `contacted`, `has_deal`, `sort`, `limit`).
3. **Inspect full details** of a specific company with `get_lead` (returns ONRC/ANAF data, contacts, financials, recent calls, notes, and linked deals).
4. **Pipeline & campaigns:** use `list_deals` / `get_deal` for sales pipeline status and `list_email_campaigns` / `get_email_campaign` for outreach metrics.
5. **Writing notes:** `add_lead_note` is the only write tool. Call it **only** when the user explicitly asks to save a note on a lead, and confirm the note text with them.

## Safety & Permissions

- All queries run under the authenticated user's own OAuth 2.1 permissions (workspace RLS enforced).
- The MCP server never sends emails or SMS messages and never deletes records.
