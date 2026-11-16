# Transaction Workflow App — Project Notes

Running record of decisions and context so every session starts from the same place.

## The business
- Aspen Snowmass Sotheby's International Realty (website: sothebysrealty.com/aspensnowmasssir), a brokerage in **Colorado**. The owner is the app owner and first admin.
- **180 agents**, **6 sales transaction coordinators (TCs)**.
- **9 offices**: Aspen (3), Snowmass (2), Basalt (1), Carbondale (1), Glenwood Springs (1). The process is the same at every office.
- Corporate transaction system: **dash** (TCs enter deal data manually; no integration planned).
- File storage: **Dropbox Business**, with folders sorted by property address.
- Email: **Microsoft 365 / Outlook**. Everyone has a company email on the `aspensnowmasssir.com` domain.
- No existing transaction-management app.

## Current process (to be replaced)
1. Agent gets a new listing (sell side) or goes under contract (buy side).
2. Agent fills out PDF intake forms and emails them to a shared TC inbox.
3. TCs enter the info into dash.
4. Agent receives a document checklist and emails documents as the deal progresses.

## Pain points
- TCs: agents submit wrong or incomplete documents, and TCs spend a lot of time chasing corrections.
- Agents (and the owner agrees): too many forms, and some ask for the same information repeatedly.
  - Idea: collect each piece of information once and pre-fill the forms from it.

## What the app does
- Agents: create a deal, see the checklist status of each of their deals, and upload PDFs to checklist items.
- TCs: see a queue of new deals to enter in dash, monitor deals and missing documents, and approve or reject documents.
- Documents **pass through** the app into Dropbox. The app does not keep copies of files; it only stores deal details, checklist status and a link to each file in Dropbox.

## Deal types
- **Phase 1: sales only.**
  - **Listing (seller representation)**: its own deal. The file must be complete **before the property goes on the MLS**. It ends there, unless the listing contract is later amended or extended, which reopens it for those documents.
  - **Seller-side transaction** (the listed property goes under contract): a **separate** deal from the listing.
  - **Buyer-side transaction**: its own deal.
- **Later:** rentals (top priority after sales; show a "coming soon" placeholder for now), referrals, land, new development, commercial, terminated contracts, expired or withdrawn listings. Each may need its own checklist.

## People and access
- **Agents** own their deals. A deal can have **co-agents**.
- **Delegates:** an agent can assign assistants or team members who get **standing access to all of that agent's deals**. They can open new deals and amend existing ones without asking the agent each time. The agent sets this up once, not per deal.
- **TC assignment:** by office, then by agent. Each agent has a TC.
- **Staff with access:** owner, managing broker, accounting, VP, director of sales, and (later) rentals TCs.

## Approval and payment
- **TCs approve every document.** An upload stays "submitted" until a TC approves it. A rejection must include a note telling the agent what to fix.
- **A transaction file must be complete before commission is paid.** This is the company's leverage for getting a fully compliant file.
- When a file is complete, the app **emails accounting@aspensnowmasssir.com** with the **commission request form (CRF)** attached or included, so accounting knows who to pay and how much.

## Notifications
- Email and in-app reminders, **every other day**, listing the missing and rejected documents.

## Decisions
- Owner owns, hosts and pays for the app (corporate card).
- Start small (MVP), pilot with a few agents, expect bugs early.
- No budget or timeline; side project.
- dash stays a manual entry step for TCs.
- Keep wire instructions and bank info out of the app.
- Sign-in uses company Microsoft accounts. Only `aspensnowmasssir.com` addresses can log in.

## Open items
- [ ] Owner to provide: document checklists for each sales deal type and all blank forms, including the CRF.
- [ ] Owner to provide: the exact Dropbox folder naming sequence.
- [ ] Pick pilot agents and a pilot TC.
- [ ] Confirm Colorado record-retention requirements with counsel or the Colorado Real Estate Commission.
- [ ] Clarify: when one agent represents both buyer and seller, is that one deal or two?
- [ ] Clarify: who fills out the CRF and when, and does anyone approve it before accounting?
- [ ] Clarify: what each staff role can see and do.
- [ ] Clarify: which TC covers which office(s).
- [ ] Clarify: can an assistant work for more than one agent?
