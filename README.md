# 📦 Agentic Prompt + Tools Template

This repository provides a reusable, customizable configuration template for agentic coding assistants such as:

- [Cascade (Windsurf)](https://www.windsurf.com/)
- [Claude](https://claude.ai/)
- [GitHub Copilot Workspaces](https://githubnext.com/projects/copilot-workspace/)
- [Cline]([https://github.com/jthistle/cline](https://cline.bot/))
- Custom local or server-based agents

It defines how an assistant should behave, what tools it can use, and how to interact with your codebase — especially for test- and automation-heavy projects.

---

## ✅ Features

- **Playwright-first** testing architecture
- **Yarn-only** package management (no npm)
- **Page Object Model** (POM) structure assumed
- Designed for **macOS + ZSH**
- Agent-agnostic: usable with any LLM coding assistant

---

## 📂 Folder Structure
  .agentic/  
  ├── README.md            # Instructions for using and renaming the folder  
  ├── system_prompt.md     # Defines assistant behavior and expectations  
  ├── tools.json           # Describes tool interfaces the assistant can invoke  
  ├── environment.json     # Optional: environment hints like cwd, OS, shell  

---

## 🛠 How to Use This Template

1. **Copy `.agentic/` into your own repo**

2. **Rename the folder** based on your target agent system:

| Agent | Rename to |
|:------|:-----------|
| Cascade / Windsurf | `.cascade/` |
| Claude | `.claude/` or custom path |
| GitHub Copilot Workspaces | `.copilot/` *(future-ready)* |
| Cline | `.cline/` |
| Custom LLM agent | `.agent/` or `.config/` or any agent-compatible path |

3. **Register the files with your agent** (see below)

---

## ⚙️ How to Register the Prompt and Tools with Your Agent

### ▶️ **Cascade / Windsurf**
- Rename folder to `.cascade/`
- In **Windsurf Workspace Settings**, point to:
  - **Prompt**: `./.cascade/system_prompt.md`
  - **Tools**: `./.cascade/tools.json`
- Use `environment.json` for OS, shell, and path hints if supported

### ▶️ **Claude Custom Agents**
- Rename to `.claude/`, or pass individual files directly
- Set the prompt using contents of `system_prompt.md`
- Register tools from `tools.json` as tool definitions
- Compatible with Claude APIs or frameworks like [Autogen](https://github.com/microsoft/autogen)

### ▶️ **GitHub Copilot Workspaces**
- Future versions may support assistant configuration. Pass individual files directly
- Prepare by renaming to `.copilot/` and following the same structure

### ▶️ **Cline (CLI Assistants)**
- Rename to `.cline/`
- Use `system_prompt.md` with CLI flags or scripts
- Load `tools.json` in your tool config or init script

### ▶️ **Custom Agents**
- Use `system_prompt.md` for agent behavior
- Parse and expose `tools.json` for controlled tool usage
- Respect `environment.json` if your runtime supports agent hints

---

## 🧠 When to Update

| File | When to Update |
|:-----|:---------------|
| `system_prompt.md` | When your test setup, workflows, or conventions change |
| `tools.json` | When you add/remove tool capabilities |
| `environment.json` | When your shell, OS, working directory, or package manager changes |

---

## 🧰 Assumptions

- Tests follow the **Page Object Model** structure
- Project uses **Playwright** for end-to-end automation
- **Yarn** is the only supported package manager
- Development occurs on **macOS** using the **ZSH** shell
- New scripts must:
  - Be added to `package.json` under `scripts`
  - Be documented in the project’s root `README.md`

---

## 🪪 License

This configuration is public-domain or MIT licensed (your choice).  
Fork, clone, copy, and adapt it into any personal or commercial project.
