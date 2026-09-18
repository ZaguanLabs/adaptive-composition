# A method for changing the composition

This method is a contemporary synthesis of the precedents in the [historical atlas](historical-atlas.md). It is not attributed to one historical designer.

## Describe the available surface

Think of a canvas as a set of conditions, not a rectangle alone.

| Condition | What to establish | Design consequence |
|---|---|---|
| Geometry | Usable width, height, aspect ratio, inset areas, panes, terminal rows/columns | Where simultaneous presentation stops working |
| Perception | Text size, contrast, distance, lighting, zoom, visual or auditory access | Effective detail and readable hierarchy |
| Input and output | Keyboard, mouse, touch, pen, voice, sound, haptics, assistive input; mixed use | Targets, focus, turn-taking, review, and alternatives |
| Content | Longest plausible text, actual language, item counts, missing media, live updates | Reflow, truncation, pagination, stable identity |
| Time, state, and agency | Loading, selection, editing, failure, stale data, interruption, approval, delegated or partial action | Feedback, accountability, and preservation across transitions |
| Environment and resources | Offline/slow links, terminal capabilities, embedded or split windows, compute, memory, battery, thermal limits | Progressive rendering, budgets, and graceful fallback |

Inspect relevant existing evidence; do not demand a comprehensive requirements workshop for a small change. Separate confirmed facts from assumed test cases.

## Classify content by responsibility

For each meaningful element decide whether it is:

- **Task-critical:** required to understand or perform the current task, including warnings and operands.
- **Contextual:** needed to orient, compare, or interpret; often important even when it is not actionable.
- **Supplementary:** useful detail that can move behind a clearly labeled access point.
- **Expressive:** supplies identity, tone, or narrative; may be central to an arts or discovery task.
- **Incidental:** redundant ornament or an implementation artifact.

These are local roles, not permanent rankings. Artwork may be central to album discovery and secondary during queue editing. A timestamp may be essential in an operations view. Do not infer the task from screen size.

## Choose a transformation for a stated reason

| Operation | Appropriate use | Failure to avoid |
|---|---|---|
| Scale | A simple mark, diagram, or image remains readable and recognizable | Shrinking body text, controls, or critical detail to preserve a screenshot |
| Reflow | Reading order stays meaningful with fewer columns or wrapped groups | Separating labels from values or producing an unintended focus order |
| Recompose | The same elements need different relationships or prominence | A different layout that silently changes the task or identity |
| Crop | Nonessential surroundings can be removed without changing the meaning | Losing part of a product, person, chart, document, or identifying artwork |
| Substitute | An authorized alternate asset, representation, or control communicates the same thing | Inventing unsupported data or a symbol users cannot interpret |
| Disclose | Supplementary detail has a clear, reachable access point | Hiding required warnings, comparisons, totals, or basic functionality |
| Sequence | Simultaneous panes cannot fit but can form a coherent journey | Losing selection, drafts, filters, or return context between views |
| Translate | The same meaning must move between visual, auditory, haptic, spatial, or textual presentation | Assuming every modality can carry the same detail or review path |
| Summarize | A truthful summary helps overview and original detail remains available | Unlabeled aggregation or claiming a partial result is complete |
| Omit | Material is truly incidental or its removal is explicitly in scope | Treating “less space” as permission to remove capabilities |

Combine operations as needed. Simple reflow is often enough. Recomposition is justified by a failure it solves, not by novelty.

## Derive transitions from content failure

Begin with representative content, legible text, usable controls, and realistic states. Reduce available width and height. Watch for:

- A title becoming excessively fragmented or obscuring its associated action.
- Controls colliding, compressing below useful targets, or losing labels.
- An image's meaningful subject becoming too small or badly cropped.
- A comparison requiring repeated horizontal and vertical hunting.
- An inspector consuming the remaining workspace.
- Sticky chrome taking most of a short viewport.
- Terminal headers and footers leaving no room for even one complete record.

Change the relationship at the failure. Record the reason for the threshold, then test just above and below it with enlarged text and longer strings. Component width often matters more than window width; height can require a separate decision. Use established project breakpoints where they already work; do not add arbitrary ones to sound more principled.

A spacious composition should gain useful context, comparison, or comfortable measure, not simply enlarge every element. A constrained composition should still expose the current task and its completion route.

## Evaluate the cost and purpose of scrolling

The opening viewport is one point in a reading or working sequence, not a container for every important element. Narrative pacing, artwork inspection, and long-form reading can justify generous imagery and deliberate scrolling. Do not shrink identity, text, or controls simply to fit more above the fold.

Identify the actual cost before changing the composition: an action whose location is unclear, repeated travel between comparison values, lost context, or persistent chrome that obstructs controls. Distinguish a task being reachable through an obvious route from all its content being simultaneously visible. For comparison work, establish which information needs to coexist; for sequential work, preserve a clear progression and return path.

Where shortening an opening is proposed, evaluate both task access and the expressive or explanatory role of what is reduced. Ordinary scrolling may already serve the task well. An element being below the first screen is an observation; the case for moving it requires a task consequence.

## Make a proposed composition implementable

For the most consequential changes, describe the arrangement rather than only its desired quality. A short prose sketch, wireframe, or adaptation table can specify:

- The reading/action order and which elements form a group.
- What remains immediately available and the labeled route to anything disclosed.
- Which image treatment and distinctive cues survive in each composition.
- What changes when space becomes insufficient, including intermediate and short conditions.
- Which state survives that change and how to check the intended benefit.

For example, “make the search opening more compact” becomes: “Keep the title and location/date controls together; place supplementary photography beside that group when both fit at readable sizes, and after the controls otherwise. Results follow the controls in reading order. Keep the same search values and focused control during the switch.” Whether search deserves this priority must come from the task or an explicit hypothesis.

If rendered measurements are unavailable, name the failure to measure: controls wrapping into confusing groups, the image crowding out the work area, or comparison fields becoming unreadable. Any numerical threshold is provisional until checked. Do not present imagined geometry as observed behavior.

Resolve a genuine tradeoff with a useful alternative when needed. A smaller image may improve access to controls but weaken recognition; preserving a distinctive crop or whole-object thumbnail could retain both. Do not generate multiple variants merely to fill a template.

## Treat transitions as stateful operations

For any layout switch, specify:

1. Which semantic object remains selected and which view now represents it.
2. Whether the focused control survives; if it disappears, where its logical equivalent receives focus.
3. How drafts, filters, queue order, playback, progress, and scroll context survive.
4. How a user returns to the previous context without repeating work.
5. How overlay, navigation, and browser/platform history interact.

For handoff, generated output, or agent actions, also preserve the action's semantic state: requested, proposed, awaiting approval, running, partially complete, completed, failed, or uncertain. Keep actor, target, scope, and material parameters attached to the action when they affect review or recovery. A layout or device transition must not become implicit approval.

Prefer keeping the same functional element and state owner when possible. If different renderers are required, share semantic state, keep inactive controls out of navigation/accessibility exposure, and deliberately transfer context. Avoid duplicate submissions and remount-triggered operations.

## Specify assets independently of layout

Record what may be cropped and what must remain whole. A square album cover can sit inside a portrait page; the page does not need a portrait version of the cover. Keep title and artist as accessible text outside the image. A thumbnail may identify the object while a separate detail view permits inspection.

For art-directed variants, specify subject, crop bounds or focal point, minimum useful detail, and any embedded text that would be lost. Different crops and different resolution files solve different problems [S25].

## Resolve competing principles

| Tension | Prefer this reasoning |
|---|---|
| Consistency versus adaptation | Preserve terms, semantics, and expected actions; vary arrangement where the constraint requires it |
| Whitespace versus density | Establish whether comparison requires simultaneous visibility or convenient inspection of one continuous set; retain the evidence needed for that task |
| Brand expression versus legibility | Keep expressive treatment where interpretation is welcome; keep operational information dependable |
| Simultaneous context versus sequencing | Keep concurrent views when comparison is necessary; otherwise sequence with stateful return |
| Clean screen versus discoverability | Make the next useful action visible; disclose secondary choices under meaningful labels |
| Animation versus continuity | Explain change without making motion necessary; respect reduced-motion preferences |
| Historical precedent versus current evidence | Use history to propose; let present task and audience evidence decide |

Deliver the smallest explanation that makes the choice reviewable. For a broad redesign, an adaptation table and representative states are useful. For a small control, a direct fix and focused verification are sufficient.
