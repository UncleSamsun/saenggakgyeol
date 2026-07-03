# Design System — 생각결

Status: Brand/Design System v1
Date: 2026-07-03
Product decision base: D14 Product-Core MVP approved

## Product Context

- **What this is:** 생각결 is a session-based Mac capture app that restores the time context behind notes. It connects typed note chunks with nearby transcript chunks so the user can understand why a thought appeared.
- **Who it is for:** First Minjoun, then builders and operators who think through meetings, solo sessions, and product work in long-form notes.
- **Space:** Mac productivity, AI notes, meeting memory, Obsidian-first personal knowledge workflows.
- **Project type:** Native macOS app with a GitHub Pages documentation and portfolio surface.
- **Memorable thing:** 조용한 맥락 복원. It should feel like serious software that gives a thought its surrounding time back.

## Aesthetic Direction

- **Direction:** Quiet Native Workspace.
- **Decoration level:** Intentional. Use fine lines, measured whitespace, timestamp rhythm, and evidence blocks. Avoid decorative blobs, generic AI gradients, and playful note-app metaphors.
- **Mood:** Calm, precise, and private. The product should look like it belongs on a Mac menu bar and can sit beside Obsidian without trying to become another workspace.
- **Reference read:** Cleft owns voice-first capture; Granola owns meeting notepad energy; Notion owns workspace memory. 생각결 should own timestamped personal context restoration.

## Brand

- **Name:** 생각결.
- **English descriptor:** Time-context capture for Mac.
- **Korean descriptor:** 메모와 transcript를 시간순으로 맞춰 생각의 맥락을 복원하는 Mac 앱.
- **Logo concept:** 결/시간선 심볼. Two quiet timelines represent note chunks and transcript chunks. The crossings and nodes show the moment context is recovered.
- **Do not use:** Microphones, brains, chat bubbles, sparkle AI marks, generic notebook icons.
- **Voice:** Korean-first, calm, exact, not hype-driven.

## Typography

- **Display/brand:** Gowun Batang. Use for the product name, page hero, and memorable Korean phrases. It gives 생각결 a quieter Korean identity than a default system sans.
- **Body/UI docs:** IBM Plex Sans KR. Use for documentation, labels, and long explanatory copy.
- **Data/time:** IBM Plex Mono. Use for timestamps, offsets, IDs, chunk ranges, and evidence references.
- **Native controls:** SF Pro / system fonts are allowed inside macOS controls, but the sizing, spacing, and semantic colors below still apply.
- **Loading:** Use Google Fonts in web docs. For the app, prefer bundled or system fallback until packaging is decided.

### Type Scale

| Token | Size | Line height | Use |
| --- | ---: | ---: | --- |
| `--sg-type-hero` | 64px | 1.04 | Docs hero, portfolio hero |
| `--sg-type-title` | 34px | 1.16 | Page title, main panel title |
| `--sg-type-section` | 24px | 1.25 | Section headings |
| `--sg-type-body` | 16px | 1.65 | Body copy and docs |
| `--sg-type-ui` | 14px | 1.45 | App labels, toolbar text |
| `--sg-type-caption` | 12px | 1.35 | Meta, timestamps, helper text |
| `--sg-type-mono` | 13px | 1.45 | Time ranges, IDs, transcript offsets |

## Color

- **Approach:** Restrained, with color carrying meaning.
- **Primary:** `#155E52`. Use for active session, primary action, logo stroke, selected tabs.
- **Context Blue:** `#355C9A`. Use for transcript context, evidence links, and secondary action.
- **Warm Signal:** `#B45F3A`. Use for decisions, warnings, and human-authored note emphasis.
- **Focus:** `#F4C95D`. Use sparingly for active capture state and keyboard focus glow.

### Core Tokens

| Token | Hex | Usage |
| --- | --- | --- |
| `--sg-color-ink` | `#1E2320` | Primary text |
| `--sg-color-muted` | `#68736D` | Secondary text |
| `--sg-color-canvas` | `#F8F9F6` | App/document background |
| `--sg-color-surface` | `#FFFFFF` | Panels, editor surfaces |
| `--sg-color-surface-soft` | `#EEF3EF` | Subtle grouped surfaces |
| `--sg-color-line` | `#D7DED9` | Dividers and control borders |
| `--sg-color-primary` | `#155E52` | Primary brand/action |
| `--sg-color-context` | `#355C9A` | Transcript/evidence context |
| `--sg-color-signal` | `#B45F3A` | Decisions/warnings |
| `--sg-color-focus` | `#F4C95D` | Active capture/focus |
| `--sg-color-success` | `#2F7D54` | Completed processing |
| `--sg-color-warning` | `#B7791F` | Recoverable issue |
| `--sg-color-error` | `#B4473F` | Failed processing |
| `--sg-color-info` | `#355C9A` | Informational state |

### Dark Mode

- Redesign surfaces instead of only inverting colors.
- Use `#151A17` for background, `#1D2420` for surfaces, and reduce accent saturation by 10-20%.
- Keep timestamp/evidence contrast high. Context recovery is the product spine.

## Spacing

- **Base unit:** 4px.
- **Density:** Comfortable-compact. The editor must hold long sessions without feeling cramped.

| Token | Value | Use |
| --- | ---: | --- |
| `--sg-space-2xs` | 2px | Hairline offsets, tight icon alignment |
| `--sg-space-xs` | 4px | Inline gaps |
| `--sg-space-sm` | 8px | Control gaps, chip padding |
| `--sg-space-md` | 16px | Panel padding, form rows |
| `--sg-space-lg` | 24px | Section rhythm |
| `--sg-space-xl` | 32px | Page bands, major groups |
| `--sg-space-2xl` | 48px | Hero and document sections |
| `--sg-space-3xl` | 64px | Large documentation breaks |

## Layout

- **Approach:** Hybrid. App screens use grid-disciplined native layout; docs and portfolio pages may use editorial rhythm.
- **Grid:** 12 columns for docs/landing on desktop, 4 columns on tablet, 1 column on mobile.
- **Capture surface:** Sticky Capture Note is the default global-hotkey surface: small, draggable, always-on-top capable, and focused on timestamped typing plus recording state.
- **Expanded editor:** Three-area structure when expanded: session list, active editor, context/actions. Expansion reveals tabs and evidence panels without changing the active session.
- **Max content width:** 1180px for docs, 860px for prose-heavy sections.
- **Radius:** `--sg-radius-sm: 4px`, `--sg-radius-md: 8px`, `--sg-radius-lg: 12px`, `--sg-radius-full: 999px`.
- **Borders:** Prefer 1px lines over heavy shadows. Shadows should be subtle and rare.

## Motion

- **Approach:** Minimal-functional.
- **Durations:** micro 80ms, short 180ms, medium 280ms.
- **Easing:** enter `cubic-bezier(.16, 1, .3, 1)`, exit `cubic-bezier(.7, 0, .84, 0)`, move `cubic-bezier(.45, 0, .2, 1)`.
- **Use motion for:** opening Sticky Capture Note, expanding into session editor, tab changes, transcript evidence reveal, processing state changes.
- **Avoid:** playful bounce, scroll choreography, decorative animation.

## Component Contracts

### Menu Bar Popover

- Width target: 360-420px.
- Shows current session, recording state, pending synthesis count, recent sessions, and quick actions.
- Use primary only for the most likely action: resume active session or start session.

### Sticky Capture Note

- Opens fast and small from the global hotkey.
- Behaves like a simple sticky note: draggable, optionally always-on-top, minimal chrome, quiet autosave, visible timer, recording toggle, and end-session action.
- The writing area may be compact, but the content cannot feel tiny: support scrolling, progressive height growth, and direct expansion before text becomes cramped.
- It captures timestamped note chunks in the same session model used by the expanded editor.

### Expanded Session Editor

- Opens from Sticky Capture Note, menu bar recent sessions, or processing states.
- Minimum expanded width target: 760px. Compact mode can hide session list and actions first.
- Required areas: Notes, Transcript, Synthesis, Tasks, plus context/evidence when enough width exists.
- Recording state must be visible but not dominant when off.

### Session List

- Rows show title, type, duration, status, and last activity.
- Use muted text for completed sessions, primary edge or dot for active session.
- Avoid card stacking. It should scan like a native sidebar.

### Tabs

- Required tabs: Notes, Transcript, Synthesis, Tasks.
- Active tab uses primary text and a 2px underline or left edge.
- Tabs must not resize when counts or status badges appear.

### Timestamp Chip

- Use IBM Plex Mono.
- Shape: small pill or square-corner chip with 4px radius.
- Notes use neutral chip; transcript context uses Context Blue; active capture can use Focus.

### Transcript Evidence Block

- Displays transcript range, confidence/status, and a short surrounding quote.
- Uses Context Blue as the semantic color.
- Must always be linkable back to the note chunk and readable without AI output.

### Marker Chip

- Optional helper, not the core interaction.
- Tags: important, task, question, decision, idea.
- Warm Signal is reserved for decision/important emphasis. Do not color every chip loudly.

### Recording State

- Off: quiet neutral text.
- On: primary dot + elapsed time. Add Focus only when actively capturing or user needs attention.
- Permission/failure states use warning/error tokens with clear copy.

### AI Synthesis Status

- States: idle, queued, processing, completed, failed.
- Completed shows summary availability. Failed must show retry and preserve raw notes/transcript.
- AI output should never visually outrank the user's original notes.

## Token Interface

### CSS

Use the `--sg-*` tokens exactly in docs and web surfaces. New tokens should follow:

- `--sg-color-*`
- `--sg-space-*`
- `--sg-radius-*`
- `--sg-type-*`
- `--sg-motion-*`

### Swift

Map tokens into native app code using:

- `SGColor.ink`, `SGColor.primary`, `SGColor.context`, `SGColor.signal`, `SGColor.focus`
- `SGSpacing.xs`, `SGSpacing.sm`, `SGSpacing.md`, `SGSpacing.lg`, `SGSpacing.xl`
- `SGRadius.sm`, `SGRadius.md`, `SGRadius.lg`
- `SGTypography.title`, `SGTypography.body`, `SGTypography.caption`, `SGTypography.mono`

## Decisions Log

| Date | Decision | Rationale |
| --- | --- | --- |
| 2026-07-03 | D14 Product-Core MVP approved | The product needs time-context restoration in v1 to avoid becoming a generic quick note app. |
| 2026-07-03 | Brand direction set to Quiet Native Workspace | The product should feel calm, precise, Mac-native, and private. |
| 2026-07-03 | Logo direction set to 결/시간선 심볼 | It represents note chunks and transcript chunks matching over time without generic AI-note imagery. |
| 2026-07-03 | Typography set to Gowun Batang, IBM Plex Sans KR, IBM Plex Mono | Korean brand identity, readable long-form docs, and precise timestamp/data rendering. |
| 2026-07-03 | Logo symbol redrawn with mirrored, point-symmetric curves and no diagonal accent stroke | The original curves were organic and asymmetric, reading as messy at hero size. A precise 180°-symmetric crossing (still two timelines meeting at one node) fits Quiet Native Workspace better. Applied to logo-symbol.svg, favicon.svg, logo-wordmark.svg, app-icon-source.svg. |
