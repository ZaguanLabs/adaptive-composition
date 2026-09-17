# Applying the principles to terminal interfaces

A TUI has a different material: character cells, terminal capabilities, keyboard commands, a cursor, and a repainting protocol. Preserve semantic relationships and work, then choose a presentation suitable for that material. Text alone does not establish accessibility.

## Cell geometry is a design constraint

Plan in **columns × rows** and reserve room for actionable content. Budget titles, headers, prompts, and status lines before assigning pane sizes. Test both dimensions; an extremely wide but short terminal can still be unusable.

Use measured terminal display width, not bytes, code points, or string length. Combining sequences, wide characters, emoji, and ambiguous-width characters require the framework's appropriate measurement and grapheme-aware clipping. Unicode's East Asian Width property is not a complete terminal-width algorithm [S32]. Strip or parse styling sequences before measuring visible content.

Prefer text labels and ordinary separators that work with the target terminal. Box drawing can help grouping but is not mandatory. Offer an ASCII-compatible treatment when the supported environment needs it. Do not use wide emoji as the sole meaning-bearing status marker.

## Compose in useful modes

The sizes below are **test examples**, not standards or default support promises:

| Example surface | Possible composition | Required behavior |
|---|---|---|
| 160 × 48 | List and detail pane, with visible status and help hint | Pane focus and selected object are clear |
| 100 × 30 | Compact list plus limited detail or an optional inspector | Comparison fields and units remain readable |
| 80 × 24 | Main list; detail opens separately | Selection and return position survive |
| 40 × 12 | Focused single-record flow, if the product can support it | Essential controls and exit route stay reachable |
| Smaller than supported minimum | Bounded explanation and usable escape/cancel route | No crash, state loss, invalid window sizes, or uncontrolled repaint loop |

Derive actual thresholds from labels, record widths, and task requirements. Never silently drop critical columns. If simultaneous comparison cannot fit, provide a deliberate comparison route or clearly state the supported constraint. Do not promise arbitrary tiny-terminal operability.

Specify what happens to unsaved work below the minimum. Preserve the draft while waiting for resize and use the application's actual confirmation or recovery mechanism for exit. If neither a safe confirmation nor recovery is available at that size, report the limitation; do not promise immediate exit without data loss. Resize itself must never discard or commit the draft.

## Keyboard grammar and visible state

Define the operations and their scopes before choosing keys. Follow the application's established conventions. Use standard navigation and discoverable command labels where practical; do not impose Vim keys on every audience.

Distinguish:

- **Focus:** which pane or control receives input.
- **Selection:** which object an operation will act on.
- **Mode:** navigation, searching, editing, command entry, or confirmation.
- **Pending change:** edited data not yet committed.

Keep these states legible without color alone. A reverse highlight plus explicit selection marker or status label can help, subject to terminal behavior. A help view should explain active bindings and how to leave; a short visible hint provides a route to it.

Single-letter commands should not fire while the user types in a search or input field. Cancel a local mode before triggering a broader destructive action. Preserve established meanings of Enter, Escape, Tab, and interrupt keys unless there is a strong, disclosed reason to differ. Avoid intercepting terminal and assistive-technology shortcuts unnecessarily.

## Resize without losing work

Use the toolkit's resize handling and perform layout/repaint work in its normal event path. For ncurses, understand its `SIGWINCH`/`KEY_RESIZE` behavior and the need to update complex windows; do not assume every pad resizes automatically [S33]. Do not perform allocation and complex rendering directly in a raw signal handler.

On resize:

1. Re-measure the available cells and choose a valid composition.
2. Keep semantic selection, draft input, filter, and active operation.
3. Keep the selected item visible where possible; clamp scroll positions safely.
4. Restore a clear focus location if a pane became a separate view.
5. Repaint without stale borders, out-of-bounds windows, or repeated side effects.

Resize must not confirm, submit, restart, or cancel an operation merely because the view changed. Test while editing and while live data changes, including repeated shrink/grow cycles.

## Color, capabilities, and output

Respect available terminal capabilities and explicit user preferences. Do not assume true color, a dark background, mouse reporting, Unicode box drawing, or particular function keys. A theme that works on one emulator may fail in another.

`NO_COLOR` is an informal convention: when present and nonempty it requests suppression of added ANSI color by default, with explicit configuration/arguments handled according to that convention. It does not itself require removing all other attributes or establish an accessibility mode [S34]. Check the framework's behavior and the application's chosen preference precedence.

If the application exposes textual/noninteractive output, keep data output separate from progress and diagnostics and do not leak cursor movement into redirected records. Detect relevant streams rather than treating all stdin/stdout/stderr combinations as one state. Do not add a full CLI/export subsystem to a small TUI task unless needed or requested.

When rich terminal interaction is unavailable, select a documented fallback or explain the limitation. Restore terminal modes and cursor on ordinary exit and handled interruption; acknowledge that uncatchable termination cannot run cleanup.

## Time, redraw, and accessibility

Repaint only as necessary for truthful state. Rapid full-screen redraw can disrupt reading, selection, scrollback, remote sessions, and assistive technology. Permit users to inspect an item without constant reordering underneath them. Show timestamps or freshness when it affects interpretation.

Some screen readers work better with sequential text than cursor-addressed layouts. Where in scope, provide an explicit linear or reduced-update mode, preserve accessible textual names, and test the actual terminal/screen-reader combination. A fallback is useful but does not prove that the primary interface is accessible.

## A useful TUI acceptance task

With a service selected, enter a filter containing non-ASCII text, open details, begin editing an allowed value, and resize narrower then wider. Verify that the same service and draft remain selected, keys act only in the correct mode, help and exit are reachable, and error/status meaning survives disabled color. Repeat with missing data and an unusually long identifier. Report any environment not actually tested.
