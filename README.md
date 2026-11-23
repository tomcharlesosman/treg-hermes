# Treg for Hermes Agent

<img src="https://raw.githubusercontent.com/superdesigndev/treg/4b4d16db49f4138552022771994600f4daf21a2b/src/treg/web/media/brand/logo-400.png" alt="Treg" width="80" height="80">

Treg is **OpenRouter for agent tools**. From Hermes, you can use Treg to access **4,200+ tools** through one connection, alongside your team’s own tools. Ask Hermes to check search rankings and backlinks, enrich a company profile, publish a post through a connected account, or generate an image, video or voiceover. Hermes can compare providers and inspect each tool’s inputs and price before calling it. [Explore the Treg catalog](https://treg.to/catalog)

## Connect from Hermes

Use one setup per Hermes profile. Both connect to the same hosted Treg catalog.

**Connect directly today.** With MCP support enabled in Hermes, run:

```sh
hermes mcp add treg --url https://treg.to/mcp/ --auth oauth
```

Authorize your Treg account in the browser and start a new Hermes session.

**Install the marketplace plugin once listed.** On Hermes 0.23.3 or later with MCP support, run:

```sh
hermes plugins install treg --enable
```

Open the Treg plugin settings, set **Treg team token** to a scoped `TREG_TOKEN`, and start a new session. The plugin adds a Treg workflow skill and configures Hermes to request approval for write-capable calls.

## Try a free lookup

Ask Hermes: **Use Treg’s catalog_get to inspect treg.web.search. Show the required search input and the pricing note. Stop after the lookup.**

The returned card identifies `treg.web.search`, gives a POST example with the `q` input and explains how the chosen provider affects the price. Looking up the card is free.

## Workflows

| Ask Hermes | What Treg contributes |
| --- | --- |
| Research a company from its domain and cite the sources. | Search for web and company enrichment tools, compare their price and inputs, then combine results around the same domain. |
| Prepare a social post for a connected account. | Discover the publishing tool, confirm the destination and draft, then submit the approved content with the team's connection. |
| Generate a short product video from an approved prompt. | Inspect available models and costs, submit the selected generation job and retrieve its result. |
| Find the tools specific to our team. | Use `my_tools` to list registered tools visible to the token. Team permissions determine which operations Hermes can call. |

## Data, permissions and billing

When using the plugin, Hermes sends the scoped team token and requested inputs over HTTPS to `https://treg.to/mcp/`. Discovery sends queries or tool IDs to Treg. Execution can send supplied inputs and media to the selected provider, publish content, change connected accounts, or spend the team's prepaid balance. Read the tool card before execution. Connected accounts can incur their own provider charges. Treg keeps downstream provider credentials on its server.

This portable package contains a server declaration and a workflow skill. It launches no local command or background process and adds no telemetry. Hermes resolves the token from its own environment or profile secret store. The server is marked `untrusted` so Hermes applies its write-tool approval policy. Tools and prices are served live by Treg. The plugin commit pins the client configuration and skill.

[Product and tool reference](https://treg.to/llms.txt) · [Integration guide](https://treg.to/integrate.md) · [Catalog](https://treg.to/catalog)
