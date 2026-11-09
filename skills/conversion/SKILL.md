---
name: conversion
description: "Find and remove what stops a Shopify store’s visitors from buying: product page and checkout obstacles, mobile usability, shopper confidence and trust, size guides, product finders and quizzes, popups and email capture, offers and landing pages, and a structured conversion (CRO) audit. Use when the merchant asks why visitors don’t buy, how to raise conversion rate or add-to-carts, or what to test."
---

# Improve conversion with Fudge

Improve the customer's ability and confidence to complete a useful action. Read `get_store_overview` (area conversion), `get_store_insights` (area conversion) and relevant work before suggesting changes. Existing evidence, observed friction and the store's goals matter more than generic benchmarks.

knowledge.md offers decision principles; audit.md scopes an investigation. Suggest custom changes grounded in the store. Fudge has no premade template catalogue. No guaranteed uplift or required count of fixes.
## Related guidance
- `conversion/knowledge.md` — the CRO principles, awareness levels, Shopify levers, benchmarks — applied when building or advising
- `conversion/audit.md` — running a structured CRO audit and presenting findings

## Using these guides

Fudge's guides are the reference articles its own agent works from: criteria, examples and checklists for each kind of work. Find one with `search_guides`, or open one by path with `read_guide` (paths look like `seo/audit.md`, and guides link each other the same way). Adapt the one that fits the merchant's goal to the store; they describe outcomes and judgment, not a script to follow step by step.

- `.plans/`, `.playbooks/`, `.memory/`, `.brand/` and `.projects/` are the store's documents. Read them with `read_store_document`.
- Take numbers and report rows from `get_store_performance` (a `breakdown` gives queries, pages, channels and similar rows), Fudge's saved findings and recommendations from `get_store_insights`, an area's current state from `get_store_overview` with an `area`, and work from `list_work` and `read_work`.
- Where a guide inspects pages or the catalogue (`inspect_page`, `.entities/` records), use `check_page`, `capture_page`, `check_page_speed`, `check_catalog_data` and `search_catalog`.
- When you build in a draft, a guide's `file_view`, `file_edit`, `file_create`, `file_delete` and `grep_files` are `read_draft_file`, `edit_draft_file`, `write_draft_file`, `delete_draft_file` and `search_draft_files`, and `edit_entities` is `edit_draft_content`. Skip steps that name tools you don't have, such as `call_tool`, `agent_script` or a handoff to the Editor; they are internal to Fudge. If the merchant wants that outcome, describe it to Fudge with `message_fudge`. A `.skills/` path that `read_guide` can't open is a guide or tool contract Fudge uses while building.
- To run one of Fudge's eight reviews (SEO, AI search visibility, conversion, speed, landing page opportunities, design and brand, content and blog, offers and AOV), follow the review table in the manage-store skill.
- Storefront changes, whether Fudge builds them through `message_fudge` or you build them in a draft (see the manage-store skill), go live only after the merchant approves them in Fudge.
