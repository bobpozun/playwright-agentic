# Agentic System Configuration Template

This directory defines behavior and tool access for an agentic coding assistant, especially suited for Playwright, load testing, and utility-driven JavaScript/TypeScript projects.

## Files
- `system_prompt.md`: Defines how the assistant behaves.
- `tools.json`: Defines the available tools the assistant can use.
- `environment.json`: (Optional) Environment hints for the agent like OS, shell, and working directory.

---

## How to Use

1. **Rename This Folder**  
   Before using, **rename `.agentic/` to match the agent tool you are using**, such as:
   - `.cascade/` for Codeium Cascade and Windsurf
   - `.copilot/` for GitHub Copilot Workspaces (future use)
   - `.cline/` for Cline local agents
   - `.claude/` for Claude custom agents
   - `.agent/` for generic agentic systems

2. **Connect It to Your Agent**  
   Depending on your agent system, you may need to:
   - Specify the folder path
   - Register the prompt and tools manually
   - Point to the `system_prompt.md` and `tools.json` directly

---

## When to Update

| File | When to Update |
|:-----|:---------------|
| `system_prompt.md` | When your project structure, test setup, or workflow preferences change. |
| `tools.json` | When you add or remove agent capabilities. |
| `environment.json` | When your local settings (cwd, OS, shell, package manager) change. |

---

## Assumptions
- Page Object Model (POM) architecture is used.
- Playwright is the preferred E2E framework.
- Yarn is the required package manager.
- macOS is the development OS, shell is assumed to be ZSH.
- New runnable scripts must update `package.json` and be documented in your project's main `README.md`.

---

**Note:**  
This template is fully agent-agnostic and can be used with **Cascade**, **GitHub Copilot Workspaces**, **Claude**, **Cline**, or any custom agentic coding system.
