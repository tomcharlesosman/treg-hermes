# Treg for Hermes Agent

<img src="https://raw.githubusercontent.com/superdesigndev/treg/4b4d16db49f4138552022771994600f4daf21a2b/src/treg/web/media/brand/logo-400.png" alt="Treg" width="80" height="80">

Use one Hermes connection to find a tool by task, inspect its inputs and price, and call it with your team's permissions. Search the web and SEO data, research people and companies, publish through connected accounts, or generate images, video and audio. Tools your team registered are available through the same connection.

## Install and try a free lookup

1. Install the package with `hermes plugins install tomcharlesosman/treg-hermes`, then run `hermes plugins enable treg`.
2. Put a scoped Treg team token in your Hermes profile's `TREG_TOKEN` secret. On Desktop, open the Treg plugin settings and set **Treg team token**. Start a new Hermes session.
3. Ask: **Use Treg’s catalog_get to inspect treg.web.search. Show its required search input and its variable pricing note. Stop after the lookup.**

The returned card identifies `treg.web.search`, gives a POST example with the `q` input and explains how the chosen provider affects the price. Looking up the card is free.

## Workflows

| Ask Hermes | What Treg contributes |
| --- | --- |
| Research a company from its domain and cite the sources. | Search for web and company enrichment tools, compare their price and inputs, then combine results around the same domain. |
| Prepare a social post for a connected account. | Discover the publishing tool, confirm the destination and draft, then submit the approved content with the team's connection. |
| Generate a short product video from an approved prompt. | Inspect available models and costs, submit the selected generation job and retrieve its result. |
| Find the tools specific to our team. | Use `my_tools` to list registered tools visible to the token. Team permissions determine which operations Hermes can call. |

## Data, permissions and billing

Hermes sends the bearer token and requested inputs over HTTPS to `https://treg.to/mcp/`. Discovery sends queries or tool IDs to Treg. Execution can send supplied inputs and media to the selected provider, publish content, change connected accounts, or spend the team's prepaid balance. Read the tool card before execution. Connected accounts can incur their own provider charges. Treg keeps downstream provider credentials on its server.

This portable package contains a server declaration and a workflow skill. It launches no local command or background process and adds no telemetry. Hermes resolves the token from its own environment or profile secret store. The server is marked `untrusted` so Hermes applies its write-tool approval policy. Tools and prices are served live by Treg. The plugin commit pins the client configuration and skill.

[Product and tool reference](https://treg.to/llms.txt) · [Integration guide](https://treg.to/integrate.md) · [Catalog](https://treg.to/catalog)
