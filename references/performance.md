# Performance as a composition constraint

Use this when load, interaction, streaming, asset weight, battery, thermal behavior, memory, or network cost could change what the interface should present or when it can present it. Performance is part of the experienced composition: late fonts reflow text, slow images erase identity, blocked input breaks operation, and background work can drain a wearable or overheat a device.

## Set a budget from the task and environment

Do not invent one universal payload or timing limit. Start with the project's measured baseline, supported devices and networks, critical tasks, and any existing service objectives. Define the smallest budget that can govern the design choice:

| Concern | Candidate measure | Composition decision it can constrain |
|---|---|---|
| Useful content | Time until the task's primary content is present and identifiable | Critical content order, placeholders, server rendering, font and hero-image strategy |
| Interaction | Response during the actual high-value interactions | JavaScript/work on the main thread, optimistic UI, control complexity, update batching |
| Stability | Unexpected movement during loading and live updates | Reserved geometry, insertion point, ad/media treatment, streaming layout |
| Transfer | Compressed bytes and request count by resource type and route | Image variants, font families/weights, video, third-party scripts, decorative assets |
| Compute and memory | CPU/GPU duration, memory pressure, long-running tasks | Visualization detail, animation, local inference, retained views, virtualization |
| Energy and thermal | Battery use, wakeups, sensor/radio use, device temperature where measurable | Polling, live effects, location/sensor sampling, model choice, background work |
| Resilience | Task behavior when offline, slow, interrupted, or storage-constrained | Caching, progressive disclosure, retry, draft preservation, fallbacks |

Specify the test condition next to the number: device or class, network profile, cache state, route/content, power mode, and measurement tool. A budget without conditions is difficult to reproduce. A lab profile supports regression testing; field data shows the distribution experienced by actual users. Use both when available and do not present one as the other.

For web work, current Core Web Vitals are useful shared field measures, not a complete product budget. The current guidance uses LCP, INP, and CLS, assessed at the 75th percentile; confirm the live source before encoding thresholds because the set evolves [S39]. Add task-specific measures for flows the generic metrics do not represent.

## Make priority visible in the delivery order

Compose the loading sequence as deliberately as the final screen:

1. Preserve meaningful structure, title, current state, and the route to the primary task.
2. Load the assets that establish recognition at an appropriate fidelity.
3. Enable the primary operation without waiting on supplementary analytics, media, or decoration.
4. Add secondary detail and enrichment without displacing work or stealing focus.

This is not a rule that text must always precede imagery. An artwork browser may need a recognizable image to become useful; a document editor may need the draft and controls first. State what “useful” means for the actual task.

Placeholders must preserve truthful expectations. A skeleton that looks like available data can mislead in operational contexts. Show stale, cached, partial, empty, and failed states distinctly. Keep dimensions stable where possible, but allow enlarged or localized text to reflow rather than trapping it in a reserved box.

## Budget visual identity deliberately

Treat each font, image, video, shader, animation, and third-party embed as a design choice with a resource cost.

- Prefer the smallest authorized image that remains fit for its rendered purpose; art direction and resolution selection solve different problems.
- Limit font files by roles actually used. Verify fallback metrics and reading order before relying on a late-loading face.
- Do not spend the constrained path's entire budget on an ornamental opening while the task waits.
- Preserve a characteristic cue in degraded conditions: typography role, color relationship, crop, mark, naming, or spatial rhythm.
- Respect reduced motion and reduced data or platform equivalents where supported, while providing an intentional fallback rather than an anonymous broken version.

A performance budget is a set of limits used to make product and design tradeoffs; older example byte counts are not timeless defaults [S44]. Establish project-specific limits and automate regression checks when the stack supports them.

## Handle live and generative work

For streaming, visualization, collaboration, or on-device inference:

- Batch visual updates enough to keep input responsive and assistive output comprehensible.
- Pause or reduce work when the result is not visible or no longer relevant, subject to task correctness.
- Avoid resorting, relayout, and full-region repaint on every event.
- Expose cancellation only when it actually stops or safely detaches the work.
- Preserve partial output without presenting it as complete; distinguish reconnection from regeneration.
- Measure end-to-end task response, not only model or server latency.

On battery- or thermally constrained hardware, test sustained use, not only a short happy path. Resource efficiency can support sustainability, but energy and carbon claims need their own measurement and scope. The W3C Web Sustainability Guidelines are current draft guidance, not a normative standard or proof of environmental benefit [S45].

## Verify a change without optimizing away the design

Compare equivalent content, cache state, device/network condition, and interaction sequence before and after. Record the distribution or repeated runs rather than selecting the best trace. Check:

- Did the primary task become available and responsive within its budget?
- Did recognition, reading order, image integrity, or comparison suffer to achieve the number?
- Did deferred work cause a later shift, focus loss, stale decision, or battery/thermal cost?
- Does the design remain useful on slow or interrupted paths, not merely show a branded loader?
- Did a third party, font, image, or new composition exceed the agreed resource limit?

If measurement tools are unavailable, provide a budget proposal and an explicit test plan. Do not claim a performance improvement from smaller source code, a visual impression, or a single uncontrolled run.
