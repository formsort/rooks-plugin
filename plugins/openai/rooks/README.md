# Rooks

Rooks is an AI form builder from Formsort. Describe the form you need, and your
AI builds it in Rooks: online forms, surveys, questionnaires, intake forms and
registration forms. Add conditional logic, calculations, validation, file
uploads, signatures and your branding. Review the draft in a preview, then
publish. Rooks hosts the form, collects the responses and gives your team a
dashboard to manage them.

The plugin contains a skill and the address of the Rooks MCP server. The skill
tells your AI how to use the Rooks tools and how to keep credentials and
respondent data out of chat.

## Examples

- "Use Rooks, check my connection, and show my workspaces."
- "Create a consultation form with contact details on the first page."
- "Show the follow-up question only when someone chooses Other."
- "Use our colors and add this logo to the header."
- "Save a draft and give me the preview link. Wait for my approval before
  publishing."

## Requirements

- A Rooks account. Sign up at [rooks.ai](https://rooks.ai).
- Sign in to Rooks when your AI asks you to connect. Never paste tokens or
  passwords into a conversation.
- For form editing, a code execution environment that can reach the file
  transfer hosts. See [File transfers](#file-transfers).

## Where it works

- **Claude Code:** install with
  `/plugin install rooks --marketplace formsort/rooks-plugin`, then connect when
  prompted. Form editing uses the shell.
- **Claude chat and Cowork:** connect Rooks from the plugin's **Connectors**
  tab. Code execution blocks most internet hosts by default. To edit forms,
  allow the Rooks domain (`rooks.ai`) and Amazon S3 (`amazonaws.com`) in the
  code execution settings. On Team and Enterprise plans, an admin controls
  these settings.

If your AI can't reach the file transfer hosts, it can still list your
workspaces and forms and answer questions about Rooks, but it can't change a
form.

## File transfers

To edit a form, your AI downloads the form files and uploads the changed files
through short-lived links that the Rooks tools return. Images, fonts and PDFs
that you add to a form are uploaded the same way. Each link goes to Rooks and
then redirects to a temporary signed URL for the Amazon S3 storage that Rooks
uses. The files travel between your AI's environment and that storage,
separately from the requests to the Rooks MCP server.

Your AI publishes a form only when you ask it to.

## Responses and data protection

Rooks collects and stores form responses, including uploaded files. The Rooks
tools in this plugin can't read submitted responses: you review them in the
Rooks dashboard.

Rooks supports HIPAA-compliant response storage and is SOC 2 Type II
certified. Sign a Business Associate Agreement (BAA) with Rooks before you
collect protected health information.

## Documentation and support

Read the [Rooks documentation](https://docs.rooks.ai). Report problems in the
[issue tracker](https://github.com/formsort/rooks-plugin/issues). Do not
include credentials, respondent data or private form content.

## Privacy and terms

Use of Rooks through this plugin is subject to the
[Rooks Terms of Service](https://rooks.ai/terms). The
[Rooks Privacy Policy](https://rooks.ai/privacy) explains how Rooks collects,
uses and shares information.

## License

The plugin is licensed under the MIT License.
