Project Meridian – PRD

Author: Saurabh Malhotra
Date: May 21, 2026
Status: GA Scope In Testing

### Purpose
This document serves as a single source of truth for all IBM Meridian product stakeholders, providing a comprehensive and continuously updated view of product requirements and scope. For context on Project Meridian, please refer the PRFAQ.

## Product Vision
Enable new/junior employees (and hence address skills gap) at enterprises to securely interact with z systems using natural language, allowing operations teams, developers, DBAs, security analysts, and business users to retrieve insights, troubleshoot issues, and automate workflows without requiring deep mainframe expertise.

Enable experienced employees/power users at enterprises to perform complex tasks using natural language and become more productive in their day-to-day operations.

## Problem Statement
Z environments contain critical enterprise data but are difficult to access because:
Data is siloed across multiple systems.
Access requires specialized expertise.
Troubleshooting is slow and manual.
Existing AI initiatives rely on stale replicated data.
Security and compliance concerns limit AI adoption.

Organizations need an agentic way to install Terraform on z, and Meridian provides Intent based workflows for Terraform on z.

Target customers (for GA): FIEs that have z17 machine, use DPM mode (don't consume classic mode), and are greenfield
# Business Goals
### Year 1 Goals
Reduce incident resolution time by 50% will be measured via use of agent(s)
Reduce operational investigation effort by 40% will be measured via use of agent(s)
Increase developer productivity by 20% measured via usability sessions, roadmap discussions, NPI surveys of junior employees and power users at target customers
Enable AI-powered access to 100% of supported z data sources
Achieve enterprise-grade auditability and compliance
# Success Metrics
| KPI | Target | How will this be measured? |
| --- | --- | --- |
| Weekly active users | X+ |  |
| Query success rate | >95% |  |
| AI answer accuracy | >90% |  |
| Incident MTTR reduction | 50% |  |
| User satisfaction score | >4.5/5 | via NPI surveys (if we are allowed to run them and customer can share the data) or other mediums (TBD) that are IBM compliant |
| Developer productivity gain | 20% |  |

EPIC 1. Secure z Connectivity (MER-12) - part of admin console/content settings
## Goal: Allow secure access to real-time mainframe data sources.
| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 1.1 | As an AI administrator, I want to connect z systems, so that AI assistants can access enterprise data. | Admin can register a z instance (MVP is z17) System validates connectivity. Connection status is displayed. Failed validations provide actionable errors. Connectivity audit logs are generated. | MER-13 | GA |
| 1.2 | As an administrator, I want to connect <DB2, IMS, MQ, RACF, and VSAM> sources, so that data can be queried through AI. | Admin can add supported data sources. Credentials are securely stored. Health checks run automatically. Connection status updates in real time. Failed sources trigger alerts. | MER-14 | GA |
| 1.3 | As a security administrator, I want native permission enforcement, so that AI cannot bypass existing security controls. | User identity maps to mainframe identity. Access respects RACF permissions. Unauthorized requests are denied. Access attempts are logged. Audit trail is immutable. | MER-33 | Post-GA |
| 1.4 | As an AI administrator, I need to configure the model provider settings | Specify what all models need to be made available to users Remove models from the list (?) | MER-97 | GA |

EPIC 2. Auditability & Observability (MER-21)
## Goal: Provide complete visibility into AI activity.
| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 2.1 | As an administrator, I want a complete audit trail, so that all AI actions are traceable. | Every prompt is logged. Every action is logged. User identity is recorded. Logs are searchable. Logs cannot be modified. | MER-23 | GA |
| 2.2 | As a compliance officer, I want AI decision transparency, so that outputs can be trusted. | Sources are displayed. Reasoning summary is provided. Confidence score is visible. Users can provide feedback. Feedback is stored. | MER-92 | Post-GA |
| 2.3 | As a platform administrator, I want observability dashboards, so that platform health is visible. | Query volumes are displayed. Latency metrics are displayed. Error rates are displayed. Agent activity is displayed. Data can be exported. | MER-93 | GA |

EPIC 3. Natural Language Query Engine (MER-15)
## Goal: Enable users to interact with z data using natural language.
| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 3.1 | As an operations engineer, I want to ask questions in plain English, so that I can investigate incidents faster.  Details: The chat interface and will include following features: (1) Ability to select a specific model (2) Ability to select a particular agent (when agents will become visible) (3) Ability to clear chat (4) Status displaying whether the connection with back-end is established or not. (5) Need to be able to view a ‘history’ of chat sessions. | User can enter natural language prompts. Queries are translated into system actions. Responses return within 10 seconds. Response includes confidence score. Query history is retained | MER-16 | GA |
| 3.2 | As a DBA, I want database insights in conversational form, so that I can analyze performance faster. | User can query DB2 performance metrics. AI summarizes findings. SQL generated is viewable. Results include source references. User can export results. | MER-95 | Post-GA |
| 3.3 | As a manager, I want executive summaries, so that I can understand system health. | AI generates summaries. Summaries include risk indicators. Key metrics are highlighted. Recommendations are provided. Reports can be downloaded. | MER-96 | TBD |
| 3.4 | As a operations engineer, I want guided troubleshooting recommendations, so that incidents can be resolved faster. | System recommends remediation actions. Recommendations include confidence scores. Operators can approve or reject actions. Previous incidents improve recommendations. | MER-17 | Post-GA |

EPIC 4. Workflow browser (MER-28)
| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 4.1 | As an operations engineer, I want the ability to browse existing workflows | See a list of all the available workflows Search across the workflows | MER-27  Design: MER-35 | GA |
| 4.2 | As a developer, I want the ability to download a workflow, customize, and upload it to the workflow browser. | Sort of Marketplace and here do we leverage the TF one for providers? | MER-29 | Post-GA |

EPIC 5. Agents (MER-30)
# (1) Operations Agent (MER-32)
## Goal: Provide AI-powered incident investigation and operational intelligence.

| # | User Story | Acceptance Criteria |
| --- | --- | --- |
| 1.1 | As an operations engineer, I want AI-assisted root cause analysis, so that I can reduce downtime. | AI correlates logs and SMF data. Potential root causes are identified. Evidence is provided. User can drill into details. Investigation timeline is generated. |
| 1.2 | As an operator, I want anomaly detection, so that I can identify issues proactively. | System continuously monitors telemetry. Anomalies are automatically flagged. Severity scores are assigned. Alerts can be acknowledged. Historical comparisons are available. |
| 1.3 | As an operator, I want health checks generated automatically, so that I can maintain system stability. | Health checks run on schedule. Findings are categorized. Risk level is assigned. Recommendations are generated. Reports are shareable. |
# (2) Developer Agent ( MER-98)
## Goal: Integrate AI into the developer workflow.
| # | User Story | Acceptance Criteria |
| --- | --- | --- |
| 2.1 | As a mainframe developer, I want JCL errors explained, so that I can resolve failures faster. | User submits JCL. AI identifies errors. Root cause is explained. Suggested fix is provided. User can re-run validation. |
| 2.2 | As a developer, I want <ABEND> analysis, so that troubleshooting is faster. | ABEND codes are interpreted. Related logs are correlated. Fix recommendations are generated. References are provided. Feedback can improve recommendations. |
| 2.3 | As a developer, I want job execution from my IDE, so that I avoid context switching. | User can submit jobs. Status updates stream live. Output is viewable. Failed jobs show diagnostics. Audit logs are maintained. |

(3) Security & Compliance Agent (MER-99)
## Goal: Provide AI-powered security analysis.
| # | User Story | Acceptance Criteria |
| --- | --- | --- |
| 3.1 | As a security analyst, I want permission change monitoring, so that I can detect risky activity. | Permission changes are tracked. AI identifies anomalies. Risk scoring is available. Alerting is configurable. Historical review is supported. |
| 3.2 | As a compliance officer, I want audit-ready reports, so that regulatory reviews are easier. | Reports are generated on demand. Reports contain access history. Reports are exportable. Reports support PDF format. Reports are immutable once generated. |
| 3.3 | As a security engineer, I want vulnerability scanning, so that I can identify risks. | Code repositories can be scanned. Findings are categorized. Remediation guidance is generated. False positives can be dismissed. Findings are tracked to resolution. |

(4) Contextual Operational Assistant (MER-31)

As an operations engineer, I want an AI assistant that understands platform context, so that I can troubleshoot issues faster.

Acceptance Criteria
Assistant can access operational telemetry.
Recommendations are context aware.
Suggested actions include risk indicators.
User feedback improves recommendations.

EPIC 6. AI Agent Platform (MER-18)
## Goal: Enable enterprises to connect external AI agents.

| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 6.1 | As an AI engineer, I want MCP-compatible access, so that AI agents can use z data. | MCP endpoints are available. Authentication is required. API documentation is provided. Usage metrics are available. Rate limiting is enforced. | MER-19 | GA |
| 6.2 | As an AI engineer, I want SDKs for integration, so that applications can connect quickly. | Python SDK is available. SDK includes examples. Authentication helpers exist. Error handling is documented. SDK usage is logged. | MER-20 | GA |
| 6.3 | As a platform admin, I want agent governance controls, so that AI usage remains secure. | Admin can approve agents. Agent permissions are configurable. Agent activity is logged. Risky actions require approval. Policies can be enforced globally. | MER-94 | Post-GA |

# EPIC 7. Integrations

| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 7.1 | As an operations engineer, I want Meridian integration with productivity tools such as Teams, Slack | Meridian integration is available with MS teams |  | Post-GA |
| 7.2 | As an operations engineer, I want Meridian integration with code assistants | Candidates: IBM Bob Co-pilot Cursor |  | Post-GA |

# EPIC 8. Identity and Access Management

Goal: Provide a secure, scalable, and standards-based identity and access management solution that enables Meridian users to authenticate through external identity providers using OIDC and SAML, while enforcing Role-Based Access Control (RBAC) across the application.

| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 8.1 | As a Meridian user, I want to authenticate using an OpenID Connect (OIDC) identity provider and have access to Meridian’s features based on my assigned role, so that I can securely access Meridian with the appropriate permissions. | AC1: Redirect to Identity Provider Given a user is not authenticated  When the user clicks "Sign In"  Then the application redirects the user to the configured OIDC Identity Provider login page.  AC2: Successful Authentication Given a user enters valid credentials at the Identity Provider  When authentication is successful  Then the application receives and validates the OIDC tokens  And creates an authenticated user session  And redirects the user to the application's home page.  AC3: User Information Retrieval Given a user has successfully authenticated  When the application processes the OIDC token or user info endpoint response  Then the user's unique identifier, name, and email address are retrieved and stored in the session.  AC4: Token Validation Given the application receives an ID token or access token  When token validation occurs  Then the token signature, issuer, audience, and expiration are validated  And invalid tokens are rejected.  AC5: Unauthorized Access Given a user is not authenticated  When the user attempts to access a protected page or API  Then the user is redirected to the login page or receives a 401 Unauthorized response.  AC6: Logout Given an authenticated user  When the user selects "Logout"  Then the application session is terminated  And the user is logged out from the Identity Provider (if supported)  And the user can no longer access protected resources without re-authenticating.  AC7: Session Expiration Given a user's session or token has expired  When the user attempts to access a protected resource  Then the user is prompted to authenticate again.  AC8: Configuration Management Given OIDC settings are required  When the application is deployed to an environment  Then the Identity Provider URL, Client ID, scopes, and redirect URIs are configurable without code changes. | MER-64 | GA |
| 8.2 | User Provisioning and Identity Mapping |  |  | Post-GA |
| 8.3 | RBAC |  |  | Post-GA |

EPIC 9. Compliance

9.1 SOX Compliance of Meridian product/code repos

Focus is usually on SOX IT General Controls (ITGCs) around change management, access management, auditability, and segregation of duties rather than financial functionality itself.

EPIC: SOX Compliance Enablement for Product Development Repositories

As a Compliance Officer, I want Meridian source-code repositories, CI/CD pipelines, and release processes to enforce SOX-compliant controls, so that all changes impacting financial reporting systems can be traced, approved, tested, and audited.

As Meridian, we want our repositories, build and release promotion activities and logs to be auditable, so that we are SOX compliant.

| # | User Story | Acceptance Criteria | JIRA | Scope |
| --- | --- | --- | --- | --- |
| 9.1.1 | Repository Access Governance  As a Repository Administrator, I want access to source-code repositories to be controlled through approved roles, so that only authorized personnel can view, modify, or administer source code | Access is granted only through approved requests. Repository roles follow least-privilege principles. Privileged roles require manager and repository-owner approval. All access grants, modifications, and removals are logged. Quarterly access review reports are available. Dormant accounts are automatically identified and reported. |  |  |
| 9.1.2 | Branch Protection Controls  As a Compliance Manager, I want protected branches to prevent unauthorized code changes, so that production-bound code cannot be modified without appropriate review. | Direct commits to protected branches are prohibited. Pull/Merge Requests are required for all changes. Force-push operations are disabled on protected branches. Branch protection settings are auditable. Any changes to branch protection rules are logged. |  |  |
| 9.1.3 | Code Review and Approval Workflow  As an Auditor, I want all code changes to undergo independent review and approval, So that change authorization controls satisfy SOX requirements. | Every code change requires at least one reviewer. The author cannot self-approve their own change. Approval history is retained indefinitely or according to retention policy. Review comments and approvals are timestamped. Merge activity is logged and auditable. |  |  |
| 9.1.4 | Segregation of Duties (SoD)  As a Compliance Officer, I want development and deployment responsibilities to be separated, so that no individual can introduce and deploy changes without oversight. | Developers cannot directly deploy to production. Production deployment permissions are restricted. The system identifies users with conflicting permissions. SoD exceptions require documented approval. SoD exception reports are available for audit review. |  |  |
| 9.1.5 | CI/CD Pipeline Governance  As a Release Manager, I want deployment pipelines to enforce approval and traceability controls, so that production releases comply with SOX change-management requirements. | All production deployments originate from approved source repositories. Deployment records reference the associated change request or ticket. Production deployments require documented approval. Pipeline execution logs are retained. Deployment artifacts are traceable to source commits |  |  |
| 9.1.6 | Audit Logging  As an Internal Auditor, I want repository and pipeline activities to be captured in immutable audit logs, so that compliance evidence can be produced during audits. | Audit logs record authentication events. Audit logs record repository administration changes. Audit logs record permission changes. Audit logs record merge and release activities. Audit logs are protected from modification. Logs are retained according to compliance policy. |  |  |
| 9.1.7 | Release Traceability  As a Compliance Auditor, I want every production release to be traceable back to approved requirements and code changes, So that release integrity can be verified. | Every release references approved work items. Every release references associated commits. Every release references review and approval records. Release artifacts are versioned and immutable. Traceability reports can be generated on demand. |  |  |
| 9.1.8 | Compliance Reporting  As a Compliance Manager, I want automated compliance reports for repositories and delivery pipelines, So that evidence collection is efficient and repeatable. | Access review reports are available. Repository permission reports are available. Deployment approval reports are available. Change traceability reports are available. Reports can be exported for audit purposes. |  |  |

## Non-Functional Requirements (often required by auditors)
| Requirement Area | Requirement |
| --- | --- |
| Auditability | All control activities must be logged and searchable |
| Retention | Audit records retained for minimum policy-defined period (e.g., 7 years) |
| Integrity | Logs and release artifacts must be tamper-evident |
| Traceability | Requirement → Code → Review → Build → Deployment traceability |
| Access Control | RBAC with least privilege |
| Segregation of Duties | No single user can develop, approve, and deploy the same change |
| Evidence Collection | Compliance evidence available without manual reconstruction |
| Monitoring | Alerts generated for control violations |

9.2 post-MVP scope
SOC2
PII
# MVP Scope
### Included
Secure z connectivity
Natural language querying
Audit logging
Admin console
OIDC Integration
### Phase 2
Agents
Operations Agent
Developer Agent
Security Agent
Automated remediation
Multi-agent orchestration
Predictive analytics
Capacity planning assistant
SAML
RBAC

Phase 3
Agent marketplace

# Non-Functional Requirements
### Security
SSO/SAML
RBAC
Encryption at rest and in transit
Audit logging
Zero trust architecture
### Performance
Query response <10 seconds
99.9% uptime
Horizontal scalability
### Compliance
SOX
FIPS - TBD
Post-GA
SOC2, PII

EPIC 8: LinuxONE and IBM Z Infrastructure Management with Meridian ( GA scope is being tested in z17 machine (in Poughkeepsie))

Pre-requisites:

GA SCOPE
|  |  | GA scope | Out-of-GA scope | JIRA |  | DEMO DETAILS | DEMO DETAILS |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Phase | FEATURE | USER STORY |  |  | owner | Is demoable? | If yes, how? |
| 1 | Platform Installation and Bootstrap (MER-2) | 1.1: Install Meridian Platform - need an inference endpoint to run an agent (use Spyre with our instance stack)  - vLLM running on x86, using nvidia H800 |  |  |  | N |  |
| 1 | Platform Installation and Bootstrap (MER-2) | 1.2: Install Terraform Enterprise (TFE)  What is the happy path/simplest path? (a) Disk mode (must give X storage) –  PROS: is simplest and works in prod CONS: (a.1) not recommended in prod,  (a.2) cannot migrate/upgrade out of disk mode  (b) External services (have all DBs external) – adds complexity (c) Active-active for failover (multiple instances of TF) |  | MER-3 have the default meridian driven install of TFE use single host to simplify our requirements for GA: https://hashicorp.atlassian.net/browse/MER-122 |  | N |  |
| 1 | Platform Installation and Bootstrap (MER-2) |  | Install TF for z in classic mode – get IIM installed – investigate feasibility to kickstart POC |  |  |  |  |
| 1 | Platform Installation and Bootstrap (MER-2) |  | 1.3: Install Vault Enterprise |  |  | N |  |
| 1 | Platform Installation and Bootstrap (MER-2) | 1.4: Providers - Install Meridian HMC provider: DPM mode  Align the resource names so that customers can use official IBM z and LinuxONE provider with Meridian. | Support for Official IBM z and LinuxONE provider. | Resource name alignment: https://hashicorp.atlassian.net/browse/MER-120  Refine and test the TFE install process that we are shipping with Meridian: https://hashicorp.atlassian.net/browse/MER-121 | Izzy, Randy |  |  |
| 2 | Infrastructure Onboarding | 2.1 Onboard HMC (POK HMC) |  |  | Randy, Mike | Partial (we can show the connector UX but we can’t expose the secret material through an onboarding flow) |  |
| 2 | Infrastructure Onboarding |  | 2.2 Onboard DS8000 Storage System |  |  | Partial (we can show the connector UX but we can’t expose the secret material through an onboarding flow) |  |
| 3 | Discovery & Import | 3.1: Discover all DS8K HMC Resources in DPM mode with our provider  discovery with HMC (version), DS8K (version) IIM (version) and HCD/HPM (version)? | Gravity is going to provide APIs to discover | MER-61 | Mike, Randy | Y | Prompt based |
| 3 | Discovery & Import |  | 3.2: Discover Existing LinuxONE Assets |  |  | Y | " |
| 3 | Discovery & Import | 3.3: Import DS8K Assets into Meridian (agent converts into scaffolding or updates existing) - API using Go TFE |  |  | Randy | Y | " |
| 4 | Resource Management |  | 4.1: Manage Classic Partitions |  |  | Y | “ |
| 4 | Resource Management | 4.2: Manage DPM Partitions |  |  | Mike | Y | “ |
| 4 | Resource Management |  | 4.3: Manage Storage Resources |  |  | Y | “ |
| 4 | Resource Management |  | 4.4: Manage Network Resources in DPM mode |  |  | Y | “ |
| 5 | Simulation and Rehearsal | 5.1: Simulate HMC Infrastructure Changes |  |  |  | Y | “ |
| 5 | Simulation and Rehearsal |  | 5.2: Simulate Partition Lifecycle Operations |  |  | Y | “ |
| 6 | Storage Integration & Validation |  | 6.1: Connect to DS8000 APIs |  |  | Y / partial | Connector UX cannot expose key material |
| 6 | Storage Integration & Validation |  | 6.2: Simulate DS8000 Operations |  |  | Y | Prompt based |
| 7 | Automated Post-Provisioning and Compliance Evidence |  | 7.1: Execute Post-Provisioning Configuration (run Ansible jobs) |  |  | Y | " |
| 7 | Automated Post-Provisioning and Compliance Evidence | 7.2: Generate Audit Evidence |  |  |  | Y | “ |

POST-GA SCOPE
| # | FEATURE | What is required? | USER STORY | JIRA |
| --- | --- | --- | --- | --- |
| 8 | z/OS use cases that require FICON and OSA management | Need IIM APIs (ICIC 1.2.5 supports z16 today and IIM will support those resources on z17) |  |  |
| 9 | zOS with classic mode |  |  |  |
| 10 | Day-2 Infrastructure Lifecycle Management (MER-6) |  | 8.1: Modify Existing Infrastructure |  |
| 10 | Day-2 Infrastructure Lifecycle Management (MER-6) |  | 8.2: Perform Operational Actions |  |
| 10 | Day-2 Infrastructure Lifecycle Management (MER-6) |  | 8.3: Certificate management |  |
| 10 | Day-2 Infrastructure Lifecycle Management (MER-6) |  | 8.4: User Management |  |
| 11 | z/VM and Vault Cluster Provisioning |  | 9.1: Provision z/VM LPAR |  |
| 11 | z/VM and Vault Cluster Provisioning |  | 9.2: Deploy Vault Cluster with Crypto Express HSM |  |
| 12 | Multi-tenancy |  |  |  |

High-level summary of the journey of data center operator

Data center operator journey

Phase 1:

Phase 2:

Phase 3:

Phase 4:

Phase 5:

Phase 6:

Phase 7:

Feature 01: Platform Installation and Bootstrap

| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 1.1 | Install Meridian Platform | As a platform administrator, I want to deploy Meridian, so that I can manage IBM Z and LinuxONE infrastructure through a centralized platform. | Meridian installation can be initiated through a guided workflow. Installation status is visible. Installation logs are retained. Post-install validation confirms system readiness. | Define installation prerequisites. Create Meridian installation workflow. Implement deployment automation. Implement installation status monitoring. Implement log collection and retention. Create readiness validation checks. Produce installation documentation. |
| 1.2 | Install Terraform Enterprise (TFE) | As a platform administrator, I want to install and configure Terraform Enterprise, so that infrastructure provisioning can be automated. | TFE deployment completes successfully. TFE is integrated with Meridian. Workspace management is enabled. Health checks pass. | Deploy TFE infrastructure. Configure authentication. Configure Meridian integration. Validate workspace creation. Implement health monitoring. |
| 1.3 | Install Vault Enterprise | As a platform administrator, I want to deploy Vault Enterprise, so that secrets and cryptographic assets can be managed securely. | Vault Enterprise is deployed. Vault initialization and unsealing are completed. Authentication methods are configured. Meridian connectivity is established. | Deploy Vault Enterprise. Configure storage backend. Configure authentication. Initialize Vault. Validate connectivity with Meridian. Configure monitoring and logging. |

# Feature 02: Infrastructure Onboarding
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 2.1 | Onboard POK HMC | As an infrastructure administrator, I want to onboard a POK HMC instance, so that I can manage associated infrastructure. | Connectivity validated. Authentication successful. Resources discovered. | Build onboarding wizard. Validate connectivity. Implement credential management. Trigger resource discovery. Generate onboarding audit logs. |

# Feature 03: Discovery & Import
| 3.1 | Discover HMC Resources | As an infrastructure administrator, I want to discover partitions, storage, and networking resources from HMC, so that I can manage them through Meridian. | HMC connectivity is established. Resource inventory is retrieved. Resources are displayed in Meridian. | Implement HMC API integration. Create inventory synchronization service. Develop inventory dashboard. Handle discovery failures. |
| --- | --- | --- | --- | --- |

| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 3.2 | Discover Existing LinuxONE Assets | As an infrastructure administrator, I want to discover unmanaged LinuxONE resources, so that they can be onboarded into Meridian. | Discovery process initiated. Existing assets identified. Inventory view populated. | Create discovery service. Implement inventory collection. Create inventory UI. Add duplicate detection. |
| 3.3 | Import Existing Assets | As an infrastructure administrator, I want to import discovered resources into Meridian, so that they become manageable resources. | Resources can be selected. Import process succeeds. Imported resources are tracked. | Create import workflow. Build resource mapping engine. Validate imported assets. Generate audit records. |

# Feature 04: Resource Management
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 4.3 | Manage DPM Partitions | As an infrastructure administrator, I want to manage DPM partitions, so that I can administer LinuxONE resources. | Create, modify, and delete DPM partitions. Changes are reflected in HMC. Create fully functioning RHEL partition with network and storage attached Create fully functioning z/VM partition with network and storage attached | Implement DPM APIs. Create DPM provisioning workflow. Implement lifecycle operations. Validate synchronization. Partitions ready for basic workloads |

# Feature 05: Simulation and Rehearsal
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 5.1 | Infrastructure Simulation and Rehearsal | As an infrastructure administrator, I want to simulate infrastructure changes before execution, so that I can reduce deployment risk. | Simulation mode available. No production changes occur. Simulation report generated. | Create simulation engine. Build simulation UI. Generate impact analysis. Create reporting capability. |
| 5.2 | Simulate Partition Lifecycle Operations | As an infrastructure administrator, I want to rehearse partition operations, so that I can validate infrastructure plans. | Simulate create, modify, delete operations. Dependency analysis available. | Create lifecycle simulation models. Build dependency analyzer. Generate simulation reports. |
# Feature 07: Automated Post-Provisioning and Compliance Evidence
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 7.1 | Execute Post-Provisioning Configuration | As an infrastructure administrator, I want to run automated configuration after provisioning, so that deployed systems meet operational standards. | Configuration workflows execute automatically. Configuration status is visible. | Create workflow engine. Define configuration templates. Build execution tracking. Implement failure handling. |
| 7.2 | Generate Audit Evidence | As a compliance administrator, I want to receive evidence artifacts and audit logs, so that compliance requirements can be satisfied. | Evidence package generated. Audit logs included. Export capability available. | Create evidence collection service. Generate evidence package. Implement artifact repository. Create export functionality. |

POST-GA SCOPE

# Feature 02: Infrastructure Management
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 2.2 | Onboard DS8000 Storage System | As a storage administrator I want to onboard a DS8000 system into Meridian So that storage resources become manageable. | DS8000 connectivity verified. Authentication successful. Storage inventory synchronized. | Create onboarding workflow. Configure credential management. Implement discovery process. Synchronize inventory. Generate onboarding reports. |

# Feature 04: Resource Management
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 4.2 | Manage Classic Partitions | As an infrastructure administrator, I want to create and manage Classic partitions, so that I can provision workloads. | Create partition. Modify partition. Delete partition. Audit trail generated. | Implement create partition workflow. Implement update workflow. Implement delete workflow. Add validation rules. Implement audit logging. |
| 4.4 | Manage Storage Resources | As a storage administrator, I want to allocate and manage storage resources, so that workloads receive required storage. | Storage assignment supported. Storage modifications supported. Capacity information displayed. | Integrate storage APIs. Build storage assignment workflow. Create capacity monitoring dashboard. Add storage validation. |
| 4.5 | Manage Network Resources | As a network administrator, I want to configure networking resources through HMC, so that workloads can communicate securely. | Network resources are visible. Network assignments can be modified. Changes are validated. | Integrate networking APIs. Create network management UI. Implement validation rules. Add audit logging. |

# Feature 8: Day-2 Infrastructure Lifecycle Management
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 8.1 | Modify Existing Infrastructure | As an infrastructure administrator I want to update deployed infrastructure resources So that environments remain aligned with business needs. | Infrastructure updates supported. Changes tracked. Rollback supported where applicable. | Create update workflows. Implement change tracking. Implement rollback capability. Add approval workflows. |
| 8.2 | Perform Operational Actions | As an infrastructure administrator I want to start, stop, restart, and maintain systems So that I can manage ongoing operations. | Operational actions available. Action status visible. Audit records generated. | Implement operational APIs. Build operational dashboard. Add notifications. Implement audit logging. |
| 8.3 | Certificate Management |  |  |  |
| 8.4 | User Management |  |  |  |

# Feature 09: Storage Integration and Validation
| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 9.1 | Connect to DS8000 APIs | As a storage administrator, I want to connect Meridian to DS8000 APIs, so that storage resources can be managed. | API connectivity validated. Authentication succeeds. Available storage resources are discovered. | Build DS8000 connector. Implement authentication. Create discovery service. Validate connectivity. |
| 9.2 | Simulate DS8000 Operations | As a storage administrator, I want to simulate storage operations against DS8000 APIs, so that I can verify expected outcomes. | API simulations supported. Request/response inspection available. No production modifications occur. | Create API simulation layer. Build request replay capability. Create response visualization. Generate audit logs. |

# Feature 10: z/VM and Vault Cluster Provisioning

| # | User Story | Details | Acceptance Criteria | Task(s) |
| --- | --- | --- | --- | --- |
| 10.1 | Provision z/VM LPAR | As an infrastructure administrator, I want to provision a z/VM LPAR, so that workloads can be deployed. | LPAR provisioning succeeds. Resource assignments are applied. Provisioning logs available. | Create LPAR templates. Implement provisioning workflow. Configure resource assignments. Implement monitoring. |
| 10.2 | Deploy Vault Cluster with Crypto Express HSM | As a security administrator I want to deploy a Vault cluster integrated with Crypto Express HSM So that secrets are protected using hardware-backed cryptography. | Vault cluster deployed. HSM integrated successfully. Cluster health verified. | Deploy Vault cluster. Configure HSM integration. Validate key operations. Configure monitoring. Create operational documentation. |

TEST-CASES
(1) Automated Installation of Meridian, TFE, and Vault Enterprise
Objective
Enable fully automated deployment of Meridian along with all dependent platform components including Terraform Enterprise (TFE) and Vault Enterprise without requiring manual installation steps by the customer.
Business Value
Reduce onboarding complexity
Eliminate dependency installation errors
Accelerate time-to-value
Enable repeatable enterprise-grade deployments
Preconditions
Target infrastructure environment is reachable
Required licenses and entitlement keys are available
Baseline networking and storage connectivity exist
Installation media/images are accessible
Trigger
Administrator initiates Meridian platform deployment.
Main Flow
User provides target environment details.
Meridian validates infrastructure prerequisites.
Meridian installs required runtime dependencies.
Meridian deploys Terraform Enterprise automatically.
Meridian deploys Vault Enterprise automatically.
Meridian configures secure integration between Meridian, TFE, and Vault.
Meridian validates health and readiness of all components.
Meridian stores deployment configuration and automation artifacts in version control.
Alternate Flows
Existing TFE/Vault deployment detected → Meridian integrates instead of installing.
Air-gapped environment detected → Meridian uses local package repository.
Postconditions
Meridian, TFE, and Vault Enterprise are fully operational.
Integrations are validated.
Deployment artifacts are version controlled.
Test Cases – UC-01
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-01.1 | Fresh automated install | Trigger installation on clean environment | Meridian, TFE, and Vault installed successfully |
| TC-01.2 | Existing TFE detected | Install with existing TFE | Meridian skips TFE install and integrates |
| TC-01.3 | Existing Vault detected | Install with existing Vault | Meridian integrates with existing Vault |
| TC-01.4 | Missing network connectivity | Disconnect target network during install | Installation fails gracefully with actionable error |
| TC-01.5 | Invalid license | Use invalid entitlement key | Installation blocked with validation message |
| TC-01.6 | Artifact versioning | Complete deployment | Generated automation stored in VCS |
| TC-01.7 | Rollback validation | Fail Vault installation midway | Partial deployment rolled back safely |

(2) Provision First Linux LPAR on Bare-Metal LinuxONE (DPM Mode)
Objective
Provision the first Linux-based LPAR on a newly installed LinuxONE system using Meridian-driven infrastructure discovery and automation.
Business Value
Accelerate bare-metal onboarding
Simplify first-time LinuxONE adoption
Reduce operator expertise dependency
Preconditions
LinuxONE hardware is physically installed
Baseline networking is configured
DPM mode is enabled
Storage/network resources are available
Bootable RHEL 9.7/9.8 image is available from a supported source in POK
Trigger
Operator requests provisioning of first Linux LPAR.
Main Flow
Meridian connects to HMC and discovers resources.
Meridian identifies available compute, storage, and networking.
Meridian generates proposed LPAR configuration.
Meridian provisions the LPAR.
Meridian attaches storage and networking.
Meridian boots Linux OS image.
Meridian validates OS accessibility.
Automation artifacts are committed to version control.
Postconditions
Functional Linux LPAR is operational.
Infrastructure topology is recorded.
Provisioning automation is versioned.

Test Cases
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-02A.1 | Discovery of clean LinuxONE | Start discovery on fresh machine | Meridian identifies available resources |
| TC-02A.2 | Provision vanilla LPAR | Execute provisioning workflow | LPAR successfully provisioned |
| TC-02A.3 | Storage assignment | Attach available storage | Storage visible inside OS |
| TC-02A.4 | Network attachment | Configure networking | LPAR receives network connectivity |
| TC-02A.5 | Resource exhaustion | Attempt provisioning with insufficient CPU | Meridian blocks provisioning |
| TC-02A.6 | HMC unavailable | Disconnect HMC during provisioning | Graceful failure and rollback |
| TC-02A.7 | Version control capture | Complete provisioning | Automation committed to repository |

(3) Simulate and Rehearse LPAR Provisioning Before Execution
Objective
Allow operators to simulate infrastructure provisioning changes before execution using speculative planning and rehearsal workflows.
Business Value
Reduce provisioning risk
Improve operator confidence
Enable “preview before apply” workflow
Preconditions
Meridian connected to LinuxONE environment
Discovery completed successfully
Trigger
Operator requests provisioning simulation.
Main Flow
Operator defines desired LPAR configuration.
Meridian performs infrastructure simulation.
Meridian generates speculative execution plan.
Meridian validates dependencies and conflicts.
Operator reviews proposed topology.
Operator approves rehearsal.
Meridian executes rehearsal validation.
Operator approves actual deployment.
Meridian provisions infrastructure.
Alternate Flows
Validation conflict detected → Meridian recommends corrective actions.
Operator rejects plan → No infrastructure changes applied.
Postconditions
Approved infrastructure changes are applied.
Simulation and rehearsal logs are retained.

Test Cases
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-02B.1 | Generate speculative plan | Request simulation | Detailed speculative plan generated |
| TC-02B.2 | Conflict detection | Simulate overlapping storage assignment | Conflict identified |
| TC-02B.3 | User rejects simulation | Cancel after preview | No infrastructure changes occur |
| TC-02B.4 | Rehearsal validation | Execute rehearsal workflow | Validation succeeds |
| TC-02B.5 | Approved execution | Approve final deployment | Infrastructure created |
| TC-02B.6 | Audit logging | Complete workflow | Simulation and approval audit retained |

(4) Post-Provisioning Configuration Handoff
Objective
Enable Meridian to hand off post-provisioning OS and application configuration tasks to external automation platforms such as Ansible.
Business Value
Decouple infra provisioning from configuration management
Reuse existing enterprise automation investments
Main Flow
Meridian detects successful OS deployment.
Meridian generates target inventory and metadata.
Meridian invokes Ansible automation workflows.
Configuration management tools apply customer-specific settings.
Meridian receives completion status.
Postconditions
LPAR fully configured according to customer standards.

Test Cases
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-02C.1 | Ansible handoff | Trigger post-config workflow | Ansible job invoked |
| TC-02C.2 | Inventory generation | Provision LPAR | Valid inventory file created |
| TC-02C.3 | Failed playbook | Inject playbook error | Meridian captures failure |
| TC-02C.4 | Status synchronization | Complete configuration | Meridian updates final status |

(5) Day-2 Infrastructure Lifecycle Management
Objective
Enable Meridian to assume ongoing management of existing LPAR environments regardless of who originally provisioned them.
Business Value
Support brownfield adoption
Centralize infrastructure lifecycle management
Simplify operational changes
Main Flow
Meridian discovers existing LPARs.
Operator submits infrastructure change request.
Meridian simulates requested modification.
Meridian generates rehearsal/speculative plan.
Operator approves changes.
Meridian applies infrastructure updates through HMC integration.
Meridian validates successful completion.
Example Changes
Add storage
Expand CPU/memory
Modify networking
Postconditions
Requested infrastructure modifications applied successfully.

Test Cases
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-02D.1 | Discover existing LPARs | Execute discovery | Existing infrastructure imported |
| TC-02D.2 | Add storage to LPAR | Submit storage expansion | Storage attached successfully |
| TC-02D.3 | Simulate infrastructure change | Request speculative plan | Impact analysis generated |
| TC-02D.4 | Reject unsafe modification | Simulate invalid storage mapping | Change blocked |
| TC-02D.5 | HMC integration failure | Interrupt HMC connectivity | Safe rollback occurs |

(6) Discover Existing LinuxONE Infrastructure
Objective
Enable Meridian to discover and inventory existing LPAR, storage, and network resources from pre-existing environments.
Main Flow
Meridian connects to HMC and infrastructure endpoints.
Meridian discovers:
LPARs
Storage pools
Networking
Resource utilization
Meridian builds infrastructure topology model.
Meridian stores discovered configuration.

Test Cases
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-03.1 | Discover LPARs | Execute scan | Existing LPARs imported |
| TC-03.2 | Partial infrastructure outage | Disable one storage endpoint | Partial discovery completed |
| TC-03.3 | Incremental discovery | Re-run discovery | Delta changes detected |

(7) Provision z/VM LPAR and Vault Cluster with Crypto Express HSM
Objective
Provision z/VM-based infrastructure and automatically deploy a Vault for Z cluster integrated with Crypto Express HSM.
Business Value
Accelerate secure infrastructure provisioning
Standardize cryptographic integration
Simplify regulated workload deployment
Main Flow
Meridian provisions z/VM LPAR.
Meridian configures storage and networking.
Meridian deploys Vault for Z cluster.
Meridian integrates Vault with Crypto Express HSM.
Meridian validates cluster health.
Meridian attaches Spyre Accelerator.
Meridian updates infrastructure definitions in version control.
Postconditions
Secure Vault cluster operational on z/VM.
HSM integration validated.
Spyre Accelerator attached.

Test Cases
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-04.1 | Provision z/VM LPAR | Execute provisioning | z/VM operational |
| TC-04.2 | Deploy Vault cluster | Start cluster deployment | Vault cluster healthy |
| TC-04.3 | HSM integration | Attach Crypto Express | Vault uses HSM successfully |
| TC-04.4 | Attach Spyre Accelerator | Execute accelerator update | Accelerator attached |
| TC-04.5 | Cluster failover | Simulate node failure | Vault cluster remains operational |
| TC-04.6 | Version control validation | Complete deployment | Automation committed to VCS |

(8) Onboarding POK HMC to Meridian
Objective
Enable Meridian to securely onboard and integrate with an existing IBM Hardware Management Console (HMC) environment running in Power-on-Key (POK) or production enterprise mode in order to discover, monitor, simulate, provision, and manage LinuxONE infrastructure resources.
Business Value
Centralize infrastructure lifecycle management
Eliminate manual HMC operational workflows
Enable infrastructure discovery and automation
Provide simulation/rehearsal capabilities prior to execution
Accelerate onboarding of existing enterprise environments
Preconditions
HMC is deployed and operational
Network connectivity exists between Meridian and HMC
Required HMC API credentials and RBAC permissions are available
DPM mode is enabled on target systems
TLS certificates and security policies are available
Trigger
Administrator initiates HMC onboarding workflow within Meridian.
Main Flow
Administrator enters HMC connection details.
Meridian validates network connectivity to HMC.
Meridian authenticates using configured credentials.
Meridian validates HMC API compatibility and permissions.
Meridian discovers:
Existing LPARs
Network configurations
Storage mappings
Capacity and utilization information
Meridian builds infrastructure topology model.
Meridian establishes continuous synchronization with HMC.
Meridian stores discovered configuration and onboarding artifacts in version control.
Meridian exposes discovered infrastructure through management and simulation interfaces.
Alternate Flows
Existing Meridian-HMC integration detected → Meridian validates and refreshes configuration.
Certificate validation failure → Administrator prompted to update certificates.
Insufficient RBAC privileges → Meridian identifies missing permissions.
Exception Flows
HMC unreachable
Invalid credentials
Unsupported HMC API version
Partial infrastructure discovery failure
Network interruption during onboarding
Postconditions
HMC successfully integrated with Meridian
Infrastructure inventory synchronized
Discovery topology available for simulation and lifecycle operations
Audit and onboarding artifacts stored in version control

Test Cases — POK HMC Onboarding
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-05.1 | Successful HMC onboarding | Provide valid HMC details and credentials | HMC integrated successfully |
| TC-05.2 | Credential validation | Provide invalid credentials | Authentication failure returned |
| TC-05.3 | API compatibility validation | Connect unsupported HMC version | Unsupported version identified |
| TC-05.4 | RBAC verification | Use read-only account | Missing privilege warning generated |
| TC-05.5 | Discover existing LPARs | Run discovery | Existing LPARs imported |
| TC-05.6 | Discover networking | Execute infrastructure scan | Network topology discovered |
| TC-05.7 | Discover storage mappings | Run discovery | Storage resources mapped |
| TC-05.8 | TLS certificate validation | Use expired certificate | Secure connection rejected |
| TC-05.9 | Partial infrastructure outage | Disable one managed system | Partial discovery completes gracefully |
| TC-05.10 | HMC unreachable | Block network connectivity | Graceful onboarding failure |
| TC-05.11 | Synchronization validation | Modify LPAR externally | Meridian detects delta changes |
| TC-05.13 | Audit logging validation | Complete onboarding | Audit records created |
| TC-05.14 | Version control validation | Complete onboarding | Generated automation stored in VCS |

(9) Onboarding DS8K Storage to Meridian
Objective
Enable Meridian to onboard and integrate IBM DS8000 (DS8K) enterprise storage systems for discovery, provisioning, simulation, lifecycle management, and automated storage attachment workflows for LinuxONE environments.
Business Value
Centralize storage lifecycle operations
Automate storage provisioning workflows
Improve visibility into enterprise storage utilization
Enable simulation and rehearsal of storage changes
Reduce operational risk during storage modifications
Preconditions
DS8K storage system is operational
Network connectivity exists between Meridian and DS8K management interfaces
Storage API credentials are available
Storage pools and logical volumes are configured
Required zoning/connectivity exists between DS8K and LinuxONE environment
Trigger
Administrator initiates DS8K onboarding workflow.
Main Flow
Administrator enters DS8K connection information.
Meridian validates network connectivity.
Meridian authenticates with DS8K APIs.
Meridian discovers:
Storage arrays
Storage pools
Volumes
Capacity utilization
Existing LUN mappings
Performance metrics
Meridian builds storage topology model.
Meridian maps DS8K resources to existing LinuxONE infrastructure.
Meridian enables storage lifecycle workflows:
Provision new storage
Expand existing volumes
Attach/detach storage
Simulate storage changes
Meridian stores discovered configuration and automation artifacts in version control.
Alternate Flows
Existing DS8K integration detected → Meridian refreshes inventory.
Read-only storage access configured → Meridian limits provisioning operations.
Exception Flows
Authentication failure
Unsupported DS8K firmware version
Storage API timeout
Missing zoning/connectivity
Insufficient storage capacity
Postconditions
DS8K storage successfully integrated with Meridian
Storage inventory and topology discovered
Storage lifecycle workflows enabled
Automation artifacts version controlled

Test Cases — DS8K Onboarding
| TC ID | Scenario | Steps | Expected Result |
| --- | --- | --- | --- |
| TC-06.1 | Successful DS8K onboarding | Provide valid DS8K connection details | DS8K integrated successfully |
| TC-06.2 | Invalid credentials | Attempt onboarding with bad credentials | Authentication failure returned |
| TC-06.3 | Discover storage pools | Execute discovery | Storage pools identified |
| TC-06.4 | Discover existing volumes | Run discovery | Existing volumes imported |
| TC-06.5 | Discover LUN mappings | Execute onboarding | Existing mappings identified |
| TC-06.6 | Capacity discovery | Run discovery | Capacity metrics displayed |
| TC-06.7 | Unsupported firmware validation | Connect unsupported DS8K version | Compatibility warning returned |
| TC-06.8 | Read-only mode validation | Use read-only credentials | Provisioning actions disabled |
| TC-06.9 | Provision new storage volume | Create storage request | Volume created successfully |
| TC-06.10 | Expand existing volume | Submit resize request | Volume expanded successfully |
| TC-06.11 | Attach storage to LPAR | Execute attachment workflow | Storage visible inside LPAR |
| TC-06.12 | Simulate storage modification | Run speculative plan | Change impact displayed |
| TC-06.13 | Storage exhaustion validation | Attempt oversized allocation | Provisioning blocked |
| TC-06.14 | Connectivity failure | Interrupt DS8K network | Graceful onboarding failure |
| TC-06.15 | Version control validation | Complete onboarding | Automation stored in VCS |
| TC-06.16 | Delta synchronization validation | Add new volume externally | Meridian detects configuration drift |
| TC-06.17 | Performance metric discovery | Execute monitoring scan | Performance telemetry visible |
| TC-06.18 | Multi-array discovery | Connect multi-DS8K environment | All arrays discovered successfully |

Additional Context from Chris Byrnes (We will look at incorporating below content into PRFAQ)
## 1. Executive Summary
Product: IBM Meridian for Z and LinuxONE 1.0.0
### Purpose
This document serves as a single source of truth for all IBM Meridian product stakeholders, providing a comprehensive and continuously updated view of product requirements, scope, and delivery strategy.
### Objectives
Provide clear, validated product requirements for product team and stakeholders
Align stakeholders on MVP scope and delivery constraints
Enable customer validation and commercialization strategy
### Success Metrics
On-time delivery of GA scope
Incorporation of validated customer requirements
Reduction in infrastructure change time
Reduction in operator effort (manual hours)
Reduction in change failure rates
incremental revenue to business
drive adoption of other products and patterns

## 2. Product Overview
### 2.1 Product Description
IBM Meridian is an autonomous data center platform focused on enabling intent-driven, workflow-based automation for all model architectures and platforms. It uses a novel implementation of industry standard AI tooling to streamline natual language processing (NLP) of grounding information for small language models. These SLMs are run locally on available GPUs to perform and validate platform specific workflow development and in accordance with stringent configuration, regulatory, and operational requirements. The initial release of IBM Meridian will support discovery, simulation, and rehearsal of infrastrucure resource changes on IBM LinuxONE through NLP.
Meridian is is a workflow-centric, intent-based system where:
Users express intent via natural language or workflow selection
Meridian executes structured workflows
Outputs, artifacts, and evidence are generated
Chat is one of several interaction surfaces.
### Problem Statement #1
Mission critical data center environments face:
High change complexity and long execution cycles
Limited availability of specialized platform skills
Pressure to adopt modern infrastructure practices
Fragmented operational workflows and tooling
Customers want to automate end to end processes for all aspects of data center operations:
Clear onboarding paths
Sufficient skill sets
Operational integration guidance
### Target Users
Site Reliability Engineers (SREs)
Platform engineers
System administrators
Security administrators
### Target Buyers
CTO
Data Center Operator
Platform Owner
### Value Proposition
Meridian enables:
Discovery of infrastructure resources and other API-enabled endpoints
Simulation of end to end resources for skills enablment and change management planning
Rehearsal of data center resource changes
Reduced operational complexity through guided workflows

## 2.2 Business Context
### Business Goals
Identify skills gaps in mission critical resource management
Provide realistic sandbox environment for organizatioal skills enablment and operational planning for mission critical resource and application environment management.
Incorporate SME guidance, best practices, regulatory requirements and other compliance requirements into platform specific workflows
### Market Opportunity
Estimated $34B autonomous data center market
### Customer Needs
Regulatory compliance and data sovereignty
Simplicity and ease of use
Guided integration of modern tooling
Automation with human oversight
Auditability and explainability of decisions
Deterministic validation of workflows
### Strategic Positioning
Align with IBM Terraform and Vault for Z and LinuxONE GTM strategy by focusing on regulated industries for auditable and compliant infrastructure
also build on increasing need for automated and automatble infrsturcuture, both of which includes compute, network, storage resources, credentials, and secrets
Enable modernization without disrupting mission-critical systems
Frame the future data center as centered on capabilities provdided by IBM products including IBM Concert for Z, WatsonX Assistant, IBM Bob, the Z and LinuxONE platform, IBM Power, IBM Storage
Drive consumption of other products by building workflows that deliver specific capabilities based on multiple products (ie Meridian, Terraform, IBM Storage)

## 2.3 Product Vision & Goals
### Long-Term Vision
Establish Meridian as the autonomous data center platform with parity of function across all modern compute platforms, including x86, cloud, Z, LinuxONE, Power, Storage
Provide mission-critical workload support for future Mars missions and
drive $100 million in additional revenue through IBM Meridian and other IBM products
Drive additional hardware revenue through
### Short-Term Goals
Deliver validated workflows to deploy Terraform in a LinuxONE environment
Deliver validated workflows to deploy Vault in a LinuxONE environment
### KPIs
Deployments (installed instances)
Adoption tiers:
Trial
POC
Development/Test
Production
Revenue growth
Change-time reduction
Failure rate reduction
### Success Criteria
20–40% reduction in infrastructure change time
20–30% reduction in manual effort
Measurable decrease in failed infrastructure changes

## 3. Functional Requirements
### 3.1 Core Feature Pillars
All Meridian capabilities must align to at least one of the following pillars:
#### 1. Discovery
Identify existing infrastructure and configurations
Provide visibility into system state
#### 2. Simulation
Model infrastructure changes before execution
Validate impact and dependencies
#### 3. Rehearsal
Execute test runs of infrastructure workflows
Ensure deterministic outcomes prior to production use

### 3.2 Workflow Model
Meridian operates through intent-based workflows:
Users can:
Enter natural language intent
Select predefined workflows
Meridian:
Gathers required inputs
Guides workflow execution
Produces artifacts and outputs

### 3.3 MVP / GA Workflow Scope
#### Included at GA
Terraform for Z installation workflow
Vault for Z installation workflow
#### Excluded from GA (Future Roadmap)
Certificate management workflows (Vault domain)
Infrastructure analysis (covered under discovery)
Auditing workflows
Reporting workflows
Capacity planning
Migration planning

### 3.4 Workflow Selection Constraints
Only workflows that can be:
Fully executed
Tested in real environments
Validated end-to-end
GA scope is intentionally minimal to ensure trust and reliability
### 3.5 User Interaction Model
#### Interaction Surfaces
Natural language (chat)
Guided workflows (UI-driven)
#### Workflow Execution Pattern
Intent declaration
Input gathering
Workflow execution
Artifact generation

## 4. Infrastructure & Deployment
### 4.1 Supported Environment
IBM Z and LinuxONE (mainframe-native only)
### 4.2 Installation Model
Focus on enabling:
Terraform installation on Z
Vault installation on Z
Installation workflows must:
Be automatable
Be testable
Reflect real customer environments

## 5. Observability, Logging & Audit
### GA Capabilities
API-based logging and observability
Exportable logs and telemetry
Integration with external observability platforms (OpenTelemetry-style)
### Future Enhancements
Agent-assisted log review
Native reporting capabilities

## 6. Trust, Safety & Governance
Trust is established through:
Product quality and correctness
Alignment with Z operational practices
### Supporting Mechanisms
Human approval gates (optional)
Workflow reviewability
Explainability of actions
Deterministic validation prior to execution

## 7. GA Definition & Commercialization Model
### Possible GA Modes
Paid GA
Customer discovery (version-zero)
Hybrid model
### Current Strategy
Maintain flexibility across all models depending on customer readiness and validation

## 8. Customer Validation Strategy
### Target Design Partners
Sogei
Kyndryl
Morgan Stanley
JPMC
Fiserv
Ensono
### Approach
Co-develop workflows with design partners
Validate real-world applicability
Transition validated use cases to commercial offerings

## 9. Product Integrations
### Integration Philosophy
Integrations are defined independently without coupling product positioning
### Initial Integration Targets
Terraform for Z
Vault for Z
IBM and Red Hat ecosystem tools
### Example Use Cases
Use Meridian to install Terraform on Z
Use Meridian to install Vault on Z

## 10. Risks & Constraints
### Key Risks
Customer adoption readiness
Installation and onboarding complexity
Slow validation cycles
Trust concerns around AI-driven automation
Over-promising workflows beyond tested capabilities
### Mitigations
Start with minimal validated GA scope
Focus on real-world testability
Prioritize product correctness and reliability

## 11. Timeline & Phasing
### Phase 1 (GA)
Deliver Terraform and Vault installation workflows
Validate workflows with design partners
### Phase 2 (Post-GA)
Expand into additional workflow categories
Introduce enhanced observability and analysis

## 12. Summary
Meridian is positioned as an autonomous data center platform that delivers value through intent-based workflows, starting with a narrowly scoped, highly validated GA focused on Terraform and Vault onboarding for Z and LinuxONE environments.
The strategy prioritizes:
Real-world validation
Customer trust
Incremental capability expansion