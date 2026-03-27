# Product Breakdown Structure (PBS)

| ID | Deliverable | Type  | Notes |
|:---|:------------|:--------------------------------------------------|:------|
| 1 |     Web application (frontend )       |      Software                                            |       |
| 1.1 |       Public website      |            Software                                      |  For all users     |
| 1.2|       Registered users website      |                         Sw                        |    For citizens    |
| 1.3|      Municipality offices website       |                sw                                  |    For operators   |
| 1.4|     Admins website        |      sw                                            |       |
| |             |                                                  |       |
| 2 |       Back-end      |                                                  |       |
| 2.1|       Authentication      |                                                  |       |
|2.2|     Reports        |                                                  |       |
| 2.3|      Notifications       |                                                  |       |
|   2.4 |  Direct messages  |    |    |
|   2.5 |  Analytics  |    |    |
|  2.6  |  Maps  |    |    |
|   3 |   Docs |    |    |




---

# Work Breakdown Structure (WBS)

### WBS with traceability to PBS
| WBS ID | Work Package | Description | Traced PBS Outputs (IDs) |
|:------|:-------------|:------------|:--------------------------|
| 1.0 | Project Management | Planning, coordination, monitoring progress | 1,2,3 |

| 1.1 | Requirements Analysis | Define functional and non-functional requirements | 3 |

| 2.0 | System Design | High-level architecture and technology choices | 1,2,3 |
| 2.1 | UI/UX Design | Design layouts and user flows for all frontend areas | 1.1, 1.2, 1.3, 1.4 |
| 2.2 | Backend Design | Define APIs, services, and architecture | 2 |
| 2.3 | Database Design | Define data models and schemas | 2.1, 2.2, 2.3, 2.4, 2.5 |

| 3.0 | Frontend Development - Public Website | Develop public-facing features | 1.1 |
| 3.1 | Frontend Development - Citizen Area | Develop features for registered users | 1.2 |
| 3.2 | Frontend Development - Operator Area | Develop municipality interface | 1.3 |
| 3.3 | Frontend Development - Admin Area | Develop admin dashboard | 1.4 |

| 4.0 | Backend Development - Authentication | Implement login, registration, roles | 2.1 |
| 4.1 | Backend Development - Reports | Implement report creation and management | 2.2 |
| 4.2 | Backend Development - Notifications | Implement notification system | 2.3 |
| 4.3 | Backend Development - Messaging | Implement direct messaging system | 2.4 |
| 4.4 | Backend Development - Analytics | Implement statistics and reporting | 2.5 |
| 4.5 | Backend Development - Maps Integration | Implement geolocation and map services | 2.6 |

| 5.0 | Frontend-Backend Integration | Connect UI with backend APIs | 1,2 |
| 5.1 | Maps Integration (Frontend) | Integrate map UI components | 1.1, 1.2 |

| 6.0 | Testing - Unit Testing | Test individual components | 1,2 |
| 6.1 | Testing - Integration Testing | Test interaction between modules | 1,2 |
| 6.2 | Testing - System Testing | End-to-end testing of the platform | 1,2 |
| 6.3 | Testing - User Acceptance Testing | Validate with expected user scenarios | 1,2 |

| 7.0 | Deployment Setup | Prepare production environment | 1,2 |
| 7.1 | CI/CD Pipeline Setup | Automate build and deployment | 1,2 |
| 7.2 | Release Management | Deploy final version | 1,2 |

| 8.0 | Documentation Writing | Produce system documentation | 3 |
| 8.1 | User Documentation | Guides for citizens and operators | 3 |
| 8.2 | Technical Documentation | Developer and API documentation | 3 |


---

# Gantt, dependencies, and critical path

## Activity table
## Activity Table

| ID | Activity | Duration (weeks) | Start (week) | End (week) | Dependencies | Critical | Milestone |
|:---|:---------|:-----------------|:-------------|:-----------|:-------------|:----------|:----------|
| A1 | Project Management | 12 | 1 | 12 | — | Yes | No |
| A2 | Requirements Analysis | 2 | 1 | 2 | — | Yes | Yes |
| A3 | System Design | 3 | 3 | 5 | A2 | Yes | No |
| A4 | UI/UX Design | 3 | 3 | 5 | A2 | Yes | No |
| A5 | Database Design | 2 | 4 | 5 | A3 | Yes | No |

| A6 | Backend - Authentication | 3 | 6 | 8 | A3, A5 | Yes | No |
| A7 | Backend - Reports | 4 | 6 | 9 | A3, A5 | Yes | No |
| A8 | Backend - Notifications | 3 | 8 | 10 | A6, A7 | Yes | No |
| A9 | Backend - Messaging | 3 | 8 | 10 | A6 | No | No |
| A10 | Backend - Analytics | 3 | 8 | 10 | A7 | No | No |
| A11 | Backend - Maps | 3 | 8 | 10 | A5 | No | No |

| A12 | Frontend - Public Website | 4 | 6 | 9 | A4 | Yes | No |
| A13 | Frontend - Citizen Area | 4 | 6 | 9 | A4 | Yes | No |
| A14 | Frontend - Operator Area | 4 | 7 | 10 | A4 | No | No |
| A15 | Frontend - Admin Area | 3 | 8 | 10 | A4 | No | No |

| A16 | Integration (Frontend + Backend) | 3 | 11 | 13 | A8, A12, A13 | Yes | No |
| A17 | Maps Integration (Frontend) | 2 | 10 | 11 | A11 | No | No |

| A18 | System Testing | 2 | 13 | 14 | A16 | Yes | No |
| A19 | Integration Testing | 2 | 12 | 13 | A16 | Yes | No |
| A20 | User Acceptance Testing | 2 | 14 | 15 | A18 | Yes | Yes |

| A21 | CI/CD Setup | 2 | 9 | 10 | A6 | No | No |
| A22 | Deployment | 1 | 15 | 15 | A20 | Yes | Yes |

| A23 | Documentation Writing | 5 | 10 | 15 | A6, A7 | No | No |


---

## Critical path
A2 → A3 → A5 → A6 → A8 → A16 → A19 → A18 → A20 → A22


Weeks →     1  2  3  4  5  6  7  8  9 10 11 12 13 14 15
A1 (PM)     ███████████████████████████████████████
A2          ██
A3             ███
A4             ███
A5                ██
A6                   ███
A7                   ████
A8                      ███
A12                  ████
A13                  ████
A16                             ███
A19                                ██
A18                                  ██
A20                                    ██
A22                                      █


# Risk Management

**Scales and thresholds**
- **Probability (P)**: 1 (rare) … 5 (almost certain)
- **Impact (I)**: 1 (minor) … 5 (critical)
- **Exposure**: `P × I` (range 1–25)

Risk level thresholds (by exposure):
- **Low**: 1–5
- **Medium**: 6–10
- **High**: 11–16
- **Very High**: >16



## Risks table
## Risks Table

| ID | Risk Statement | Category | P | I | P×I | Level | Mitigation / Response |
|:---|:--------------|:---------|:-:|:-:|:---:|:------|:----------------------|
| R1 | Incorrect or incomplete requirements leading to rework | Requirements/Scope | 4 | 4 | 16 | High | Conduct early stakeholder workshops, validate with prototypes, freeze requirements after review |
| R2 | Delay in backend development affecting integration | Technical | 4 | 5 | 20 | Very High | Build backend modules incrementally, define API contracts early, parallel frontend mock integration |
| R3 | Map service (OpenStreetMap) integration issues or API limitations | External/Third-party | 3 | 4 | 12 | High | Early prototyping of map integration, fallback to static map rendering, cache map data |
| R4 | Authentication and user data security vulnerabilities | Security/Privacy | 3 | 5 | 15 | High | Use established auth frameworks, enforce encryption, perform security testing and code reviews |
| R5 | Notification system failure (email or in-app) | Technical | 3 | 4 | 12 | High | Implement retry mechanisms, use reliable email service providers, monitor delivery logs |
| R6 | Performance issues with large number of reports and map markers | Technical | 4 | 4 | 16 | High | Implement pagination, clustering on maps, database indexing, and load testing |
| R7 | Data inconsistency between frontend and backend during integration | Technical | 3 | 4 | 12 | High | Strict API contracts (OpenAPI), automated integration tests, versioned APIs |
| R8 | Delays due to team coordination or lack of resources | Organizational | 3 | 4 | 12 | High | Use Agile planning, daily standups, task tracking tools, clear role assignments |
| R9 | Incorrect handling of anonymous reports causing privacy leaks | Security/Privacy | 2 | 5 | 10 | Medium | Enforce strict data masking, review all public endpoints, audit logs |
| R10 | Messaging system complexity (real-time or near real-time communication) | Technical | 3 | 3 | 9 | Medium | Start with simple async messaging, avoid real-time features unless required, use polling |
| R11 | Failure in CSV export due to large datasets | Technical | 2 | 3 | 6 | Medium | Implement streaming export, limit export size, paginate data |
| R12 | Integration delays between frontend and backend APIs | Technical | 4 | 5 | 20 | Very High | Start integration early, use mock APIs, enforce strict interface contracts |
| R13 | Lack of adoption / usability issues from citizens | Operational | 2 | 4 | 8 | Medium | Conduct usability testing, iterative UI improvements, simplify workflows |
| R14 | Data loss or corruption in database | Technical | 2 | 5 | 10 | Medium | Implement automated backups, database replication, transaction handling |
| R15 | Deployment issues (environment mismatch, configuration errors) | Operational | 3 | 4 | 12 | High | Use CI/CD pipelines, containerization (e.g., Docker), staging environment testing |

