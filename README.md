<div align="center">

<img src="assets/cover.png" alt="Amazon Seller Central through HeyMetra's MCP server" width="100%">

# Amazon Seller Central &times; HeyMetra

**Amazon sales, orders, inventory and fees, from Seller Central.**

Your orders live in Amazon Seller Central. What you spent to win them lives in your ad accounts. One question, both answers.

[![MCP Registry](https://img.shields.io/badge/MCP_Registry-com.heymetra%2Fheymetra-1f6feb)](https://registry.modelcontextprotocol.io/v0/servers/com.heymetra%2Fheymetra/versions)
[![Transport](https://img.shields.io/badge/transport-Streamable_HTTP-444)](https://modelcontextprotocol.io/)
[![Auth](https://img.shields.io/badge/auth-OAuth_2.1-444)](https://heymetra.com/security/)
[![Connector page](https://img.shields.io/badge/heymetra.com-amazon--seller--central-1f6feb)](https://heymetra.com/connectors/amazon-seller-central/)

```
https://mcp.heymetra.com/mcp
```

</div>

---

## Ask it things like

> How many units did I sell on Amazon last week, and for how much?

> Which FBA products are about to run out?

> What did Amazon charge me in fees last month?

No dashboard, no export, no query language. You ask in the assistant you already use and the answer comes back with the account it came from.

## Connect Amazon Seller Central

**1. Choose the Amazon store you sell in**

Choose Amazon Seller Central on the Connections screen and pick your store from the list, for example Turkey for Amazon.com.tr.

> HeyMetra works out the Seller Central address and the region from it, so there is no URL to type.

**2. Sign in to Seller Central and approve HeyMetra**

Amazon opens its own approval page. Sign in with your Seller Central account and approve HeyMetra. You come back here once it is done.

> It is the Seller Central login, not your shopping account on Amazon.

**3. Add HeyMetra to the assistant you use**

Claude, ChatGPT, Grok, Perplexity, Claude Code, Codex, Cursor or Antigravity. Your Amazon store answers there once it connects.

The same steps are on the docs page: [Amazon Seller Central setup guide](https://heymetra.com/docs/amazon-seller-central/).

## Then add HeyMetra to your assistant

Add HeyMetra once and it is there in every conversation. The address is the same everywhere:

```
https://mcp.heymetra.com/mcp
```

### One command

```bash
npx add-mcp https://mcp.heymetra.com/mcp
```

[`add-mcp`](https://www.npmjs.com/package/add-mcp) is a third-party installer that writes the configuration for Claude Code, Codex, Cursor, Antigravity, VS Code and seventeen other agents. It infers the name from the address, so the server lands as `heymetra`. Run against this endpoint before it was written here.

### Or by hand

<details>
<summary><b>Claude</b> — Settings → Customize → Connectors → Add custom connector</summary>

Paste the address above into Settings → Customize → Connectors → Add custom connector.

_On Team and Enterprise plans, an owner adds the connector for the whole organization under Organization settings → Connectors, and each member then connects to it._

Full walkthrough: [heymetra.com/mcp/claude/](https://heymetra.com/mcp/claude/)
</details>

<details>
<summary><b>ChatGPT</b> — chatgpt.com/plugins → + → Add custom MCP server</summary>

Paste the address above into chatgpt.com/plugins → + → Add custom MCP server.

_Add it on chatgpt.com in a browser, because the mobile app cannot add one. Every ChatGPT plan can, Free included. In a Business, Enterprise or Edu workspace, an admin or owner decides whether members can add custom MCP servers. ChatGPT needs the full address, including /mcp at the end._

Full walkthrough: [heymetra.com/mcp/chatgpt/](https://heymetra.com/mcp/chatgpt/)
</details>

<details>
<summary><b>Grok</b> — grok.com/connectors → New Connector → Custom</summary>

Paste the address above into grok.com/connectors → New Connector → Custom.

_On Grok Business and Enterprise, a team admin has to provision the connector in xAI's cloud console before members can use it._

Full walkthrough: [heymetra.com/mcp/grok/](https://heymetra.com/mcp/grok/)
</details>

<details>
<summary><b>Perplexity</b> — Plugins → Add custom → Connector → Add MCP connector → Remote</summary>

Paste the address above into Plugins → Add custom → Connector → Add MCP connector → Remote.

_In an organization, members can add a custom connector only after an admin turns on Allow members to add custom connectors, which is off by default._

Full walkthrough: [heymetra.com/mcp/perplexity/](https://heymetra.com/mcp/perplexity/)
</details>

<details>
<summary><b>Claude Code</b> — claude mcp add --transport http</summary>

```bash
claude mcp add --transport http heymetra https://mcp.heymetra.com/mcp
```

_You can also add the server to a .mcp.json file at the project root. Run /mcp in a session to sign in and to check that it connected._

Full walkthrough: [heymetra.com/mcp/claude-code/](https://heymetra.com/mcp/claude-code/)
</details>

<details>
<summary><b>Codex</b> — ~/.codex/config.toml</summary>

```toml
[mcp_servers.heymetra]
url = "https://mcp.heymetra.com/mcp"
```

_Codex reads the server from an [mcp_servers.<name>] section in config.toml, and you sign in with codex mcp login <name>._

Full walkthrough: [heymetra.com/mcp/codex/](https://heymetra.com/mcp/codex/)
</details>

<details>
<summary><b>Cursor</b> — ~/.cursor/mcp.json, or .cursor/mcp.json in a project</summary>

```json
{
  "mcpServers": {
    "heymetra": { "url": "https://mcp.heymetra.com/mcp" }
  }
}
```

_Cursor signs in to HeyMetra without a client ID or secret, so the server entry needs no auth block._

Full walkthrough: [heymetra.com/mcp/cursor/](https://heymetra.com/mcp/cursor/)
</details>

<details>
<summary><b>Antigravity</b> — ~/.gemini/config/mcp_config.json, or .agents/mcp_config.json in a project</summary>

```json
{
  "mcpServers": {
    "heymetra": { "serverUrl": "https://mcp.heymetra.com/mcp" }
  }
}
```

_Antigravity's documented key for the address is serverUrl, though it also accepts url._

Full walkthrough: [heymetra.com/mcp/antigravity/](https://heymetra.com/mcp/antigravity/)
</details>

## What it may and may not touch

Propose a change to this account. Nothing is sent until you approve it, and HeyMetra cannot undo it afterwards.

Permissions are switched on per connection, and one you leave off is a tool your assistant never sees.

| Permission | What it covers | Changes anything? |
|---|---|---|
| **Full account access** | Lets your assistant read anything in this account to answer your questions. The figures are the provider's own, not ones HeyMetra has checked. It can also propose changes: none is applied until you approve it, and HeyMetra cannot undo one afterwards. | Yes — every change waits for your approval |

<details>
<summary>What each permission lets an assistant do, in full</summary>

- Ask anything about this account and get the answer from its live data. Reads only, and the figures are the provider's own rather than ones HeyMetra has checked.
- Propose a change to this account. Nothing is sent until you approve it, and HeyMetra cannot undo it afterwards.
</details>

Anything that would change something comes back as a proposal you approve. Nothing is applied before your yes, and only on an account you connected with permission to change it. [How that works](https://heymetra.com/security/).

## When something goes wrong

<details>
<summary>Seller Central will not let you approve HeyMetra.</summary>

**Why:** Approving an app needs a Seller Central user allowed to manage apps. The account's primary user always is.

**Fix:** Sign in as the primary user, or ask them to give your user permission to manage apps, then connect again.

</details>

<details>
<summary>It connects, and the store you sell in is not listed.</summary>

**Why:** A different store was chosen. Amazon answers for the stores in the region of the one you picked.

**Fix:** Connect again and choose the store you sell in. Each store is its own connection.

</details>

## What HeyMetra reads from Amazon Seller Central

In beta. Choose the Amazon store you sell in, sign in to Seller Central and approve HeyMetra there; no key to copy. Then ask from your assistant about sales and units by day, week or month, orders, FBA inventory, and the fees and payouts Amazon reports. When you connect, you choose whether your assistant may also propose changes, such as a listing's price or quantity, and every change it proposes waits for your approval.

<details>
<summary>About Amazon Seller Central</summary>

Amazon Seller Central is where third-party sellers manage what they sell on Amazon’s marketplaces, from listings and orders to inventory and payouts.
</details>

## One connection, not seven

The reason to read Amazon Seller Central through HeyMetra rather than through a server that only knows Amazon Seller Central is everything else it can answer in the same breath:

**Ads** — [Google Ads](https://github.com/zeisoft/google-ads-mcp) · [Meta](https://github.com/zeisoft/meta-ads-mcp)

**Analytics** — [Google Analytics 4](https://github.com/zeisoft/google-analytics-4-mcp) · [Google Search Console](https://github.com/zeisoft/google-search-console-mcp) · [PostHog](https://github.com/zeisoft/posthog-mcp)

**Ecommerce** — [Trendyol](https://github.com/zeisoft/trendyol-mcp) · [n11](https://github.com/zeisoft/n11-mcp) · [Çiçeksepeti](https://github.com/zeisoft/ciceksepeti-mcp) · **Amazon Seller Central** · [ikas](https://github.com/zeisoft/ikas-mcp) · [WooCommerce](https://github.com/zeisoft/woocommerce-mcp)

**Revenue & CRM** — [Stripe](https://github.com/zeisoft/stripe-mcp) · [Zoho CRM](https://github.com/zeisoft/zoho-crm-mcp) · [Zoho SalesIQ](https://github.com/zeisoft/zoho-salesiq-mcp) · [Zoho Marketing Automation](https://github.com/zeisoft/zoho-marketing-automation-mcp)

**Mobile** — [AppsFlyer](https://github.com/zeisoft/appsflyer-mcp) · [RevenueCat](https://github.com/zeisoft/revenuecat-mcp) · [Adapty](https://github.com/zeisoft/adapty-mcp) · [App Store Connect](https://github.com/zeisoft/app-store-connect-mcp)

**Work** — [Jira](https://github.com/zeisoft/jira-mcp)

**Channels** — [Slack](https://github.com/zeisoft/slack-mcp) · [Telegram](https://github.com/zeisoft/telegram-mcp)

The full catalogue is at [heymetra.com/connectors/](https://heymetra.com/connectors/).

## Links

- [Amazon Seller Central connector page](https://heymetra.com/connectors/amazon-seller-central/)
- [Amazon Seller Central setup guide](https://heymetra.com/docs/amazon-seller-central/)
- [HeyMetra](https://heymetra.com/) — what the product is
- [Setup for every assistant](https://heymetra.com/mcp/)
- [Security and limits](https://heymetra.com/security/)
- [Pricing](https://heymetra.com/pricing/)
- [HeyMetra's own repository](https://github.com/zeisoft/heymetra-mcp)

---

<sub>Built by <a href="https://zeisoft.com">Zeisoft</a>, who make HeyMetra. Not affiliated with Amazon Seller Central. This README is generated from HeyMetra's live connector catalogue and refreshed daily; corrections are welcome as issues.</sub>
