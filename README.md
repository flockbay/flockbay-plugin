# Flockbay for Claude Code, Codex, Cursor and Gemini CLI

Connects your coding agent to [Flockbay](https://flockbay.com), the Godot
editor with an AI agent built in. With it, Claude Code, Codex, Cursor or
Gemini CLI can build, run and playtest a Godot 4 game in a live Godot editor:
- edit scenes and GDScript;
- run the game headless and read Godot's output and parse errors;
- send input events;
- capture the viewport.

This plugin only registers Flockbay's MCP server, `flockbay`. The tools come
from the Flockbay app.

## Before you install

Install Flockbay for Windows from [flockbay.com](https://flockbay.com/), and
open your game in it. The plugin starts `flockbay mcp`, which the Windows app
puts on your PATH; open a new terminal after installing so it is found.

On a Mac or Linux the app does not put that command on your PATH yet, so the
plugin cannot start the server there. In the app, open Connectors, then
Connect your agent (MCP), press Turn on, and copy the line it writes for your
machine instead.

## Claude Code

```bash
claude plugin marketplace add flockbay/flockbay-plugin && claude plugin install flockbay@flockbay
```

Or, inside a session:

```
/plugin marketplace add flockbay/flockbay-plugin
/plugin install flockbay@flockbay
```

Start a new session in your game's folder; `/mcp` lists `flockbay`.

## Codex

```bash
codex plugin marketplace add flockbay/flockbay-plugin
```

Then install Flockbay from the Plugins Directory. Or add the server without
the plugin:

```bash
codex mcp add flockbay -- flockbay mcp
```

## Cursor

Add the server to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "flockbay": { "command": "flockbay", "args": ["mcp"] }
  }
}
```

## Gemini CLI

```bash
gemini extensions install https://github.com/flockbay/flockbay-plugin
```

## Without the plugin

Any MCP client can run the same server:

```bash
claude mcp add --scope user flockbay -- flockbay mcp
```

Setup for each agent, and what the tools do:
[flockbay.com/godot-ai-mcp](https://flockbay.com/godot-ai-mcp/).

## Privacy

The plugin itself collects nothing: it only starts the Flockbay app's MCP
server on your machine. The app's privacy policy is at
[flockbay.com/privacy](https://flockbay.com/privacy/).

## License

MIT. See [LICENSE](LICENSE).
