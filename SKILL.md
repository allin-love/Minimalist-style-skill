---
name: minimalist-style
description: "Design, refactor, or review professional GUIs, desktop workbenches, and interface mockups, especially for instrumentation, scientific acquisition, and data analysis. Remove redundant information and tiny gray text; unify typography, visual hierarchy, and control layout while preserving readability and operational efficiency. Use for practical professional software, rather than marketing landing pages or decorative showcase interfaces."
---

# Professional Minimalist GUI

Help users read data, find controls, and understand state quickly. Organize the interface around high task information density and low visual noise. Preserve the user's approved functionality, interactions, and design system; do not remove capabilities or change behavior merely to achieve visual consistency.

## Visual Direction

- Simplify information selection, typography, and task flows. Prioritize what users need now and remove repeated explanations and decoration.
- Achieve compactness through grouping, alignment, and consistent spacing. Leave enough separation between channels, control rows, and action groups.
- Give screen area and visual attention to the primary work: waveforms, images, tables, editing content, or experiment state.
- Avoid promotional headings, oversized KPI cards, excessive empty space, decorative gradients, repeated icons, and slogans. Enlarge metrics only when the task justifies it.
- When referencing ChatGPT, adopt restrained color, clear typography, subtle boundaries, and consistent controls. Do not copy its chat layout into a professional workbench.

## Remove Information Before Styling

Evaluate each piece of text: does it provide unique information, support a decision, or enable a necessary action? Remove content without a clear purpose.

| Information | Default treatment |
| --- | --- |
| Current target, primary data, essential parameters, main actions | Show directly and keep clearly readable |
| Connection, battery, RSSI, packet loss, and other supporting status | Use concise, ordinary-sized text in an appropriate location; increase emphasis when the task or an abnormal condition requires it |
| Link details, diagnostic counters, raw readbacks | Put behind a clearly accessible details or diagnostics entry |
| Restatements of headings, obvious control explanations, repeated status messages | Remove |
| Error causes, units, unsaved changes, overwrite scope, necessary limits | Keep in context; do not demote them to illegible fine print |

Apply these rules:

- Give each state one primary display location within a working context. Repeat it only when spatial separation or task needs justify duplication.
- Use short nouns for headings and clear verbs for buttons. Include the target when needed to distinguish actions.
- Remove formulaic headings such as "Acquisition Settings - Adjust your parameters" or "Device Panel - Everything at a glance." Put necessary explanations near the relevant controls and show them when useful.
- Do not attach a line of small gray helper text to every card, group, or input.
- When a value already has a unit, do not add another line restating its meaning.
- Distinguish states with different meanings: preview versus recording, sent versus applied, write acknowledgement versus measured output.
- Do not hide essential instructions entirely in tooltips, icons, or menus. Ordinary users should be able to complete the main task directly.
- Keep normal states quiet. For errors, give an understandable cause and a useful next step instead of a generic "Operation failed."

## Typography and Formatting

Define a small set of text roles and reuse them across pages. Do not choose font size, weight, gray level, or line height independently for each widget.

| Role | Optional desktop starting point | Purpose |
| --- | --- | --- |
| Body, labels, values, buttons, chart axes | 14 px, Regular | Default reading and operation |
| Group headings | 14-16 px, Medium | Limited hierarchy |
| Page title or brand | 16-18 px, Medium | Use when needed |
| Secondary information | Prefer body size with moderately reduced emphasis | Remain easy to read |

Adapt these starting points to the existing application, target device, and scaling requirements:

- Use one primary font family with consistent multilingual fallbacks. Verify actual Regular and Medium faces; avoid accidentally rendering Thin or Light.
- Build hierarchy mainly through position, grouping, spacing, and limited weight changes. Avoid scattered bold text, large numbers, and arbitrary colors.
- Do not combine small size with low contrast to weaken information. Retained content must be readable; unnecessary content should be removed.
- Battery, RSSI, and packet loss usually do not need oversized bold values. Adjust emphasis for dedicated monitoring or alarm workflows.
- Keep equivalent roles consistent across languages. Shorten long labels, adjust width, or wrap sensibly instead of shrinking one language's text.
- Standardize precision, time formats, capitalization, units, label alignment, and decimal places across pages.
- Do not expose internal variable names, debug fields, or implementation terminology as user-facing labels.

## Color and Controls

- Reuse semantic tokens. If missing, define a small set for background, surfaces, borders, primary text, secondary text, accent, and status.
- One main accent is usually enough. Use consistent treatments for primary actions, selection, and focus; do not make every button an accent button.
- Secondary text must retain sufficient contrast. Do not make values, axes, units, or primary labels faint for a supposedly sophisticated appearance.
- Give colors clear roles. Charts can use distinct channel colors; keep each object's color consistent across pages.
- Do not rely on color alone for state. Add concise text or symbols where needed.
- Standardize control heights, corner radii, borders, and icon sizes. Avoid mixing conspicuous native arrows with unrelated custom decoration.
- A 4/8/12/16 px spacing system and 32 px input height are useful starting points, subject to application and platform needs.
- Optional LOTUS dark reference: background #121212, sidebar #1E1E1E, content surface #19171F, primary text #E0E0E0, purple accent #BB86FC. Other applications do not need this palette.
- Preserve hierarchy and readability in both light and dark themes; do not simply invert colors.

## Layout and Control Ownership

- Concentrate primary controls in a stable area. Group them in task order so one operation does not require searching multiple corners.
- Place controls near their scope: batch gain belongs in the gain section, STFT channel selection belongs beside its chart, and save paths belong in recording settings.
- Make targets explicit in multi-device interfaces. Visual consolidation must preserve independent drafts, states, and parameters.
- Let single-device mode use the available space; keep a comparable structure in multi-device mode. Avoid empty panels occupying half the workspace.
- Keep the target data visible while adjusting it. Prefer inline, docked, or push layouts over drawers that cover the waveform being tuned.
- Keep frequent actions easy to reach. Distinguish primary and secondary actions through position and styling. Reserve room for fixed footer actions.
- Show scrollbars only when scrolling is needed. Leave clearance beside them so they do not cover the last column. Clicking, focusing, or sending a command must not pan the entire control panel horizontally.
- Resolve redundant content, grouping, column widths, and scrolling before reducing overall text size. Apply bounded UI scaling afterward.
- At low resolutions and high DPI, essential labels, values, units, and buttons must remain visible without overlapping charts or controls.

## Charts and State Feedback

- Preserve axes, units, legends or channel labels, and separation in scientific plots. Distinct colors do not replace numerical calibration.
- Separate display scale from acquisition gain. Do not normalize, clip, fabricate samples, or conceal anomalies to make data look attractive.
- Keep idle, running, recording lock, unapplied, applying, disconnected, and failed states clear and visually stable.
- Distinguish disabled controls from available ones. Usable buttons must not resemble faint explanatory text.
- Do not add confirmation to ordinary parameter edits. For consequential copying or overwriting of independent configurations, use a concise confirmation identifying source, targets, and consequences.
- Derive preview and recording rules from actual product behavior. Allowing preview adjustments while locking recording parameters is an experimental-software example, not a universal rule.
- Prevent unrelated layout shifts, lost focus, and obvious interaction pauses. Do not repeatedly rebuild tables, whole-window styling, or chart layouts just to update a short status.
- Average FPS and low packet loss do not prove smooth presentation. Investigate long frames and event timing in the actual window when traces pause and then jump.

## Common Corrections

| Problem | Correction |
| --- | --- |
| "Acquisition Settings - Adjust sample rate, gain, and filters" | Use "Acquisition Settings"; let grouping and labels explain the contents |
| "Connected" and the full device name repeated in several corners | Consolidate status in the device or connection area; retain target labels only where needed |
| Battery, RSSI, and loss dominate the waveforms | Use compact status in ordinary-sized text; emphasize abnormal conditions |
| Every button has a small gray explanation below it | Remove obvious explanations; retain context for real ambiguity or limitations |
| Global settings contain "01 / CH2" and "02 / CH2" | Move each channel selector to its own STFT heading and show an identifiable channel name |
| Batch Gain is far below the gain controls | Put batch actions inside the gain section; keep apply actions and their scope in the footer |
| A settings drawer hides the data being adjusted | Use docking, inline expansion, or a push layout that keeps the target visible |

## Workflow and Delivery

Inspect the existing pages, styling, and user tasks first. Identify the most important data, actions, and exceptional states. Compose existing components, unify tokens, and add only missing elements. A color and radius refresh alone does not resolve redundant information or scattered controls.

When the user requests design before implementation, deliver a reviewable design first. Once approved, continue implementation without repeatedly asking for permission. Use Figma tools and workflows only when the task involves Figma; this skill has no mandatory Figma dependency. If a tool is unavailable, report that accurately instead of claiming synchronization.

Inspect actual rendered output. Cover relevant normal, expanded-settings, unapplied or disabled, long-label, and small-window states. For multi-device products, also check single-device mode. Prioritize these questions:

- Are there repeated subtitles, explanatory suffixes, or clusters of tiny gray text?
- Are font, weight, color, line height, and numeric formats consistent within each role?
- Is primary data clear, with supporting metrics receiving appropriate emphasis?
- Are settings easy to find, with explicit targets and action scope?
- Do scrollbars, focus changes, language switching, or expanded panels cause clipping, overlap, or layout shifts?
- Are necessary units, error causes, and meaningful state differences preserved?

Fix issues within the requested scope and report actual validation results and any untested areas. Deliver only necessary designs, code, and a concise explanation. Keep test screenshots and intermediate artifacts in temporary storage and clean them up afterward. Do not create multiple repetitive reports for one interface change.
