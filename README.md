# Rooks plugin

Plugin packages for Claude Code and Codex. These files connect your agent to
Rooks and provide a bootstrap skill. The MCP server runs separately; no server
implementation or credentials are included here.

| Plugin       | Environment | MCP endpoint                    |
| ------------ | ----------- | ------------------------------- |
| `rooks-beta` | Beta        | `https://app.beta.rooks.ai/mcp` |
| `rooks`      | Production  | `https://app.rooks.ai/mcp`      |

Enable only the environment you intend to use. Use beta for authenticated form
tools. Claude Code's production OAuth client is not configured yet.
Form editing requires a shell and access to the server-provided download and
upload URLs. These installation steps are for Claude Code and Codex.

## Install

Claude Code:

```sh
claude plugin marketplace add formsort/rooks-plugin
claude plugin install rooks-beta@rooks
```

Codex:

```sh
codex plugin marketplace add https://github.com/formsort/rooks-plugin.git
codex plugin add rooks-beta@rooks
```

Use `rooks@rooks` instead for the production package. Start a fresh session and
ask the agent to use Rooks and call `check_connection`. Complete the host's
OAuth sign-in when prompted; never paste tokens into a conversation.

## Update

Claude Code:

```sh
claude plugin marketplace update rooks
claude plugin update rooks-beta@rooks
```

For automatic updates, open `/plugin` in Claude Code, select **Marketplaces**,
choose **rooks**, and enable auto-update. Third-party marketplaces do not
enable it by default.

Codex:

```sh
codex plugin marketplace upgrade rooks
codex plugin add rooks-beta@rooks
```

Start a fresh session after updating. Use `rooks@rooks` for production.

## Releases

The [GitHub releases](https://github.com/formsort/rooks-plugin/releases) contain
the versioned beta and production ZIPs. Provider directory submissions are
separate; a GitHub release is not an approved store listing.

This repository contains generated files. Report problems through the
[issue tracker](https://github.com/formsort/rooks-plugin/issues). Do not include
credentials, respondent data or private form content.
