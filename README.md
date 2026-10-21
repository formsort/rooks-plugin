# Rooks plugin

Plugin packages for Claude Code and Codex. These files connect your agent to
Rooks and provide a bootstrap skill. The MCP server runs separately; no server
implementation or credentials are included here.

The `rooks` plugin connects to the production Rooks service at
`https://app.rooks.ai/mcp`.

Form editing requires a shell and access to the server-provided download and
upload URLs. These installation steps are for Claude Code and Codex.

## Install

Claude Code:

```sh
claude plugin marketplace add formsort/rooks-plugin
claude plugin install rooks@rooks
```

Codex:

```sh
codex plugin marketplace add https://github.com/formsort/rooks-plugin.git
codex plugin add rooks@rooks
```

Start a fresh session and ask the agent to use Rooks and call
`check_connection`. Complete the host's OAuth sign-in when prompted; never paste
tokens into a conversation.

## Update

Claude Code:

```sh
claude plugin marketplace update rooks
claude plugin update rooks@rooks
```

For automatic updates, open `/plugin` in Claude Code, select **Marketplaces**,
choose **rooks**, and enable auto-update. Third-party marketplaces do not
enable it by default.

Codex:

```sh
codex plugin marketplace upgrade rooks
codex plugin add rooks@rooks
```

Start a fresh session after updating.

## Releases

The [GitHub releases](https://github.com/formsort/rooks-plugin/releases) contain
the versioned production plugin ZIP (`rooks.zip`). Provider directory submissions
are separate; a GitHub release is not an approved store listing.

This repository contains generated files. Report problems through the
[issue tracker](https://github.com/formsort/rooks-plugin/issues). Do not include
credentials, respondent data or private form content.

## File transfers

The Rooks skill instructs Claude Code and Codex to upload form files and assets
directly to Amazon S3 using temporary signed URLs issued by Rooks MCP tools.
These uploads send the files from your agent's environment to AWS storage used
by Rooks, separately from requests to the Rooks MCP endpoint. Form editing also
requires downloading form files using server-provided URLs. Your agent's
environment must allow access to the storage hosts in those URLs.

## Privacy and terms

Use of the Rooks service through this plugin is subject to the [Rooks Terms of Service](https://rooks.ai/terms). See the [Rooks Privacy Policy](https://rooks.ai/privacy) for how Rooks collects, uses, and shares information.

## License

The plugin software is licensed under the [MIT License](LICENSE).
