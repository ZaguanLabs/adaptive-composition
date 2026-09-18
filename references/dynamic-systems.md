# Composing dynamic, distributed, and probabilistic systems

Use this for interfaces whose important conditions are not only rectangular: conversational or voice interaction, streaming or generative output, delegated actions, multi-device handoff, glanceable wearables, spatial computing, or combinations of them. Consult current official platform and assistive-technology guidance for implementation details.

## Model the changing condition

Establish which dimensions actually vary:

| Condition | Questions that change the composition |
|---|---|
| Modality | Is information seen, heard, spoken, typed, touched, or felt? Can the user review it, or does it pass in time? |
| Attention | Is this a focused workspace, an interruption, a glance, a hands-free moment, or a shared/public setting? |
| Location and device | Which surface starts the task, which can complete it, and what context is available or private on each? |
| System certainty | Is output deterministic, retrieved, inferred, generated, stale, partial, or contested? What evidence affects reliance? |
| Agency | Is the system describing, proposing, drafting, simulating, or taking an external action? Who authorized which scope? |
| Time | Does content stream, wait on a tool, expire, update live, or continue in the background? Can it be paused or resumed? |
| Embodiment | What can be occluded, overheard, out of reach, motion-inducing, unsafe, or physically tiring? |

Do not infer reduced intent from a watch, voice request, or narrow surface. A surface can expose a useful slice and a continuation route without pretending to contain the whole task.

## Preserve an action ledger

For generated or agentic work, distinguish states that conventional loading indicators often collapse:

1. **Requested:** the person expressed an intent; the system has not committed an external effect.
2. **Interpreted:** the system shows the target, scope, constraints, or assumptions it derived when these matter.
3. **Proposed or drafted:** output can still be reviewed and changed.
4. **Awaiting approval:** the exact consequential action, recipient or target, material parameters, and reversibility are visible.
5. **Running:** progress is truthful; cancellation and side effects are described accurately.
6. **Completed, partially completed, failed, or uncertain:** results identify what actually changed and what did not.

The interface need not expose this vocabulary verbatim. Its state model must not visually present a proposal as a completed act or a queued action as safely undone. Ask for confirmation based on consequence and ambiguity, not as ritual before every operation. Never label a compensating action “undo” unless it restores the relevant prior state.

Keep an inspectable history for consequential actions when the product requires accountability. Show the actor, target, material inputs, time, result, and available recovery at the level the user needs; do not expose sensitive internal traces merely to appear transparent. NIST's Generative AI Profile treats human oversight, source verification, provenance, override, incident response, and recovery as risk-management concerns; it does not prescribe one interface pattern [S41].

## Design streaming output as a changing document

Reserve a stable place for output so arrival does not repeatedly displace controls or the user's reading position. Preserve selection and text the person is copying or editing. New content should not steal focus or force scrolling when the person has moved elsewhere.

Distinguish:

- **Transport progress:** connected, waiting, receiving, interrupted, or retrying.
- **Semantic completeness:** a heading, answer, code block, result set, or citation may be incomplete even while bytes arrive.
- **Verification state:** generated, grounded in named sources, checked by a tool or person, disputed, or unknown.

Offer stop, continue, retry, or edit only when the system can honor them. If a retry may duplicate an external effect, resolve idempotency or make the risk explicit. Batch assistive announcements around meaningful changes; do not turn every token into a live-region interruption. W3C guidance warns that excessive live updates can become too chatty and distinguishes progress/status messages from focus-changing content [S40].

## Represent uncertainty and provenance where decisions happen

Attach evidence and uncertainty to the claim, recommendation, or action they qualify. A global “AI can make mistakes” footer cannot explain which source supports a number or which step remains uncertain.

- Show source identity, retrieval time, scope, and transformation where these affect trust.
- Make citations inspectable and preserve the route back after opening them.
- Separate absence of evidence from a negative result, and model disagreement rather than averaging it away.
- Use calibrated language or bounded ranges when supported; do not invent percentages to decorate uncertainty.
- In high-consequence contexts, provide a review or escalation path appropriate to the domain. Do not imply that human approval automatically makes a result safe.

## Translate across conversation and voice

Conversation is a sequence with memory, repair, and turn ownership—not a narrow visual chat log. Keep the current subject, constraints, and unresolved question apparent. Let people correct a single operand without restating the whole request. Preserve prior turns needed to understand a result, while making retention and privacy clear.

For auditory output, put the decision or result before optional detail, use language that stands without a screen, and provide a visual or textual review route when exact values, spelling, citations, or multiple options matter. Avoid long spoken menus; ask a discriminating follow-up or continue on a richer surface. Account for interruption, misrecognition, shared spaces, and the possibility that the action begins on one device and finishes on another. Current Siri guidance likewise calls for responses that work audibly and visually and warns against misleading device-specific wording [S43]; apply platform rules only to that platform.

## Design handoff as a state transfer

State what transfers and what deliberately does not:

- Semantic object, draft, selection, playback/progress, filters, permissions, and action status.
- Identity of the account, workspace, device, or actor that will receive the task.
- Freshness and conflict behavior if both surfaces continue changing the same object.
- Private content that must remain concealed until the receiving surface is authenticated or explicitly chosen.
- A return path when the other surface is unavailable, declines the handoff, or completes only part of the task.

Do not use visual sameness as proof of continuity. The receiving device should use its native input and layout conventions while preserving the task and recognizable terminology.

## Treat wearables and spatial interfaces as different materials

A glanceable surface favors one timely, discriminable state and a clear next action; it is not merely a tiny phone screen. Preserve access to the full task through a deliberate continuation route. Test wake/sleep, notification age, privacy near others, motion, one-handed or hands-busy use, and loss of connectivity.

Spatial composition adds depth, field of view, reach, occlusion, anchoring, and physical comfort. Keep system controls and real-world hazards unobstructed. Avoid making essential operation depend on precise gaze, a large gesture, a particular hand, or depth perception alone. Test seated and standing conditions and relevant accessibility settings. Apple platform guidance is one current example of adapting to safe areas, text size, input, watch surfaces, and spatial bounds [S42]; it is not a universal geometry standard.

## Verification scenarios

Choose only those relevant to the product:

- Interrupt a streamed response, navigate away, return, and establish whether it resumes, restarts, or remains explicitly partial.
- Change the target after an agent has prepared an action but before approval; confirm the proposed effect updates and no stale action executes.
- Lose connectivity after a subset of actions succeeds; show exactly what changed and provide safe recovery.
- Begin on one device and continue on another while the source device also changes; verify conflict and privacy behavior.
- Perform the voice flow without looking at a screen, then review exact values and provenance visually.
- Use the wearable or spatial flow with relevant accessibility settings, interruptions, and alternate inputs.

Report simulated states as simulations. Do not claim real tool execution, handoff, assistive-technology behavior, or recovery unless it was exercised.
