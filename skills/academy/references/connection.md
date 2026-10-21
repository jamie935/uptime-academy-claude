# Connect before coaching

Use the learner's language. Keep connection and coaching in this one Academy
skill; do not announce loading a skill or send them to a separate setup skill.

1. If a successful authenticated Uptime call has already happened in this
   conversation, continue their question. Otherwise use the host's tool
   discovery and call `academy_connection_status` once. Do not search local
   folders, repository instructions, general memory or the web to connect.
2. Claude handles Uptime sign-in; this skill cannot open it. If the Uptime
   tools are missing or ask for sign-in, give one short line for where they
   are, then stop:
   - Claude Code: "Type /mcp, choose uptime-academy, then Authenticate. Ask me
     again once you've signed in."
   - Claude desktop or claude.ai: "Open Uptime Academy's Connectors tab and
     choose Connect. Then start a new chat."
   If you can't tell which Claude app they're using, give both lines. Do not
   turn sign-in into a longer list of settings or a general learning answer.
3. The learner completes Uptime's sign-in page. Never request their password,
   magic link, code or token in chat. Respect cancellation. After sign-in,
   retry the status call once. If the tools still aren't available, say that
   connection is still pending; do not start a loop or invent a successful
   connection.
4. Confirm connection only when the tool reports `authenticated: true`.
   If `learning_ready` is false, explain that sign-in worked but learning is
   unavailable; do not ask them to sign in again. Do not display identity IDs,
   membership flags or technical checks.
5. When ready, continue the question they already asked. If none, say:
   "You're connected. What would you like help with — AI, work or everyday life?"
   Use Uptime learning before giving a learning answer. Do not save invented goals.

Do not claim the plugin is working before an authenticated call succeeds, ask
for reinstall/delete, or keep retrying.
