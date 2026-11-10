# My Budget Control for AI assistants

![My Budget Control](assets/mbc-app-icon-1024.png)

Official Cenulinq connector configuration for the existing My Budget Control MCP service: **https://cenulinq.com/mcp**.

View monthly totals from your own entered budget records, prepare one expense proposal for separate human confirmation on MBC, and check its approval status. These are budget records, not a verified bank balance. No bank payments, banking access, subscription changes, deletion or bulk editing.

## Account and privacy

Use your own confirmed MBC account, age 18+, with the existing applicable trial/subscription access. Sign in and approve OAuth on cenulinq.com. Grants last 15 minutes without background refresh; reconnect after expiry. Each proposed expense requires a separate confirmation in MBC. Keep your AI platform’s tool approvals enabled. Never paste a password or token into an assistant, configuration or public issue. No shared API key is needed.

Native clients use a strict localhost callback. A localhost callback does not verify the client publisher; MBC displays that limitation before consent. Only connect from the assistant you intended.

## Install

### Gemini CLI

`gemini extensions install https://github.com/cenulinq/mbc-ai-connectors`

Authenticate the my-budget-control MCP server through `/mcp auth my-budget-control`. Keep tool approvals enabled. Gemini CLI 0.67.0 completed real OAuth, monthly budget reading, an identical proposal retry and status checking with the fixed fictitious MBC account. The proposal remained pending and the budget stayed unchanged. This is Gemini CLI, not a listing in the consumer Gemini app.

The test used Google AI Studio free-tier API access with billing disabled and an available Flash-Lite model. Google Code Assist individual sign-in was refused by Google for this CLI; it is not a demonstrated route. Your Google eligibility, model availability and quotas can differ. Configure your own API key privately through the official Gemini CLI instructions; never add it to this repository, chat, or MBC configuration. No shared MBC key is needed.

### Cursor

Install this repository as a local/custom plugin using Cursor’s documented plugin workflow, or add the endpoint as a custom HTTP MCP server. The portable root plugin.json and mcp.json follow the Agent Plugins 1.0 specification; the .cursor-plugin manifest supplies Cursor metadata and the current logo. A marketplace review is a separate step.

### VS Code / GitHub Copilot

GitHub Copilot CLI 1.0.108 completed actual OAuth, monthly reading, a repeated expense proposal and status checking on Copilot Free. The same pending proposal was returned twice and no budget entry was added. Use `/mcp add`, HTTP URL https://cenulinq.com/mcp and the three explicit tools in configs/copilot-mcp.json. Keep individual tool approvals enabled. Sign in to your own eligible GitHub Copilot account and then approve the separate MBC account connection.

VS Code uses a different `servers` format (configs/vscode-mcp.json); the CLI uses `mcpServers` with an explicit `tools` list (configs/copilot-mcp.json). Merge only the server entry into an existing configuration. The tested client is GitHub Copilot CLI: no claim of consumer Copilot, Microsoft 365 Copilot, VS Code OAuth testing or Microsoft agent-directory publication.

### Other remote MCP clients

Perplexity: the free account imported the skill but skipped the MCP server (zero connectors). The owner declined a paid upgrade; actual MBC account access remains unverified.

### Grok

In Grok, open Settings → Connect Apps → Add a custom connector. Set the name to My Budget Control and the server URL to `https://cenulinq.com/mcp?auth=required`. Leave custom headers blank. This auth-first URL uses the same MBC account service and scopes as the canonical endpoint; it prompts Grok to complete OAuth during setup. Approve your own MBC account connection on cenulinq.com. A generic Connected badge alone is not account-access proof.

Actual Grok Free OAuth, budget reading, two identical expense-proposal calls and status checking passed with the fixed fictitious account. Both calls returned the same pending draft; no budget entry was added. The exact observed Grok callback is permitted; callback lookalikes, changed paths, query strings and fragments remain refused. This is a custom connector, not a public Grok catalogue listing.

A compatible client needs Streamable HTTP, OAuth discovery, dynamic client registration, S256 PKCE, a resource indicator and a supported exact callback. Client support is not equivalent to an official marketplace listing. Hosted clients need an individually verified callback; unsupported callbacks fail closed.

## Examples

- Show my MBC monthly totals for November 2026.
- Prepare a planned expense; ask me for its amount, date, description and category.
- Check whether the expense I reviewed was recorded.

Use the locale and currency of your account. The confirmation UI supports the 15 existing MBC app languages. The SDK returns minorUnitDigits: EUR 12.34 is 1234 minor units; JPY 123 is 123. Preparing a proposal is not a booking; only status `recorded` means it was recorded. Reuse one requestKey for identical retries.

## Publication and tests

The remote server is listed in the public MCP Registry as `com.cenulinq/my-budget-control@1.0.0`. Claude has approved and published its community listing, and the public catalogue entry has been visually confirmed. Other marketplace approvals are reported only after their own readback.

The server has passed 461 isolated/static security and compatibility checks and 4 live anonymous protocol checks. Actual Claude, Gemini CLI, GitHub Copilot CLI and Grok OAuth, budget reading, expense preparation and status were verified with a fictitious account. Gemini, Copilot and Grok retries returned the same pending draft without adding a budget entry. The optional auth-first MCP discovery mode retains the same account authentication and canonical resource. This does not claim every client has been tested or publicly listed. No customer records or credentials are included in this repository.

## Help

[Connection guide](https://cenulinq.com/mbc-ai/) · [Privacy](https://cenulinq.com/mbc-ai/privacy.html) · [Terms](https://cenulinq.com/mbc-ai/terms.html) · [Support](https://cenulinq.com/mbc-ai/support.html)

Contact info@cenulinq.com for support or security concerns. Do not include credentials or budget details in public GitHub issues.
