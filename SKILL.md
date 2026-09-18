---
name: adaptive-composition
description: Design, implement, or review interfaces that must adapt across space, modality, capability, or state. Use for web, desktop GUI, terminal, conversational, agentic, wearable, spatial, and multi-device work involving responsive composition, visual identity, hierarchy, comparison, continuity, or performance. Especially useful when a design merely shrinks or stacks, loses its character, hides essential work, or obscures what a system is doing.
metadata:
  version: "1.1.0"
---

# Adaptive Composition

Preserve meaning, identity, agency, and the ability to complete the task as conditions change. Recompose relationships when necessary; scale when scaling actually works.

Historical work can supply precedents and hypotheses, but it is optional and never automatic proof of usability. Solve the present problem without imposing a period's appearance or a generic contemporary style.

## Reference router

Read the smallest set that can change the decision. Usually begin with one task reference and, for implementation, one medium reference. Add another only when the work actually contains that concern. Do not preload the history or source register.

| Need | Read |
|---|---|
| Adapt an existing composition or define cross-format behavior | [Composition](references/composition.md) |
| Create a visual language where identity is absent or weak | [Visual language](references/visual-language.md) |
| Review a design, verify an implementation, or test this skill | [Evaluation](references/evaluation.md) |
| Implement for web or desktop GUI | [Web / GUI](references/web-gui.md) |
| Implement a terminal interface | [TUI](references/tui.md) |
| Design streaming AI, agent actions, conversation/voice, handoff, wearables, or spatial interfaces | [Dynamic systems](references/dynamic-systems.md) |
| Performance, resource, battery, or slow-network constraints can alter the design | [Performance](references/performance.md) |
| Need decision cards or a concrete analogue | [Principles](references/principles.md) or [examples](references/examples.md) |
| A historical precedent will clarify a tradeoff, or the user requests history | [Historical atlas](references/historical-atlas.md); open [sources](references/sources.md) only to verify a claim |

## Working method

### Establish the design problem

Inspect the actual content, existing visual language, working interface, and supported environments. Identify the user's task before changing the composition. Preserve explicit preferences and project conventions. Ask only for missing information that materially affects the design; otherwise state reasonable assumptions and proceed.

For reviews, use [the evidence and prioritization method](references/evaluation.md). Distinguish observed behavior, source facts, inferred effects, and product hypotheses at the relevant finding. A general opening disclaimer is not enough. Business priorities such as acquisition versus immediate use need support from the brief or a stated assumption; layout alone cannot establish them.

Record the relevant constraints: available width **and height**, readable type or character cells, input and output modalities, viewing or listening conditions, language and text expansion, accessibility needs, latency and resource cost, privacy, and content/state variability. Include interruption, handoff, or delegated action when the task has them. A small window is not evidence of a different user intention. Do not infer touch, expertise, urgency, or reduced feature needs from width.

### Define what must survive

Separate three kinds of invariants:

- **Meaning and task:** content relationships, required actions, units, warnings, comparison criteria, and truthful state.
- **Recognition:** names, distinctive imagery, typographic roles, tone, and approved identity cues. Exact positions need not survive.
- **Continuity:** selected object, drafts, focus, navigation history, scroll context, and ongoing work when the layout changes.

For systems that generate, stream, hand work to another surface, or act on a person's behalf, also preserve **agency and accountability**: who or what will act, the target and scope, what is proposed versus committed, uncertainty and provenance that affect a decision, approval state, and a realistic route to stop, correct, retry, or recover.

Identify variables such as arrangement, number of columns, image treatment, simultaneous versus sequential presentation, and disclosure. Keep access to required information and capabilities; different visibility is not permission to remove them.

### Use precedents only when they help

Use [the principle cards](references/principles.md) for concrete decisions and failure checks. Use [the historical atlas](references/historical-atlas.md) only when a precedent helps choose a direction, challenge a default, or explain a tradeoff. For culturally specific work, research the actual context and writing system instead of treating the atlas as a universal canon.

Examples: publication grids for a coherent family of varied pages; wayfinding for navigation and location; packaging for recognition at different sizes; instrument controls for state and action; cartography for comparison and detail; terminal/HCI history for efficiency, feedback, and recovery.

Use a precedent to explain a decision: identify the relevant constraint, transferable principle, and relationship it changes. Surface that connection only when it makes the recommendation easier to assess. A historical citation is not required for an ordinary usability fix. Prefer one useful connection over several designer names. Source IDs resolve in [the annotated source register](references/sources.md). Verify a source before adding a historical claim or quotation.

### Compose for the actual conditions

Use [the composition method](references/composition.md) to select among scaling, reflow, cropping, substitution, disclosure, and sequencing. Work with real content in a constrained and a spacious composition; check intermediate conditions and short viewports. Derive transition points from observed failure, not device labels.

When the brief does not supply a strong identity, use [the visual-language method](references/visual-language.md) to establish a characteristic relationship and a bounded formal grammar before polishing components. When the surface changes modality, location, or actor—or output arrives probabilistically over time—use [dynamic-systems guidance](references/dynamic-systems.md). If asset, compute, network, energy, or thermal cost could change what should be composed or when it can appear, set and verify a project-specific budget with [performance guidance](references/performance.md).

For substantial cross-format work, make a compact adaptation table:

| Element or task | Invariant | Constrained presentation | Spacious presentation | Transition and verification |
|---|---|---|---|---|
| Required content/control | What must remain true | Arrangement and access | Arrangement and access | Failure that triggers change; how to check |

For the leading recommendations in a substantial review, describe the actual replacement composition: element order and grouping, visible content and routes to disclosed content, retained identity, and relevant state continuity. Explain the condition that would trigger a change and what result would justify it. “Improve hierarchy,” “use less imagery,” and “show more context” need this concrete follow-through. Without rendering access, provide a provisional arrangement and a measurable failure condition; do not invent a verified breakpoint.

Keep this proportional: a small component may need only a sentence. Do not turn a review into an unrequested implementation, a narrow styling fix into a full redesign, or add surfaces or product requirements the user did not request.

### Implement in the medium

- **Web or desktop GUI:** read [web and GUI guidance](references/web-gui.md). Preserve semantics and native/platform behavior while changing visual relationships.
- **Terminal UI:** read [terminal guidance](references/tui.md). Design in cells and keyboard operations, including resize and terminal capability limits.
- **Other surfaces:** read [dynamic systems](references/dynamic-systems.md), then consult current official guidance for the actual platform, assistive technology, and input/output hardware.

Use the project's framework, toolkit, design system, and assets unless the task calls for changing them. This skill supplies composition reasoning, not exhaustive platform instructions or authorization to replace a stack, install packages, publish artifacts, or copy protected artwork. Pair it with current platform, accessibility, security, or implementation guidance when those details determine correctness.

### Verify the result

Use the relevant checks in [evaluation](references/evaluation.md). Inspect the actual rendered or presented result and exercise the task where tools permit. Record enough environment, content, state, and performance conditions to reproduce consequential findings. Test transitions, interruptions, and non-ideal content, not just two attractive screenshots. Assess identity, reading/action order, task completion, comparison, agency, and recovery separately. Judge scrolling by its effect on the intended task; content below the opening viewport is not itself a defect.

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
