# Adaptive Composition

An agent skill for interfaces that must keep working—and remain recognizable—as available space, modality, capability, state, and resource constraints change.

**Preserve meaning, identity, agency, and the ability to complete the task. Recompose when necessary; scale when scaling works.**

Current version: **1.1.0** · [Read the skill](SKILL.md)

## A responsive interface can fit and still fail

A page can stack cleanly while losing its hierarchy. A dashboard can turn into cards and destroy comparison. A compact view can hide a required action. A layout transition can reset a draft, restart playback, or make an agent's proposal look like a completed action.

Adaptive Composition treats these as composition problems, not width problems. It asks what must survive, which relationships may change, and what evidence would show that the new arrangement works.

The method applies to:

- Web and desktop interfaces.
- Terminal interfaces designed in character cells and keyboard operations.
- Visual systems that need recognizable constrained and spacious variants.
- Streaming and generative output, agent actions, approvals, and recovery.
- Conversation, voice, wearables, spatial interfaces, and device handoff.
- Performance conditions that affect when content becomes useful or interaction remains responsive.

Historical design can supply a useful precedent, but it is optional. The present task, audience, medium, and evidence decide whether an idea belongs.

## The core method

The skill separates what must survive from what may change:

| Invariant | What must survive |
|---|---|
| Meaning and task | Content relationships, required actions, comparison criteria, units, warnings, and truthful state |
| Recognition | Names, distinctive imagery, typographic roles, tone, and approved identity cues |
| Continuity | Selection, drafts, focus, navigation history, scroll context, playback, and ongoing work |
| Agency and accountability, when applicable | Actor, target, scope, proposal versus commitment, approval, provenance, and realistic recovery |

It then chooses a transformation for a stated reason:

- **Scale** when the object remains legible and recognizable.
- **Reflow** when the reading and action order still make sense.
- **Recompose** when the same elements need different relationships.
- **Crop or substitute** when an authorized treatment preserves meaning.
- **Disclose or sequence** when simultaneous presentation no longer works.
- **Translate** when meaning must move between visual, auditory, haptic, spatial, or textual presentation.
- **Summarize or omit** only when the result remains truthful and the removed material is genuinely nonessential.

Transitions come from observed failure in real content—not device labels or arbitrary breakpoints. The skill also treats a transition as a stateful operation: selection, focus, drafts, filters, playback, approvals, and return paths should not disappear because the composition changed.

## What it changes in practice

Consider an incident dashboard that shows six services, their state, observation time, error rate, owner, and a route to logs.

| Condition | Composition |
|---|---|
| Spacious | An aligned comparison table and a selected-service inspector can coexist. |
| Constrained | The comparison table stays compact or becomes an intentionally bounded scrolling region; details and logs move to a separate view. |
| Through the transition | The same service remains selected, active filters survive, freshness and units remain visible, and live updates do not retarget an action. |

The method does not convert every row into a card simply because the viewport is narrow. The required comparison determines which fields must remain together. A useful acceptance task is concrete: answer “Which unhealthy service has the oldest observation?” at each supported condition, then open logs, return, and confirm that selection and filters remain intact.

The same reasoning applies to an album interface, an illustrated essay, a native multi-pane application, a narrow TUI, a streamed answer, or an action that moves from proposal to approval and execution.

## When to use it

Use the skill when:

- A layout shrinks or stacks successfully but loses hierarchy, identity, comparison, or task access.
- Artwork overwhelms essential information, or cropping removes its meaning.
- A table, workspace, navigation system, or inspector stops working under constraint.
- Width, height, language, text enlargement, input method, latency, or content variability matters.
- A new interface needs a visual language that will not collapse into a generic template.
- Generated output, delegated actions, streaming state, or handoff make agency and recovery visible design concerns.
- Fonts, imagery, scripts, compute, memory, battery, thermal behavior, or intermittent networks can change the composition.
- A review needs concrete replacement arrangements and reproducible verification rather than aesthetic verdicts alone.

It can support a focused component fix or a broad cross-format design. Invoking it does not authorize a redesign, framework replacement, dependency installation, deployment, or external action that the user did not request.

## What it is not

- It is not a fixed design system or a library of period styles.
- It does not replace full brand research, although it includes a method for developing an adaptable visual direction from a weak brief.
- It does not replace current platform documentation, accessibility testing, security review, or domain-specific expertise.
- It does not treat a checklist, source diff, or agent walkthrough as proof of usability.
- It is not yet an empirically validated methodology; the repository includes a release-test protocol, not completed benchmark results.

## Install

### Skills CLI

From the project where you want to use the skill:

```zsh
npx skills add zaguanlabs/adaptive-composition
```

See the CLI documentation for agent targeting and installation scopes.

Update a CLI-managed installation with:

```zsh
npx skills update adaptive-composition
```

The community [skills CLI documentation](https://skills.sh/docs/cli) describes target selection, updates, and its default anonymous telemetry. Review third-party skills before installing them.

### Git checkout for Codex

For a user-scoped installation:

```zsh
mkdir -p ~/.agents/skills
git clone https://github.com/zaguanlabs/adaptive-composition.git \
  ~/.agents/skills/adaptive-composition
```

Update it with:

```zsh
git -C ~/.agents/skills/adaptive-composition pull --ff-only
```

Codex discovers user skills in `$HOME/.agents/skills`. It can also discover repository-scoped skills under `.agents/skills` between the current working directory and repository root. See the [official OpenAI skills documentation](https://developers.openai.com/codex/skills) for current discovery and invocation behavior.

Keep `SKILL.md`, `references/`, and their relative paths together. The repository has no build step or runtime dependency. Rendering, browser inspection, performance measurement, and interaction checks depend on the tools available to the agent.

## Use it

Invoke the skill explicitly with `$adaptive-composition`, or let a compatible agent select it from the task description.

### Review without changing code

```text
Use $adaptive-composition to review this interface at constrained,
intermediate, and spacious sizes, including a short window. Preserve its
visual identity. For the leading findings, propose concrete arrangements,
state the evidence for each finding, and explain how to verify the result.
Do not change code.
```

### Implement an adaptation

```text
Use $adaptive-composition to adapt this dashboard for smaller windows.
Keep comparison between records useful and preserve selection, filters,
focus, and drafts when the arrangement changes. Use the existing stack
and design system. Implement and verify the changes.
```

### Develop an adaptable visual direction

```text
Use $adaptive-composition to create a visual direction for this public
archive. It should feel meticulous but alive and must not resemble a
generic media app. Define the signature relationship and visual grammar,
then show how recognition survives spacious, constrained, and text-only
conditions. Do not invent cultural references or artwork.
```

### Design a streaming or agentic workflow

```text
Use $adaptive-composition to design this assistant from draft through
approval, external execution, partial failure, retry, and recovery. Keep
the actor, target, scope, provenance, and actual completion state clear.
Account for streamed updates without letting them move controls or steal
focus.
```

### Design a terminal interface

```text
Use $adaptive-composition to design this terminal interface for narrow
and wide terminals. Specify pane transitions, keyboard actions, focus,
and recovery after resize. Account for Unicode display width, short
terminals, disabled color, and unsaved work.
```

Give the agent the real task, representative content, supported environments, existing identity or assets, and relevant product boundaries. A focused request should remain focused.

## What a useful result contains

For substantial work, expect:

1. The task, supported conditions, and material assumptions.
2. The meaning, recognition, continuity, and—where relevant—agency invariants.
3. A concrete arrangement: order, grouping, visibility, disclosure routes, image treatment, and state transitions.
4. The failure condition that triggers a different composition, rather than an invented breakpoint.
5. Verification with equivalent content and state across constrained, intermediate, spacious, and non-ideal conditions in scope.
6. A clear boundary between observed behavior, source facts, design inference, product hypotheses, and untested checks.

A recommendation such as “improve hierarchy” is incomplete until it says which relationship changes and how to tell whether the change helped. A screenshot can establish appearance; it cannot establish keyboard behavior, state continuity, performance, assistive-technology behavior, or audience comprehension.

## Reference routing

The agent starts with [SKILL.md](SKILL.md) and reads only the references that can change the current decision.

| Need | Start here |
|---|---|
| Adapt an existing composition | [Composition method](references/composition.md) |
| Create a visual language | [Visual language](references/visual-language.md) |
| Review or test a design | [Evaluation](references/evaluation.md) |
| Implement for web or desktop GUI | [Web and GUI guidance](references/web-gui.md) |
| Implement a terminal interface | [Terminal guidance](references/tui.md) |
| Handle AI, agent actions, voice, handoff, wearables, or spatial work | [Dynamic systems](references/dynamic-systems.md) |
| Treat performance or resource cost as a design constraint | [Performance](references/performance.md) |
| Apply a concrete principle or study a worked transformation | [Principle cards](references/principles.md) and [worked examples](references/examples.md) |
| Select or verify a historical precedent | [Historical atlas](references/historical-atlas.md) and [source register](references/sources.md) |

History and the source register are not default context. They should be opened when a precedent materially changes a decision or a historical claim needs verification.

## Evidence and validation status

The skill is **not yet empirically validated**. The prompts in [evaluation](references/evaluation.md) are test fixtures, not records of completed tests.

The evaluation reference defines how to compare a baseline with the skill under the same model, settings, tools, and task. It includes:

- Public fixtures plus held-out-task requirements.
- Pass, partial, fail, and not-applicable judgments by outcome dimension.
- Critical failures such as removed capabilities, lost work, ambiguous approval, invented evidence, or unauthorized action.
- Recording for model and host versions, tools, output artifacts, reviewer judgments, tokens, wall time, and cost when available.

Published pass rates, cross-model portability, token cost, and user outcomes require completed runs. Following the skill does not prove accessibility, usability, recognition, comprehension, conversion, or environmental benefit.

## Research scope

The historical library surveys approximately 1966–2026, with earlier foundations where relevant. It is selective and remains weighted toward European and North American published design and HCI.

For culturally situated work, the skill directs research toward the product's actual languages, institutions, tools, vernacular forms, disability communities, living practitioners, and affected communities. It does not treat the supplied atlas as a universal canon or add a token example to imply global coverage.

The [source register](references/sources.md) distinguishes primary material, institutional records, publisher descriptions, current technical guidance, and this skill's own synthesis. A source beside a modern recommendation indicates lineage or support at the stated scope; it does not convert a proposal into measured evidence.

## Contributing

Issues and pull requests are welcome. The most useful contributions are:

- Reproducible evaluations showing where the skill helped, failed, or added unnecessary context.
- Sourced precedents from underrepresented practices and communities.
- Clearer medium-specific guidance grounded in current platform behavior.
- Corrections that replace a demonstrated failure with a generalizable decision rule.

For an evaluation, include the task, skill version, model and host, relevant conditions, expected behavior, actual output, reviewer judgment, and available token, time, or cost data. Do not submit invented test results, unsourced historical claims, or rules tuned only to one screenshot.
