# Skiplagged plugins for Claude

This repository is the Claude plugin marketplace for [Skiplagged](https://skiplagged.com). It holds one plugin, **Skiplagged Travel** (`plugins/skiplagged`), which lets Claude find cheap flights (including hidden-city fares), hotels, and rental cars and link you straight to booking on skiplagged.com.

See the [plugin's README](plugins/skiplagged/README.md) for what it does, example prompts, and what data it sends.

## Install

### claude.ai, the Claude desktop app, and Cowork

Install once on your Claude account and the plugin is available in chat on the web, desktop, and mobile, in Cowork, and in Claude Code.

1. Open **Customize > Plugins** in claude.ai or the Claude desktop app.
2. Find **Skiplagged Travel** under **Discover**. Or select **Add > Add marketplace**, enter `skiplagged/claude-plugins`, and install **Skiplagged Travel**.
3. On the plugin's **Connectors** tab, connect **Skiplagged**. No sign-in is needed.

### Claude Code

```
/plugin marketplace add skiplagged/claude-plugins
/plugin install skiplagged@skiplagged
```

### Connector only (no skills)

To add only the connector, go to **Settings > Connectors > Add custom connector** in Claude and enter:

```
https://mcp.skiplagged.com/mcp
```

Setup for ChatGPT, Cursor, VS Code, Gemini CLI, and Codex is at https://skiplagged.github.io/mcp/.

## Support

https://support.skiplagged.com or support@skiplagged.com
