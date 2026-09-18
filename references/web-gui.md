# Applying the principles to web and desktop GUI

Use this reference for the surfaces actually requested. The implementation choices below are contemporary applications of the historical principles, not claims that print designers prescribed CSS or native widgets.

## Structure before surface

Identify content objects and operations: album and track; document and selection; service and health state; product and price. Preserve their relationships in semantic HTML or the native toolkit's accessibility tree.

Prefer ordinary controls with known behavior. Styling a label to resemble a button does not supply its role, keyboard behavior, or state. Custom widgets need their complete interaction contract; consult the applicable toolkit or WAI-ARIA pattern [S24]. Do not add ARIA merely because the design is visually sophisticated.

For web layouts, keep logical source order meaningful. CSS placement that looks correct can still create confusing sequential reading and keyboard focus. When a content relationship truly changes, choose markup and focus handling intentionally. Avoid separate mobile and desktop trees with divergent content or state unless necessary.

For native GUI, preserve platform roles, menu conventions, focus behavior, shortcuts, and accessibility integration. Familiarity is specific to a platform and audience; a shared brand does not require identical widget mechanics everywhere.

## Build layouts from useful relationships

- Let prose have a comfortable bounded measure. Extra width can support context or deliberate margins.
- Use intrinsic wrapping and layout constraints for ordinary variation; introduce composition changes when a relationship fails.
- Use a container size query when the component's available space drives the change. A large window can contain a narrow panel [S26].
- Derive page-level changes from relevant viewport conditions. Width is not the only constraint; short viewports and on-screen keyboards can make persistent bars obstructive.
- Preserve existing framework/toolkit facilities instead of recreating layout systems without need. GNOME's adaptive guidance is one contemporary example of changing panes and controls while preserving functionality [S36].

An album summary might move from image-beside-text to image-above-text. Its play action still targets the same album, and an ongoing track does not restart. That is a composition change with a behavioral invariant.

## Art direction and content

Choose image treatment explicitly: whole object, focal crop, alternate composition, or decorative texture. An object image and a page background need not use the same rule.

In HTML, resolution variants selected through `srcset` address resource size; `<picture>` with appropriate sources can provide different compositions. Neither mechanism automatically chooses a good crop [S25]. Keep artist/title, prices, and other required text in the document, even when visible in artwork. Alternative text should describe the image's function in context, not duplicate every adjacent word.

Give fallback behavior equal care: missing image, failed webfont, long title, no results, unknown status, and slow content. Reserve space where it prevents disruptive movement, but do not trap enlarged text in a fixed-height box.

When asset weight, font loading, script work, or live updates can delay the task or destabilize the layout, set project-specific conditions and measures with [performance guidance](performance.md). Do not import example byte limits as universal requirements.

## Typography and writing systems

Use text roles with room to grow; avoid a global scale that makes every label smaller in compact mode. Distinguish reading text from compact but legible metadata. Numeric values used for comparison benefit from alignment and clear units.

Test text enlargement and spacing overrides, actual fallback fonts, translations, bidirectional text, and line breaking appropriate to the script [S27]. Use logical directional properties where applicable. Mirroring a directional arrow is not the same decision as mirroring a playback symbol or product image. Do not truncate critical identifiers into identical strings; provide wrapping or a reliable full-value route.

## Accessibility checks with the correct scope

WCAG 2.2 is the reference baseline in this skill, not a claim about a project's legal obligations or the latest future standard. Confirm the target standard when a project specifies conformance [S22]. The following are selected checks, not the whole standard:

| Concern | What to check |
|---|---|
| Reflow | Ordinary vertically scrolling content remains usable at 320 CSS pixels wide; equivalently test a 1280 CSS-pixel starting viewport at 400% zoom. Two-dimensional-content exceptions are limited to the relevant content, not the whole page [S23] |
| Horizontally scrolling content | For content designed to scroll horizontally, reflow uses a height equivalent to 256 CSS pixels; do not translate this into a universal minimum viewport [S23] |
| Pointer targets | SC 2.5.8 uses 24 × 24 CSS pixels or specified exceptions, including spacing. Treat this as a minimum criterion, not an ideal touch-target prescription [S37] |
| Reading and operation | Meaningful sequence, keyboard access, visible/unobscured focus, accessible names and state, color-independent meaning, and recoverable errors [S22, S24] |
| User settings | Enlargement, text spacing, contrast preferences, and reduced motion do not break task completion; test rather than assuming a CSS preference query is sufficient |

Use the normative standard and relevant understanding pages for exact requirements and exceptions. Do not claim native GUI or terminal conformance just by applying CSS-pixel rules.

## Data and operational interfaces

Choose a representation for the decision. Preserve table semantics and row/column relationships when comparison is central. If a table genuinely requires two-dimensional layout, an accessible bounded scrolling region may be appropriate; communicate its presence and keep the surrounding page reflowable.

Before turning a table into cards, identify the comparisons lost. Alternatives include user-chosen columns, pinned identity columns, filtering, a dedicated compare mode, or a summary plus full table. Do not remove risk, units, freshness, or provenance to reduce visual clutter.

Live updates should not steal focus, silently change the selected row's identity, or reshuffle targets under the pointer. Use stable object identifiers. Convey stale/disconnected state separately from a measured healthy result. Preserve meaningful status text if color is removed.

For streaming generated content, approvals, or external actions, use the state and recovery model in [dynamic systems](dynamic-systems.md). Batch programmatic announcements around meaningful changes rather than exposing every token as a new status message.

## Native application transitions

A spacious app can show navigation, a collection, and an inspector together. A narrower window may sequence them. Keep selection, drafts, undo scope, and return position stable. Test tiling and resize while editing, not just after reopening.

Retain access to commands when menus or toolbars overflow. Do not put the only route to an operation in hover content or an unlabeled glyph. A menu can supply discoverability while shortcuts support experts. Where multiple documents or windows exist, make the active document and command target unambiguous.

## Verification proportional to the change

For a local typography fix, inspect the affected component with long text and enlargement. For cross-format changes, exercise a main task through relevant widths, heights, input methods, and states. Check transitions, not only endpoints. Record actual results separately from planned tests; do not invent screenshots, screen-reader checks, or user-study evidence.
