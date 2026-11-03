# teja-claude-marketplace

A Claude Code marketplace with all of my plugins. Skills, agents, slash commands, mods, hooks and MCP servers are all
shipped as plugins, so each one is an entry in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json).

## Install

Inside Claude Code:

```
/plugin marketplace add teja156/teja-claude-marketplace
/plugin install <plugin>@teja-claude-marketplace
```

Shell equivalents: `claude plugin marketplace add teja156/teja-claude-marketplace` and
`claude plugin install <plugin>@teja-claude-marketplace`. Pick up new versions with
`claude plugin marketplace update teja-claude-marketplace`.

## Plugins

| Plugin | What it does | Source |
|---|---|---|
| `voiceover-cleanup` | Cleans a raw voiceover against its script (keeps the best take of each sentence, drops retakes, fillers and asides), with an editor to add back missed words. | [teja156/voice-cleanup-claude-plugin](https://github.com/teja156/voice-cleanup-claude-plugin) |

## Adding a plugin

- **A plugin with its own repo:** add an entry whose source is that repo:
  `"source": { "source": "github", "repo": "teja156/<repo>" }`.
- **A small plugin kept here:** put it in `plugins/<name>/` (with its own `.claude-plugin/plugin.json`) and use
  `"source": "./plugins/<name>"`.

Then run `claude plugin validate .` before pushing. Bump the version in the plugin's `plugin.json` when you release a
change, or installed copies won't update.
