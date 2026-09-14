<p align="center">
  <img src="docs/images/hebi-logo.png" alt="HEBI logo" width="420">
</p>

<h1 align="center">HEBI · CAD to SketchUp 911</h1>
<p align="center"><strong>Build from architectural evidence. Keep every decision traceable.</strong></p>
<p align="center">Windows · SketchUp · Human or optional independent-agent review</p>

> **Release 2026.09.11 · Experimental workflow**
> Automated regression and packaging checks have passed. A new end-to-end modeling trial using the 911 release has not yet been completed.

## What is this?

A reusable Skill for turning architectural CAD plans, elevations and sections into controlled SketchUp models.
It runs through a primary agent capable of reading project files and executing scripts.
It is not standalone modeling software or a promise of one-click delivery from arbitrary drawings.

**One Skill, two review paths.** Choose human review at intake, or use an existing connection to another agent.
No additional agent subscription, specific model provider or multi-agent orchestration platform is required for the human path.

## How it works

![Drawing-led modeling and review workflow](docs/images/workflow.svg)

1. **Read** complete drawing frames, annotations and nested blocks; check readability and coverage.
2. **Register** axes, orientations and level datums across plans, elevations and sections.
3. **Build a white model** to validate the envelope, levels, roofs and actual openings before detailing.
4. **Detail** reusable components, opening subdivisions and simple materials.
5. **Compare** exports of the actual SKP against independent drawing evidence at matching orientation and scale.

When a mismatch appears, repair the earliest incorrect source interpretation or model constraint, not just its visible symptom.
File hashes detect changes to evidence; they do not replace architectural judgment.

## Development snapshots

**These are real screenshots from an earlier project, not a fresh automated test of the 911 release.**
The interior additions and facade design involved user decisions and project-specific scripts.
They illustrate the development process, not guaranteed one-click reproduction by the generic Skill.

### 01 / Validate the white model and openings

![White model with openings, canopies and entrances](docs/images/01-white-model.jpg)

Check the building envelope, opening positions, canopies and entrances before fine details obscure basic geometry errors.
Window detailing and material work were not complete at this stage. The visible rooflight strips alone are not proof of verified through-openings.

### 02 / Components and interior framing

![Interior framing, columns, purlins and window subdivisions](docs/images/02-interior.jpg)

Roof members were added around existing column positions, with shared definitions for repeated components.
Reference images and user-authorized estimates supported illustrative modeling only.
Member sizes and connections were not structurally engineered and must not be used as construction design.

### 03 / Facade exploration without moving openings

![Silver-white cladding and dark horizontal bands around existing openings](docs/images/03-facade.jpg)

This design study retained the existing openings while exploring silver-white aluminum cladding and dark horizontal bands.
It was an additional user-requested design task, not an original finish automatically inferred from the CAD.

## What changed in 911?

| Retained | Simplified or optional |
| --- | --- |
| Complete reading, coordinate registration and actual-model comparison | No fixed model provider or coordinator |
| Real openings, reusable components and simple materials | No unrelated modeling applications or download scripts |
| Versioned saves, evidence checks and review receipts | No personal logs, credentials or historical project files in the Skill package |
| Actual human or independent-agent responses | No requirement for users to edit JSON or type mode-switch commands |

Reuse valid intermediate artifacts and recheck affected dependencies instead of repeating the entire workflow.
Routine model adjustments no longer automatically trigger Skill maintenance.

## Install and start

**Requirements:** Windows, a script-capable primary agent, the Python dependencies in the Skill, and SketchUp with the required solid operations.
The current white-wall merging path requires SketchUp Pro solid union support.
DWG input needs a matching DXF obtained through an available, authorized converter or a user export.
PDFs and images are supporting evidence, not replacements for CAD geometry.

Download the [911 Skill package](dist/cad-to-sketchup-model-2026-09-11.zip), or use the
[complete Skill folder](skills/cad-to-sketchup-model-2026-09-11/).
Install the entire `cad-to-sketchup-model-2026-09-11` folder into your agent's skills directory, not only `SKILL.md`.
For Codex, the default location is `~/.codex/skills/`.
See the [Skill entrypoint](skills/cad-to-sketchup-model-2026-09-11/SKILL.md) for execution requirements.

Then ask:

> Use CAD to SketchUp 911 to build a model from the drawings in this folder.

Choose a review path once per project. Later, say “switch to human review” or “switch to another agent for review.”
Choosing another agent does not install software or create an account; an existing usable connection and image-reading capability are required.

In human mode, the user inspects readable drawing/model comparisons and responds in natural language; the primary agent records the response.
Drawing review takes place before modeling. Topology review and approval are presented together, as are final review and acceptance.
The implementation documentation retains some Chinese interaction examples and references; the workflow can be requested in English.

## Validation and limitations

- **69 automated tests** passed during 911 packaging and again from an isolated extracted directory.
- **8 execution checks** covered the suite, command entrypoints, review selection and arbitrary CAD filenames.
- Skill structure, Python/JSON parsing, documentation links and PowerShell syntax were checked.
- Synthetic fixtures are not real-building acceptance and do not establish another agent's visual reliability.
- Missing required evidence or failed checks restrict the output to a clearly labeled candidate, not verified delivery.
- This release does not promise a macOS workflow or structural, construction or fabrication certification.

The original HEBI branding and development images are retained. License: not yet specified.
