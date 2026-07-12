# LifecycleDesk AI

LifecycleDesk AI is a Streamlit-based AI workflow application that demonstrates an end-to-end client proposal, executive approval, CEO quotation, client response, delivery planning, employee allocation, and weekly project execution lifecycle.

This project is built as a hackathon-ready prototype to show how AI-assisted business agents can coordinate a full service-delivery workflow from the first client enquiry to active project tracking.

---

## Project Overview

LifecycleDesk AI works like an AI-powered business lifecycle desk for an AI and data services company.

A client can submit a project enquiry through the AI Front Desk. The system then performs an internal multi-agent analysis, routes the proposal to department executives, allows the CEO to approve and send the quotation, collects the client response, and continues into delivery planning, employee allocation, weekly updates, and post-kickoff project changes.

The complete workflow is:

```text
Client Enquiry
-> AI Front Desk Intake
-> Internal Agent Meeting
-> Executive Review
-> CEO Quotation
-> Client Response
-> Detailed Requirement
-> Technical Architect Delivery Plan
-> Employee Allocation
-> Weekly Project Updates
-> Post-Kickoff Change Management
```

---

## Problem Statement

In many service companies, client proposal handling and delivery execution are split across emails, spreadsheets, meetings, chat tools, and manual follow-ups.

This creates common problems:

* proposal details get scattered
* executive approvals are delayed
* quotations are not linked to delivery feasibility
* HR, Finance, Sales, and Technical teams work in silos
* client communication is disconnected from internal decisions
* employees do not always receive clear weekly targets
* post-kickoff requirement changes are hard to track

LifecycleDesk AI solves this by bringing the complete proposal-to-delivery lifecycle into one AI-assisted Streamlit workspace.

---

## Solution

LifecycleDesk AI provides a role-based AI workflow system where each stakeholder sees only the information relevant to them.

The app supports:

* AI Front Desk for intake and routing
* Sales, HR, Finance, Technical Architect, and CEO review
* client-safe quotation and response portal
* Supabase-backed live workflow tracking
* static Excel master data for demo/reference information
* delivery plan generation
* weekly targets
* employee allocation
* employee weekly updates
* client-safe project progress dashboard
* post-kickoff requirement change management

---

## Main Roles

The application supports the following role-based experiences:

| Role                | Purpose                                                                          |
| ------------------- | -------------------------------------------------------------------------------- |
| AI Front Desk       | Receives client enquiries and routes requests                                    |
| Sales Executive     | Reviews client fit and commercial positioning                                    |
| HR Executive        | Reviews skill gap, hiring need, and people risk                                  |
| Finance Executive   | Reviews cost, margin, quote safety, and payment risk                             |
| Technical Architect | Reviews delivery feasibility, plans execution, allocates employees               |
| CEO                 | Gives final approval and sends quotation                                         |
| Client              | Views quotation, responds, submits detailed requirement, tracks progress         |
| Employee            | Views assigned project, targets, requirement changes, and submits weekly updates |

---

## Key Features

### 1. AI Front Desk

The AI Front Desk receives client enquiries and checks whether all required proposal details are available.

Required client proposal details include:

* company name
* contact email or phone number
* basic project requirement
* expected budget
* expected timeline

The AI Front Desk can also route internal employee queries to HR, Finance, Technical Architect, Sales, or CEO workflows based on the user role and request type.

---

### 2. Multi-Agent Proposal Analysis

After a valid client proposal is received, the system prepares internal AI-assisted analysis for:

* Sales Agent
* HR Agent
* Technical Architect Agent
* Finance Agent
* CEO Agent

The analysis includes:

* project type
* client budget
* client requested timeline
* realistic delivery timeline
* technical scope
* estimated delivery cost
* target quotation
* margin
* skill gap
* hiring need
* resource availability
* timeline risk
* department-level recommendations

---

### 3. Executive Decision Room

Each department executive reviews the proposal from their own perspective.

Department responsibilities:

* Sales comments on client fit, negotiation path, and commercial communication.
* HR comments on hiring need, availability, skill gaps, and people risk.
* Finance comments on cost, margin, payment risk, and quote feasibility.
* Technical Architect comments on delivery feasibility, timeline, blockers, and execution plan.
* CEO reviews every department opinion and gives the final decision.

The system notifies relevant executives when decisions or lifecycle updates happen.

---

### 4. CEO Quotation Approval

The CEO can approve and send the final quotation to the client.

The CEO decision includes:

* final decision
* approved quote
* approved timeline
* CEO note
* internal hiring necessity decision
* generated client quotation

The client quotation is client-safe. It does not expose:

* salary
* internal margin
* employee names
* internal hiring notes
* department comments
* executive discussion
* private blockers

---

### 5. Client Portal

The client portal shows only client-safe information.

Clients can:

* view the CEO-approved quotation
* accept the proposal
* decline the proposal
* request reconsideration
* submit detailed requirements after acceptance
* track delivery progress after project kickoff
* message the Technical Architect

The client cannot see internal decision-room content.

---

### 6. Client Renegotiation Flow

If a client requests reconsideration, the app keeps the original proposal and combines it with the new negotiation terms.

The workflow then:

* reopens the same proposal
* reruns internal analysis using the updated terms
* clears previous human decisions
* notifies executives for a fresh review
* prepares an updated quotation after CEO approval

This avoids creating duplicate proposals for the same client opportunity.

---

### 7. Delivery Planning

After the client accepts the quotation, the client submits a detailed requirement.

The Technical Architect Agent prepares:

* delivery readiness plan
* technical approach
* weekly targets
* module breakdown
* cloud and security direction
* client clarifications needed
* role and resource planning

The Technical Architect then verifies the plan and moves the project into delivery.

---

### 8. Employee Allocation

The Technical Architect can allocate delivery employees based on:

* role
* skill
* department
* current availability
* bandwidth
* allocation percentage

The system excludes non-delivery roles such as:

* CEO
* executives
* Sales
* HR
* Finance
* business support roles

The allocation workflow supports:

* initial allocation
* adding employees after kickoff
* removing employees after kickoff
* soft removal without deleting history
* bandwidth recalculation after add/remove actions

---

### 9. Employee Project Workbench

Allocated employees can log in and view their assigned project work.

Employees can see:

* assigned project
* project role
* assigned module
* customer requirement
* Technical Architect plan
* weekly targets
* current project week
* requirement-change alerts
* previous weekly updates

Employees submit weekly updates with:

* project status
* progress percentage
* blockers
* support needed
* notes

---

### 10. Weekly Project Tracking

LifecycleDesk AI calculates the current project week from kickoff or allocation date.

The system tracks:

* project week number
* week start date
* week end date
* Friday checkpoint
* mandatory employee update count
* team progress
* client-safe weekly update

Client dashboards show summarized progress only.

Technical Architect and CEO dashboards can see deeper internal project activity.

---

### 11. Post-Kickoff Requirement Change

After project kickoff, the Technical Architect can update the project requirement.

When a requirement changes:

* the updated requirement is saved
* completed weeks are preserved
* pending weekly targets are regenerated
* active project members are notified
* employees see a clear requirement-change alert
* the latest requirement is shown in the employee workbench
* client and CEO are not automatically notified from this internal control

This helps teams adapt to scope changes without losing delivery history.

---

## Architecture

LifecycleDesk AI uses a simple demo-friendly architecture.

```text
Streamlit UI
   |
   |-- AI Front Desk
   |-- Executive Dashboards
   |-- Client Portal
   |-- Employee Workbench
   |
Python Workflow Layer
   |
   |-- proposal analysis
   |-- role-based routing
   |-- quotation workflow
   |-- delivery planning
   |-- notification workflow
   |-- weekly update workflow
   |
Data Layer
   |
   |-- Supabase for live workflow data
   |-- Excel for static master/demo data
```

---

## Database and Static Data

LifecycleDesk AI uses **Supabase** as the main workflow database.

Supabase stores dynamic/live records such as:

* client proposals
* proposal decision history
* executive decisions
* CEO quotation status
* client accounts
* client responses
* delivery projects
* delivery plans
* project allocations
* employee notifications
* employee weekly updates
* weekly client-safe project updates
* client and Technical Architect messages
* post-kickoff requirement changes

The Excel workbook is used only for **static master data** and sanitized hackathon demo reference data.

The Excel workbook may contain sample/static sheets such as:

* employees
* users
* skills
* salary bands
* role mappings
* project requirement templates
* static company reference data

For the hackathon version, the Excel workbook should contain only fake or sanitized data.

---

## Why Supabase + Excel

The project uses a clear separation:

```text
Supabase = dynamic workflow database
Excel = static master/demo data
```

Supabase is used for live records because workflow data changes whenever users interact with the app.

Excel is used only for static demo data because it is simple, portable, and easy to explain in a hackathon.

This avoids using Excel as the production transaction database.

---

## Data Privacy for Hackathon

This hackathon version should not include real company, employee, salary, client, or confidential project data.

Recommended demo statement:

```text
LifecycleDesk AI uses Supabase for live workflow data and a multi-sheet Excel workbook for sanitized static master data. Real employee, salary, client, and confidential company data are not included in this hackathon version.
```

Use only:

* fake employee names
* fake employee IDs
* fake client names
* fake salary bands
* fake project requirements
* fake login users
* fake workflow records

Do not commit:

* real API keys
* real Supabase keys
* real client data
* real salary data
* real production database URLs
* `.env` files
* confidential company records

---

## Tech Stack

LifecycleDesk AI uses:

* Python
* Streamlit
* Pandas
* OpenPyXL
* Supabase
* Excel for static master/demo data
* LLM integration through `llm_client.py`
* Environment variables or Streamlit secrets for credentials

---

## Project Structure

```text
lifecycledesk_ai_final/
  app.py
  requirements.txt
  llm_client.py

  decisiondesk_chunks/
    01_bootstrap_detection.py
    02_employee_receptionist.py
    03_storage_client_delivery.py
    04_proposal_ui.py
    05_design_system.py
    06_streamlit_runtime.py

  core/
  agents/

  db/
    virtual_company_db_final.xlsx
```

---

## Installation

Create a virtual environment.

```bash
python -m venv .venv
```

Activate the environment.

For Windows PowerShell:

```powershell
.venv\\Scripts\\Activate.ps1
```

For macOS/Linux:

```bash
source .venv/bin/activate
```

Install dependencies.

```bash
pip install -r requirements.txt
```

If required, install common dependencies manually.

```bash
pip install streamlit pandas openpyxl python-dotenv requests plotly supabase
```

Install the LLM SDK used by `llm_client.py`, if it is not already included in `requirements.txt`.

---

## Running Locally

From the project root, run:

```bash
streamlit run app.py
```

The app usually opens at:

```text
http://localhost:8501
```

---

## Environment Variables and Secrets

Do not hardcode secrets in the source code.

Use environment variables, `.env`, or Streamlit secrets for:

* LLM API key
* Supabase URL
* Supabase key
* Supabase database URL
* external API tokens

Example `.env` format:

```text
OPENAI_API_KEY=your_key_here
SUPABASE_URL=your_supabase_url_here
SUPABASE_KEY=your_supabase_key_here
SUPABASE_POOLER_DB_URL=your_supabase_pooler_database_url_here
```

Do not commit `.env` files.

For Streamlit Cloud deployment, add secrets through Streamlit app settings.

---

## Suggested Hackathon Demo Flow

1. Start the Streamlit app.
2. Submit a client enquiry through AI Front Desk.
3. Show the generated internal multi-agent analysis.
4. Log in as Sales, HR, Finance, or Technical Architect and submit opinions.
5. Log in as CEO and approve/send the quotation.
6. Log in as client and accept the proposal.
7. Submit detailed requirement from the client portal.
8. Log in as Technical Architect and verify the delivery plan.
9. Allocate eligible delivery employees.
10. Log in as employee and submit a weekly update.
11. Show the client-safe weekly progress dashboard.
12. Demonstrate a post-kickoff requirement change.
13. Show the employee requirement-change alert.
14. Add or remove a delivery employee and show bandwidth recalculation.

---

## Deployment Notes

For a local hackathon demo:

```bash
streamlit run app.py
```

For Streamlit Cloud deployment, the project normally needs to be available in a GitHub repository.

Before deployment:

* use sanitized demo data only
* confirm `requirements.txt` is complete
* confirm `app.py` is the main entry point
* configure Supabase secrets securely
* configure LLM secrets securely
* avoid uploading real Excel data
* avoid committing `.env` files

If Git access is not available, the project can be zipped and shared with a teammate who has repository access.

---

## Known Limitations

* This is a hackathon/demo prototype.
* Excel is used only for static master/demo data.
* Supabase is used for live workflow records.
* Real production deployment should use stronger authentication, audit logs, access control, backup policies, and monitored database operations.
* Real employee, salary, client, and confidential company data should not be included in the demo version.
* Multi-user production usage should be tested carefully before rollout.

---

## Future Enhancements

Possible future improvements:

* full Supabase migration for all static master data
* stronger authentication and authorization
* audit dashboard
* admin panel for master data management
* project analytics dashboard
* calendar-based sprint planning
* automated weekly client email summaries
* richer employee capacity planning
* production-ready deployment pipeline
* improved notification center
* document upload and parsing for detailed client requirements

---

## Project Status

LifecycleDesk AI is a hackathon-ready AI workflow prototype.

It demonstrates how AI agents and role-based dashboards can coordinate proposal intake, executive approval, CEO quotation, client response, delivery planning, employee allocation, weekly updates, and post-kickoff project changes in one Streamlit application.
::: 
