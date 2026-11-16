# Transaction Workflow App — Project Notes

Running record of decisions and context so every session starts from the same place.

## The business
- Owner runs a real estate brokerage (Sotheby's International Realty affiliate) in **Colorado**.
- **180 agents**, **6 transaction coordinators (TCs)**.
- Corporate transaction system: **dash** (TCs enter deal data manually; no integration planned).
- File storage: **Dropbox** (already in use).
- No existing transaction-management app.

## Current process (to be replaced)
1. Agent gets a new listing (sell side) or goes under contract (buy side).
2. Agent fills out PDF intake forms and emails them to a shared TC inbox.
3. TCs enter the info into dash.
4. Agent receives a document checklist and emails documents as the deal progresses.

## What the app does
- Agents: create a deal (listing or contract), see the checklist status of each of their deals, and upload PDFs to checklist items.
- TCs: see a queue of new deals to enter in dash, monitor all deals and missing documents, and approve or reject documents.
- Documents **pass through** the app into Dropbox. The app does not keep copies of files; it only stores deal details, checklist status and a link to each file in Dropbox.

## Decisions
- Owner owns, hosts and pays for the app (corporate card).
- Start small (MVP), pilot with a few agents, expect bugs early.
- No budget or timeline; side project.
- dash stays a manual entry step for TCs.
- Keep wire instructions and bank info out of the app.

## Open items
- [ ] Owner to provide: document checklists (listing and buy side) and all blank intake forms.
- [ ] Confirm Colorado record-retention requirements with counsel or the Colorado Real Estate Commission.
- [ ] Decide Dropbox folder structure and which Dropbox account the app connects to.
- [ ] Decide how agents sign in (email link vs. Google/Microsoft account).
