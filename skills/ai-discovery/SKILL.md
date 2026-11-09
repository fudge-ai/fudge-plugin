---
name: ai-discovery
description: "Help a Shopify store get found, cited and recommended in AI answers such as ChatGPT, Claude, Gemini and Perplexity: clear product and brand facts, answerable product pages, comparisons and FAQs, structured data, llms.txt, and measuring AI mentions, citations and referral traffic. Use when the merchant asks how shoppers find them through AI assistants or what their AI traffic shows."
---

# Get recommended in AI answers with Fudge

Make accurate store knowledge and useful answers easy to find, understand and cite. Start from customer questions, product distinctions, credible expertise and existing coverage, not an arbitrary content quota.

Read `get_store_overview` (area ai-discovery), `get_store_insights` (area ai-discovery) and relevant .plans before proposing work. Use seo/index.md for crawling/indexing/search intent, content/quality.md for supported claims and content/structured-content.md for reusable facts. Read relevant .playbooks for ongoing work; a one-off improvement may be sufficient.

Useful tactics include direct answers, explanatory comparisons, original demonstrations, clear product/entity facts, accessible HTML and supported structured data. They are hypotheses to adapt and measure, not ranking guarantees. /llms.txt and /agents.md can describe a brand; do not sell them as proven ranking levers.

Distinguish a sampled mention, a citation, an attributable referral and a purchase. Record model/query/date/scope for samples; visibility varies across prompts and time. Referral analytics miss untracked or unattributed visits and cannot prove all AI influence. Never turn missing data into zero or a causal uplift claim. Use report/evidence scope, observation dates and source links.

## Using these guides

Fudge's guides are the reference articles its own agent works from: criteria, examples and checklists for each kind of work. Find one with `search_guides`, or open one by path with `read_guide` (paths look like `seo/audit.md`, and guides link each other the same way). Adapt the one that fits the merchant's goal to the store; they describe outcomes and judgment, not a script to follow step by step.

- `.plans/`, `.playbooks/`, `.memory/`, `.brand/` and `.projects/` are the store's documents. Read them with `read_store_document`.
- Take numbers and report rows from `get_store_performance` (a `breakdown` gives queries, pages, channels and similar rows), Fudge's saved findings and recommendations from `get_store_insights`, an area's current state from `get_store_overview` with an `area`, and work from `list_work` and `read_work`.
- Where a guide inspects pages or the catalogue (`inspect_page`, `.entities/` records), use `check_page`, `capture_page`, `check_page_speed`, `check_catalog_data` and `search_catalog`.
- When you build in a draft, a guide's `file_view`, `file_edit`, `file_create`, `file_delete` and `grep_files` are `read_draft_file`, `edit_draft_file`, `write_draft_file`, `delete_draft_file` and `search_draft_files`, and `edit_entities` is `edit_draft_content`. Skip steps that name tools you don't have, such as `call_tool`, `agent_script` or a handoff to the Editor; they are internal to Fudge. If the merchant wants that outcome, describe it to Fudge with `message_fudge`. A `.skills/` path that `read_guide` can't open is a guide or tool contract Fudge uses while building.
- To run one of Fudge's eight reviews (SEO, AI search visibility, conversion, speed, landing page opportunities, design and brand, content and blog, offers and AOV), follow the review table in the manage-store skill.
- Storefront changes, whether Fudge builds them through `message_fudge` or you build them in a draft (see the manage-store skill), go live only after the merchant approves them in Fudge.
