# CitizenAI plugin

This plugin connects the agent of your AI app to your CitizenAI agent. The agent can then use the email address, the phone number, the wallet, the provider accounts, the public research tools, and the cloud browser of your CitizenAI agent. The owner approval rules of CitizenAI stay the same.

## What the plugin adds

- **The CitizenAI MCP server** at `https://api.citizenagent.ai/mcp`.
- **The `citizen-ai-accounts` skill.** It tells the agent how to use the CitizenAI tools, and when to ask the owner first.

## Before you start

You need a CitizenAI account. Sign up at https://citizenagent.ai.

## Connect

The plugin uses the open [Agent Plugins](https://agent-plugins.org) format, so each app that loads this format can install it. Each app then signs in to CitizenAI with OAuth. You make a new agent or select an existing agent in the browser.

### Cursor

1. Install the plugin from the Cursor Marketplace.
2. Open **Cursor Settings → MCP**, and click the sign-in button next to `citizen-ai`.
3. Sign in to CitizenAI in the browser, and approve the connection.
4. In the agent chat, ask: "What accounts does my agent have?"

### ChatGPT

1. Find CitizenAI in the ChatGPT app directory, and connect it.
2. Sign in to CitizenAI in the browser, and approve the connection.

### Another app

Add the MCP server `https://api.citizenagent.ai/mcp` in the app, or install this plugin if the app loads the Agent Plugins format. Then sign in to CitizenAI when the app asks.

## Examples

- "What is my agent's email address?"
- "Read my agent's new emails."
- "Find a cute Halloween costume on Shopee and Lazada."

## Money and approvals

- Paid tools take money from the wallet of the connected agent. Add funds at https://citizenagent.ai.
- A purchase above the owner approval limit, a send, a post, and a payment need the owner's approval.
- The agent never asks for card details in the chat.

## Privacy and support

- Privacy policy: https://citizenagent.ai/privacy
- Terms: https://citizenagent.ai/terms
- Support: https://citizenagent.ai/support

## License

Apache License 2.0. See `LICENSE` and `NOTICE`. The license gives no right to use the CitizenAI name or logo.
