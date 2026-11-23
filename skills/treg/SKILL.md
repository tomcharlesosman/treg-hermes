---
name: treg
description: Find live data, connected-account actions, media generation and team tools through Treg. Inspect a tool's inputs and price before using it.
---

Start with `catalog_search` for the user's task. Use `my_tools` when the user asks about their team's registered tools. Inspect the selected endpoint with `catalog_get`. Read the input schema, pricing notes, execution method and account requirements. A routed endpoint can have variable pricing even when its base price is zero.

For a free first run, inspect `treg.web.search` with `catalog_get` and report the input and pricing note. Stop after returning the card.

For a company brief, find web search and company enrichment, use the company domain as the join, and cite source URLs from the results. For publishing, confirm the destination account and exact post. For a generation job, confirm the prompt, output and expected cost, then use the execution and result tools specified for that endpoint. Send only the inputs the user intended to share. Respect Hermes approvals and the team's permissions and spending limits.
