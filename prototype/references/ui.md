# UI prototype

Use variants when layout, hierarchy, interaction, or visual direction cannot be settled in prose.

1. Default to three variants and cap at five. Make them structurally different in layout, information hierarchy, density, and primary action, not merely color or copy changes.
2. Prefer the real surrounding page when its navigation, data density, or shell materially affects the decision. Keep data read-only and gate the full prototype from production.
3. Otherwise use an isolated prototype route or workspace that follows the host framework's conventions. If no UI runtime exists, use the lowest-dependency local browser surface already available, such as a single static HTML file, and document its run command.
4. Make variants switchable from one stable URL or compact control. Preserve the selected variant across reloads when the framework makes that cheap.
5. Reuse the project's components and tokens where they are part of the constraint, but let each variant own its layout.
6. Keep controls keyboard-accessible and avoid intercepting shortcuts while an input or editable element has focus.
7. Verify every variant in the browser at representative widths. Capture screenshots or URLs when they materially help the verdict.
8. Record which parts won and why. Remove losing variants and the switcher from production work; rebuild the chosen direction with normal tests and error handling.
