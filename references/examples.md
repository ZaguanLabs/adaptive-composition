# Worked examples

These are invented design exercises, not historical artifacts, tested products, or evidence that a particular album release used a particular adaptation. Sizes are illustrative. Apply only the surfaces in the actual request.

## 1. Album identity: square packaging to a music interface

**Brief:** a music collection presents albums, tracks, credits, and playback. The album has square artwork and a long title. Users need to recognize it, play a chosen track, and inspect credits on both spacious and constrained screens.

**Historical connection:** packaging and series design preserve recognizable elements across different contexts [S01, S03, S16]. The front of a cassette package is only one surface; the folded insert, spine, and back provide other information locations. That suggests considering presentation and access together, not cutting everything into one rectangle.

**Invariants:** album/artist identity, correct track order, explicit playback state, track access, credits access, and continuity of playback. The artwork's aspect ratio and integrity matter because it is the object being recognized.

| Element | Spacious screen | Constrained screen | Why |
|---|---|---|---|
| Cover | Whole square beside album information | Whole square at a useful size, paired with text; need not fill screen width | Recognition without sacrificing all initial space to art |
| Title and artist | Beside cover in distinct typographic roles | Wrap above or beside a smaller cover according to measured fit | Preserve hierarchy without shrinking text |
| Playback | Clearly labeled controls near album/track state | Same operations in a compact, reachable group | Preserve task and truthful state |
| Track list | Aligned titles and durations; additional useful columns | Titles and duration remain related; supplementary metadata available in details | Keep selection and order clear |
| Credits | Adjacent section or panel if useful | Labeled disclosure or page with stable return | Access survives even if not simultaneously visible |
| Ongoing session | Stable player state | Same player state through resize/navigation | Layout change is not a new playback command |

Do not force the album image into a portrait crop just because the viewport is portrait. If a decorative campaign image needs different artwork, use approved variants and keep it distinct from the actual album object.

**A terminal version, only if requested:** artist/title text identifies the album, the selected track has a visible marker, and playback state is textual. Album art can be optional capability-dependent enrichment. Match terms and operations, not the web's image geometry.

**Counterexample:** scaling the whole page to 60% technically fits but reduces type and targets. Another failure is keeping the artwork enormous and hiding tracks under several screens of ornament. The opposite failure is deleting all identity and presenting an anonymous list despite an explicit discovery-oriented brief.

**Check:** choose track 8, open credits, return, resize, and confirm playback did not restart and selection remains correct. Test a missing cover and a long album title. Recognition testing with actual listeners would be additional evidence, not implied by this walkthrough.

## 2. Operations dashboard: preserve comparison

**Brief:** an operator must compare six services, identify stale observations, and open the relevant logs. The same task is required in a desktop window, a narrow web view, or a TUI if those surfaces are in scope.

**Historical connection:** information graphics supply comparative alignment; control interfaces supply status/command distinctions; wayfinding supplies current location [S05, S09–S12].

**Invariants:** service identity, health label, freshness, units, access to logs, active filters, and action target. “Unknown” must remain different from “healthy.”

Spacious layout: aligned table with a selected-service inspector. Narrow layout: keep the compact comparison table or an intentionally scoped scrollable table with clear headers and identity; move logs/detail into a separate view with return state. If a summary is useful, include the observation time and route to underlying records.

TUI: allocate cells to identity, state, and age before secondary metrics. Show the currently selected service in the detail heading. Use the toolkit's display-width measurement for names. Preserve service selection by stable ID rather than its changing row number.

**Counterexample:** replacing each row with a large card requiring repeated scrolling makes relative age and failures harder to compare. Hiding the timestamp can turn stale green into misleading reassurance. Automatic sorting during a click can make a command target the wrong service.

**Check:** answer “Which unhealthy service has the oldest observation?” in each composition. Filter to two services, open logs, return, and resize. Verify that state updates do not steal focus or retarget an operation. No real service action is authorized by this exercise.

## 3. Editorial reading: keep the argument intact

**Brief:** an illustrated essay includes headings, quotations, a data figure, notes, and related reading. It must work in a wide browser and with enlarged text in a narrow window.

**Historical connection:** editorial grids coordinate text and supporting matter, while Unigrid permits content-specific composition [S02, S08].

Spacious layout: a bounded reading column with notes alongside relevant passages where useful. Narrow layout: notes follow their references or use accessible links/disclosure with a return route; supporting material does not interrupt a sentence. A figure keeps its caption and units. If its full complexity cannot fit, provide an inspectable view and a useful textual account.

**Counterexample:** moving all illustrations to the top changes the argument's sequence. Making a two-column page into a single image preserves its appearance while destroying reflow, selection, and semantic reading order.

**Check:** read headings and paragraphs in source/accessibility order; follow and return from a note; enlarge text; inspect the figure. Test a long citation and missing illustration. Keep the reading experience useful without the preferred font.

## 4. Expressive cultural site: preserve the requested character

**Brief:** a punk archive should retain collage, irregular display lettering, and a DIY visual voice while exposing searchable records and ticketed events clearly.

**Historical connection:** punk graphics and Emigre show that expression and legibility have been contested, contextual design questions [S15, S28]. They do not establish that all text should be irregular.

Keep collage and expressive lettering in artwork, display headings, and selected transitions. Use clear labels for search, filters, dates, prices, availability, and purchase controls. Maintain contrast and focus visibility. A constrained view can simplify the surrounding collage while retaining a distinctive fragment and typographic role.

**Counterexample:** converting the entire site to neutral monochrome cards violates the brief. Setting every form label as ransom-note lettering treats all content as if it had the same purpose.

**Check:** compare whether identity survives, then separately perform search and event selection by keyboard and touch where supported. Respect reduced motion. Verify that changing composition does not change prices, options, or access.

## 5. A deliberately small change

**Brief:** a toolbar label clips when translated; keep the existing app style and behavior.

Use the principles locally: allow an appropriate wrap or flexible width, adjust spacing if necessary, preserve command grouping, and test the long label with keyboard focus and enlarged text. Load only the relevant typography and surface guidance. A historical essay, new navigation scheme, or fresh design system would expand the task without benefit.

## 6. A source-based review with competing goals

**Brief:** a fictional exhibition site serves ticket buyers and members. Its current source stacks a campaign title, membership CTA, illustration, and date selection until a wide breakpoint. A middle breakpoint makes the illustration square. A public capture is older than the source, and the current interface cannot be rendered. The client wants both attendance and memberships and has not ranked them.

**Evidence and consequence:** the breakpoint sequence is a source fact. A large square illustration could delay access to date selection in the stacked composition, but actual displacement and difficulty are unverified. The older capture cannot prove the current geometry. “Move membership below ticket discovery” is a product hypothesis, not a conclusion established by the CSS.

**A concrete conditional proposal:** if choosing an exhibition date is the opening task, group the campaign title, date selector, and ticket action before supporting imagery. Keep a labeled membership action in that group with secondary emphasis. At spacious sizes, place the illustration beside the group; when their useful widths no longer fit, sequence the illustration after it. Retain the campaign's distinctive lettering and authorized image. Give a complete-poster image a whole-object treatment; a decorative illustration can use an approved crop. Keep selected dates and keyboard focus stable through recomposition.

If the opening is explicitly a membership campaign, retain its primary CTA and give date selection a clear adjacent route. A readable date control and appropriate image treatment remain valuable under either priority. Choosing a primary task does not authorize removing the other capability.

**Historical reasoning:** publication systems separate common identity from each composition [S01, S08]. That connection supports retaining the campaign's recognizable cues while moving its illustration. It does not decide the site's commercial priority.

**Verification:** inspect the actual interface through the interval between the two existing breakpoints, with long exhibition titles and a short viewport. Establish whether artwork obstructs the intended opening task; choose any new threshold from that failure. Compare the current and proposed layouts using the same date-selection task and content. Check that controls remain readable, the correct exhibition remains recognizable, membership access survives, and date/focus state is retained. If the present layout already supports these outcomes, the case for recomposition is weaker. Do not claim better ticket sales or membership conversion from these checks alone.
