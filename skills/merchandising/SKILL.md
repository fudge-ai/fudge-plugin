---
name: merchandising
description: "Help shoppers find products that belong together in a Shopify store: related-product and complementary recommendations, carousels, “complete the look” sets, bundles and offers, product finders, collection curation, and product data quality. Use when the merchant asks what to recommend alongside a product, how to build bundles or sets, or how to improve average order value."
---

# Merchandise products with Fudge

Start with `read_guide` for `merchandising/index.md`, the area overview, and follow its links to the guide that fits.

## Using these guides

Fudge's guides are the reference articles its own agent works from: criteria, examples and checklists for each kind of work. Find one with `search_guides`, or open one by path with `read_guide` (paths look like `seo/audit.md`, and guides link each other the same way). Adapt the one that fits the merchant's goal to the store; they describe outcomes and judgment, not a script to follow step by step.

- `.plans/`, `.playbooks/`, `.memory/`, `.brand/` and `.projects/` are the store's documents. Read them with `read_store_document`.
- Take numbers and report rows from `get_store_performance` (a `breakdown` gives queries, pages, channels and similar rows), Fudge's saved findings and recommendations from `get_store_insights`, an area's current state from `get_store_overview` with an `area`, and work from `list_work` and `read_work`.
- Where a guide inspects pages or the catalogue (`inspect_page`, `.entities/` records), use `check_page`, `capture_page`, `check_page_speed`, `check_catalog_data` and `search_catalog`.
- When you build in a draft, a guide's `file_view`, `file_edit`, `file_create`, `file_delete` and `grep_files` are `read_draft_file`, `edit_draft_file`, `write_draft_file`, `delete_draft_file` and `search_draft_files`, and `edit_entities` is `edit_draft_content`. Skip steps that name tools you don't have, such as `call_tool`, `agent_script` or a handoff to the Editor; they are internal to Fudge. If the merchant wants that outcome, describe it to Fudge with `message_fudge`. A `.skills/` path that `read_guide` can't open is a guide or tool contract Fudge uses while building.
- To run one of Fudge's eight reviews (SEO, AI search visibility, conversion, speed, landing page opportunities, design and brand, content and blog, offers and AOV), follow the review table in the manage-store skill.
- Storefront changes, whether Fudge builds them through `message_fudge` or you build them in a draft (see the manage-store skill), go live only after the merchant approves them in Fudge.
