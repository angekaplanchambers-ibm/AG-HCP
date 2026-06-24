# Six-Month Vision: Verified Infrastructure Intent

- **Status:** Draft notes
- **Last updated:** 2026-06-23
- **Audience:** HCP Terraform design, PM, engineering, leadership workshop participants

---

## 1) One-line vision

HCP Terraform should be the safest place to turn infrastructure intent into verified change.

Not:

```text
Terraform has an AI chatbot.
```

Instead:

```text
Terraform grounds an infrastructure goal in my estate, shows the plan, tests the change, enforces policy, opens the PR, explains the run, and leaves an audit trail.
```

## 2) Customer grounding

Airbnb is the clearest current signal. The account is moving from TFE to Spacelift, so treat the feedback as product-direction evidence, not account noise.

The gaps are specific:

1. **Agentic workflow, not isolated primitives**
   - End-to-end Terraform work across development and operations.
   - Hooks for customer-specific agent workflows.

2. **Verification and guardrails**
   - Checks around agent output.
   - Policy enforcement and fine-grained runtime permissions.

3. **Testing inside the Terraform workflow**
   - Module tests tied to registry and HCP Terraform workflows.
   - Validation before deployment.

4. **Developer/operator assistance**
   - Failed-run explanation.
   - Embedded debugging.
   - Better help writing HCL.

5. **Visible product motion**
   - Faster release signal.
   - Faster fixes.
   - Clear proof that HCP Terraform is moving with the market.

## 3) Competitive read

Agentic IaC is becoming a workflow system, not a chat surface. Spacelift is the sharpest direct signal because Airbnb chose it over TFE, but the pressure also comes from Scalr, Pulumi, env zero, Firefly, GitHub Copilot, cloud copilots, Atlantis, Backstage, and Geniez/Genie Z.

Spacelift's story is connected:

```text
intent → generated IaC → policy → run → explanation → drift → remediation → audit
```

Competitors are teaching users to expect:

- intent-to-IaC
- run explanation
- MCP/tool access
- Slack and PR actions
- policy, hierarchy, and worker controls
- drift detection and remediation
- module tests and registry evidence

The issue is not whether HCP Terraform has pieces of this. The issue is whether users experience a trusted loop with modes, evidence, approvals, PR handoff, module testing, and audit.

Geniez adds a useful pattern: HCP Terraform should not assume the web UI is the only front door. Copilot, Claude, Cursor, Slack, terminal agents, GitHub, and the HCP Terraform UI can all start work. HCP Terraform should own the context scope, validation, approval, audit, and evidence.

## 4) HCP Terraform advantage

HCP Terraform already has the native Terraform record:

- workspaces
- runs
- plans
- state lineage
- policy checks
- variables
- registry/module context
- VCS integration
- approvals
- audit expectations
- enterprise permissions

The opportunity is to turn those primitives into an intent-to-verification loop.

## 5) Product promise

Use this as the shared product loop:

```text
intent → context → plan → code → validation → approval → run → explanation → remediation → audit
```

Each team should be able to point its work to one or more links in that chain.

## 6) Six-month scope

### In scope

- Contextual run explanations.
- Failed-run diagnosis with evidence.
- Clear agent modes: explain, plan, prepare PR, operate.
- Workbench handoff for proposed fixes.
- PR generation for narrow, reviewable changes.
- PR summaries/comments that link to HCP Terraform evidence.
- Speculative run validation.
- Policy and approval gates.
- MCP setup/scoping UX for read/write tool exposure.
- Audit trail for agent action.
- Slack/GitHub/terminal handoffs that preserve context.
- Scheduled infra pulse for failed runs, drift, policy, modules, cost, and risk.
- Registry/module testing direction for the next slice.
- Admin visibility into assistant entry point, Terraform context/tools used, permission scope, and captured evidence.

### Out of scope for the first proof

- Full autonomous apply.
- Generic Terraform chatbot.
- Full HCP Terraform IA redesign.
- Blank-prompt multi-cloud provisioning.
- Replacing GitHub review.
- Replacing policy-as-code.

## 7) Culture and alignment phrases

Use concrete language that helps teams make the same trade-offs:

1. **Verified infrastructure intent**
   - Broader strategy.

2. **Plans before changes, proofs before applies**
   - Safety and enterprise trust.

3. **Every agent action leaves evidence**
   - Audit and implementation guardrails.

4. **From request to reviewed run**
   - Cross-surface workflow framing.

5. **Not chat. Change control.**
   - Pushes the work away from chatbot assumptions.

6. **Terraform-native agent rails**
   - Engineering scope and differentiation.
