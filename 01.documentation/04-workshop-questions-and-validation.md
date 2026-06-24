# Workshop Questions and Validation Plan

- **Status:** Draft notes
- **Last updated:** 2026-06-23
- **Purpose:** Provide workshop questions and a validation path for the HCP Terraform agentic vision.

---

## 1) Workshop framing

Don't ask, "What is our AI north star?"

Ask:

```text
What can HCP Terraform ship next that proves Terraform is the trusted place for agentic infrastructure change?
```

Run three moves: review evidence, map broken handoffs, then pick slices by customer value, feasibility, trust risk, and competitive urgency.

Use `05-competitor-agentic-iac-analysis.md` before prioritization. It shifts the frame from "what AI feature should we add?" to "which agentic IaC loop must HCP Terraform own?"

## 2) Airbnb follow-up questions

1. What were the 2-3 workflows where TFE most clearly fell short?
2. What did Spacelift let you do quickly that TFE did not?
3. When you say agentic workflows, what is the exact loop?
4. Where do agents enter today: terminal, GitHub, Slack, CI, UI, or internal platform?
5. Which actions are allowed without a human, and which require approval?
6. What evidence do you need before trusting an agent-generated Terraform change?
7. What does "testing in the registry" mean: unit, integration, policy, sandbox, or full e2e?
8. What would HCP Terraform need to show next to feel credible again?
9. Which competitor feature changed your expectation most: Spacelift Intent, Infra Assistant, run AI, MCP, Slack actions, module tests, Scalr PR-native GitOps, or something else?
10. Should HCP Terraform show up inside existing assistants like Copilot, Claude, Cursor, Slack, and terminal agents, or primarily inside the HCP Terraform UI?

Secondary questions:

- Are failed-run explanations high-value or table stakes?
- Which failed-run classes create the most platform-team load?
- How should runtime permissions be scoped for agents?
- What would no-human-in-the-loop deployment require before it is acceptable?
- Where is Sentinel/OPA insufficient today?
- What proof would make you reconsider HCP Terraform in 6-12 months?

## 3) Internal workshop questions

### Product scope

- What is the first flagship slice?
- Is failed-run repair the right proof point?
- Which user is primary first: platform engineer, app developer, Terraform admin, SRE, or support?
- Which HCP Terraform surfaces can change without Atlas/platform dependency risk?
- What must be visible in the first demo?

### Data and tool access

- Which run, plan, log, state, policy, and workspace data is accessible to the agent today?
- What does the Terraform MCP server expose today?
- Can MCP become product-grade remote setup with visible scope, tool filtering, and per-user token boundaries?
- Can the agent create branches, PRs, speculative runs, and registry/module test evidence?

### Trust rails and handoff

- What is read-only by default?
- What write actions require approval?
- Where does approval happen?
- What appears in the audit log?
- How does policy apply to agent-suggested actions?
- What canonical session/evidence object ties Slack, GitHub, terminal/MCP, and HCP Terraform UI together?
- What admin/debug UI is needed when an external assistant uses HCP Terraform context or tools?

## 4) Prioritization matrix

```text
Candidate slice              Customer pain  Feasible  Trust story  Competitive trigger
---------------------------  -------------  --------  -----------  ---------------------------
Failed-run repair            High           High      High         Spacelift run AI, Scalr ai-explain
Module-backed intent to IaC  High           Medium    Medium       Spacelift Intent + module tests
Drift remediation            High           Medium    High         env zero, Firefly, Scalr drift
Policy failure repair        Medium         High      High         Spacelift policies, Scalr OPA/Checkov
Workspace setup              Medium         Medium    Medium       Backstage templates, env zero templates
Autonomous apply             High           Low       Low          Pulumi Neo, Spacelift Build mode
```

Recommended order:

1. Failed-run repair
2. Module-backed intent to IaC
3. Drift remediation
4. Policy repair
5. Workspace lifecycle automation

## 5) Prototype validation plan

Prototype failed-run repair first.

Surfaces:

- HCP Terraform run page entry point.
- Inline failed-run explanation.
- Mode indicator: explain, plan, prepare PR, operate.
- Workbench with evidence and proposed fix.
- GitHub PR summary/comment with diagnosis, evidence link, validation status, and next action.
- Approval gate and MCP/tool scope panel.

User tasks:

1. Diagnose a failed run.
2. Inspect evidence.
3. Open the workbench.
4. Review the proposed fix.
5. Check validation.
6. Approve PR creation.
7. Explain what the agent did.

Measures:

- time to understand failure
- confidence in diagnosis and proposed fix
- clarity of evidence, approval boundary, mode, and tool permissions
- usefulness of PR summary versus raw plan/log review
- perceived safety versus local-only agent
- admin confidence in debugging and auditing an external-agent session

## 6) Technical spike plan

Spike one real or representative failed-run class.

```text
input: failed HCP Terraform run
step 1: classify failure
step 2: cite evidence from logs/plan/policy
step 3: propose minimal fix
step 4: create branch/PR in test repo
step 5: trigger speculative run
step 6: attach audit evidence
```

Proof signal:

```text
One failed-run class can move from failed run to validated fix PR with an auditable evidence chain.
```

## 7) Leadership demo script

```text
1. A production run fails.
2. The user asks HCP Terraform what happened.
3. The agent explains with evidence.
4. The user opens the workbench.
5. The agent proposes the smallest safe fix.
6. HCP Terraform validates it.
7. GitHub PR is opened.
8. Policy passes.
9. Approval is requested.
10. Audit trail records every step.
```

Close with:

> HCP Terraform wins agentic infrastructure by being the verification and control layer, not by bolting chat onto the UI.
