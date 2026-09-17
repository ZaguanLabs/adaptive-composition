# Adaptive Composition

An agent skill for designing, implementing, and reviewing web, desktop GUI, and terminal interfaces using lessons from graphic, information, industrial, and interaction design.

**Preserve meaning, identity, and the ability to complete the task as conditions change. Recompose when necessary; scale when scaling works.**

Current skill version: **1.0.1**, recorded in [SKILL.md](SKILL.md).

## Why this exists

An LP sleeve and a cassette insert can represent the same album through different compositions. The artwork, typography, and information must work within different dimensions, physical structures, and reading conditions. Recognition depends on more than keeping every element in the same position.

Interface designers face related problems. A dashboard in a short window, an application with enlarged text, and a terminal reduced to fewer columns all require decisions about what stays together, what remains visible, and how people continue their work.

This skill brings historical approaches to those decisions: publication grids, identity systems, wayfinding, cartography, instrument controls, early graphical interfaces, and terminal interaction. It applies their reasoning without prescribing their period's appearance.

Responsive web design already includes adaptation. “Adaptive composition” names the emphasis of this skill: treating changing constraints as a composition problem, with identity and functionality considered together.

## When to use it

- A layout shrinks or stacks successfully but loses its hierarchy or character.
- Artwork overwhelms essential information, or cropping removes its meaning.
- A table, workspace, or navigation system becomes difficult to use in limited space.
- An interface needs to work across width, height, text size, language, or input constraints.
- You want a design review with concrete alternatives and checks tied to the user's task.

It also supports new designs. It supplies design reasoning and a working method; it does not require a particular framework, component library, or visual style.

## Install

### With the skills CLI

With Node.js and npm available, run this from the project where you want to use the skill:

```zsh
npx skills add ZaguanLabs/adaptive-composition --skill adaptive-composition
```

The CLI lets you choose your agent and installation scope. To install directly for Codex at user scope:

```zsh
npx skills add ZaguanLabs/adaptive-composition --skill adaptive-composition --agent codex --global
```

Update a CLI-managed installation with:

```zsh
npx skills update adaptive-composition
```

The [skills CLI documentation](https://skills.sh/docs/cli) explains installation and its default telemetry, which powers the public directory. Choose either the CLI or the Git checkout method below to manage an installation. Preserve any local customizations before installing over an existing copy.

### With Git for Codex

For a fresh user-level installation, clone this repository into your skills directory:

```zsh
mkdir -p ~/.agents/skills
git clone https://github.com/ZaguanLabs/adaptive-composition.git \
  ~/.agents/skills/adaptive-composition
```

The destination must not already contain an installation. If you have a manually copied or customized version, reconcile those files before replacing it.

Codex discovers user skills in `~/.agents/skills`. Invoke this one with `$adaptive-composition`; if it does not appear, restart Codex. These conventions are described in the [official skills documentation](https://developers.openai.com/codex/skills).

To update an installation made with the clone command:

```zsh
git -C ~/.agents/skills/adaptive-composition pull --ff-only
```

The repository contains instructions and reference material; there is no build step or runtime dependency to install. Rendering, browser inspection, and implementation checks depend on the tools available to your agent.

For another agent that supports directory-based skills, use that host's installation instructions and keep `SKILL.md`, `references/`, and their relative paths together. The `agents/openai.yaml` file provides Codex interface metadata.

## Example prompts

### Review an existing interface

```text
Use $adaptive-composition to review this interface at constrained,
intermediate, and spacious sizes, including a short window. Preserve its
visual identity. For the leading findings, propose concrete arrangements
and explain how to verify them. Distinguish observations from hypotheses.
Do not change code.
```

### Implement an adaptation

```text
Use $adaptive-composition to adapt this dashboard for smaller windows.
Keep comparison between records useful and preserve selection, filters,
and drafts when the arrangement changes. Use the existing stack and
design system. Implement and verify the changes.
```

### Design a terminal interface

```text
Use $adaptive-composition to design this terminal interface for narrow
and wide terminals. Specify pane transitions, keyboard actions, focus,
and recovery after resize. Account for Unicode display width and a
terminal without color.
```

Give the agent the task, existing design, supported environments, and any product boundaries you already know. A focused component fix should remain focused; invoking the skill does not require a full redesign.

## What it asks the agent to preserve

| Invariant | What must survive a change in composition |
|---|---|
| Meaning and task | Content relationships, required actions, comparison criteria, units, warnings, and truthful state |
| Recognition | Names, distinctive imagery, typographic roles, tone, and approved identity cues |
| Continuity | Selection, drafts, focus, navigation history, scroll context, and ongoing work |

The arrangement can change to support those invariants. A poster can remain whole with event details beside or below it. A dense comparison view can retain aligned fields instead of becoming disconnected cards. A terminal workspace can move between adjacent panes and sequential views while keeping the selected object and a clear return route.

Transitions should follow actual failures in the content and task. Width alone does not establish touch input, expertise, or a need for fewer capabilities.

## What a useful result looks like

For substantial work, expect the agent to establish the task and constraints, identify what must survive, and select relevant precedents. Recommendations should explain element order, grouping, visibility, access to disclosed content, and the condition that triggers a different arrangement.

Verification should include real content, intermediate and short viewports, non-ideal states, and continuity through transitions. A review should identify what was observed, what the source establishes, what is inferred, and what needs testing. Scrolling is judged by its effect on the task; appearing below the opening viewport is not itself a defect.

The scope remains yours: a review produces proposals, while an implementation request authorizes changes within the requested scope.

## Repository guide

The agent starts with `SKILL.md` and reads relevant references as needed.

| File | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Entry point, workflow, scope, and guardrails |
| [Historical atlas](references/historical-atlas.md) | Historical problems, precedents, transferable ideas, and limits |
| [Principle cards](references/principles.md) | Practical decisions and failure checks |
| [Composition method](references/composition.md) | Constraints, transformations, transitions, and tradeoffs |
| [Web and GUI guidance](references/web-gui.md) | Semantics, layout, imagery, typography, and platform behavior |
| [Terminal guidance](references/tui.md) | Character cells, keyboard interaction, resize, and terminal capabilities |
| [Worked examples](references/examples.md) | Concrete adaptations and counterexamples |
| [Evaluation](references/evaluation.md) | Evidence, reproducible reviews, task checks, and regression prompts |
| [Source register](references/sources.md) | Annotated sources, attribution, and research limits |
| [Codex metadata](agents/openai.yaml) | Display name, description, and suggested invocation |

## Research scope and contributions

The library surveys roughly 1966–2026, with earlier foundations where relevant. It is selective, with a substantial European and North American emphasis. The source register distinguishes original material from retrospective accounts and publisher descriptions; it does not imply that every referenced book was read in full.

Historical precedents provide useful hypotheses. Their age or reputation does not establish usability, accessibility, or suitability for a current audience. The worked examples are illustrative exercises, and following the skill does not replace testing the actual interface.

Issues and pull requests are welcome. Useful contributions include sourced precedents from underrepresented traditions, clearer medium-specific guidance, and evaluations showing where the skill helped or failed. Include the task, relevant conditions, expected behavior, actual result, and evidence available. Generalize the lesson so it remains useful beyond one product.
