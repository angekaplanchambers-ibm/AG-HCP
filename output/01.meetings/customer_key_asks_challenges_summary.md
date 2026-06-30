Customer Key Asks & Challenges Summary
AI-driven infrastructure / Terraform customer themes

# Executive summary
The strongest customer ask is: use AI to make Terraform easier, faster, safer, and more self-service for application teams.
Across the accounts, customers are not mainly asking for generic AI chat. They want AI-driven infrastructure workflows that sit around Terraform, module registries, policies, testing, CI/CD, and platform engineering processes.
# Common asks / challenges
| Theme | What customers are asking for | Customers showing this pattern |
| --- | --- | --- |
| Faster Terraform module creation | Reduce the time it takes platform teams to build, update, test, and release compliant modules. | Westpac, CBA, Clover, Pickles, PMI, Applied Materials |
| Easier module consumption / self-service | Let app teams find and consume approved modules without needing deep Terraform expertise or heavy platform-team handholding. | KiwiBank, Westpac, CBA, Oxy, Elevance, Clover, Salesforce DET |
| Natural-language infrastructure requests | Users want to request infrastructure in Slack/chat or natural language and have the system generate Terraform/config, tests, PRs, and compliance checks. | Salesforce DET, Oxy, Bank of America, Westpac |
| Migration acceleration | Use AI to help convert or modernize from CloudFormation, Bicep, CDK, or existing unmanaged workloads into Terraform/TFE/HCP Terraform. | CBA, Booking.com, Pickles, Bank of America |
| Governance, testing, compliance, and safety | Customers want AI acceleration, but still need policy-as-code, approval workflows, security controls, identity, auditability, and testing. | Westpac, Clover, Fifth Third Bank, Bank of America, Salesforce DET |

# Customer-by-customer readout
| Customer | Key ask / challenge | Current signal |
| --- | --- | --- |
| CBA | Large-scale migration from CloudFormation and Bicep to Terraform; accelerate module development; improve module consumption. | Very strong fit. AI-first bank, executive support, active testing, successful workshop, already deploying pieces. |
| Westpac | Reduce 2+ week module development cycle; generate Terraform tests; support consumer workflows; possibly launch a Terraform managed service. | Strong fit. Multiple demos, clear workstreams, real module backlog, 350+ modules. |
| Salesforce DET | 2,000 app developers producing IaC; deployments can take up to 2 weeks; wants Slack-based agent request workflow with governance/security checks. | Strong commercial signal. Product sale and RS engagement closed; needs support/enablement. |
| Oxy | Non-technical users need AWS/Azure infrastructure through natural language while still flowing through TFC pipelines and guardrails. | Strong use case. Needs Azure DevOps skill / integration work. |
| Clover / Fiserv | Platform team bottleneck for module delivery; inconsistent module quality; poor discoverability; interested in Terraform MCP, Vault, Nomad, InfraGraph. | Technically advanced, but ultimately flagged as not a fit for AI Driven because of restrictions; still good for MCP / remediation / roadmap feedback. |
| Booking.com | Help non-IaC developers move from CDK to HCL/Terraform and consume TFC workflows. | Interested but hesitant. Needs stronger business justification and PS-led positioning. |
| Pickles | Small/thin team wants AI to reduce BAU toil, accelerate module workflows, and onboard workloads into HCP Terraform. | Good narrative fit, but budget/maturity constraints. AI readiness done; next step is business case. |
| PMI | Wants AIOps / AI-first infrastructure modernization through IBM Consulting; module discovery and module production acceleration are key use cases. | Strategic IBM Consulting opportunity; hard dependency on AWS Bedrock/API access and internal account alignment. |
| Elevance Health | Help developers consume modules in a strict IaC environment where infra deployment goes through TFE. | High interest, but needs PS/SOW path; not ready for a standalone lighthouse motion. |
| Bank of America | Internal MCP server for best practices/rules and TFE modules; structured prompting to generate commits, then agent workflow for compliance. | Strong executive sponsor and budget; no update notes captured yet. |
| Applied Materials | Small staff wants to scale Terraform deployment using AI; using Vertex AI / internal AI pipeline. | Earlier-stage. Needs qualification and positioning around RS / readiness assessment. |
| KiwiBank | Wants developer velocity / portal-like experience, but knows module foundations need to be right first; Day 2 module operations. | Mature TFC customer; principal engineer looking for budget/support. |
| Fifth Third Bank | Asked about AI agent identity/access, MCP hosting/deployment, and whether MCP can be hosted remotely. | More technical discovery / support than lighthouse motion. |
| Salesforce Slack Platform | Small platform team wants standardized but flexible module code for app developers; needs higher configuration velocity. | Early signal; limited update data. |

# What product / field teams should focus on
The repeatable customer problem is not “write Terraform with AI” alone. It is a broader platform workflow:
request → discover approved module → generate Terraform/config → generate tests → open PR → validate policy/security → deploy through TFC/HCP Terraform → manage Day 2 changes
## Biggest product / solution gaps implied by the notes
- Module intelligence: AI needs deep context from PMR, module docs, examples, versions, provider constraints, policy rules, and existing workspace patterns.
- Testing automation: Westpac especially highlights Terraform test generation and validation as a high-value, concrete use case.
- Enterprise control plane / MCP story: Customers are asking where MCP servers run, how remote hosting works, how identity works, and how this connects to TFE/HCP Terraform, Vault, Nomad, and InfraGraph.
- Security and governance: Banks and regulated customers want agentic workflows, but only if identity, access, approvals, auditability, and policy-as-code are clear.
- Services packaging: Several customers need RS/PS help. The opportunity may require a packaged “AI readiness + workflow implementation” engagement rather than just a demo or repo handoff.
# Best-fit lighthouse / priority candidates
## Top candidates
1. CBA — strongest AI-first posture, executive support, migration pain, and active testing.
1. Westpac — very concrete use cases: module testing, module lifecycle, Terraform managed service.
1. Salesforce DET — large developer base, clear Slack/agent workflow, commercial traction.
1. Oxy — strong natural-language self-service use case and executive goal around AI-augmented Terraform.
1. Bank of America — strong strategic account, executive sponsor, MCP/server architecture use case.
## Good but needs shaping
- PMI: strategic because of IBM Consulting, but depends on internal alignment and Bedrock/API access.
- Pickles: good story, but budget/maturity are constraints.
- Booking.com: interested, but needs clearer executive/business justification.
- Elevance: strong interest, but needs PS/SOW path.
## More technical-feedback / roadmap accounts
- Clover/Fiserv
- Fifth Third Bank
- Applied Materials
- KiwiBank
- Salesforce Slack Platform