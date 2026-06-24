# Cross-Surface Agentic HCP Terraform Journeys

- **Status:** Draft notes
- **Last updated:** 2026-06-23
- **Purpose:** Show how agentic HCP Terraform works across terminal, GitHub, Slack, HCP Terraform UI, and registry/module surfaces.

---

## 1) Surface principle

The HCP Terraform UI is no longer the only interface. Agents widen the product surface across terminal, editor, MCP, GitHub, Slack, run pages, registry/module pages, workspace/policy pages, and support handoffs.

The design job is continuity: start anywhere, verify in HCP Terraform, keep the evidence trail intact.

Competitor signals from `05-competitor-agentic-iac-analysis.md`:

- Spacelift: explicit Ask/Build-style modes and hosted/scoped MCP.
- Scalr and Atlantis: rich PR summaries, slash commands, and action ergonomics.
- GitHub Copilot: agents leave branches, PRs, checks, and logs.
- Azure Copilot: contextual prompts and explicit context attachment near resources.
- env zero and Firefly: scheduled pulse, drift, codification, cost, and remediation.
- Backstage: visible tasks, review pages, dry runs, logs, and rerun paths.
- Geniez: domain platforms can make existing assistants domain-aware while retaining admin, observability, debugging, permission, and audit controls.

## 2) Terminal / CLI to HCP Terraform

```text
Terminal agent → Terraform MCP/context request → HCP Terraform workspace/run data
→ local agent plan → PR/speculative run → HCP Terraform validation/audit
→ HCP workbench for evidence and approval
```

Requirement: terminal remains fast, HCP Terraform remains the trust record. The MCP handoff must show read/write scope, enabled tools, whose token applies, and which actions require approval.

## 3) GitHub PR / failed run / debug loop

```text
GitHub PR → HCP speculative run fails → HCP run agent diagnoses
→ PR comment summarizes failure and next action → HCP workbench opens
→ proposed fix becomes reviewed PR change → run passes → audit stored
```

Requirement: GitHub shows enough to keep review moving. HCP Terraform owns deeper evidence, validation, approval state, and the durable audit record.

PR comments should match Scalr/Atlantis expectations: concise run summary, exact failed check, suggested action, and a link into the HCP workbench.

## 4) Slack daily infra pulse

```text
HCP Terraform scheduled analysis → Slack daily pulse
→ Explain failed run / Open workbench / Create ticket / Dismiss or snooze
→ HCP workbench → PR/run/audit outcome posted back
```

Requirement: Slack summarizes and routes. It should not become a parallel control plane. Actions must be policy-scoped and mirror HCP approval state.

## 5) HCP Terraform run page and workbench

```text
Run page → Ask Terraform → inline explanation with evidence
→ Open workbench → proposed fix + validation + approval/PR controls
→ audit record stores intent, context, tools, diff, validation, approval
```

Requirement: do not turn every page into chat. Inline surfaces explain and route. Workbench appears when the user moves from understanding to action.

The run page should expose mode: explain, plan, prepare PR, or operate. Context chips should show what the agent is using: run, workspace, repo, policy, module, variable set, and last successful run.

## 6) Registry / module testing

```text
Intent → registry assistant → module fit report → module test case
→ generated PR → HCP run evidence linked to module
```

Requirement: Terraform registry advantage becomes agentic advantage only when module adoption includes fit, variables, risks, tests, and evidence.

Module testing should answer the Spacelift module-test challenge: what was created, what was destroyed, which phases passed, and what evidence attaches to the module.

## 7) Handoff rules

1. **Start anywhere.** Terminal, Slack, GitHub, and UI are valid entry points.
2. **Verify in Terraform.** Plans, policy, state, and runs stay in the trust layer.
3. **Act in reviewable units.** PRs and run actions stay visible.
4. **Preserve evidence.** Each surface links back to the same agent session/audit record.
5. **Escalate the surface when needed.** Inline help for explanation, workbench for consequential change.
6. **Make external agents Terraform-aware, not Terraform-authoritative.** Copilot, Claude, Cursor, Slack, and local agents can carry intent and draft work; HCP Terraform owns validation, permission scope, and durable proof.
