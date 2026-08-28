# System Architecture Specification: VibeCoder Engine

## 1. Executive Summary & Purpose

The **VibeCoder Engine** is a single-file, zero-dependency, client-side web application designed to orchestrate LLM-driven software development workflows (vibe coding). It provides structured prompt pipelines for Greenfield (new project) and Brownfield (existing repo) execution, embedded system prompt templates, starter project blueprints, and a copy-to-clipboard mechanism with real-time semantic versioning tracking (`v1.1.x`).

---

## 2. Technical Stack Constraints

* **Architecture:** Terminal-free, single-file HTML (`index.html`) deployment.
* **Frontend:** Vanilla HTML5, Modern JavaScript (ES6+), Tailwind CSS (loaded via CDN).
* **Dependencies:** Zero build tools, zero bundlers, zero Node.js/npm dependencies.
* **Runtime:** Pure browser client-side execution; cross-platform compatible (optimized for iPad/mobile-first environments).

---

## 3. System Architecture & Component Mapping

```
+-------------------------------------------------------------------------------+
|                             VibeCoder Engine (index.html)                     |
+-------------------------------------------------------------------------------+
|                                                                               |
|  [ HEADER BAR ]                                                               |
|  - App Title & Status Indicator                                               |
|  - Dynamic Version Badge (#version-badge) -> v1.1.x                           |
|  - How-To Guide Trigger Button                                                |
|  - View Navigation Tabs (Greenfield | Brownfield | Templates | Starters | Vault)|
|                                                                               |
+-------------------------------------------------------------------------------+
|                                                                               |
|  [ MAIN CONTENT AREA ]                                                        |
|                                                                               |
|  +-------------------------------------------------------------------------+  |
|  | VIEW 1: Greenfield Pipeline                                             |  |
|  | - 3-Step Stepper Header (Brainstorm -> Planning -> Execution)           |  |
|  | - Split Pane: Dynamic Prompt Display (7 cols) + Rubric/Gate (5 cols)    |  |
|  +-------------------------------------------------------------------------+  |
|                                                                               |
|  +-------------------------------------------------------------------------+  |
|  | VIEW 2: Brownfield Pipeline                                             |  |
|  | - 4-Step Stepper Header (Bundle -> Audit -> Issues -> Tests)            |  |
|  | - Full-width Code Review & Analysis Prompt Container                    |  |
|  +-------------------------------------------------------------------------+  |
|                                                                               |
|  +-------------------------------------------------------------------------+  |
|  | VIEW 3: Stack Templates Grid                                            |  |
|  | - 2-Column Responsive Grid containing 8 System Prompt Modules:           |  |
|  |   * Vanilla Web / iPad Native                                           |  |
|  |   * Cloudflare Workers Edge API                                         |  |
|  |   * Supabase CDN Client Architecture                                    |  |
|  |   * Direct REST Gemini Free API                                         |  |
|  |   * GSAP 3 UI Animation Engine                                          |  |
|  |   * Three.js Interactive WebGL Scene                                    |  |
|  |   * Anime.js Micro-Interaction Engine                                   |  |
|  |   * Theatre.js Motion Director                                          |  |
|  +-------------------------------------------------------------------------+  |
|                                                                               |
|  +-------------------------------------------------------------------------+  |
|  | VIEW 4: Starter Project Blueprints                                      |  |
|  | - 3 Production-ready specs (Markdown Dash, Gemini Extractor, Analytics)   |  |
|  +-------------------------------------------------------------------------+  |
|                                                                               |
|  +-------------------------------------------------------------------------+  |
|  | VIEW 5: Master Prompt Vault                                             |  |
|  | - Single vertical feed of all system prompts with direct copy triggers    |  |
|  +-------------------------------------------------------------------------+  |
|                                                                               |
+-------------------------------------------------------------------------------+
|                                                                               |
|  [ MODAL LAYER ]                                                              |
|  - Overlay How-To Guide (`#modal-howto`) containing 5-step operational model  |
|                                                                               |
+-------------------------------------------------------------------------------+

```

---

## 4. Core Data Dictionary & Prompt Repository

### State Variables

* `major` (Integer, default `1`)
* `minor` (Integer, default `1`)
* `patch` (Integer, default `0`)

### Prompt Store (`PROMPTS` Object)

| Key | Context / Intent | Target Output |
| --- | --- | --- |
| `g1_1` | Greenfield Step 1 Interactive Brainstorming | Forces LLM to ask 1 question at a time to hone project requirements. |
| `g1_2` | Greenfield Step 1 Spec Compilation | Compiles answered questions into a structured `spec.md`. |
| `g2_tdd` | Greenfield Step 2 TDD Prompt Plan | Transforms `spec.md` into incremental, testable prompt steps. |
| `g2_todo` | Greenfield Step 2 Checklist Generation | Generates an actionable `todo.md` task matrix. |
| `b_review` | Brownfield Code Review | Performs deep architectural and line-by-line code review. |
| `b_issues` | Brownfield Issue Extraction | Extracts top bugs and design flaws formatted for GitHub Issues. |
| `b_tests` | Brownfield Test Gap Analysis | Identifies missing test cases and edge-condition coverage. |
| `tmpl_vanilla` | Stack: Vanilla Single-File | Constrains code output to single `index.html` with zero dependencies. |
| `tmpl_worker` | Stack: Cloudflare Workers | Constrains code output to pure ES module fetch handlers for edge APIs. |
| `tmpl_supabase` | Stack: Supabase CDN Client | Controls client-side initialization via CDN scripts and RLS handling. |
| `tmpl_gemini` | Stack: Gemini Free REST API | Direct fetch implementation to `gemini-1.5-flash` endpoint with retries. |
| `tmpl_gsap` | Stack: GSAP 3 Animations | CDN script implementation of timeline sequencing and ScrollTrigger. |
| `tmpl_three` | Stack: Three.js WebGL | Pure client WebGL setup with animation loop and raycasting. |
| `tmpl_anime` | Stack: Anime.js Micro-Interactions | Keyframe arrays and staggered grid animation setup. |
| `tmpl_theatre` | Stack: Theatre.js Motion Director | Studio initialization and 3D property keyframe mapping. |

---

## 5. Key Functional Workflows

### Version Bumping Logic

1. User clicks any **"Copy Prompt"** or **"Copy Blueprint Prompt"** button.
2. `copyToClipboard(text)` reads prompt content and writes to `navigator.clipboard`.
3. `incrementVersion()` is executed:
* Increments `patch` by 1 (`v1.1.0` $\rightarrow$ `v1.1.1`).
* Updates `#version-badge` element inner text.
* Flashes badge background (`bg-emerald-400` highlight for 300ms).



### Tab Switcher Execution

1. User clicks navigation button (`#tab-[view]`).
2. `switchTab(targetView)` hides all `<section>` containers by applying the `.hidden` utility class.
3. Removes active styling from previous tab and applies active state (`bg-emerald-500 text-zinc-950 font-semibold`) to the target tab.
4. Unhides `#view-[targetView]`.

---

## 6. Deployment & Execution Instructions

1. Save the solution HTML file as `index.html`.
2. Host on any static host (Cloudflare Pages, GitHub Pages) or open directly in any browser (iPad Safari, Chrome, Firefox).
3. Zero build commands required (`npm install` or `npx` prohibited).
