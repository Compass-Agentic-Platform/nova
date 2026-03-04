# Nova Changelog

What's new in Nova — your AI-powered development assistant.

---

## [v1.0.63] - 2026-03-03

### Unleash Mode
Nova now supports an **Unleash Mode** — a special mode that removes the guardrails for users who want fully unfiltered AI responses. Enable it via the CLI flag or your project config. Use responsibly.

### Smarter UI
- The Plan Execution Tracker now has a clean bottom border, making it easier to visually separate it from the rest of the conversation.
- Git tool output is now hidden from the stream by default — less noise, cleaner results.

### Under the Hood
- Nova's memory system now follows a clearer, step-by-step process when wrapping up context — more reliable and predictable behaviour.
- Self-correction guidelines have been added to the system prompt, so Nova learns from mistakes mid-session.

---

## [v1.0.62] - 2026-03-01

### Per-Model Daily Token Limits
You can now set daily token limits on a per-model or per-provider basis. Great for keeping costs predictable when using multiple AI providers.

### Cleaner Screen Clears
Fixed an issue where clearing the conversation could leave stale content or cause duplicate renders. `/clear` now works exactly as expected.

---

## [v1.0.61] - 2026-02-25

### Built-in Skills System
Nova now ships with a **Skills** system — reusable prompt templates you can invoke with a single command. Out of the box, Nova includes skills for writing newsletters, preparing releases, sanitising memory, and more. You can also create your own.

### Smarter Plan Updates
Plans can now be updated **mid-execution** — if something changes while Nova is working through a task list, you do not have to start over. Nova adapts on the fly.

### Better Context Management
Nova is now smarter about when to compact conversation history, reducing unnecessary interruptions and keeping long sessions running smoothly.

---

## [v1.0.60] - 2026-02-24

### Cost Tracking
Nova now calculates and tracks the cost of every conversation locally — no need to check your provider dashboard. Use `/cost` to see a breakdown at any time.

### Longer Responses
Increased the maximum response length to prevent Nova from cutting off mid-answer on complex tasks.

---

## [v1.0.59] - 2026-02-23

### Reliability Improvements
- Fixed an issue where file paths containing stray quotes (sometimes inserted by AI models) would cause tool failures.
- General code quality improvements across multiple files.

---

## [v1.0.58] - 2026-02-23

### European Portuguese Support
Nova now correctly uses **European Portuguese** (pt-PT) when responding in Portuguese — including the informal "tu" form, as is natural in Portugal.

### File and UI Polish
Improved file handling reliability and tightened up several UI rough edges.

---

## [v1.0.57] - 2026-02-22

### Memory Consolidation
Nova's memory system now actively consolidates what it knows about your project — trimming outdated notes and keeping context lean and relevant across long sessions.

---

## [v1.0.56] - 2026-02-21

### Scheduled Tasks
You can now create **recurring tasks** directly in Nova. Set a cron schedule or use plain English ("every Friday at 9am") and Nova will remember to run it. Tasks are stored in your project's `.compass` directory.

### Quieter MCP Servers
MCP server tool output can now be suppressed from the UI — useful when you want clean conversation output without server chatter.

### Smarter Session Resets
Starting a new session and clearing mid-session are now handled separately, giving you more predictable behaviour when you restart.

---

## [v1.0.55] - 2026-02-20

### New Models
- **Claude Sonnet 4.6** is now available and set as the default.
- **MiniMax M2.5** replaces the previous MiniMax model with improved performance.

### File Upload Tool
Nova can now upload local files and use them as inputs for document parsing, OCR, and other tools — no need to manually copy file contents.

### Performance and Cost Savings
- Smarter classification means Nova spends fewer tokens deciding what to do.
- Cloud environment detection is now faster at startup.
- File listing is more informative and easier to read.

### Subscription UX
The subscription flow has been improved — clearer messaging when a model requires an upgrade, with a smoother path to get there.

---

## [v1.0.54] - 2026-02-12

### New Model: GLM-5
Z.AI's **GLM-5** is now available as a model option.

### MCP Authentication Commands
New `/mcp auth` commands let you authenticate with MCP servers that require credentials — including OAuth and token-based flows.

### UI and Reliability
- Sub-agent output is now displayed more clearly in the conversation.
- Edit tool reliability has been improved — fewer "text not found" errors.
- Message duration is only shown for responses that take 60 seconds or longer, reducing visual clutter.

---

## [v1.0.53] - 2026-02-11

### Persistent Memory
Nova now remembers things across sessions. Project patterns, user preferences, past decisions — all stored in a `MEMORY.md` file that Nova reads at the start of every conversation.

### Keyboard Shortcut: Ctrl+X
Press **Ctrl+X** to skip the current tool execution step without cancelling the whole task.

### Smoother Streaming
Fixed a flickering issue where the spinner would overlap with streamed output.

---

## [v1.0.52] - 2026-02-10

### Subscription-Gated Models
Anthropic models now require an active Compass subscription. Nova will let you know clearly if a model is not available on your plan.

### Structured Output (Beta)
Nova now supports Anthropic's structured output feature in beta — enabling more reliable, schema-conformant responses for complex tasks.

### Cleaner Config Display
The `/config` command has been streamlined — easier to read, less clutter.

---

## [v1.0.51] - 2026-02-09

### Ollama Auto-Configuration
If you use Ollama for local models, Nova can now automatically fetch your Ollama configuration from Compass — no manual setup required.

### Stability Improvements
- Session handling is more robust across restarts.
- The plan tracker no longer flashes briefly during the classification phase.

---

## [v1.0.50] - 2026-02-08

### Chat Archival
Long conversations can now be **archived** — saved for future reference without cluttering your active session. Retrieve them later when you need context from past work.

### Welcome Banner
Nova's startup banner has been polished, and shell compatibility across PowerShell, Bash, and Zsh has been improved.

---

## [v1.0.49] - 2026-02-07

### Scrollable Conversation History
The conversation view now uses a proper scrollback buffer — you can scroll up to review earlier messages without losing your place.

### Smarter File Trees
Directory trees are now more compact and easier to scan. Dotfiles are now correctly included in glob pattern matching.

### Parallel Task Polling
The `poll_task` tool now blocks properly until a background agent finishes — no more polling loops needed.

---

## [v1.0.47] - 2026-02-06

### Claude Opus 4.6
**Claude Opus 4.6** is now available — the most capable model in the Claude family, ideal for complex reasoning and long-context tasks.

### Agent Delegation and Parallel Execution
Nova can now **delegate work to specialised sub-agents** and run multiple tool calls in parallel. This makes complex, multi-step tasks significantly faster.

### Refined Plan UI
The plan execution tracker has been cleaned up — tighter layout, better spacing, and a more polished look overall.

---

## [v1.0.46] - 2026-02-05

### File Attachments
You can now **attach files** to your conversation by pasting from the clipboard. Images, documents, and code files can be dropped directly into the chat.

---

## [v1.0.45] - 2026-02-04

### MCP Reconnect Command
Added `/mcp reconnect` — if an MCP server drops, you can now reconnect without restarting Nova.

### Spinner Improvements
Replaced custom spinners with a more reliable library, significantly reducing UI flickering during long operations.

### Increased MCP Timeout
MCP servers now have a longer default timeout, reducing false disconnections on slower machines.

---

## [v1.0.44] - 2026-02-02

### Personality Modes
Nova now supports **personality modes** — switch between communication styles using `/personality`. Options include professional, verbose analyst, and brutally honest. Each mode changes how Nova explains its reasoning and structures responses.

### Unguarded Mode
A new unguarded mode lets Nova respond without the usual safety framing — useful for advanced users who want direct, unfiltered output.

### File Operation Optimisations
File reads and writes are faster and more responsive, especially on large projects.

---

## [v1.0.43] - 2026-01-31

### UI Stability
Fixed flickering that occurred when approval modals appeared during active streaming. Consecutive file edits are now consolidated into a single approval step.

---

## [v1.0.40] - 2026-01-30

### Longer Responses
Increased the maximum token output to 4096 — Nova can now produce longer, more complete responses without cutting off.

### Compass MCP Enabled by Default
If you have a Compass API key, the Compass MCP server is now enabled automatically — no manual configuration needed.

---

## [v1.0.38] - 2026-01-29

### ACP (Agent Client Protocol) Support
Nova can now run as an **ACP server**, enabling integration with ACP-compatible editors and tools like Zed and VSCode extensions.

### New Models: Kimi K2.5 and Gemini
**Kimi K2.5** and **Gemini** are now available as model options, expanding your choice of AI providers.

---

## [v1.0.37] - 2026-01-28

### Hook System
Nova now supports **system hooks** — shell commands that run automatically in response to events (like tool calls or session starts). Configure hooks in your project settings to automate repetitive actions.

### Multi-Provider API Keys
You can now configure API keys for multiple AI providers in a single setup — no need to switch configs when changing models.

### MiniMax M2.1
**MiniMax M2.1** is now available as a model option.

### Smarter Context Compaction
The compaction trigger is now more reliable — Nova compacts conversation history at the right moment, not too early and not too late.

---

## [v1.0.35] - 2026-01-27

### Directory-Based Skills
Skills are now discovered from `.compass/skills/` directories — both global and project-level. Create a markdown file in that folder and Nova will pick it up automatically.

### MCP OAuth Authentication
MCP servers that require OAuth can now be authenticated directly from Nova using `/mcp auth`.

### GLM 4.7 Model
**Z.AI GLM 4.7** is now available as a model option.

### Long Prompt Collapsing
Long user prompts can now be collapsed and expanded with **Ctrl+O**, keeping the conversation view clean when you have written a detailed request.

---

## [v1.0.34] - 2026-01-25

### Automatic Tool Retry
If a tool call fails, Nova now automatically retries with a corrected approach — rather than stopping and asking you what to do.

### Nested .gitignore Support
Nova now respects `.gitignore` files in subdirectories, not just the root — so file searches and indexing correctly exclude the right files.

---

## [v1.0.30] - 2026-01-23

### Auto-Update on Startup
Nova now checks for updates automatically when it starts — you will always be on the latest version without having to run update commands manually.

### Smarter File Exclusions
Session folders and common noise directories are now excluded from file searches by default.

---

## [v1.0.29] - 2026-01-22

### Cleaner Command Output
Slash command output is now integrated cleanly into the conversation display — no more output appearing in the wrong place or at the wrong time.

---

## [v1.0.28] - 2026-01-21

### LLM-Powered Agent Prompt Generation
When creating a custom agent, Nova can now generate the agent's system prompt for you using AI — just describe what you want the agent to do.

### Configurable HTTP Timeouts
You can now set custom timeout values for HTTP connections — useful when working with slow or remote MCP servers.

### Sub-Agent Question Support
All built-in sub-agents (explore, code-reviewer, debugger, planner) can now ask you clarifying questions mid-task.

---

## [v1.0.27] - 2026-01-20

### Anthropic Permission Mode
Nova is now compatible with Anthropic's permission mode — making it easier to use alongside Claude's native tool approval flows.

### Disallowed Tools
You can now configure a list of tools that Nova is not allowed to use — useful for restricting access in sensitive environments.

---

## [v1.0.26] - 2026-01-20

### Runtime Agent Switching
Switch between agent configurations on the fly using `/agents use` — no need to restart Nova. Use `/agents reset` to return to the default.

### Per-Agent MCP Server Restrictions
Agents can now be configured to only access specific MCP servers — useful for sandboxing what each agent can do.

---

## [v1.0.25] - 2026-01-19

### Compass Spinner
Nova now displays a branded animated spinner during complex operations — a small but satisfying visual touch.

### Plan Complexity Feedback
When entering plan mode, Nova now shows you why it classified the task as complex — giving you more insight into its reasoning.

---

## [v1.0.24] - 2026-01-18

### User Rating System
Nova now occasionally asks for feedback on its responses — a quick thumbs up or down helps improve the experience over time. Only shown to authenticated Compass users.

### NO_ACTION Mode
For requests that do not require any action (e.g. "what is X?"), Nova now correctly identifies this and responds directly without spinning up a full agentic loop.

### Verbose Logging Flag
Added a `--verbose` CLI flag for detailed logging output — useful when debugging Nova's behaviour.

---

## [v1.0.23] - 2026-01-15

### Double-Escape to Cancel
Press **Esc** twice to cancel an in-progress agentic loop — a quick escape hatch when Nova is heading in the wrong direction.

### Improved Autocomplete
File system autocomplete is now smarter and faster — better suggestions when typing file paths.

### Plan UI Improvements
The plan execution dialog has been refined with cleaner task display and better status indicators.

---

## [v1.0.22] - 2026-01-14

### Smarter Edit Tool
The search-and-replace tool now returns helpful error messages when it cannot find the target text — helping Nova self-correct without getting stuck.

### Smoother Updates
The auto-update process has been improved for more reliable version transitions.

---

## [v1.0.21] - 2026-01-14

### Real-Time Streaming for Slash Commands
Slash commands now stream their output in real time — you see results as they arrive, not all at once at the end.

### Markdown Themes
Nova now supports **markdown themes** — syntax highlighting and styled output that makes reading code and structured content much more pleasant.

### Token Optimisation
Several improvements to reduce unnecessary token usage, keeping conversations within context limits for longer.

---

## [v1.0.19] - 2026-01-12

### NO_ACTION Execution Mode
Nova can now recognise when a request is already implemented or does not require any changes — and say so clearly, rather than attempting unnecessary work.

---

## [v1.0.18] - 2026-01-12

### Vim-Style Approval Navigation
The approval dialog now supports **vim-style keyboard navigation** — use `j`/`k` to move through options and `Space` to select.

### Gitignore Fallback
When no `.gitignore` is present, Nova now uses sensible default ignore patterns so file searches still work correctly.

### Context Usage Display
The status line now shows what percentage of the context window has been used — so you always know how much room is left before compaction kicks in.

---

## [v1.0.17] - 2026-01-11

### Cost Tracking and `/cost` Command
Nova now tracks token usage and estimated costs per session. Use `/cost` to see a breakdown at any time.

### Compass API Key — Now Optional
The setup wizard no longer requires a Compass API key to get started — you can use Nova with just an Anthropic key.

### File Integrity Protection
Nova now tracks file state before editing — if a file has been modified externally since it was last read, Nova will warn you before overwriting.

### Sub-Agent Budget Enforcement
Sub-agents now have strict token and turn budgets — they cannot run indefinitely, keeping costs predictable.

### `update_plan` Tool
Plans can now be modified mid-execution — adjust scope, add tasks, or change approach without starting over.

---

## [v1.0.14] - 2026-01-09

### Compass Authentication
Nova can now authenticate with the Compass backend and automatically retrieve your Anthropic API key — no need to manage keys manually.

### Interactive Logout
`/logout` now shows a confirmation prompt before signing you out.

### Execution Mode Selector
A new interactive UI lets you choose how Nova approaches each task — plan mode, direct execution, or hybrid.

---

## [v1.0.13] - 2026-01-09

### Hybrid Execution Mode
Nova now supports a **hybrid mode** that combines planning and direct execution — for tasks that need some structure but do not require a full plan.

### Built-in MCP Servers
Nova now ships with built-in MCP servers for filesystem access, memory, and web fetching — enabled explicitly when needed.

### Plan Adoption
If you provide a structured plan in your message, Nova will adopt it directly rather than generating its own.

---

## [v1.0.12] - 2026-01-08

### Official Anthropic Tokenizer
Nova now uses Anthropic's official tokenizer for accurate token counting — no more estimates.

### Nova Branding in Commits
Commit messages generated by Nova now include a Nova attribution footer.

### Context Visualisation
The context usage display has been redesigned with a cleaner grid layout — easier to read at a glance.

---

## [v1.0.9] - 2026-01-08

### MCP Server Configuration
Nova now supports configuring MCP servers for filesystem, memory, and fetch capabilities — with an interactive approval flow for project-scoped servers.

### Improved Shell Commands
Shell command execution now completes more gracefully, with better handling of long-running processes.

### Smarter Complexity Classifier
The classifier that decides whether to plan or act directly has been tuned to reduce false positives — fewer unnecessary plan prompts.

---

## [v1.0.5] - 2026-01-07

### Immediate Command Execution
Commands marked with `executeOnComplete` now run immediately after being issued — no extra confirmation step needed.

### Development Mode Fallback
Nova now falls back to a JavaScript build when the TypeScript build is not available — useful during development.

---

## [v1.0.4] - 2026-01-07

### Plan UI Polish
Early improvements to the plan execution UI — better layout and bug fixes for the initial plan mode implementation.

---

## [v1.0.2] - 2026-01-06

### Cleaner Builds
The `dist` folder is now automatically cleared before each build — no more stale compiled files causing unexpected behaviour.

---

## [v1.0.1] - 2026-01-06

### The Beginning

This is where Nova started. The very first release laid the foundation for everything that followed:

- **Plan Mode** — LLM-powered task planning with per-task iteration tracking and automatic transition to execution
- **Agentic Loop** — The core loop that lets Nova work through multi-step tasks autonomously
- **File Search** — Recursive project-wide file search with intelligent ranking
- **Commit Message Generation** — Conventional commit messages generated from staged changes
- **MCP Support** — Initial integration with the Model Context Protocol
- **Observability** — Logging, audit trails, and a workflow viewer for understanding what Nova is doing
- **Architecture Decision Records** — Documentation of key design decisions baked in from day one
- **CI/CD Pipeline** — Automated build and release infrastructure
- **Status Line** — Real-time context usage display
- **System Hooks** — Early hook architecture for extending Nova's behaviour

Nova was born ready to work.

---

*Co-authored by [Nova](https://www.compassap.ai/portfolio/nova.html)*
