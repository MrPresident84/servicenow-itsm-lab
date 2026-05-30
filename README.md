# ServiceNow IT Service Management (ITSM) Lab

## Objective

> This project demonstrates hands-on experience performing core Tier 1 IT help desk
> tasks within ServiceNow, one of the most widely deployed ITSM platforms in enterprise
> environments.
>
> Tasks were completed in a ServiceNow Personal Developer Instance (PDI) using
> real-world workflows, including incident creation and lifecycle management, priority
> triage, escalation procedures, problem record creation, knowledge base authoring,
> SLA monitoring, and reporting.

## Key Skills Demonstrated

- Incident creation, triage, and lifecycle management
- Priority assignment using Impact/Urgency matrix
- Work note documentation and resolution recording
- Escalation identification and handoff procedures
- Problem record creation and incident linking
- Knowledge base article authoring and publishing
- SLA awareness and timer interpretation
- User and group administration
- Role-based access control (RBAC)
- Reporting and dashboard configuration
- End-user portal experience via user impersonation


## Tools & Technologies Used

- ServiceNow (Personal Developer Instance — PDI)
- ServiceNow Incident Management module
- ServiceNow Problem Management module
- ServiceNow Knowledge Management module
- ServiceNow SLA module
- ServiceNow Reports module


## Real-World Relevance

ServiceNow is the industry-standard ITSM platform used by thousands of enterprises
worldwide. Tier 1 help desk technicians use ServiceNow daily to log incidents,
document work notes, manage ticket queues, and escalate issues that exceed Tier 1
scope. Familiarity with ServiceNow's interface and workflows is one of the most
commonly listed requirements in IT help desk job postings.

---


## Part 1 — User and Group Administration

### Objective

Create user accounts representing the three core roles in a help desk environment —
end user, help desk agent, and manager — and configure a support group to simulate
realistic ticket assignment and queue ownership.

### Steps Performed

- Created 3 user accounts in User Administration: Linda Marsh (end user / Finance),
  Derek Holt (Help Desk Technician / IT), and Yvonne Carter (IT Service Desk Manager / IT)
- Assigned the **itil** role to Derek Holt and Yvonne Carter, granting access to
  work on incident records
- Created a support group named **Meridian Help Desk** with Yvonne Carter as manager
- Added Derek Holt as a group member to enable ticket assignment to the group

### Screenshots

[![Users List](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/01-users-list.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/01-users-list.png)

[![Agent User Record](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/02-agent-user-record.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/02-agent-user-record.png)

[![Support Group](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/03-support-group.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/03-support-group.png)

### Real-World Relevance

Help desk platforms require proper user roles and group structures before tickets
can be routed and assigned correctly. In a real environment, a new technician's
account must be configured with the appropriate role before they can open, update,
or resolve incident records. Group membership drives queue visibility and workload
distribution across the team.

---


## Part 2 — Incident Management

### Objective

Create and manage a realistic set of incidents covering a range of priorities,
categories, and states — then work them through the full incident lifecycle
from intake to resolution, including work note documentation and resolution recording.

### Incident Priority Matrix

ServiceNow calculates Priority automatically from the combination of Impact and Urgency:

| Priority | Impact | Urgency | Description |
| --- | --- | --- | --- |
| P1 — Critical | High | High | Major outage, multiple users affected |
| P2 — High | Medium | Medium | Significant issue, productivity impacted |
| P3 — Moderate | Low | Low | Minor issue, workaround available |

### Incidents Created

| # | Short Description | Category | Priority | State |
| --- | --- | --- | --- | --- |
| INC001 | User unable to log into Outlook after password reset | Software | P3 | Resolved |
| INC002 | VPN client fails to connect — remote worker | Network | P2 | Resolved |
| INC003 | Shared office printer showing offline | Hardware | P3 | On Hold |
| INC004 | Request to install Adobe Acrobat Pro | Software | P3 | New |
| INC005 | File server unreachable — 25 users impacted | Network | P1 | In Progress |
| INC006 | Outbound emails not delivering to external recipients | Software | P2 | Resolved |
| INC007 | New hire workstation setup and account creation | Request | P3 | New |
| INC008 | Recurring Windows login delays — second report this week | Software | P2 | Resolved |

### Steps Performed

- Created all 8 incidents using the Incident → Create New module
- Populated all required fields: caller, category, subcategory, short description,
  full description, impact, urgency, assignment group, and assigned agent
- Added work notes to each incident documenting diagnostic steps taken
- Resolved applicable incidents with resolution codes and resolution notes
- Set INC003 to On Hold pending user confirmation
- Left INC005 (P1) in In Progress state to simulate an active escalated outage

### Screenshots

[![Incident List — All](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/04-incident-list-all.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/04-incident-list-all.png)

[![P1 Incident Detail](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/05-p1-incident-detail.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/05-p1-incident-detail.png)

### Real-World Relevance

Incident management is the primary daily function of a Tier 1 help desk technician.
Accurate priority assignment ensures that critical outages receive immediate attention
while lower-impact requests are queued appropriately. Thorough work note documentation
creates an auditable record of every action taken — essential for escalations, shift
handoffs, and post-incident reviews. The ability to recognize when an incident
exceeds Tier 1 scope and escalate it correctly is one of the most important
judgment calls a help desk technician makes.

---


## Part 3 — P1 Escalation Procedure

### Objective

Demonstrate recognition of a major incident requiring escalation beyond Tier 1
scope, and document the escalation process within the incident record.

### Incident

**INC005 — File server unreachable — estimated 25 users impacted across Finance,
HR, and Operations.**

### Steps Performed

- Confirmed server unresponsive via simulated ping and RDP connection attempt
- Determined the issue exceeded Tier 1 scope (infrastructure-level failure)
- Documented escalation decision and rationale in work notes
- Notified manager (Yvonne Carter) of P1 status
- Advised affected users of outage and pending ETA
- Left incident in In Progress state pending senior infrastructure team resolution

### Work Note Documented

> *"Confirmed server unresponsive via ping and RDP. Escalating to senior infrastructure
> team — beyond Tier 1 scope. Notified Yvonne Carter (manager) of P1 status.
> Users advised of outage and ETA pending."*

### Screenshot

[![P1 Incident Detail](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/05-p1-incident-detail.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/05-p1-incident-detail.png)

### Real-World Relevance

Knowing when not to keep troubleshooting is a critical Tier 1 skill. Attempting
to resolve infrastructure-level failures at Tier 1 wastes time and can worsen
an outage. Proper escalation — with documentation, manager notification, and
user communication — is what separates a proficient help desk technician from
one who is still learning the role.

---


## Part 4 — Problem Management

### Objective

Create a Problem record to investigate the root cause behind a recurring incident,
demonstrating awareness of the distinction between incident management
(restoring service) and problem management (eliminating root cause).

### Background

INC008 — recurring Windows login delays — was the second report of the same
symptoms within five days on the same workstation. Resolving the individual
incident is not sufficient when a pattern is emerging. A Problem record was
created to drive root cause investigation and prevent recurrence.

### Steps Performed

- Navigated to Problem → Create New
- Created a problem record documenting the recurring login delay pattern
  and suspected root cause: conflicting Group Policy Objects from a recent
  domain policy update
- Linked INC008 to the problem record via the Related Incidents tab
- Set state to Open pending infrastructure team investigation

### Screenshot

[![Problem Record](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/06-problem-record.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/06-problem-record.png)

### Real-World Relevance

Incident management restores service. Problem management prevents recurrence.
A Tier 1 technician who recognizes a pattern across multiple incidents and
flags it for problem management is demonstrating a level of situational
awareness that directly reduces ticket volume over time. Many organizations
expect Tier 1 staff to at minimum identify potential problem candidates even
if the investigation is handled at Tier 2 or above.

---


## Part 5 — Knowledge Base Article

### Objective

Author and publish a knowledge base article documenting the resolution to a
common incident, making it available for end users and other agents to resolve
the same issue without opening a new ticket.

### Article Published

**Title:** How to Clear Cached Credentials After a Password Reset

**Summary:** Documents the step-by-step resolution for users who cannot log
into applications after a company-wide password reset due to stale cached
credentials stored in Windows Credential Manager.

**Applies to:** Windows 10, Windows 11 — Microsoft Outlook, Office 365

### Steps Performed

- Navigated to Knowledge → Create an Article
- Selected the IT knowledge base
- Authored the full article including issue description, root cause explanation,
  and numbered resolution steps
- Published the article to make it available to end users and agents

### Screenshot

[![Knowledge Article](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/07-knowledge-article.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/07-knowledge-article.png)

### Real-World Relevance

Knowledge base articles directly reduce ticket volume by enabling end users
to self-resolve common issues and allowing agents to resolve recurring tickets
faster. Organizations track knowledge base contribution as a performance metric
for help desk staff. Every article published represents a permanent reduction
in future ticket handling time for that issue category.

---


## Part 6 — SLA Awareness

### Objective

Demonstrate understanding of how SLA timers function in ServiceNow and how
priority levels map to response and resolution time targets.

### What Is an SLA?

A Service Level Agreement (SLA) defines the maximum time allowed to respond
to and resolve an incident based on its priority. ServiceNow tracks SLA
compliance automatically and flags tickets that are at risk of breaching
their targets. SLA awareness is a core help desk competency — a technician
who does not understand SLA timers cannot effectively prioritize their queue.

### Steps Performed

- Opened INC002 (VPN Access Failure — P2) and navigated to the SLA tab
- Reviewed the active SLA timer showing time elapsed against the resolution target
- Navigated to SLA → SLA Definitions to review the default priority-based
  time targets configured in the instance

### Screenshots

[![SLA Timer on Incident](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/08-sla-timer-on-incident.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/08-sla-timer-on-incident.png)

[![SLA Definitions](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/09-sla-definitions.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/09-sla-definitions.png)

### Real-World Relevance

SLA breaches carry real consequences in managed service and enterprise environments —
including contract penalties, escalation to management, and formal incident reviews.
A technician who understands how SLA timers work and uses that awareness to
prioritize their queue is a more effective and reliable team member than one
who works tickets in random order regardless of urgency.

---


## Part 7 — Reporting

### Objective

Run existing reports and build a custom report to demonstrate the ability to
surface meaningful data from the incident queue — a skill used by help desk
agents and managers alike to monitor team performance and identify trends.

### Reports Run

| Report | Purpose |
| --- | --- |
| Open Incidents by Priority | Shows current queue distribution across P1–P4 |
| Incidents by Category | Identifies which issue categories are generating the most volume |
| Resolved Incidents | Summary of tickets closed within the reporting period |

### Custom Report Built

**Name:** Meridian Help Desk — Weekly Incident Summary

**Type:** Bar chart

**Source:** Incident table

**Grouped by:** Priority

This report gives a manager a single-glance view of how many incidents were
handled at each priority level during the week — a standard reporting
deliverable in most help desk environments.

### Screenshots

[![Report — Open by Priority](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/10-report-open-by-priority.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/10-report-open-by-priority.png)

[![Report — By Category](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/11-report-by-category.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/11-report-by-category.png)

[![Report — Resolved Incidents](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/12-report-resolved.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/12-report-resolved.png)

[![Custom Report — Weekly Summary](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/13-custom-report-weekly-summary.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/13-custom-report-weekly-summary.png)

### Real-World Relevance

Help desk managers rely on reports to identify staffing gaps, recurring issue
categories, and SLA compliance trends. A technician who understands how to
pull and read these reports contributes to team-level visibility rather than
just individual ticket throughput.

---


## Part 8 — End User Portal (Impersonation)

### Objective

Demonstrate awareness of the end-user experience in ServiceNow by impersonating
a non-admin user and viewing the platform from the perspective of someone
submitting a ticket rather than working one.

### Steps Performed

- Used the admin Impersonate User feature to log in as Linda Marsh (end user)
- Observed the simplified Service Portal interface available to non-IT users
- Noted the absence of admin navigation, queue views, and configuration tools
- Ended impersonation and returned to admin view

### Screenshot

[![Impersonate End User](https://github.com/MrPresident84/servicenow-itsm-lab/raw/main/screenshots/14-impersonate-end-user.png)](https://github.com/MrPresident84/servicenow-itsm-lab/blob/main/screenshots/14-impersonate-end-user.png)

### Real-World Relevance

Help desk technicians regularly need to understand what the end user sees when
they submit a ticket or access the service portal. Impersonation is a real
admin tool used to troubleshoot user-reported issues with portal access and
to validate that role assignments are working correctly. Understanding the
gap between the admin view and the end-user view is fundamental to supporting
both sides of the ticketing system.

---


## Summary of Skills Demonstrated

| Skill | Tool Used |
| --- | --- |
| User account creation and role assignment | ServiceNow User Administration |
| Support group creation and membership management | ServiceNow User Administration |
| Incident creation and lifecycle management | ServiceNow Incident Management |
| Impact/Urgency/Priority triage | ServiceNow Incident Management |
| Work note documentation and resolution recording | ServiceNow Incident Management |
| P1 escalation identification and documentation | ServiceNow Incident Management |
| Problem record creation and incident linking | ServiceNow Problem Management |
| Knowledge base article authoring and publishing | ServiceNow Knowledge Management |
| SLA timer interpretation and priority-based queue management | ServiceNow SLA Module |
| Report execution and custom report creation | ServiceNow Reports |
| End-user portal experience via impersonation | ServiceNow Admin Tools |

---


## Notes

This lab was performed using a ServiceNow Personal Developer Instance (PDI),
which is a fully-featured free instance available through the ServiceNow
Developer Program at developer.servicenow.com. All incidents, users, and
records are simulated using a fictional managed service provider scenario —
Meridian Technology Services — designed to reflect realistic help desk
workflows. No production data was used.
