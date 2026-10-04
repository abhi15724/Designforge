# DesignForge

Design decision engine for coding agents: senior-designer UI/UX judgment, compact output, minimal tokens.
One source (`src/`) -> every platform. Edit `src/`, run `python3 build.py`.

## Install

| Tool | How |
|---|---|
| **Claude Code** | `/plugin marketplace add <your-github-user>/designforge` then `/plugin install designforge@designforge`. Local test: `claude --plugin-dir .` |
| **Claude.ai / Claude Desktop** | Upload `designforge.skill` (Settings > Capabilities > Skills) |
| **ChatGPT** | Follow `chatgpt/SETUP.md` (Custom GPT or Project; instructions + 3 knowledge files) |
| **Cursor** | `./install.sh cursor /path/to/project` (-> `.cursor/rules/*.mdc`, agent-requested, so it loads only for UI work) |
| **Windsurf** | `./install.sh windsurf /path/to/project` |
| **Cline / Roo** | `./install.sh cline /path/to/project` |
| **GitHub Copilot** | `./install.sh copilot /path/to/project` (path-scoped to UI files) |
| **Codex, Jules, Aider, Zed, any AGENTS.md tool** | `./install.sh codex /path/to/project` |
| **Gemini CLI** | `./install.sh gemini /path/to/project` |
| Everything | `./install.sh all /path/to/project` |

Note: `AGENTS.md` / `GEMINI.md` are always loaded (~1.5k tokens). If that matters, prefer the scoped options above.

## Use

Just ask: "Design a pricing page for ...", "Review this dashboard", "Build a settings page". Output is a compact spec (direction, tokens, layout, components, UX priorities, responsive, notes) or code; review mode returns score + critical/improve/keep/next action.

## Layout

```
src/                 source of truth (core.md + references/)
build.py             generates all targets
.claude-plugin/      Claude Code plugin + marketplace manifests
skills/designforge/  Agent Skill (Claude.ai, Claude Code)
.cursor/rules/       Cursor
.windsurf/ .clinerules/ .github/instructions/ AGENTS.md GEMINI.md   other tools
.designforge/        shared reference files for non-Claude targets
chatgpt/             Custom GPT instructions + knowledge
```
"# Designforge" 
