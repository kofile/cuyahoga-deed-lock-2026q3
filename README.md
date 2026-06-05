# Deed Lock — Phase 1 Walkthrough
**Cuyahoga County · Q2 2026 · Draft v4**

A single-file interactive demo of the Deed Lock fraud prevention feature, built for walkthrough with the Records, Platform, and Cuyahoga County teams.

> "Demo don't memo." This artifact replaces a spec document. Walk stakeholders through it; don't send them a PDF.

---

## What this is

Cuyahoga citizens enroll a parcel ID at the recorder's counter. Any transfer document submitted against that parcel locks the order at recorder intake and triggers a single SMS — branded as Cuyahoga County Fiscal Office, not Neumo — to the citizen with a one-time code. The citizen replies `CONFIRM` or `DISPUTE`. The order doesn't move until the citizen acts or a supervisor manually resolves it. Claims are valid 12 months and require renewal (Phase 2).

---

## Architectural context

The enrollment framework is **not** Deed Lock-specific. It is a generalized **Enrollment Framework** that will support multiple programs: Deed Lock (Cuyahoga, Q2), Protected Individuals (Summit County), Safe at Home, and others. **Deed Lock is the first program riding on the framework.**

The parcel-match trigger fires at **order intake / processing in the recorder's office.** Cuyahoga is a combined recorder/auditor office, but transfer documents enter the workflow at the recorder side — that's where the lock applies.

---

## What's in the demo

The walkthrough covers eight tabs:

| Tab | What it shows |
|---|---|
| **Full Flow** | End-to-end swimlane across all four phases and three personas |
| **Persona 01 — Citizen** | Step-by-step citizen journey with SMS mockups |
| **Persona 02 — Records Clerk** | Clerk intake view with locked order UI mockup |
| **Persona 03 — Supervisor** | Manual resolution queue and override flow |
| **Reference — System & Specs** | Decision log, business rules, edge cases |
| **Eng Review — Open Questions** | Unresolved architecture and implementation questions |
| **Strategic Sidenotes** | GTM positioning, expansion signals, auditor angle |

---

## How to update it

Everything lives in `index.html`. No build step, no dependencies, no framework.

1. Open `index.html` in any text editor
2. Find the section you want to update (sections are clearly commented)
3. Edit, save, re-upload to GitHub
4. GitHub Pages re-publishes automatically within ~60 seconds

---

## Live URLs

| Environment | URL |
|---|---|
| GitHub Pages | `https://[org].github.io/[repo-name]` |
| Netlify (original) | `https://cuy-fraud-feature-crd429.netlify.app` |

---

## Key contacts

| Name | Role |
|---|---|
| Brian O'Malley | Cuyahoga County — primary contact, include on all Deed Lock meetings |
| Don Roy | Cuyahoga County — `droy@cuyahogacounty.gov` |
| Miguel Basora | Cuyahoga County — `mbasora@cuyahogacounty.gov` |
| Shawn Beeson | Neumo Records Engineering Lead |
| Joe Balfantz | Platform Engineering Lead |
| Tamara Woodward | Product Owner / delivery lead — primary internal owner going forward |

---

## Jira

- Epic: **CRD-429**
- Enrollment Framework: **CRD-581**
- Project: Neumo Records (`CRD`)

---

## Handoff note

This demo and the Enrollment Framework spec are leave-behind artifacts. **Tamara Woodward** is the designated successor for Deed Lock delivery coordination and ongoing PO work. She should be the primary point of contact for Cuyahoga after the current transition window closes.
