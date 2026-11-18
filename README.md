# REPER CRM — Cursor Plugin

Official Cursor plugin for [REPER.APP](https://reper.app), a Romanian B2B Sales CRM with ONRC/ANAF company data, sales pipelines, and email outreach.

It connects Cursor to your REPER workspace via the remote **Streamable HTTP MCP server** (`https://api.reper.app/mcp`) using **OAuth 2.1 with Dynamic Client Registration (DCR) and PKCE**.

## Setup

1. Install the **REPER CRM** plugin from the Cursor Marketplace (or **Customize → MCPs**).
2. Click **Connect** on `reper` to open the browser sign-in flow at `https://app.reper.app/oauth/consent`.
3. Sign in to your REPER account and click **Permite accesul**.

No API keys or client secrets are required. All access strictly respects your REPER workspace role and row-level security (RLS).

## Tools

| Tool | Access | Description |
| --- | --- | --- |
| `list_projects` | Read-only | List workspaces, projects, your role, and lead counts. |
| `search_leads` | Read-only | Search and filter leads by name, CUI, phone, email, county, city, CAEN, stage, assignment, or deal status. |
| `get_lead` | Read-only | Full company profile (ONRC/ANAF details, contacts, financials, scores, recent calls, notes, linked deals). |
| `add_lead_note` | Write | Add a text note to a lead (only when explicitly requested; never sends external messages or deletes data). |
| `list_deals` | Read-only | List pipeline deals, stages, and currency totals. |
| `get_deal` | Read-only | Detailed view of a specific pipeline deal. |
| `list_email_campaigns` | Read-only | List project email campaigns with delivery/open/click/reply/conversion stats. |
| `get_email_campaign` | Read-only | Detailed campaign report (step performance, top links, daily trend, conversion sources). |

## Support & Policies

- Website: [reper.app](https://reper.app)
- Privacy Policy: [reper.app/legal/confidentialitate.html](https://reper.app/legal/confidentialitate.html)
- Terms of Service: [reper.app/legal/termeni.html](https://reper.app/legal/termeni.html)
- Support: `contact@reper.app`
