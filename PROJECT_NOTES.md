# Transaction Workflow App — Project Notes

Running record of decisions and context so every session starts from the same place.

## The business
- Aspen Snowmass Sotheby's International Realty (website: sothebysrealty.com/aspensnowmasssir), a brokerage in **Colorado**. The owner is the app owner and first admin.
- **180 agents**, **6 sales transaction coordinators (TCs)**.
- **9 offices**: Aspen (3), Snowmass (2), Basalt (1), Carbondale (1), Glenwood Springs (1). The process is the same at every office.
- Corporate transaction system: **dash**. The **front desk** enters new deals manually (no integration planned).
- File storage: **Dropbox Business**, with folders sorted by property address.
- Email: **Microsoft 365 / Outlook**. Everyone has a company email on the `aspensnowmasssir.com` domain.
- No existing transaction-management app.

## Current process (to be replaced)
1. Agent gets a new listing (sell side) or goes under contract (buy side).
2. Agent fills out PDF intake forms and emails them to a shared TC inbox.
3. Staff enter the info into dash.
4. Agent receives a document checklist and emails documents as the deal progresses.

## Pain points
- TCs: agents submit wrong or incomplete documents, and TCs spend a lot of time chasing corrections.
- Agents (and the owner agrees): too many forms, and some ask for the same information repeatedly.
  - Idea: collect each piece of information once and pre-fill the forms from it.

## What the app does
- Agents: create a deal, see the checklist status of each of their deals, and upload PDFs to checklist items.
- Front desk: a queue of new deals to enter in dash and the MLS, and listing office tasks.
- TCs: monitor deals and missing documents, and approve or reject documents.
- Documents **pass through** the app into Dropbox. The app does not keep copies of files; it only stores deal details, checklist status and a link to each file in Dropbox.

## Deal types
- **Phase 1: sales only.**
  - **Listing (seller representation)**: its own deal. The file must be complete **before the property goes on the MLS**. It ends there, unless the listing contract is later amended or extended, which reopens it for those documents.
  - **Seller-side transaction** (the listed property goes under contract): a **separate** deal from the listing.
  - **Buyer-side transaction**: its own deal.
  - **Dual agency** (same agent represents buyer and seller) = **two deals**, one buy side and one sell side, linked. A "dual agency" option links them, and a document that belongs on both sides is uploaded once and filed to both automatically.
- **Later:** rentals (top priority after sales; show a "coming soon" placeholder for now), referrals, land, new development, commercial, terminated contracts, expired or withdrawn listings. Each may need its own checklist.

## People and access
- **Agents** own their deals.
- **Assistants:** an agent assigns them once and they get **standing access to all of that agent's deals**. They can open new deals and amend existing ones without asking the agent each time. One assistant can work for **several agents**.
- **Co-agents** are added **deal by deal**. They only see the deals they're added to.
- **TC assignment:** by office, then by agent. Each agent has a TC.
- **Front desk staff:** see **every deal** (to start). They enter deals into dash and the MLS and do the listing office tasks (MLS, Crest, brochure, ICM, showing instructions, B2B, admin email, advertising).
- **Staff with access:** owner, managing broker, VP, director of sales, accounting, and (later) rentals TCs.
  - Staff can **view** deals only. **Only TCs approve documents.**
  - **Accounting sees completed files only.**

## Approval and payment
- **TCs approve every document.** An upload stays "submitted" until a TC approves it. A rejection must include a note telling the agent what to fix.
- **A transaction file must be complete before commission is paid.** This is the company's leverage for getting a fully compliant file.
- **Commission flow** (transaction deals):
  1. All transaction documents approved by the TC; file is complete.
  2. Title company receives funds and sends an **"advice"** (amount and deal name) to the **TCs**.
  3. **TC uploads the advice to the deal in the app** (replaces emailing it), and the app notifies the agent.
  4. **Agent fills out the CRF** (commission request form).
  5. **TC approves** the CRF.
  6. **Accounting approves** the CRF **in the app**, then wires the agent and marks it paid.
- The app emails **accounting@aspensnowmasssir.com** when a CRF is ready for them, with the CRF included.
- Both CRF approvals (TC and accounting) are recorded on the deal, so everyone can see where payment stands.
- Exception to "only TCs approve": **accounting approves CRFs** (and only CRFs).

## Activity log
- Every change on every deal is logged with who and when. Each deal shows its own log; front desk and leadership also see a company-wide feed.

## Notifications
- Email and in-app reminders, **every other day**, listing the missing and rejected documents.

## Decisions
- Owner owns, hosts and pays for the app (corporate card).
- Start small (MVP), pilot with a few agents, expect bugs early.
- No budget or timeline; side project.
- dash stays a manual entry step, owned by the **front desk** (not TCs).
- Keep wire instructions and bank info out of the app.
- Sign-in uses company Microsoft accounts. Only `aspensnowmasssir.com` addresses can log in.

## Source documents (from owner, Nov 2026)
**All forms and checklists below are outdated placeholders.** The owner is sending current versions. The Closing Checklist (agent to-do list) is **out of scope**: the app is only about collecting the correct document package for each deal.
Kept out of the repo because the examples contain real client data. Summarized here.
- **New-listing intake forms:** Residential Listing Form (dash), MLS Input Form (Aspen Glenwood MLS), Information Form (marketing/brochure/showing), Listing Checklist.
- **Listing Checklist office tasks:** entered into MLS, Crest, brochure created and ordered, ICM, showing instructions, B2B, admin email, advertising. Changes (amend/extend) redo MLS, brochure, B2B, Crest, admin email, ICM.
- **Closed File Checklist (transaction):** agency disclosure or buyer agency contract (not if our listing), title commitment, square footage disclosure (not vacant land), seller's property disclosure, inspection objection and resolution, inspection report, inventory list, lead paint disclosure (built before 1978), contracts, amend/extends, listing checklist, closing checklist, brochure, MLS listing sheet, listing contract (only if our listing), earnest money check/wire copy, earnest money receipt, closing documents, closing instructions (signed by buyer, seller, listing broker and title), closing funds check/wire copy, CRF. "Check not released to broker until file fully executed."
- **Closing Checklist:** an agent's to-do list during the contract (create Under Contract Form and send to TC, MLS status change, dates and deadlines, disclosures, due diligence, closing instructions, utilities, signage, close MLS).
- **Title advice:** a bank wire notice to CLMF LLC dba ASSIR with date, amount, sender (title company), and a reference naming the commission side, agent and property.
- **CRF (Compensation Request Form – Sales):** MLS #, dash trans #, address, seller/buyer legal names, closing date, title company, list/sold price, listing/selling brokers, compensation % offered each side, adjustment amount and explanation, broker gross compensation, ASSIR and outside referral fees, then:
  - gross less referrals → Sotheby's/admin 5% → remainder × agent split = net to agent; rest = ASSIR compensation.
  - Payable-to name, requested by. Broker must approve (signature or email). Attach referral or compensation reduction agreements.

## Current forms (received Nov 17, 2026) — New Listing package (1 of 4 messages)
1. **DASH Residential Sale Listing (SIR)** — 11 pages, **fillable PDF (943 fields)**, so the app can fill it automatically.
   - Required (✓): property subtype, property style, country, address line 1, city, state, zip, listing office, list price, MLS ID, list date (or anticipated list date if prelisting), expiration date, bedrooms, sales associate/team name, English property description.
   - Sections: essentials (subtype, style), location, listing info (prelisting, foreclosure, short sale, display and showing options), open houses, property info (beds/baths, building area, lot, taxes), sales associate, remarks (description, area description, directions, headline, 6 highlights, location, owner quote, transportation, zoning), long feature checklists, property details (year built/renovated, parking, zoning, tax roll #), geographic location, rooms, floors, schools, seller info (type, names, entity, contact, address), contact details, internal notes, property fees.
   - Overlaps with other forms: address, price, beds/baths, taxes, description/highlights, seller names, showing info. Candidates for type-once.
   - Oddity: "Brand Programs" lists ERA options (ERA Distinctive Properties, ERA Home Protection Plan, Gold Star), not SIR. Ask owner.

2. **MLS Input Forms (Aspen Glenwood MLS)** — five versions, chosen by property type: **Residential** (4 pp), **RES Vacant Land** (3 pp), **Fractional** (4 pp), **Commercial Sale** (3 pp), **Commercial Land** (3 pp).
   - **Not fillable PDFs** (0 form fields). The app would collect this information as an online form; it can then print a matching PDF or simply hand the data to the front desk for MLS entry.
   - Shared core on all five: listing member, co-listing agent, address (street #, direction, name, suffix, unit, city, state, zip, county, country, parcel #), type, major area/area, asking price, listing and expiration dates, short sale/REO/auction/foreclosure, agency, seller/owner licensed, member association, deeds, seller's name, zoning, acres/lot sqft, sub/loc, legal, directions, metro tax district, taxes and tax year, transfer tax, HOA/association fees, special assessments, earnest money and payable to, HOA management contact, financing remarks, seller will trade, public remarks, addendum, showing instructions, seller internet opt-outs.
   - Residential adds: beds/baths, garage, furnished, square footage breakdown, stories, primary bedroom on main, loft/den/bonus, short-termable, year built/remodeled, ADU, right of first refusal, new construction/ARC/plans transferable, energy programs.
   - Vacant Land adds: sub-type, development approved, ARC, plans transferable, ADU allowed, FAR and allowable FAR.
   - Fractional adds: ownership interest, rotation system, vacation trading, seasonal interest, floating unit, unit faces.
   - Commercial Sale adds: inside city limits, condominiumized, building sqft, occupant type, # units, business name, inventory, ceiling heights, N.O.I., total expenses.
   - Commercial Land adds: original list price, # units allowed, PUD.
   - Implication: commercial listings are sales too; confirm whether commercial is in phase 1.
3. **Listing Contract Drafting Form** (1 page, fillable, 18 fields): seller, property address, legal/subdivision, listing broker, start and end dates, commission (total, buyer agent, transaction broker), price, earnest money, furnished, parking and storage, association dues, additional provisions. Seller agency vs. transaction broker.
4. **Exclusive Right-to-Sell Listing Contract (LC50)** — Colorado Real Estate Commission form, mandatory from Jan 1, 2026. 11 pages, **fillable (173 fields)**.
5. **Seller Advisory** (Cox Peterson LLC for ASSIR, CP-8-26) — three versions by property type: **Residential** (6 pp), **Vacant Land** (5 pp), **Commercial** (5 pp). Not fillable. Header: seller, property, broker, brokerage firm. Covers confidential-information consent and other disclosures.
6. **Amend/Extend Checklist** — per change: date, type of change, saved to folder named `EX Amend.<what changed>.<M.D.YYYY>` (e.g. price change, expiration date, terms), then office tasks: **MLS, DASH, Foundation, Admin Email, B2B, Brochure**.
7. **Admin Email Template** — one block per listing event, each with MLS #, legal, address, city, seller, list broker, price and an event date: New Listing, New/Old Listing (old and new MLS #), Extended, BOM/Extended, Price Change/Extended, Price Change, Expired, Withdrawn, BOM (back on market), BOM/Price Change, Cancelled, Under Contract (U/C date, close date, transaction ID), Fell Through/BOM, Fell Through, Fell Through/Withdrawn, Closed (sell broker, sale price, close date). The app can write these automatically from deal data.
8. **Area Descriptions** — standard paragraph per town (Aspen, Snowmass Village, Basalt, Carbondale, Glenwood Springs, ...). The app can drop the right one into the dash "Area Description" based on the town.

### Implied new-listing package (to confirm)
- Agent: Listing Contract Drafting Form → signed ERTS Listing Contract (LC50) → signed Seller Advisory (version by property type) → dash listing form → MLS input form (version by property type).
- Front desk: enter in dash and MLS, Foundation, B2B, brochure, admin email; same set again for each amend/extend.
- Property type drives which MLS form and which Seller Advisory are required.

## Current forms — Buyer contracts (received Nov 17, 2026)
1. **Buyer Advisory** (Cox Peterson for ASSIR, CP-8-26) — three versions by property type: **Residential** (9 pp), **Vacant Land** (7 pp), **Commercial** (8 pp). Not fillable. Header: buyer, broker, brokerage firm.
2. **Buyer agreement — one of:**
   - **Exclusive Right-to-Buy Listing Contract (BC60)** — CREC form, mandatory from Jan 1, 2026. 7 pages, **fillable (93 fields)**.
   - **Buyer Transaction-Broker Listing Contract (Non-Exclusive)** (Cox Peterson, CP-9-26) — 3 pages, not fillable.
- Likely replaces the old "Agency Disclosure or Buyer Agency Contract" item on buyer-side deals (confirm).

## Mockup
- `mockup/index.html` — clickable prototype with example data (published as a private artifact).

## Open items
- [ ] Owner to provide: current checklists and blank forms for each sales deal type, including the CRF (coming).
- [ ] Owner to provide: the exact Dropbox folder naming sequence.
- [ ] Pick pilot agents and a pilot TC.
- [ ] Confirm Colorado record-retention requirements with counsel or the Colorado Real Estate Commission.
- [ ] TBD: which TC covers which office(s).
