<p align="center">
  <img src="https://gyoz.ai/logo.png" alt="gyoza logo" width="80" />
</p>

<h1 align="center">gyoza</h1>

<p align="center">
  <strong>AI companion for the browser.</strong><br/>
  gyoza can see your screen, understand any website, and do things for you — clicks, forms, navigation, all by just asking.
</p>

<p align="center">
  <a href="https://gyoz.ai">Website</a> &nbsp;&middot;&nbsp;
  <a href="https://gyoz.ai/docs">Docs</a> &nbsp;&middot;&nbsp;
  <a href="https://gyoz.ai/recipes">Recipes</a> &nbsp;&middot;&nbsp;
  <a href="https://x.com/gyozaworks">X / Twitter</a>
</p>

---

### What is gyoza?

gyoza is a browser extension powered by AI. Point it at any website, tell it what to do in plain language, and it handles the rest — navigating pages, clicking buttons, filling out forms, extracting data, and more.

- **Works on any website** — no setup needed. Reads what's on screen and can click, scroll, fill forms, and find information for you
- **Supercharged with recipes** — web skills that teach gyoza how a site works, making it faster, cheaper, and more accurate
- **Choose your AI** — works with Claude, ChatGPT, or Gemini. Use your own API key for free, or subscribe for a hassle-free managed experience
- **Does things for you** — click buttons, fill out forms, navigate pages, translate content — just describe what you want
- **Privacy first** — your data stays on your device. No tracking, no data collection
- **Multilingual** — works on sites in any language, speaks 23+ languages

### The Extension

The gyoza extension is our flagship project — a browser extension that turns any website into an AI-navigable workspace. Install it on Chrome or Firefox, point it at any page, and tell it what to do.

The extension is open source under the [FSL-1.1-Apache-2.0](https://github.com/gyoz-ai/web-copilot/blob/main/LICENSE) license — source-available today, fully Apache 2.0 open source from April 2028.

**[gyoz-ai/web-copilot](https://github.com/gyoz-ai/web-copilot)** — the full source code for the gyoza browser extension.

### Community Projects

Tools and experiments built by the gyoza team and community:

| Repo | Description |
|---|---|
| [web-copilot](https://github.com/gyoz-ai/web-copilot) | The gyoza browser extension — AI companion for any website (FSL-1.1-Apache-2.0) |
| [terminal-chromium-skill](https://github.com/gyoz-ai/terminal-chromium-skill) | Claude Code skill: full Chromium browser in your terminal with CDP |
| [terminal-chromium](https://github.com/gyoz-ai/terminal-chromium) | Chromium running inside your terminal (Rust) |
| [terminal-firefox-skill](https://github.com/gyoz-ai/terminal-firefox-skill) | Claude Code skill: Firefox browser in your terminal via Browsh + CDP |
| [auto-research](https://github.com/gyoz-ai/auto-research) | Autonomous skill improvement inspired by Karpathy's autoresearch |
| [gyoza-recipes](https://github.com/gyoz-ai/gyoza-recipes) | Claude Code plugin for creating gyoza recipes (llms.txt) |

### Agent Harness Suite

A second stack, independent from the browser extension: a coding-agent harness built from two upstream forks plus six purpose-built extensions, all under the `gyoz-ai` org.

**The forks**

- **[herdr](https://github.com/gyoz-ai/herdr)** — terminal multiplexer fork that adds an agent-awareness layer on top: a sidebar rendering live subagents (grouped, sorted running-first), deep-focus navigation between them, and a socket protocol for reporting subagent state from an attached coding agent.
- **[oh-my-pi](https://github.com/gyoz-ai/oh-my-pi)** — coding agent fork (CLI: `omp`) wired to speak herdr's socket protocol: clickable agent rows and `agent://` links in the TUI, live output tails for running subagents, and deep-focus chords, so herdr can render and navigate what `omp` is doing in real time.

**The extensions**

Six standalone repos — none are forks — that plug into `omp`'s extension/tool/agent loader at runtime, each owning one piece of agent behavior:

| Repo | What it does | Install |
|---|---|---|
| [omp-governance](https://github.com/gyoz-ai/omp-governance) | Session-wide engineering rules — dispatch discipline, comment bans, test skip-marker bans, mandatory post-task verification | `omp plugin install github:gyoz-ai/omp-governance` |
| [omp-bash-guard](https://github.com/gyoz-ai/omp-bash-guard) | Intercepts every `bash` call and blocks or gates dangerous commands (`git push --force`, `rm -rf`, `sudo`, ask-first commands) | `omp plugin install github:gyoz-ai/omp-bash-guard` |
| [omp-memory](https://github.com/gyoz-ai/omp-memory) | Session-memory system backed by local Typesense — summarizes sessions into searchable facts plus a cross-project user profile | `omp plugin install github:gyoz-ai/omp-memory` |
| [omp-project-tools](https://github.com/gyoz-ai/omp-project-tools) | Project-agnostic `project_format` and `project_test` tools, auto-detecting Rust vs. TS/JS | `omp plugin install github:gyoz-ai/omp-project-tools` |
| [omp-ponytail](https://github.com/gyoz-ai/omp-ponytail) | Injects a YAGNI/minimality doctrine into every agent's system prompt, nudging for a pass marker before session end | `omp plugin install github:gyoz-ai/omp-ponytail` |
| [omp-smith-agent](https://github.com/gyoz-ai/omp-smith-agent) | `omp-smith` subagent role for building and refactoring the extensions above, with the real loader/cutover rules baked in | `git clone https://github.com/gyoz-ai/omp-smith-agent && ln -s "$(pwd)/omp-smith-agent/omp-smith.md" ~/.omp/agent/agents/omp-smith.md` |

**How it composes**

`omp` runs inside a `herdr`-managed pane and reports its live subagent tree over the socket both forks speak, so herdr's sidebar can render and navigate it. Inside `omp`, `omp-governance` and `omp-bash-guard` constrain what the agent is allowed to do, `omp-memory` and `omp-smith-agent` give it continuity and expertise across sessions, `omp-project-tools` gives it stack-agnostic build/test/format commands, and `omp-ponytail` keeps its output lean — six independently upgradable pieces (`git pull`, no redeploy step) composing into one harness.

### How it works

```
1. Install the extension       → Chrome or Firefox — one click
2. Add your API key or subscribe → BYOK for Claude/ChatGPT/Gemini, or use our managed plan
3. Visit any website and ask   → Natural language prompt, AI handles the rest
```

### Get involved

- Browse and install [community recipes](https://gyoz.ai/recipes)
- Follow us on [X / Twitter](https://x.com/gyozaworks)

<p align="center">
  <sub>Built by <a href="https://github.com/kevinfaveri">Kevin Faveri</a></sub>
</p>
