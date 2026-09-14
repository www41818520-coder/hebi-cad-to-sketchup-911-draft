---
name: cad-to-sketchup-model-2026-09-11
description: Build or revise architectural SketchUp models from DWG/DXF plans, elevations and sections on Windows, with traceable geometry, reusable components, simple materials and user-selected human or independent-agent review.
---

# CAD to SketchUp 911

Use this folder as one coherent runtime; do not mix older generators. Contract
schema dates are compatibility identifiers, not the skill release date. One
implementation owner edits and integrates; reviewers do not modify the model.

## Start or resume

1. Confirm the project folder, approved inputs and scope. Inspect workflow state
   and valid artifacts before creating work; do not restart a completed stage.
2. On first use ask: **本项目选择人工审核，还是使用你已有的其他 Agent 审核？
   没有其他 Agent 可以直接选人工。** Ask which available agent only if chosen.
3. Record the choice with `scripts/review_session.py configure` using the exact
   project root. On resume read `work/review/settings.json`, without asking again.
   “切换人工审核 / 切换其他 Agent 审核” changes that setting internally. Users need
   no terminal commands. This does not change models, quotas or old review identities.
4. Check Windows, Python dependencies in `requirements.txt`, usable DXF and
   SketchUp operations required by the builder (white-wall solid union needs
   SketchUp Pro). Detect the installed year. DWG requires an available authorized
   converter or user-exported DXF; do not install software without permission.

Read [review.md](references/review.md) for both routes. This is one skill with
optional review providers, not a mandatory multi-agent company framework.

## Model workflow

Read only the current stage guide and its relevant references:

1. **Read**: [stage-reading.md](references/stage-reading.md). Preserve complete
   frames, nested blocks, titles, dimensions and units. Render with strong contrast;
   weaken material-only hatch without erasing cut boundaries. Validate coverage
   and review readability before deriving geometry.
2. **Topology**: [stage-topology.md](references/stage-topology.md). Register axes,
   directions, datums and sections using asymmetric anchors. Derive one envelope
   and measured inventory of all in-scope systems. Compare white-model views and
   obtain topology approval before detailing.
3. **Detail**: [stage-production.md](references/stage-production.md). Preserve true
   openings and wall/roof junctions. Equal geometry uses shared component definitions;
   different sizes/sections use distinct families. Use CAD finish annotations or
   labeled illustrative materials. Local SU material assets are optional.
4. **Verify**: [stage-qa.md](references/stage-qa.md). Export actual SKP evidence
   and independently compare CAD at the same scale, orientation and section.
   Check omissions, additions, silhouettes, openings, levels and cross-view links.
   A plausible perspective or successful script is not architectural QA.
5. **Deliver**: [stage-delivery.md](references/stage-delivery.md). After checks,
   request final acceptance, save a new version and issue the validated receipt.
   Retain limitations and estimates; do not claim structural engineering approval.

## Review and interaction

Human and agent reviewers use the same evidence and contracts. Neither can waive
machine failures. A producer cannot certify its own interpretation with a new ID.
For human review, present readable comparisons and a plain-language checklist;
record actual responses, not inferred approval. Combine topology review with
topology approval, and final review with final acceptance, validating review
before acceptance internally. Reading review needs an explicit human response
before modeling; bundle it with intake questions where practical, not one question
per frame. With another agent, two routine user approvals remain: topology and final.

## Keep work short and portable

- Resume valid artifacts; invalidate only changed dependencies. Fix the earliest
  wrong contract before regenerating its dependents, not just the visible model.
- Test a representative sample when changing geometry logic; otherwise reuse
  working generators and avoid repetitive full rebuilds.
- Send a reviewer a bounded packet with required evidence, views, schema and
  focused questions. Do not duplicate full analysis through several coordinators.
- Use project-relative evidence and runtime-relative tools; no personal paths,
  credentials, caches, logs, live bridge registries or test projects in the package.
- Preserve original CAD/SKP files. Use transactions, explicit targets and versioned
  saves; see [sketchup-execution.md](references/sketchup-execution.md). Inspect
  live task/output state after timeout before resubmitting.
- Ask only about consequential gaps. User-authorized estimates are illustrative,
  never measured CAD or structural design; do not turn project dimensions into defaults.
- For SU-only edits verify the requested changes without claiming CAD agreement.
  Candidate files may be shared with limitations, not labeled verified delivery.
