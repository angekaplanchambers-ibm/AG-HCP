# Vertical Slice: Failed Run to Verified Fix PR

- **Status:** Draft recommendation
- **Last updated:** 2026-06-23
- **Purpose:** Define the tightest compelling slice for agentic HCP Terraform.

---

## 1) Recommendation

Start with failed-run repair.

```text
failed run → evidence-grounded explanation → workbench fix → PR → speculative run → policy gate → approval → audit
```

This proves the trust model without autonomous production changes or a full UI rebuild.

## 2) Why this slice

Failed-run repair fits the current pressure:

- Airbnb asked for help understanding failed runs.
- HCP Terraform already has runs, plans, logs, policies, and workspace context.
- Enterprise trust stays visible through review, approval, audit, and policy.
- GitHub Copilot, Scalr, and Atlantis train users to expect PR/check/comment workflows.
- Scope can start with known failure classes.

Intent-to-IaC matters, but it's less constrained. Failed-run repair proves the rails first; the same rails can later support module-backed intent, drift remediation, and workspace setup.

## 3) Target user story

As a Terraform user with a failed HCP Terraform run, I need an explanation, evidence, and the smallest safe fix so I can recover through a reviewed PR and validated run instead of digging through logs.

## 4) Target experience

```text
Run failed: payments-prod #9281

Agent summary
The run failed because variable `db_subnet_group_name` is missing for module `payments_db`.
The policy failure is secondary; the generated resource cannot be evaluated until the variable is set.

Evidence
- plan log line 188: missing required argument
- module source: app.terraform.io/org/rds/aws
- workspace variable set: payments-shared
- last successful run used `payments-private-subnets`

Recommended fix
Add `db_subnet_group_name = var.private_subnet_group_name` and point the workspace variable to `payments-private-subnets`.

Expected result
- no new public networking
- 1 database resource change
- policy `no-public-db` should pass

[Open in workbench] [Create PR] [Ask follow-up] [Dismiss]
```

## 5) Workbench anatomy

```text
Context: workspace, run, repo, policy, last successful run
Proposed fix: changed files, diff, expected impact
Validation: syntax check, speculative plan, policy check, human approval
Agent reasoning: root cause, confidence, uncertainty, evidence
Controls: Open PR, Run validation again, Request approval
```

## 6) Required capabilities

### Must have

- Run failure classification.
- Log, plan, and policy evidence extraction.
- Workspace-aware explanation.
- Mode label: explain, plan, prepare PR, or operate.
- Suggested next action.
- Minimal fix for a small set of known error classes.
- PR creation for reviewable HCL/config changes.
- PR comment/update with diagnosis, evidence link, expected impact, and validation state.
- Speculative run validation.
- Policy and approval gate.
- Audit record for agent action.
- MCP/tool scope record for what the agent could read/write.

### Nice to have

- Slack status and approval handoff.
- Support packet export.
- Compare with last successful run.
- Module/registry references for module-input failures.
- Confidence and uncertainty labels.
- Rerun/start-over path.
- Drift/cost/security hints when relevant.

## 7) First failure classes

Start narrow:

1. missing required variable
2. invalid module input
3. provider version conflict
4. policy failure with clear remediation
5. drift-caused plan surprise

## 8) Explicit non-goals

- No fully autonomous apply.
- No arbitrary repo refactor.
- No blank-prompt provisioning demo as first proof.
- No hidden workspace variable mutation.
- No policy exception creation without explicit approval.
- No replacement of GitHub code review.

## 9) Success metrics

- reduced median failed-run triage time
- increased failed-run self-resolution rate
- fewer support tickets for common failed-run classes
- percentage of agent-created PRs that pass speculative plan
- approval/rejection reasons captured
- PR comment engagement: workbench opens, suggested action clicks, rerun attempts
- percent of sessions with complete evidence: intent, context, tool scope, diff, validation, approval
- user can explain why the agent recommended the fix
- admin can audit what the agent read and changed

## 10) Demo storyline

```text
A production run fails.
The user asks HCP Terraform what happened.
The agent explains with evidence.
The user opens the workbench.
The agent proposes the smallest safe fix.
HCP Terraform validates it.
GitHub PR is opened.
Policy passes.
Approval is requested.
Audit trail records every step.
```

Demo message:

> This is not a chatbot. This is Terraform-native verified infrastructure intent.
