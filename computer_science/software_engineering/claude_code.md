Claude Code
===========
# Overview
* Start Claude Code session with `claude`.
* Claude code uses the `/` for special commands. 
* Use `/init` to initialize Claude Code in a new repository. This will create a `CLAUDE.md` file in the root directory if it does not already exist. `CLAUDE.md` servers as the main configuration and memory file for Claude Code in the repository.
* Use `/help` to show a list of available commands.
* Use `/exit` to exit Claude Code session.


# Memory
* There are three types of memory:
  1. Project memory: specific to the current project/repo. Project memory is stored within `CLAUDE.md`. 
  2. User memory: shared across all projects/repos for a specific user. Usually stored in `~/.claude/CLAUDE.md` on local. 
  3. Local memory: deprecated.
* Use `#` symbol to add information to memory. Claude code should prompt you to confirm before adding to memory.

# Context 
* You can add context to Claude Code by using the `@` symbol followed by the context you want to provide.

```
@<directory_path / file_name> <prompt> 
```

* Use `/clear` to clear the current context. 
* Use `/compact` to clear the conversation history but summarize the context.
* Use `/context` to show and visualize the current context. 

# Tool Permissions
* `/permissions` adds permissions for Claude Code to access external tools and services.
* Permission rules can be saved in:
    1. Project settings: stored in `<project>/.claude/settings.json` in the project root directory.
    2. User-level: stored in `~/.claude/settings.json` on local machine.
* Permission rules are stored in a json blob such as:

```json
{
  "permissions": {
    "allow": [
      "Bash(ls: *)"
    ],
    "deny": [],
    "ask": []
  }
}
```

# Claude Code Modes
* Use `shift` + `tab` to switch between modes:
    1. **Default Mode**: Standard Claude Code behavior.
    2. **Accept Edits Mode**: Automatically accept code edits without confirmation.
    3. **Plan Mode**: Generate a plan before executing commands. For more complex tasks.

# Custom Commands
* You can create custom commands by adding markdown files in the `.claude/commands/` directory in the project root.
* Give directions to the markdown file. 
* Use `/commands` to list available custom commands.
* Add headers in the markdown file to provide structure:
    1. Brief description of the command.
    2. Argument hints for inputs the command takes.

```
---
description: Brief description of the command.
argument-hint: arg1 | arg2
---
```

# MCP Servers
* You can add an mcp server with the command `claude mcp add`.
* // TODO: More information about using tools from mcp server.

# Subagents
* Subagents have their own isolated context and memory. Reduce context overload of main workflow.
* `/agents` create new agent or list existing agents
    * Claude code can generate subagent on description.
    * Manually configurable
* Can be invoked by adding subagent to new command markdown.
* // TODO: Async subagents
