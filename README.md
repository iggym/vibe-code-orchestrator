# 🚀 Vibe Code Orchestrator

> **Turn raw vibes into production-ready code!** ✨
> The ultimate prompt engineering & workflow orchestration tool built for single-file web apps, edge functions, and zero-build stack development.

🌐 **[Live Demo & Web App](https://www.google.com/search?q=https://iggym.github.io/vibe-code-orchestrator)** 👈 *Click here to launch the app directly in your browser!*

---

## 🌟 What is Vibe Code Orchestrator?

**Vibe Code Orchestrator** operationalizes modern LLM code-generation workflows (inspired by Harper Reed's iterative codegen methodology). Whether you are starting a project from a blank screen or wrangling a legacy codebase, this tool gives you structured pipelines, battle-tested system prompts, and strict evaluation rubrics to get clean code on the first try! 🎯

Designed for **terminal-free**, **single-file HTML/JS**, **Cloudflare Workers**, **Supabase**, and **Gemini API** stacks. ⚡

---

## 🛠️ Key Modules & Functional Features

### 🟢 1. Greenfield Pipeline (New Projects) 🆕

Take an abstract idea and turn it into full application code in 3 structured loops:

* 💡 **Step 01: Idea Honing & Spec Compilation** — Generates one targeted question at a time to lock in scope, then packages everything into a comprehensive `spec.md`.
* 📐 **Step 02: Prompt Plan & Checklist Generator** — Uses reasoning models ($o1$, $o3$, $R1$) to break `spec.md` down into small, TDD-ready chunks. Outputs `prompt_plan.md` and `todo.md`.
* 🔄 **Step 03: Iterative Execution & Debug Loop** — Runs code-gen prompts step-by-step with Claude or Aider, paired with continuous state checking and instant debugging protocols.

### 🟤 2. Brownfield Pipeline (Legacy & Bug Fixing) 🔧

Audit, refactor, and improve existing codebases without blowing up your context window:

* 📦 **01 • Context Packing (Repomix Hub)** — Pre-configured CLI tasks to strip out lockfiles, binaries, and bloat into a clean `output.txt` payload.
* 🔍 **02 • Code Review Suite** — Deep-dive architectural review with exact line-number targeting and zero hallucinations.
* 🐛 **03 • GitHub Issue Extraction** — Scans the codebase for edge cases and auto-formats discrete, copy-pasteable GitHub Issues.
* 🧪 **04 • Missing Test Generator** — Identifies untested paths and outputs targeted unit/integration tests.

### ⚡ 3. Pre-Configured Tech Stack Templates 🎨

Tailor-made system prompts designed for modern, zero-dependency stack constraints:

* 📄 **Vanilla Single-File Apps** — Enforces pure HTML/CSS/JS, zero npm modules, zero build tools, and single-file portability (perfect for iPad/browser editing!).
* ☁️ **Cloudflare Workers** — Enforces standard ES Module `fetch` handlers, CORS preflight handling, and edge-native JS.
* 🗄️ **Supabase CDN Integration** — Injects CDN scripts and window-initialized client boilerplate with built-in RLS error handling.
* 🤖 **Direct REST Gemini Free API** — Simple browser-native `fetch` templates calling Gemini models with automatic 429 backoff support.

### 🔐 4. Prompt Vault & Quality Gates 📋

* 📑 **Master Copy-Paste Library** — One-click access to every system prompt in the workflow.
* ✅ **Evaluation Rubrics** — Integrated checklists at every step so you can verify prompt output quality before moving to execution.

---

## 🚀 Quick Setup & Deployment

Since this app is built with **zero external dependencies**, deploying your own copy is as simple as uploading a single file:

1. **Clone the Repo** 📥
```bash
git clone https://github.com/iggym/vibe-code-orchestrator.git
cd vibe-code-orchestrator

```


2. **Run Locally** 💻
Open `index.html` in any web browser! No `npm install`, no build scripts, no hassle.
3. **Deploy to GitHub Pages** 📡
* Push `index.html` to your `main` branch.
* Go to **Settings** ⚙️ $\rightarrow$ **Pages**.
* Set Source to `main` branch / `root`.
* Boom! 🎉 Your vibe coding engine is live on the web!



---

## 🤝 Contributing & Feedback

Got a prompt tweak or a new stack template? Pull requests are always welcome! Let's build the ultimate vibe-coding tool together. 💫

---

Made with ❤️ and ☕ for high-velocity builders. 🛠️✨
