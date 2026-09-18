# Principles as decisions

These cards are the skill author's synthesis. Historical sources support their lineage; suggested implementations and tests are present-day applications, not quotations or claims of experimental validation. Source IDs refer to [sources](sources.md).

## 1. Identity is a family of relationships

**Lineage:** Marber's book series, Gerstner's programmes, IBM identity, NPS Unigrid [S01–S04, S08].

Define the minimum recognizable cues and their relationships. A title's typographic role, characteristic image, and repeated naming may survive while every element changes position. In a text terminal, verbal identity and terminology may carry more than a logo.

When there is no useful identity to preserve, use the [visual-language method](visual-language.md) to establish a product-specific position, signature relationship, and bounded grammar before deriving variants.

**Do:** maintain a small vocabulary of roles and valid variants; allow content to determine composition.

**Avoid:** treating a screenshot as the identity specification, or assuming a brand color alone supplies recognition.

**Check:** compare variants without their surrounding application chrome. Can users identify the same object and distinguish neighboring objects? Validate with people when recognition matters; an agent's judgment is preliminary.

## 2. Hierarchy allocates attention to the task

**Lineage:** editorial grids, public signs, information graphics [S02, S05, S07–S09].

Choose the first useful recognition, decision, and action. Use size, contrast, position, whitespace, wording, and grouping together. A large heading is not useful hierarchy when it pushes the required action out of a short window.

**Do:** place exceptions where operators compare status; keep captions and units beside their referents; let exploration pages emphasize discovery.

**Avoid:** promoting every section equally or treating a sales page's focal hierarchy as suitable for a data workspace.

**Check:** describe the expected reading/action sequence, then inspect whether the actual composition supports it.

## 3. Grouping makes semantic structure visible

**Lineage:** grids, control organization, consistent objects and commands [S02, S10, S12].

Use proximity, alignment, enclosure, repetition, and whitespace to communicate real relationships. Familiar perceptual grouping concepts are diagnostic tools; they do not establish one universal layout.

**Do:** make spacing within a group smaller than separation between unrelated groups where that helps reading. Preserve label-value, command-target, and legend-data relationships during reflow.

**Avoid:** equal gaps everywhere, cards around every fragment, and decorative borders that imply false grouping.

**Check:** remove color and ornament. If relationships disappear, strengthen wording or structure.

## 4. Grids are coordination rules

**Lineage:** Müller-Brockmann and Unigrid [S02, S08].

Choose tracks from content roles and useful reading widths, not a compulsory twelve-column template. Shared alignment makes repetition economical and variation legible. A deliberate span or break should explain priority.

**Do:** align comparable values; bound prose width while allowing tables to use available space.

**Avoid:** preserving empty columns on a narrow window or stretching prose across an ultrawide monitor.

**Check:** identify what each grid constraint accomplishes. Remove constraints whose only purpose is resemblance to a reference image.

## 5. Typography changes with use and reproduction

**Lineage:** publication typography, optical identity corrections, experimental legibility debates [S01, S04, S15].

Distinguish display text, reading text, labels, values, and controls. Give each role appropriate measure, spacing, contrast, and emphasis. Glyph size, stroke weight, x-height, viewing distance, language, and rendering affect the result; matching point sizes is insufficient.

**Do:** proof the actual font with actual language and long content. Allow wrapping and text resizing. Use tabular figures where numerical comparison benefits.

**Avoid:** indiscriminate all-caps paragraphs, essential text only inside artwork, forced tracking in joining scripts, and shrinking labels until they fit.

**Check:** read at intended size and zoom, with fallback fonts and representative non-Latin text. Latin line-length heuristics are starting points for Latin prose, not global laws [S27].

## 6. Image treatment preserves meaning

**Lineage:** music packaging and coordinated publication imagery [S01, S08, S16].

Decide whether an image is evidence, an identifiable object, a mood, or decoration. Cropping an ornamental photograph differs from cropping an album cover, chart axis, or person important to the story.

**Do:** preserve the whole object when identity depends on it; use a separate authorized crop when the focal subject survives. Recompose adjacent text independently.

**Avoid:** cover-cropping every image, distorting aspect ratio, or generating an alleged historical variant that never existed.

**Check:** inspect every crop and its information. Higher resolution alone does not rescue unreadable composition.

## 7. Navigation is wayfinding with memory

**Lineage:** road signs, Olympic systems, information exploration [S05–S07, S17].

At decision points expose location, destinations, and consequences. Keep signs near the choices they explain. Use stable terms across navigation, headings, results, and history.

**Do:** preserve selection and filters when a sidebar becomes a separate screen; restore context on return.

**Avoid:** unknown icon-only navigation, hiding the current section in a menu, or assuming pictograms transcend language and culture.

**Check:** enter a deep link, navigate elsewhere, then return. Can users locate themselves and recover prior work?

## 8. Density serves comparison and work

**Lineage:** Bertin, Tufte, information exploration [S09, S11, S17].

Distinguish information density from crowding. Aligned observations may be easier to understand than a sparse sequence that forces memory-based comparison. Preserve units, scale, baseline, time range, uncertainty, and missing-data distinctions.

**Do:** retain comparable rows and shared axes; disclose supplementary detail. Label aggregation and changes of representation.

**Avoid:** converting every row to a card, dropping dimensions, silently changing scales, or stripping context simply to look clean.

**Check:** ask an actual comparison question at each size. If answering requires remembering values across screens, redesign or supply a dedicated comparison route.

## 9. Action and feedback complete the composition

**Lineage:** industrial design, Xerox Star, Shneiderman, Norman [S10, S12–S14].

Explain what can be done, what is selected, what is happening, and what happened. These are temporal as well as spatial relationships. Use signifiers appropriate to the medium; a visible cue is not the action capability itself.

**Do:** provide control labels, truthful progress, recognizable focus, completion, and recovery. Distinguish focus from selection where both exist.

**Avoid:** specifying only a beautiful default screen, or communicating feedback solely through transient motion.

**Check:** exercise loading, empty, edited, disabled, failure, interruption, retry, and cancellation states as applicable. Confirm success means actual completion.

For generated output or delegated action, distinguish requested, proposed, awaiting approval, running, partially complete, completed, failed, and uncertain states as applicable. Read [dynamic systems](dynamic-systems.md) rather than treating a conversational transcript as the whole interaction.

## 10. Efficiency includes effort and recovery

**Lineage:** pointing research, command systems, human factors [S10, S12, S19, S20].

Judge effort in the relevant mode: pointer travel, keyboard steps, visual search, context changes, and error recovery. Fewer clicks alone do not establish a better workflow.

**Do:** provide platform shortcuts and alternatives to dragging; enable efficient repeated work without making novices memorize commands. Keep undo truthful about its scope.

**Avoid:** applying a pointing-time model to reading comprehension, inventing universal timing thresholds, or hiding all controls behind gestures.

**Check:** repeat a frequent task with supported inputs; examine mistakes and recovery as well as successful traversal.

Include delayed input, slow delivery, and sustained resource use where they change effort. Use [performance guidance](performance.md) for task-specific budgets; a fast animation or small source diff is not evidence of a responsive workflow.

## 11. Inclusion is a design input

**Lineage:** universal design and accessibility standards [S21–S24, S27].

Account for variable perception, motor ability, language, expertise, and equipment. Consistent semantics can survive visually different presentations.

**Do:** preserve essential meaning without color, motion, hover, or a particular font. Use assistive-technology checks where possible.

**Avoid:** equating monochrome with accessibility, terminal text with screen-reader compatibility, or heritage with universal comprehension.

**Check:** test relevant alternatives and report limitations. A checklist does not prove every user can complete the task.

## 12. Expression and clarity can occupy different layers

**Lineage:** music graphics, punk, Emigre, Cooper's digital experiments [S15, S16, S28, S29].

Distinctiveness can carry culture, emotion, and invitation. Retain the brief's expressive purpose while making operational text and controls dependable. Interpretive challenge can belong in artwork; it usually does not belong in an error message or purchase total.

**Do:** identify where experimentation serves the experience and where immediate comprehension is required.

**Avoid:** homogenizing cultural interfaces in the name of clarity, or excusing unusable navigation in the name of expression.

**Check:** evaluate expressive content and the operational layer against their respective purposes.
