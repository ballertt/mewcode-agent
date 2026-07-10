# MewCode

A terminal AI coding assistant built with Python and Textual.

## Features

- **Terminal-native TUI** — built with [Textual](https://github.com/Textualize/textual), runs entirely in your terminal
- **Multi-model** — supports Anthropic (Claude) and OpenAI models
- **Agent system** — built-in agents for code review, planning, exploration, and verification
- **Subagent orchestration** — coordinate multiple agents for complex workflows
- **MCP support** — Model Context Protocol integration for extensible tooling
- **Skills** — pluggable skill modules for extended capabilities
- **Hooks** — event-driven hook system for custom automation
- **Permission system** — fine-grained permission modes (default, accept-edits, bypass)
- **Sandbox** — optional sandboxing for safe code execution
- **Teams** — multi-agent team coordination with mailboxes
- **File history** — edit history with diff tracking
- **Memory** — persistent project and user memory

## Requirements

- Python >= 3.11
- [uv](https://github.com/astral-sh/uv) (recommended) or pip

## Installation

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/mewcode.git
cd mewcode

# Install with uv
uv pip install -e .

# Or with pip
pip install -e .
```

## Quick Start

```bash
mewcode
```

This launches the interactive TUI. Start chatting with the AI assistant directly in your terminal.

## Configuration

Copy the example config and edit it:

```bash
cp .mewcode/config.yaml.example .mewcode/config.yaml
```

Configure your API keys and model preferences in `config.yaml`.

## Development

```bash
# Install dev dependencies
uv sync --group dev

# Run tests
pytest
```

## Project Structure

```
mewcode/
├── __init__.py          # Package init
├── __main__.py          # Entry point
├── app.py               # Main TUI application
├── agent.py             # Agent logic
├── client.py            # LLM client (Anthropic / OpenAI)
├── config.py            # Configuration management
├── conversation.py      # Conversation state
├── driver.py            # App driver
├── prompts.py           # System prompts
├── agents/              # Agent system
│   ├── builtins/        # Built-in agent definitions
│   ├── loader.py        # Agent loading
│   └── task_manager.py  # Task orchestration
├── commands/            # Slash commands
│   └── handlers/        # Command handlers
├── hooks/               # Event hooks system
├── mcp/                 # MCP client & manager
├── memory/              # Persistent memory
├── permissions/         # Permission system
├── sandbox/             # Code sandboxing
├── skills/              # Skill modules
└── teams/               # Multi-agent teams
```

## Tech Stack

- **Framework**: [Textual](https://textual.textualize.io/) (TUI)
- **AI**: Anthropic SDK, OpenAI SDK
- **Protocol**: MCP (Model Context Protocol)
- **Async**: httpx, websockets
- **Config**: YAML (PyYAML)
- **Validation**: Pydantic
- **Testing**: pytest, pytest-asyncio

## License

MIT
