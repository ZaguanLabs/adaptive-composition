---
name: adaptive-composition
description: Design, implement, or review web, desktop GUI, and terminal interfaces using historical graphic, information, industrial, and interaction design principles. Use for cross-format identity, responsive composition, hierarchy, typography, navigation, information density, and adapting a design to different constraints. Especially useful when a layout merely shrinks or stacks, loses its character, or hides essential work on smaller surfaces.
metadata:
  version: "1.0.1"
---

# Adaptive Composition

Preserve meaning, identity, and the ability to complete the task as conditions change. Recompose relationships when necessary; scale when scaling actually works.

Draw on the connected histories of publication design, packaging, identity systems, signage, cartography, industrial controls, terminals, and HCI. Historical work supplies precedents and hypotheses, not automatic proof of usability. Apply the principle that solves the present problem without imposing the period's appearance.

## Working method

### Establish the design problem

Inspect the actual content, existing visual language, working interface, and supported environments. Identify the user's task before changing the composition. Preserve explicit preferences and project conventions. Ask only for missing information that materially affects the design; otherwise state reasonable assumptions and proceed.

For reviews, use [the evidence and prioritization method](references/evaluation.md). Distinguish observed behavior, source facts, inferred effects, and product hypotheses at the relevant finding. A general opening disclaimer is not enough. Business priorities such as acquisition versus immediate use need support from the brief or a stated assumption; layout alone cannot establish them.

Record the relevant constraints: available width **and height**, readable type or character cells, input methods, viewing conditions, language and text expansion, accessibility needs, latency, and content/state variability. A small window is not evidence of a different user intention. Do not infer touch, expertise, urgency, or reduced feature needs from width.

### Define what must survive

Separate three kinds of invariants:

- **Meaning and task:** content relationships, required actions, units, warnings, comparison criteria, and truthful state.
- **Recognition:** names, distinctive imagery, typographic roles, tone, and approved identity cues. Exact positions need not survive.
- **Continuity:** selected object, drafts, focus, navigation history, scroll context, and ongoing work when the layout changes.

Identify variables such as arrangement, number of columns, image treatment, simultaneous versus sequential presentation, and disclosure. Keep access to required information and capabilities; different visibility is not permission to remove them.

### Choose precedents by the problem they solved

Use [the historical atlas](references/historical-atlas.md) when a precedent helps choose a direction or explain a tradeoff. Use [the principle cards](references/principles.md) for concrete decisions and failure checks. Read only relevant sections; do not load the entire library for every task.

Examples: publication grids for a coherent family of varied pages; wayfinding for navigation and location; packaging for recognition at different sizes; instrument controls for state and action; cartography for comparison and detail; terminal/HCI history for efficiency, feedback, and recovery.

Use a precedent to explain a decision: identify the relevant constraint, transferable principle, and relationship it changes. Surface that connection when it makes the recommendation easier to assess; a historical citation is not required for every ordinary usability fix. Prefer one useful connection over several designer names. Source IDs resolve in [the annotated source register](references/sources.md). Verify a source before adding a new historical claim or quotation.

### Compose for the actual conditions

Use [the composition method](references/composition.md) to select among scaling, reflow, cropping, substitution, disclosure, and sequencing. Work with real content in a constrained and a spacious composition; check intermediate conditions and short viewports. Derive transition points from observed failure, not device labels.

For substantial cross-format work, make a compact adaptation table:

| Element or task | Invariant | Constrained presentation | Spacious presentation | Transition and verification |
|---|---|---|---|---|
| Required content/control | What must remain true | Arrangement and access | Arrangement and access | Failure that triggers change; how to check |

For the leading recommendations in a substantial review, describe the actual replacement composition: element order and grouping, visible content and routes to disclosed content, retained identity, and relevant state continuity. Explain the condition that would trigger a change and what result would justify it. “Improve hierarchy,” “use less imagery,” and “show more context” need this concrete follow-through. Without rendering access, provide a provisional arrangement and a measurable failure condition; do not invent a verified breakpoint.

Keep this proportional: a small component may need only a sentence. Do not turn a review into an unrequested implementation, a narrow styling fix into a full redesign, or add surfaces or product requirements the user did not request.

### Implement in the medium

- **Web or desktop GUI:** read [web and GUI guidance](references/web-gui.md). Preserve semantics and native/platform behavior while changing visual relationships.
- **Terminal UI:** read [terminal guidance](references/tui.md). Design in cells and keyboard operations, including resize and terminal capability limits.
- **Examples:** read [worked examples](references/examples.md) for an album interface, an operational dashboard, editorial content, or an expressive identity.

Use the project's framework, toolkit, design system, and assets unless the task calls for changing them. This skill supplies design reasoning, not authorization to replace a stack, install packages, publish artifacts, or copy protected artwork. It can complement an existing visual-design or implementation skill without requiring one.

### Verify the result

Use the relevant checks in [evaluation](references/evaluation.md). Inspect the actual rendered result and exercise the task where tools permit. Record enough environment, content, and state information to reproduce consequential findings. Test transitions and non-ideal content, not just two attractive screenshots. Assess identity, reading/action order, task completion, comparison, and recovery separately. Judge scrolling by its effect on the intended task; content below the opening viewport is not itself a defect.

Report what changed or is proposed, why it serves the task, what was verified, and material limitations. Judge an implemented adaptation against the original task under comparable conditions, including whether recognition or useful context was lost. Do not call a design accessible, usable, or historically proven solely because it follows this skill.

## Guardrails for applying history

- A grid coordinates relationships; it does not require every page to have the same composition.
- Accessibility, accurate meaning, and operability take priority over stylistic purity. Keep explicit cultural and brand expression where it serves the brief.
- Functional consistency often matters more than pixel consistency. Preserve actions and terms across variants, but respect established platform conventions.
- Dense information can be appropriate. Do not replace a comparison table with disconnected cards merely to create more whitespace.
- Use historical optical correction and selective detail as precedents; do not equate bitmap resolution, CSS pixels, physical size, and perceived legibility.
- LP-to-cassette adaptation is an instructive analogy, not a claim that every release was recomposed successfully. A J-card has panels, a spine, and a folded sequence; it is not simply a portrait rectangle. Some artwork scales adequately.
- Responsive web design already includes adaptation; Marcotte's 2010 article is not a manifesto for shrinking desktop layouts [S18]. “Adaptive composition” is the working emphasis here, not a claim to have invented a replacement discipline.
- Age, fame, repeated use, and museum acquisition establish neither universal effectiveness nor inclusion. Test the current audience and task. Do not portray Western modernism as the whole history of design.
- Do not enforce golden ratios, seven-item menus, universal icon meanings, obligatory minimalism, fixed reading patterns, or an allegedly scientific ideal font. Explain measurable tradeoffs.

## Library

| Reference | Read when |
|---|---|
| [Historical atlas](references/historical-atlas.md) | Selecting a precedent or distinguishing historical evidence from analogy |
| [Principles](references/principles.md) | Making hierarchy, typography, identity, interaction, or information decisions |
| [Composition](references/composition.md) | Adapting content and controls across constraints |
| [Web / GUI](references/web-gui.md) | Implementing semantic, responsive, or native application behavior |
| [TUI](references/tui.md) | Designing keyboard and character-cell interactions |
| [Examples](references/examples.md) | Needing concrete transformations and counterexamples |
| [Evaluation](references/evaluation.md) | Reviewing a design or testing the skill's behavior |
| [Sources](references/sources.md) | Checking attribution, dates, scope, and current implementation guidance |
