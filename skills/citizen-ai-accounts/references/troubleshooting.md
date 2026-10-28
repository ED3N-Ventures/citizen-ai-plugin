# Citizen AI Accounts skill — troubleshooting

Symptoms and fixes for the connection to the `citizen-ai` MCP server. These steps work in every
app. The CitizenAI docs page for your app gives the app-specific steps.

Your app connects in one of two ways:

- **Setup link.** The setup stored a CitizenAI key in the MCP configuration of your app.
- **OAuth sign-in.** Your owner signed in to CitizenAI from the app, and the app keeps the access.

Never print the CitizenAI key, never send it in chat, and never ask your owner for it.

## The CitizenAI tools are not loaded

Some apps load MCP servers only when a session starts. Tell your owner to start a new session.
If the tools are still missing, your owner connects the app again: the setup link sends the
setup prompt again, and OAuth sign-in connects again in the app.

## `404 {"error":"unknown agent"}` on every MCP call

The stored CitizenAI key matches no agent. These are the causes:

- Your owner deleted the agent or connected it again, and the old key stays in your app.
- Your app points to a different CitizenAI server than the one that holds this agent.

Tell your owner to send the setup prompt again. On the approval page, your owner can connect the
existing agent again. The setup replaces the old key.

## `401 {"error":"missing bearer token"}`

No `Authorization` header reached the MCP server. With the setup link, tell your owner to send the
setup prompt again. With OAuth sign-in, tell your owner to connect again in the app.

## `401 {"error":"invalid_token"}`

The OAuth access stopped. Your owner revoked it on the dashboard, or your owner deleted the agent.
Tell your owner to connect again in the app and to select an agent.

## `429 {"error":"rate limited"}`

You sent too many requests in a short time. Wait, then call the tool again. Do not send the same
call many times.

## You answer "you have no accounts" or make up an answer

You answered from memory, or an MCP call failed and you did not see the error. Call
`citizenai_list_accounts` and use its result. A result, also an empty list, proves the connection.
If the call fails, report the error to your owner as written.

## Connection refused, or the CitizenAI server does not answer

Your app cannot reach the MCP URL. Check that the URL that setup gave is still in the MCP
configuration of your app. If it is correct, tell your owner that CitizenAI does not answer, and
try again later.
