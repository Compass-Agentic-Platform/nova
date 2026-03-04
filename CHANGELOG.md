# Changelog

All notable changes to Nova will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [v1.0.63] - 2026-03-04

This is the initial changelog release, documenting the complete development history of Nova - an AI-powered development assistant that brings advanced language models directly to your terminal.

### Added

#### Core Features
- **Plan Mode Workflow System** - LLM-powered implementation planning with task breakdown, progress tracking, and mid-execution plan updates
- **Agent System** - Spawn specialized sub-agents (explore, code-reviewer, debugger, planner) with isolated context and budget enforcement
- **MCP (Model Context Protocol) Support** - Built-in MCP servers for filesystem, memory, fetch, and compass tools with interactive approval flows
- **ACP (Agent Client Protocol) Support** - Server mode for integration with ACP-compatible clients like Zed and VSCode extensions
- **Memory System** - Persistent auto-memory across sessions with consolidation and context management
- **Scheduled Tasks** - Create and manage recurring tasks with cron expressions and natural language scheduling
- **Chat Archival** - Archive and restore conversation history for long-term reference
- **Built-in Skills System** - Reusable prompt templates including sanitize-memory, write-newsletter, prepare-release, and more

#### Authentication & Configuration
- **Compass API Key Authentication** - Secure authentication with automatic API key retrieval from Compass backend
- **Subscription Gating** - Model access control based on subscription tiers with automatic fallback
- **Ollama Integration** - Auto-configuration for local Ollama models
- **Multiple Model Support** - Claude (Opus 4.6, Sonnet 4.6, Sonnet 4, Haiku), GLM-5, MiniMax M2.5, Gemini, Kimi K2.5

#### Tools & Capabilities
- **File Operations** - Read, write, edit, search, and manage files with intelligent diff previews
- **Code Search** - Grep-based pattern matching with context and line numbers
- **Git Integration** - Status, diff, log, stage, commit with conventional commit message generation
- **Shell Execution** - Run commands with approval flows and background process support
- **Web Fetch** - Retrieve and parse web content as markdown
- **Image Analysis** - OCR and visual analysis for images
- **Audio Transcription** - Speech-to-text using Whisper
- **Document Parsing** - Convert PDF, DOCX, XLSX, PPTX to markdown
- **Chart Generation** - Create professional charts with consistent branding

#### User Interface
- **Interactive Approval Dialogs** - Vim-style navigation, diff previews, and approval modes (Y/N/A/Smart)
- **Plan Execution Tracker** - Real-time progress visualization with task status
- **Streaming Output** - Real-time markdown rendering with syntax highlighting
- **Status Line** - Context usage display with token percentages
- **Clarification Wizard** - Interactive question flow for ambiguous requests
- **Execution Mode Selector** - Toggle between plan, direct, and hybrid modes
- **Rating System** - User feedback collection with progressive cooldown

#### Slash Commands
- `/agents` - Manage and switch between agent configurations
- `/clear` - Clear conversation history
- `/commit` - Generate conventional commit messages
- `/compact` - Compact conversation context
- `/config` - View and manage configuration
- `/cost` - Display token usage and costs
- `/files` - Browse project files
- `/help` - Display available commands
- `/login` / `/logout` - Authentication management
- `/mcp` - Manage MCP servers
- `/model` - Switch AI models
- `/personality` - Switch communication styles (professional, verbose_analyst, brutally_honest)
- `/unleash` - Enable unguarded mode for unrestricted responses

### Changed

#### Performance Improvements
- Optimized streaming rendering with Ink Static components
- Multi-layered token optimization to prevent context window overflow
- Context window protection with blocklists and limits
- Efficient file indexing with ignore pattern support
- Compact edit response format for token efficiency

#### User Experience
- Improved startup UX with welcome messages and setup wizard
- Enhanced shell compatibility across PowerShell, Bash, and Zsh
- Better error messages with actionable guidance
- Refined diff previews with smart adaptive rendering
- Smoother cursor animations and reduced UI flickering

#### Architecture
- Modularized built-in tools into separate files
- Event-based output system for slash commands
- Centralized prompts into dedicated module
- Unified logging system with configurable verbosity

### Fixed

- File integrity tracking to prevent external overwrites
- Edit tool validation with clear error messages
- Glob pattern matching to include dotfiles
- MCP approval dialog race conditions
- Plan tracker flash during classification phase
- Stale content and duplicate renders on clear
- Streaming cursor blinking and layout shifts
- Line ending normalization in diff tools
- Haiku model ID and model selection persistence
- Complexity classifier false positives
- Token calculation accuracy

### Security

- Input validation for path sanitization
- Stray quote sanitization in tool inputs
- Shell command safety improvements
- Approval permissions for executing shell commands

### Documentation

- Architecture Decision Records (ADR) for key design decisions
- Built-in tools documentation
- Workflow system documentation
- Compatibility documentation for Claude agents

---

**Development Statistics:**
- Total commits: 499
- Development period: Initial release to 2026-03-04
- Major contributors: BrunoV21, dherbe, Bruno Vitorino

**Key Architecture Decisions:**
- ADR001: Orchestration system design
- ADR004: Multi-phase workflow system
- ADR005: Unified logging architecture
- ADR006: MCP support implementation
- ADR008: System hooks architecture
- ADR012: Temperature configuration
- ADR017: Runtime agent switching
- ADR020: ACP unleash mode

---
Co-authored by [Nova](https://www.compassap.ai/portfolio/nova.html)
