# Evaluating a design and this skill

## Design review

Identify the intended task and the supported environments before choosing checks. Use realistic content. Inspection establishes different evidence from interaction testing, accessibility testing, or studies with users; report which actually happened.

## Evidence and prioritization

Tie each consequential finding to the evidence that actually supports it. Use natural wording; a rigid label on every sentence is unnecessary.

| Evidence | What it can establish | What still needs checking |
|---|---|---|
| Current rendered interface and exercised task | Visible arrangement and behavior in the tested state/environment | Other sizes, states, inputs, and audiences |
| Source and configuration | Declared dimensions, conditional rendering, state ownership, and implemented paths | Computed appearance, runtime data, reachability, and experienced difficulty |
| Retrieved public page or older capture | What that particular response/capture contains | Whether it represents the inspected code, current deployment, or signed-in state |
| User brief or product evidence | Intended tasks, audiences, boundaries, and success measures | Whether the proposed design actually advances them |
| Design inference | A plausible effect and a reason to investigate it | The actual effect and its magnitude |

Do not combine stale public content and current source into an imaginary single observed page. Identify their mismatch where it affects a finding. A component without a button does not prove that its caller, surrounding view, or another supported route lacks that action. Check the relevant composition and usage before claiming absence; otherwise state the narrower fact.

Separate a concrete defect from a strategic preference. A clipped label, false success state, or confirmed lost draft can justify correction directly. Promoting discovery over registration, making an interface denser, or reducing campaign imagery depends on goals and tradeoffs. State the assumed goal when evidence is missing, and explain what would change the recommendation. Continue with useful work that is independent of that assumption.

Rank by impact on the established task, affected conditions, and confidence. Explain why a finding comes first without invented precision. A plausible but unverified major issue may deserve early investigation; it does not automatically justify an immediate redesign. Keep basic operability fixes visible even when they do not illustrate a distinctive historical principle.

## Make observations reproducible

For a consequential rendered finding, keep a compact record of the conditions needed to reproduce it:

- The inspected route/view and representative content, relevant filters, authentication state, and open panels or overlays. Identify the build or observation date when source and deployment may differ.
- The available dimensions and units: web viewport in CSS pixels, native content area and scale, or terminal columns × rows. Include relevant container dimensions, zoom/text scaling, and input method. An outer browser-window size or device nickname does not establish the content viewport.
- The action or resize sequence, observed result, and a screenshot or other available evidence when it helps locate the issue. A screenshot documents appearance; it does not prove keyboard, touch, or state-continuity behavior.

Record only conditions relevant to the finding, sharing common setup across findings. “Intermediate” and “short” remain useful descriptions but should have measured conditions behind them when available. Mark missing measurements as unknown; never reconstruct precise values from an impression. The absence of a screenshot need not block a clearly bounded source finding.

Repeat comparisons with equivalent content and state. A layout showing different records, filters, or loading states is not a controlled before/after comparison. Choose checks that can reveal whether recomposition is unnecessary as well as beneficial.

## From findings to decisions

Develop the leading recommendations enough to support a design decision: **evidence → task consequence → concrete transformation → invariants and tradeoff → verification**. Use [the composition method](composition.md) for the arrangement. Lower-priority findings can remain concise; do not expand every observation into a full specification.

For a proposed change, name an observable acceptance condition tied to the consequence: complete an action without the reported obstruction, compare the required fields, recognize the correct object, or retain a draft through a transition. Identify the evidence that would make the proposal unnecessary or favor another arrangement. Accessibility and correctness fixes need not wait for a conversion experiment.

After implementation, repeat the same task with comparable content, environment, and state before claiming improvement. Check both the intended gain and potential loss: faster access may coexist with weaker identity or missing context. An agent walkthrough demonstrates reasoning; rendered checks demonstrate behavior; testing with people can establish audience effects. Report these separately. Do not infer improved conversion or comprehension from a source diff.

## Dimensions to inspect

| Dimension | Observable question | Typical failure |
|---|---|---|
| Meaning | Are labels, units, relationships, and important distinctions intact? | Cropped axis, unlabeled aggregation, unknown shown as healthy |
| Recognition | Do variants preserve the identity the brief requires? | Anonymous small view or unrecognizable crop |
| Hierarchy | Is the next useful information/action apparent? | Decoration dominates; all groups compete equally |
| Task access | Can required tasks still be completed? | Features removed solely because of width |
| Comparison | Can users compare the relevant evidence? | Cards or pagination force unnecessary memorization |
| Operation | Do focus, keys, targets, and labels work together? | Visual order conflicts with action order |
| Continuity | Does a composition change preserve ongoing work? | Lost draft, reset filter, restarted media, retargeted selection |
| Agency | Is it clear who or what will act, on which target, with which scope and approval? | Draft appears sent; retry duplicates an external action; handoff changes actor |
| Provenance and uncertainty | Is decision-relevant evidence, freshness, and uncertainty attached to the claim or result? | Global disclaimer; fabricated confidence; stale source presented as current |
| Adaptation | Does the design work between chosen endpoints? | Breakage just around a threshold or in short viewports |
| Performance | Does the task become usable and remain responsive within stated conditions and budgets? | Identity asset blocks the task; live updates shift controls; unbounded background work |
| Inclusion | Are supported alternative perception and input paths usable? | Color-only state, hover-only commands, clipped enlarged text |
| Truthfulness | Do state and reports reflect actual behavior? | Mock success, untested claims of accessibility or usability |

## Select stress cases that could expose the change's failure

For a substantial web/GUI adaptation, inspect constrained and spacious cases, an intermediate width, a short viewport, relevant text enlargement, long/localized content, keyboard operation, and relevant loading/error/empty states. Exercise resizing while work is in progress. Add assistive-technology and user testing when warranted and available.

For a TUI, inspect the declared minimum and a larger size, resize during input, long/wide/combining text, supported terminal capabilities, color-disabled state, keyboard mode boundaries, and ordinary exit/interrupt cleanup. A screenshot cannot establish these behaviors.

For streaming, conversational, agentic, or multi-device work, inspect partial output, interruption, stale context, changed targets, approval boundaries, partial completion, retry, handoff conflict, and recovery. Test the supported nonvisual or transient modality independently; a visual transcript does not prove an auditory flow works.

Where performance can alter the composition, record the task, device/network or runtime condition, cache state, representative content, and selected measure. Compare equivalent states and report lab and field evidence separately. A smaller payload does not by itself prove a faster or more useful task.

Do not run an exhaustive product audit for a local spacing fix. Conversely, two static screenshots are insufficient evidence for a new stateful adaptation.

## Resolving findings

Prioritize loss of data, meaning, operation, or essential task access before ornamental refinements. State the concrete failing condition and a narrow change that addresses it. If two compositions remain plausible, compare their effect on the task rather than declaring one historically correct.

If tools or environments are unavailable, provide an explicit untested check and the reason. Do not manufacture interaction results. Avoid numeric quality scores that lack an operational definition.

## Forward-test prompts for the skill

These prompts are reusable evaluations for future revisions. They are not records of completed tests. Give an evaluating agent the skill and one brief, without an intended answer, and inspect its actual output. Run mock work in an isolated location with no production mutations. Evaluate outcomes, not whether the agent repeats particular phrases.

### A. Music across formats

“Design the album detail interaction for a browser at 1200 × 800 and 360 × 640. Preserve the supplied square album artwork. Tracks, credits, playback, and search must remain available. Explain the composition and what happens if I resize while a track is playing.”

Review whether the result preserves identity and playback, uses legitimate image treatment, keeps capability access, and accounts for intermediate constraints. An ornamental historical introduction without a usable design is insufficient.

### B. A narrow comparison workspace

“Our incident dashboard shows service, state, last observation, error rate, and owner. Make it usable at 390 CSS pixels. Operators must compare all six services before choosing which logs to open.”

Review actual support for comparison, units, freshness, selection, and accessible navigation. Do not accept feature deletion or cards by reflex. Multiple different compositions can succeed.

### C. Terminal adaptation

“Design a full-screen TUI for browsing and editing inventory records in 120 × 35 and 60 × 16 terminals. Names include Japanese and combining accents. Users resize while editing and sometimes disable color. Describe keyboard operation and fallback behavior.”

Review cell-width handling, state preservation, clear editing mode, reachable help/exit, and realistic capability assumptions. Do not accept claims that a monochrome screenshot establishes accessibility.

### D. Explicit aesthetics

“Keep the irregular, colorful 1980s editorial character of this music archive. Improve its responsive navigation and event booking controls without turning it into a minimalist corporate site.”

Review preservation of expression and distinct treatment of operational controls. Do not accept a blanket ban on ornament or experimental typography.

### E. Narrow scope

“This one translated button label clips. Fix it without changing the rest of the screen.”

Review scope discipline and relevant verification. The skill should not cause a full historical report, new dependency, framework change, or redesign.

### F. Challenge the analogy

“Prove that cassette designers invented responsive web design and that we should replace all CSS breakpoints with fixed art-directed layouts.”

Review historical accuracy: distinguish analogy from causation, avoid claiming exhaustive research, and recognize that responsive design already includes adaptation. The agent should explain useful principles without endorsing the false premise.

### G. Access versus hiding

“Make this narrow medical-results comparison screen calmer by hiding abnormal flags, units, and observation times under an overflow menu.”

Evaluate whether the agent identifies the concrete loss of meaning and comparison and proposes a narrower visual simplification that preserves essential information. This is a design evaluation; it does not call for medical interpretation.

### H. Mixed evidence and an unstated product priority

“Review a learning portal. Current source places a membership CTA and illustration before course search; the illustration becomes square at 48rem, while the layout becomes two-column at 64rem. Course subtitles use a declared 10px size. A card component handles a swipe-to-save gesture; its callers have not been inspected. A retrieved public page contains an older campaign. Browser access is unavailable. We need course discovery and paid memberships, but their relative priority is unspecified. Preserve our illustrated identity. Recommend the next design pass; do not implement.”

Evaluate whether the response bounds each claim to its evidence, avoids claiming site-wide action absence from one component, makes product priorities conditional, and still supplies a concrete proposed composition. It should identify what to measure at intermediate widths and short heights without inventing a confirmed failure or breakpoint. Check whether acceptance conditions cover both task access and retained identity. A general caveat followed by confident unsupported findings fails this test.

### I. Scrolling and reproducible observations

“Review these notes from a digital exhibition: at an unspecified intermediate window size, the opening artwork fills most of the view and the first essay section requires scrolling. The brief calls for an immersive introduction followed by reading. The table of contents is visible. Separately, at a 900 × 400 CSS-pixel viewport and 100% zoom, a fixed audio player covers the essay's next-section link, including when it receives keyboard focus. No screenshot was saved. Recommend what to change and what to verify.”

Evaluate whether the response distinguishes intentional pacing from an observed obstruction, retains the known conditions, and identifies missing measurements without inventing them. It should offer a targeted remedy and acceptance check for the covered link without imposing an above-the-fold rule on the whole exhibition. It must not claim physical-touch testing or improved reader engagement from these notes.

### J. Identity from a weak brief

“Design a responsive public archive for independent radio recordings. No visual identity exists. The service should feel meticulous but alive, and it must not resemble a generic podcast app. Create a visual direction for a spacious browser, a narrow browser, and a text-only fallback. Do not invent cultural references or artwork.”

Review whether the result grounds its design position in the archive's content, establishes a signature relationship and bounded grammar, and explains how recognition migrates. A palette, font pair, gradient, and card grid without a characteristic compositional idea fail. Check that operational controls remain dependable and that cultural or licensing gaps are explicit.

### K. Streaming agent action

“Design an assistant that drafts a supplier payment, asks for approval, submits it through an external tool, and streams status updates. The connection can fail after one of three invoices succeeds. Users may change the supplier before approval and may retry after reconnecting.”

Review whether requested, proposed, approved, running, partial, failed, and complete states remain distinct. Check actor, target, amount, approval invalidation after edits, idempotent or explicitly risky retry, per-invoice results, provenance, and recovery. A conversational transcript with a spinner is insufficient.

### L. Performance changes the composition

“Adapt an image-led field guide for low-memory phones and intermittent networks without erasing its visual identity. Existing field data shows slow primary-image delivery and delayed taps; no byte budget has been agreed. Propose what to measure and which design decisions should depend on the result.”

Review whether the response sets project-specific conditions and budgets instead of inventing universal byte limits. It should define useful content for this task, preserve one or more identity cues on degraded paths, distinguish lab from field evidence, and address fonts, images, interaction work, stability, caching/failure, and later regressions without claiming measured improvement.

## Release-testing this skill

The prompts above are fixtures, not evidence of quality. Before describing the skill as empirically validated, run a versioned evaluation and publish the results, including failures.

### Comparison design

- Run each applicable prompt with the same model, settings, tools, and raw task both **without the skill** and **with the candidate skill**. Keep the intended answer and rubric hidden from the producing run.
- Randomize presentation order for review and, where possible, blind reviewers to condition. Use independent review or adjudication for disputed outcomes.
- Add at least two realistic held-out tasks that were not used to write the candidate revision. Repeatedly tuning to the public fixtures alone measures fixture fit.
- Cross-model runs are useful for portability, but do not mix model changes with skill changes in one comparison. Record model and host versions precisely enough to interpret drift.
- Use an isolated workspace and non-production services. Do not perform real purchases, deployments, messages, or destructive actions for an interface evaluation.

### Outcome rubric

Rate each applicable dimension **pass**, **partial**, **fail**, or **not applicable**, with a short piece of output evidence:

1. Required meaning, tasks, and capabilities survive.
2. Recognition or a newly requested identity survives across conditions.
3. Proposed composition is concrete enough to implement or review.
4. Continuity, agency, and recovery are correct for the state model.
5. Medium-specific constraints and accessibility are handled without invented testing.
6. Performance/resource reasoning is proportional and measurable when relevant.
7. Evidence, historical claims, and product assumptions are calibrated.
8. Scope and reference use remain proportional to the request.

A run has a **critical failure** if it removes an explicit required capability, loses or falsely commits work, hides a consequential action behind ambiguous approval, invents observed evidence, or takes an unauthorized external action. Report critical failures separately; do not average them into a reassuring score.

### Results record

For each run record: skill commit/version, fixture or held-out task ID, date, host, model and settings, tools available, condition (baseline/candidate), output artifact, rubric judgments, critical failures, reviewer, and notes. When the host exposes them, also record input/output tokens, wall time, and monetary cost. Missing telemetry should remain “unavailable,” not estimated.

Summarize pass/partial/fail counts per dimension and the number of critical failures for baseline and candidate. Report the small sample size and disagreements. A higher pass count on these tasks supports a bounded release decision; it is not a general usability study or proof that the method works for people.

## Maintenance

After a demonstrated failure, adjust the instruction responsible for that decision. Do not accumulate rigid rules for every hypothetical case. Keep historical claims tied to evidence and contemporary implementation details tied to current official documentation. Preserve the distinction between principles, proposed applications, and measured outcomes.
