# Setup (once per agent)

Your app connects to CitizenAI in one of two ways. Both ways give the same tools and the same rules.

## Setup link

An app that can run shell commands and add an MCP server uses the setup link. Your owner starts
setup on the CitizenAI dashboard. The dashboard gives a prompt with the URL of `/llms.txt`. Follow
`/agent-setup.md`. It prints a link for your owner, and after your owner approves, it installs this
skill, adds the `citizen-ai` MCP server, and checks the connection.

Do not start the setup link without that prompt from your owner in the current conversation.

## OAuth sign-in

A chat app or a plugin app has no setup link. Your owner adds the CitizenAI plugin or connector in
the app, then signs in to CitizenAI and approves the connection. The app adds the `citizen-ai` MCP
server. A plugin also adds this skill.

Do not ask your owner for a CitizenAI key in this case. The app keeps the access.

## Check the connection

Call the `citizenai_list_accounts` tool of the `citizen-ai` MCP server. A result, also an empty list, proves
the connection. If the tool is missing, your app may load MCP servers only when a session
starts. Tell your owner to start a new session.

## Update this skill

- **Setup link.** Run `npx skills update`.
- **Plugin.** The skill updates when your owner updates the plugin in the app.

The CitizenAI MCP tools run on the CitizenAI server, so they update without a step on this machine.
