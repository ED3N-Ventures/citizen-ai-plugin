# Browser work and provider keys

## Cloud browser contract

For account-backed provider actions, use the `citizenai_browser_*` MCP tools of the CitizenAI
server. Do not create ad-hoc Playwright scripts or a provider-specific browser.

CitizenAI owns the cloud browser profile, the session, the credential protection, and the live
browser link. Reuse the same session for the complete task, and call `citizenai_browser_close`
when the task ends. The link stops working when the session ends. Do not send `watch_url`
after you call `citizenai_browser_close`.

Call `citizenai_browser_read` before `citizenai_browser_ask_owner`. Request the owner
only when the inspection proves a private owner-only step. Then call `citizenai_browser_read`
with `wait_seconds` until the page changes, and resume.

## Typing secrets

For passwords, OAuth tokens, API keys, access keys, or any secret-bearing field, ask the owner
to enter it on the live browser page. Call `citizenai_browser_ask_owner` only after an inspection
proves the step. Never pass a raw secret through a browser tool argument or chat.

If an action needs a key CitizenAI does not store yet, ask the owner to sign in on the live browser
page instead of asking the owner for the key.

## Provider API/access key workflow

Do not generate or reveal a provider key unless there is a secure destination: the CitizenAI
credential store, a provider setting that consumes it directly, or a trusted service skill that
accepts it without echoing it. With no secure destination, stop before generating and say so.

Once a key is visible in the UI, treat the page as secret-bearing: do not inspect, screenshot, extract,
or otherwise echo page text into the transcript. Never paste a new key into tool arguments, commands,
files, or messages. Confirm with non-secret status text only —
"API key generated and stored", or "API key generated but requires a secure destination before use."
