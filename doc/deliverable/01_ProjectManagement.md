# Product Breakdown Structure (PBS)  

| ID | Deliverable | Type | Notes |
| ----- | ----- | ----- | ----- |
| S1 | Back-end | Software   | Parent category for all server-side  . |
| S1.1 | Status Management | Software  | Tracks report lifecycle: Pending Approval, Assigned, In Progress, Suspended, Rejected, Resolved. |
| S1.2 | Authentication | Software  | Registration, email verification, login and session management for citizens and operators. |
| S1.3 | APIs | Software  | Endpoints connecting back-end, front-end and database; supports all client types. |
| S1.4 | Administrative Tools | Software  | Tools for admins and municipal offices to manage users, reports and system configuration. |
| S1.5 | Geo-location Service | Software  | Handles lat/long storage and OpenStreetMap API integration for report positioning. |
| S1.6 | Notifications Service | Software  | In-platform notifications on status changes for reporters and followers; triggers email dispatch. |
| S1.7 | Messaging Service | Software  | Direct messaging channel between citizens and municipal operators for clarifications and updates. |
| S1.8 | Report Follow / Subscription | Software  | Allows citizens to follow any report and receive the same notifications as the original reporter. |
| S1.9 | Statistics & Analytics Service | Software  | Public stats (by category, time trends) and private admin stats (by status, reporter, top 1%/5%). |
| S1.10| Export Service | Software  | Generates CSV exports from the table view for transparency and offline analysis. |
| S2 | Front-end | Software  | Parent category for all client-side application and design deliverables. |
| S2.1 | Web Client (Responsive) | Software  | Browser-based responsive web application — the primary client per requirements. |
| S2.2 | UX/UI Design | Software  | Wireframes, user flow mapping and high-fidelity visual mockups for all roles. |
| S2.3 | User Interface | Software  | Functional front-end code: map view, table view, report detail, filters, forms, dashboards. |
| I1 | Cloud Hosting | Infrastructure  | Server environments (AWS, Azure) for hosting the web application and back-end services. |
| I2 | Relational Database | Infrastructure  | Structured storage for reports, users, statuses, categories and messaging data. |
| I3 | SMTP Service | Infrastructure  | Email server configuration for verification emails, status alerts and notification emails. |
| I4 | Content Delivery (CDN) | Infrastructure  | CDN for fast asset loading including report photos (max 3 per report). |
| I5 | Backups (Disaster Recovery) | Infrastructure  | Automated backups and data restoration protocols to prevent data loss. |
| I6 | Deployment / CI-CD | Infrastructure  | Setup of CI/CD pipelines and release processes for continuous delivery. |
| D1 | Requirements Documentation | Documentary  | Detailed business and technical specifications. |
| D2 | Test Documentation | Documentary  | QA reports, test plans and test case scenarios. |
| D3 | API Documentation | Documentary  | Reference for endpoints, payloads and auth (Swagger / REST API). |
| D4 | User Documentation | Documentary  | Manuals, guides or help centre articles for citizens, operators and admins. |
| D5 | Database Documentation | Documentary  | Data dictionaries, schema details and ER diagrams. |
| D6 | Architecture & Design Documentation | Documentary  | System diagrams, component maps and technical design decisions. |


---

# Work Breakdown Structure (WBS)

| ID   | Work Package          | Traced PBS IDs           |
|------|----------------------|-------------------------|
| 1.1  | Requirements         | D1                      |
| 2.1  | Design    | S2.2                    |
| 2.2  |  Design      | I2, D5                  |
| 2.3  |  Design     | I1, I4, D6              |
| 3.1  |  Development  | S1.2, S1.3, D3          |
| 3.2  |  Development | S1.5, S1.6, S1.7        |
| 3.3  |  Development  | S1.1, S1.4, S1.8        |
| 3.4  |  Development  | S1.9, S1.10             |
| 3.5  | Development          | S2.1                    |
| 3.6  | Development   | S2.3                    |
| 4.1  | Validation| D2                      |
| 4.2  |  Validation | I5                    |
| 5.1  | Deployment       | I3, I6                  |
| 5.2  |  Deployment| D4                      |

---

# Gantt, dependencies, and critical path

## Activity Table


| ID    | Activity                                                    | Duration (weeks) | Dependencies           | Start (week) | End (week) | Critical Path | Milestone |
|-------|-------------------------------------------------------------|----------------|----------------------|--------------|------------|---------------|-----------|
| T1.1  | Definition of business and technical specifications        | 2              | -                    | 1            | 2          | Yes           | –         |
| T2.1  | Wireframing, user flow mapping, and visual UI design       | 3              | T1.1                 | 3            | 5          | No            | –         |
| T2.2  | Data modeling, schema design, and relational DB setup      | 3              | T1.1                 | 3            | 5          | Yes           | –         |
| T2.3  | Cloud infrastructure, CDN, and system architecture planning| 5              | T1.1, T2.2           | 6            | 10          | Yes           | M1        |
| T3.1  | Core back-end setup, authentication, and API gateway routing| 10             | T2.2, T2.3           | 11            | 20         | Yes           | –         |
| T3.2  | Feature services: Geo-location, Messaging, Notifications   | 5              | T3.1                 | 21           | 25         | No            | –         |
| T3.3  | Status management, Admin tools, Report Follow/Subscription| 3              | T3.1                 | 21           | 23         | No            | –         |
| T3.4  | Statistics & Analytics service and CSV Export service      | 3              | T3.1                 | 21           | 23         | No            | –         |
| T3.5  | Development of the responsive Web Client                  | 12             | T2.1, T3.1           | 21           | 32         | Yes           | M2        |
| T3.6  | Development of functional UI components                    | 4              | T2.1, T3.1           | 21           | 24         | No            | –         |
| T4.1  | Creation of QA test scenarios and execution of test plans  | 2              | T3.2, T3.3, T3.4, T3.5 | 33           | 34         | Yes           | –         |
| T4.2  | Implementation and testing of Disaster Recovery and Backups| 3              | T4.1                 | 35           | 37         | Yes           | M3        |
| T5.1  | Setup of CI/CD pipelines, SMTP server, production release  | 2              | T4.2                 | 38           | 39         | Yes           | –         |
| T5.2  | Finalization of User Manuals and project handover          | 1              | T5.1                 | 40           | 40         | Yes           | –         |


---


## Gantt Chart

![alt text](/data/img/gantt_chart.png)


---


## Critical Path


`T1.1 → T2.2 → T2.3 → T3.1 → T3.5 → T4.1 → T4.2 → T5.1 → T5.2`


---


# Risk Management

## Risk Table 

| ID | Risk | Category | P | I | P×I | Level | Mitigation / Response |
|---|---|---|:-:|:-:|:-:|---|---|
| R1 | Requirements poorly defined or incomplete | Requirements | 3 | 4 | 12 | High | Structured stakeholder interviews; formal sign-off before WP2 begins; change request process for post-approval modifications. |
| R2 | Database schema changes mid-project | Technical | 3 | 4 | 12 | High | Freeze schema at end of T2.2; any change requires PM approval and impact assessment; use versioned migrations. |
| R3 | Cloud provider availability or cost overrun | Infrastructure | 2 | 3 | 6 | Medium | Define multi-region fallback; configure budget alerts from day one; evaluate reserved vs on-demand pricing. |
| R4 | OpenStreetMap API rate limits or downtime | Technical | 2 | 4 | 8 | Medium | Cache geo-location responses server-side; configure fallback tile server; implement graceful degradation with manual coordinate entry. |
| R5 | Authentication security vulnerability | Security | 2 | 5 | 10 | Medium | Follow OWASP Top 10 checklist; conduct penetration test before go-live; enforce HTTPS, rate limiting, and token expiry. |
| R6 | Front-end performance on slow networks | Performance | 3 | 3 | 9 | Medium | CDN and lazy-loading from design phase; Lighthouse performance audits run automatically in CI pipeline. |
| R7 | Statistics & Analytics query performance | Performance | 2 | 3 | 6 | Medium | Design appropriate indexes during T2.2; paginate heavy queries; consider materialized views for top-reporter statistics. |
| R8 | Incomplete test coverage before deployment | Quality | 3 | 4 | 12 | High | Enforce minimum 80% code coverage gate in CI; automated regression suite; manual exploratory testing for edge cases. |
| R9 | Backup restoration failure | Infrastructure | 2 | 5 | 10 | Medium | Monthly full-restore drills on staging; dual-region backup storage; RTO defined and tested in T4.2. |
| R10 | SMTP deliverability issues (emails in spam) | Operations | 2 | 3 | 6 | Medium | Configure SPF, DKIM, DMARC records; warm up sending domain; pre-launch tests with major email providers. |
| R11 | Production release rollback needed | Deployment | 2 | 4 | 8 | Medium | Blue-green deployment strategy; automated smoke tests post-release; rollback procedure documented and tested in staging. |
