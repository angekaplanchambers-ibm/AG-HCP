BUSINESS CASE
Project Meridian
An autonomous infrastructure operating layer for IBM Z & LinuxONE

Classification: IBM Confidential.

# 1.  Overview / Opportunity
## The industry
Enterprise infrastructure is moving away from static, manually coordinated automation toward an agentic business fabric, an intelligent ecosystem in which AI agents, enterprise data, and employees jointly orchestrate workflows behind the scenes. In infrastructure specifically, agentic systems replace static scripts with adaptive value loops: an agent senses telemetry, applies policy, decides on an action, and executes it through APIs. As agents absorb routine work, the value of human operators shifts from doing the work to supervising the system, managing exceptions, and defining guardrails.
## The problem
IBM Z and LinuxONE carry the deep trust footprint in enterprise infrastructure, yet the platform is still operated largely by hand. Infrastructure changes are slow, costly, and dependent on scarce expert knowledge that is retiring out of the building. Early Terraform-on-Z customers report acute pain in onboarding and integration, and Z had one remaining gap that kept it from being fully governed and automated.
## The solution
Meridian is an autonomous infrastructure operating layer for sovereign, AI-driven data centers, a data center that governs itself. It combines product connectors (HMC, DS8000) and domain knowledge to perform infrastructure workflows easily while preserving audit, compliance, and governance standards. The model is guided workflow from intent to apply: simulate first, then execute, with every action logged, not just the outcome.
## Why now
Market timing: ~$34B TAM today, growing at a 34% weighted CAGR, as the agentic shift hits infrastructure.
Regulatory tailwinds: DORA, GDPR, and sovereign-cloud mandates are accelerating in IBM’s direction.
Asset readiness: Post-HashiCorp, IBM owns both the deep trust hardware (Z) and the enterprise governance stack (Terraform/Vault) the AI moment demands.
Stated target: $100M in revenue on Z

# 2.  Differentiator: Right to Win
IBM owns both the platform of record for regulated workloads and the governance layer that makes it programmable. The acquisition of HashiCorp closed the one gap that previously kept Z from being fully governed and automated. Three capabilities are genuinely differentiated:
Z as Code. Industry-first, built-in IBM Z hardware Terraform providers make physical infrastructure fully declarative, feeding a persistent brain of topology, configuration, telemetry, and change history that both operators and AI agents continuously learn from.
Vault from the hardware up. Vault is embedded from the hardware Secure Element up, establishing hardware-rooted identity and quantum-safe encryption for every human operator and AI agent on the platform.
Simulation-backed change. Changes are safely tested and governed before apply (simulate first, then execute), which is what makes AI-driven infrastructure change trustworthy in a regulated estate.
The strategic upside: selling Meridian on a standalone basis provides future optionality to enter a growing, nascent market that is orthogonal to Terraform and Vault use cases: new TAM rather than cannibalized TAM.
# 3.  Key Risks
Standalone-launch risk. Sellers don’t pitch anything besides Terraform and Vault at meaningful scale, and new HashiCorp products have historically struggled to get off the ground (Boundary, Waypoint, Radar). SFDC closed-won data confirms newer products lag the core.
Pricing risk. The $100M supporting-program path requires effectively doubling the billed price of Terraform on Z.
Penetration risk. Hitting $100M requires ~20% to 25% Z install-base penetration concentrated in higher-MSU buyers ($1M ACV+); today Terraform & Vault sit at only ~2% penetration (10 to 12 customers).
Pipeline visibility. There is no line of sight to the Z software pipeline and closed-wons; the closed-won assumptions (33% on the overlap cohort, 20% on the remainder) are estimates.
Competitive intensity and timing. In early 2026 BMC, Broadcom, and Rocket all shipped agentic, MCP-based mainframe AI, and the funded startup Geniez holds a granted patent on secure AI access to the mainframe. The category is validating fast, which compresses Meridian’s window and raises a freedom-to-operate question (see Section 7).
Adoption barriers. Customers cite security/compliance concerns, integration complexity, and unclear ROI/business case as top blockers.
# 4.  Expert / Customer Feedback
## Analyst view (Gartner)
Gartner frames the shift toward an agentic business fabric and, in infrastructure, toward adaptive value loops that replace static scripts. Crucially, the analyst view is that the technology only captures the market when paired with an operating-model transformation, with human value moving to supervision, exception handling, and guardrail definition.
# 5.  Team
Project Meridian is an IBM Software / IBM Z initiative, built on IBM’s HashiCorp assets (Terraform and Vault). It is imperative that there is aligned, cross-functional position across all teams involved.
## Core team
| Function | People |
| --- | --- |
| Executive Sponsor | Chris Audie |
| Engineering | Jacob; Dan; 2 hired engineers; Robbie (front-end); 2 open positions |
| Design | Ashley |
| Product | Paul, Tiffany, Saurabh, Chris B |
| TPM | Amy |

Headcount note: engineering is still ramping, with two roles hired, one front-end engineer in place, and two positions open. Closing those reqs is on the critical path to the August 12 GA.
## Capability gap to flag
As of the writing of this business case, none of the named team has known mainframe experience. This is a material risk for a product whose value rests entirely on deep IBM Z and LinuxONE specifics (HMC, DS8000, RACF, LPARs, MSU-based economics), and it stands in contrast to the competitive set: Geniez, BMC, Broadcom, and Rocket are all mainframe-native, with leadership measured in decades on the platform. Recommended mitigations: embed or formally advise with the IBM Z and Automation field teams, add at least one senior mainframe engineer or architect to the open reqs, and stand up a small bench of Z practitioner advisors to pressure-test workflows, simulation fidelity, and audit requirements before GA.
# 6.  Market
TAM today: ~$34B, growing at a 34% weighted CAGR. Sources cited in the deck are Gartner and IDC estimates plus IBM’s Agentic Fabric strategy documents. Meridian spans five addressable segments:
Infrastructure Automation (IaC)
Security Automation & Secrets Management
AI Agents & Agentic Systems
AIOps & Data Center Automation
Sovereign Cloud Infrastructure
On the 2024-vs-2030 projection, the largest segments by 2030 are the AI-agents, AIOps/data-center-automation, and sovereign-cloud categories (reaching roughly the $50 to $73B range on the chart), while IaC and secrets management are smaller but faster-compounding bases. The thesis: Meridian sits at the intersection of all five, which is why the standalone opportunity is treated as orthogonal upside rather than a Terraform/Vault adjacency.

## Serviceable base on Z: “there is room to grow”
| Z & LinuxONE | 2023 | 2024 | 2025 | 2026E | 2030E |
| --- | --- | --- | --- | --- | --- |
| # Z HW customers | 586 | 591 | 584 | 590 | 614 |
| Avg MSUs / customer | n/a | n/a | 6,135 | 6,300 | 6,500 |

Terraform & Vault on Z today reach only ~2% of the install base (10 customers in 2025, 12 in 2026E) at ~$36 to $38 per MSU, for total TF&V ACV of $8.17M (2025) rising to $9.15M (2026E). The $100M target therefore implies roughly an 11x step-up over the 2026E baseline, which is the headroom the case is built to capture.
# 7.  Competitor Landscape
The market moved quickly in early 2026. Agentic AI for the mainframe went from a thesis to a contested field, with the three largest mainframe-software incumbents and at least one funded startup all shipping or announcing agentic, MCP-based capabilities for IBM Z. Meridian no longer enters an empty category; it enters a forming one, which raises both validation (the demand is real) and urgency (the window is narrowing).
## Agentic AI operating on IBM Z
BMC Software (AMI + Control-M). The most direct incumbent threat. In April 2026 BMC launched purpose-built agentic AI: Model Context Protocol (MCP) support plus a dedicated Agent Gateway in Control-M that provides centralized governance and auditability for autonomous agents acting on the mainframe, alongside AMI Assistant (Knowledge Hub / Knowledge Expert Chat) aimed squarely at the retiring-expert skills gap, AMI DevX for z/OS DevOps, and new AMI Digital Certificate Management. BMC also acquired Model9 in 2023, the team that now runs Geniez. (Futurum, Apr 2026; BMC newsroom, Jan & Apr 2026)
Broadcom Mainframe Software. WatchTower (AIOps/observability, shifting ops from reactive recovery to proactive avoidance) and Automation Analytics & Intelligence (AAI), which already includes a simulation / what-if agent that models a change’s impact against SLAs before deployment, a capability that overlaps directly with Meridian’s simulation-and-rehearsal pitch. Broadcom exposes mainframe context through MCP tools so it plugs into the customer’s own agent stack, and pairs this with its ACF2 / Top Secret security portfolio as the agent access-control layer. (Moor Insights, Everest Group, 2026; Klover.ai, Dec 2025)
Rocket Software (Rocket EVA). Agentic AI for mainframe operations: a conversational assistant, initially focused on z/OS, that lets operators analyze system status, identify dependencies, and troubleshoot without deep platform expertise, delivered as a pluggable start small framework that keeps humans in control.
Geniez AI. Venture-backed startup ($6M seed, StageOne and Canapi) founded by Gil Peleg and Dan Shprung, the Model9 team that BMC acquired in 2023. Its MCP-native framework runs natively on the mainframe and gives LLMs and agents (Claude, ChatGPT, Llama, Gemini, Bedrock) secure, real-time access to MF data sources (DB2, IMS, MQ, VSAM, datasets) with RACF controls, end-to-end encryption, audit/governance, and a Python SDK. It holds granted US patent US12596831B1, Secure mainframe access for AI agents. Today Geniez is data-access-and-insight led rather than infrastructure-provisioning led, but the secure agent-to-mainframe access pattern overlaps with Meridian’s gateway and Metro MCP design. (DBTA, Calcalist, Blocks & Files, 2025; US Patent US12596831B1)
## Competitive matrix
| Player | Focus / agentic posture | Where it overlaps Meridian | Gap Meridian fills |
| --- | --- | --- | --- |
| BMC (AMI, Control-M) | Mainframe automation, DevOps, AIOps; agentic via Control-M Agent Gateway, MCP | Governed, audited autonomous agents; skills-gap knowledge | No hardware-level declarative provisioning of Z or storage |
| Broadcom | AIOps (WatchTower), AAI what-if simulation, ACF2/Top Secret; MCP context tools | What-if change simulation; agent access control | Exposes context to the customer’s agents; not an end-to-end provisioning layer |
| Rocket (EVA) | Agentic AI assistant for z/OS operations | Natural-language ops, troubleshooting, human-in-loop | Assistive ops, not declarative infra plus Vault identity |
| Geniez AI | MCP-native secure LLM/agent access to real-time MF data | Secure RACF-backed agent access, audit (patented) | Data access and insight, not provisioning or simulation |
| Generic IaC | Distributed infrastructure as code and orchestration | IaC workflows and pipelines | Not native to Z; cannot make HMC/DS8000 declarative |

## Right to win
Several Meridian differentiators are now contested: governed, audited agentic execution (BMC’s Agent Gateway), what-if simulation before apply (Broadcom’s AAI), secure RACF-backed agent access to the mainframe (Geniez, with a granted patent), and the retiring-expert / institutional-knowledge play (BMC, Rocket, and Broadcom all market it). Meridian’s genuinely defensible wedge narrows to three things and, critically, their combination under one owner:
Z as Code. Built-in IBM Z hardware Terraform providers (HMC, DS8000) that make physical infrastructure declarative. No competitor provisions the hardware itself; they read from it, assist around it, or orchestrate above it.
Hardware-rooted identity. Vault embedded from the Secure Element up, giving every operator and agent hardware-rooted, quantum-safe identity rather than software-only access tokens.
Full-stack ownership. Post-HashiCorp, only IBM owns the platform (Z) and the governance stack (Terraform, Vault) together. Competitors must plug into someone else’s LLM, agent framework, or hardware.
## Patent and freedom-to-operate flag
Geniez’s granted patent US12596831B1 (granted April 2026) claims an intermediate agent plus a restricted on-mainframe agent that spawns a privilege-scoped process to give AI/LLM clients secure access over MCP. Meridian’s HMC and DS8K gateways, the Metro MCP Service (agent tool), and the Vault-based connectors should be reviewed by Legal for freedom to operate against this claim set before GA.
# 8.  Product Overview
## Who we’re solving for
Infrastructure Producer / Operator. Wants secure, automated foundations: deploy and maintain Vault and Terraform in a highly available, RACF-backed configuration and run changes through a trusted, repeatable workflow. Value: reduces operational risk and expert dependency; the data center runs with institutional knowledge baked in.
Application & Data Consumer / Requester. Wants to migrate environments onto refreshed Z hardware (LPARs, storage, OS install paths) and safely discover/modify Linux-hosting partitions. Value: guided workflow from intent to apply, simulate first then execute, every action captured in an exportable audit record.
## Potential features in the initial release
| # | Capability | # | Capability |
| --- | --- | --- | --- |
| 01 | Platform Installation & Bootstrap | 05 | Automated Post-Provisioning & Compliance Evidence |
| 02 | HMC Infrastructure Management | 06 | Existing LinuxONE Discovery |
| 03 | Infrastructure Simulation & Rehearsal | 07 | HMC Onboarding |
| 04 | DS8000 Integration & Simulation | 08 | DS8000 Onboarding |

## Roadmap to GA
RC1 (end of May ’26). Intent-based workflows via the Meridian agent service (Granite 4.1 8B default/required, Falcon3 7B optional; Evals for Cases, Workflows (E2E), and Retrieval (RTEM)); an Audit Log capturing all gateway interactions, prompts, and artifacts; and Settings for Vault-based connectors (HMC, DS8K, SSH), simulation configuration, and audit controls. Services: HMC Gateway and DS8K Gateway (simulation/proxy) and the Metro MCP Service (agent tool for Meridian). Data Product Packages (Metro): the metro CLI/SDK and schemas, PDF extraction/packaging skills, terraform-provider-hmc and -ds8k with agent support, Terraform Enterprise / DPM-mode / health-and-migration workflows, and a knowledge base (Terraform Enterprise, DPM best practices, DS8K Red Book, zOS, zVM). Integrations: Concert.
RC2 (end of June ’26). Authentication (SSO and RBAC) plus bug fixes.
Timeline. Code-freeze one month prior to GA; GA date August 12, 2026.
# 9.  Go-to-Market
## At GA: package Meridian for Z under Terraform for Z as a Bundled Program
Create a PID and parts for Meridian for Z which would roll up to a new UT-35 under the existing Terraform for Z UT-30: one price (via Terraform for Z), one selling motion.
Revenue attribution tracked at the UT-35 level, so performance is measurable from day one.
Customer buys Terraform for Z with a single Terraform for Z PID & parts; HashiCorp, Automation and Z sellers are compensated on the Meridian sale, revenue is recognized for the Meridian part, and the customer gets full (not partial) entitlement, with all features included.
More conducive to joint marketing than a Supporting Program arrangement.
Aligns with current product maturity and Meridian’s natural “attachment” to Terraform: onboarding, rehearsal, and simulation before deployment changes.
## Future: graduate into a Standalone Offer
Lift Meridian from UT-35 to UT-30 (“Meridian for Z and LinuxONE”) and position it as the autonomous-data-center product that combines connectors and domain knowledge to perform workflows easily while maintaining audit, compliance, and governance. This is the path to the orthogonal, standalone TAM.
## Selling motion
Lead with the pain Terraform for Z customers already feel, onboarding and integration, and position Meridian’s platform installation plus agentic discovery, simulation, and rehearsal as the way to make infrastructure changes easier and more trustworthy for Z practitioners.
# 10.  Financials
Target: $100M revenue in Z. Two modeled paths reach it
## Baseline today
Terraform & Vault on Z generate $8.17M ACV (2025), project to rise to $9.15M (2026E), across 10 to 12 customers at ~2% install-base penetration. The $100M target is therefore a ~11x step-up over the 2026E baseline.
## What $100M requires: ~20–25% install-base penetration at TF-on-Z economics
Pricing stays anchored to Terraform on Z today — MSU-based, ~$80–90 billed per unit off a $400 list (the VUE-007 required-discount curve) — and the target is reached on volume, not on a new premium SKU. The curve shows where $100M sits: 20% penetration clears ~$94M and 25% clears ~$117M, so the target lands inside that band. It only works if penetration is concentrated in higher-MSU buyers — the high-MSU engine (~$1.1M average deal size) carries the model.
| Install base penetration | ACV sum |
| --- | --- |
| 10% | $46.9M |
| 15% | $70.4M |
| 20% | $93.9M |
| 25% | $117.4M |
| 30% | $140.8M |

## How we get there: win the distributed-Hashi / Z-HW overlap first
20% to 25% will not be won evenly across the base. It comes primarily from the customers who already overlap Z hardware and distributed HashiCorp deployments. They carry ~14k MSU (roughly 10x the median) and convert at a higher assumed rate, and at ~$1.1M per customer they are the high-MSU engine the curve depends on. This overlap cohort alone delivers ~$51.5M at a 33% closed-won assumption. Penetrating the remaining base at a more conservative 20% adds ~$52.6M, bringing the combined number to ~$104M, which is the ~20% to 25% penetration the curve requires. Both pieces assume effectively doubling the billed price of Terraform on Z.
| Cohort | Customers | “On Z CWs” | Avg MSU | Billed | Per-cust. ACV | Total ACV |
| --- | --- | --- | --- | --- | --- | --- |
| A: Overlapping | 142 | 47 | 13,701 | $80 | $1,096,108 | $51.5M |
| B: Remaining | 442 | 88 | 6,640 | $90 | $597,600 | $52.6M |
| Total A + B |  |  |  |  |  | $104.1M |

## Financial Projection
TBD
## Recommendation
Launch bundle program under Terraform at GA (with a UT-35) to compensate both seller motions and de-risk the under-attach problem, while the standalone model (UT-30) is held as the graduation path once product maturity and demand are proven. This is the aligned recommendation across the Meridian team after consulting Finance, Legal, and the Z teams.
# 11.  Measurements
Expert Labs attached rate