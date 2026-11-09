---
name: seo
description: "Plan and improve a Shopify store’s SEO with Fudge: search intent and keyword research, indexing and sitemaps, titles and meta descriptions, schema and structured data, buying guides, blog articles and collection copy, and why pages gained or lost Google clicks. Use when the merchant asks about Google rankings, organic traffic, Search Console, keywords, content to write, or an SEO audit."
---

# Grow organic search traffic with Fudge

Two parallel tracks with overlapping tactics: traditional search (Google, Bing) and AI search (ChatGPT/ChatGPT Shopping, Perplexity, Google AI Overviews & AI Mode). On a Shopify store the same structural work — clean crawlable HTML, accurate feed data, intent-matched content — feeds both.

Read `get_store_overview` (area seo), `get_store_insights` (area seo) and .plans for current store context; .playbooks exposes reusable workflows. AI-specific judgment lives in ai-discovery/index.md.

## Cross-phase invariant
Search and AI systems do not all render client JavaScript reliably. Anything that matters for ranking or citation — specs, Q&A, descriptions, reviews — must be available in the server HTML, with JavaScript used only to enhance it.

## Keyword evidence
Use `get_keyword_metrics` to verify exact terms, `find_keyword_ideas` to generate long-tails containing a seed, `find_keyword_ideas` with a broader seed for broad related-term discovery, `get_search_results` to judge winnability from who ranks, and `get_ranked_keywords` on the competitor’s domain and this store’s, for what a competitor ranks for that this store does not (browse seo/index.md for each exact tool reference; pass the explicit target country as location). These reads own numeric keyword evidence — never take volume, difficulty, CPC, or traffic figures from your own web search, and never estimate them. Use web research only for qualitative competitor angles, product facts, and article substance.

Solve a real reader task with accurate, useful content. Never invent evidence or experience. Check finished claims and metadata, preserve uncertainty and leave drafts for merchant review. content/quality.md owns factual standards and seo/evidence.md owns case-study evidence; neither content volume nor AI production guarantees rankings.

Read `evidence.md` for sourced AEO case studies and limits, and `content/quality.md` for Google policy and post-draft review. Read `knowledge.md` for technical/on-page/AI-visibility principles; `content.md` for query-family research, opportunity comparison, utility, and routing; `weekly-cycle.md` for SEO Content Engine recurring execution; `measurement.md` for performance analysis; `entities.md` for routine entity SEO; `agents-md.md` to customize /agents.md · /llms.txt; `audit.md` for a structured audit.
## Related guidance
- `seo/evidence.md` — choosing AEO tactics, explaining what has worked, or citing measured case-study results without overstating them
- `seo/plan-template.md` — creating a new SEO Content Engine setup plan; copy to .plans/seo-content/plan.json
- `seo/weekly-cycle.md` — executing one recurring SEO Content Engine occurrence
- `seo/knowledge.md` — the technical, on-page, schema, and AI-visibility principles + the structured-content plays this store unlocks — applied when building or advising
- `seo/content.md` — researching query families and reader jobs, comparing opportunities, choosing utility and format, or checking keyword-data provenance
- `seo/measurement.md` — weekly reflection, performance review, opportunity replenishment, refresh, consolidation, retirement, or AI-visibility sampling
- `seo/entities.md` — setting SEO on an entity (create or accepted edit) — per-field best values, per-entity plays, and choosing the target keyword/intent
- `seo/agents-md.md` — customizing /agents.md · /llms.txt (theme templates/) — brand-framing, not a ranking lever
- `seo/audit.md` — running a structured SEO + AI-visibility audit and presenting findings

## Using these guides

Fudge's guides are the reference articles its own agent works from: criteria, examples and checklists for each kind of work. Find one with `search_guides`, or open one by path with `read_guide` (paths look like `seo/audit.md`, and guides link each other the same way). Adapt the one that fits the merchant's goal to the store; they describe outcomes and judgment, not a script to follow step by step.

- `.plans/`, `.playbooks/`, `.memory/`, `.brand/` and `.projects/` are the store's documents. Read them with `read_store_document`.
- Take numbers and report rows from `get_store_performance` (a `breakdown` gives queries, pages, channels and similar rows), Fudge's saved findings and recommendations from `get_store_insights`, an area's current state from `get_store_overview` with an `area`, and work from `list_work` and `read_work`.
- Where a guide inspects pages or the catalogue (`inspect_page`, `.entities/` records), use `check_page`, `capture_page`, `check_page_speed`, `check_catalog_data` and `search_catalog`.
- When you build in a draft, a guide's `file_view`, `file_edit`, `file_create`, `file_delete` and `grep_files` are `read_draft_file`, `edit_draft_file`, `write_draft_file`, `delete_draft_file` and `search_draft_files`, and `edit_entities` is `edit_draft_content`. Skip steps that name tools you don't have, such as `call_tool`, `agent_script` or a handoff to the Editor; they are internal to Fudge. If the merchant wants that outcome, describe it to Fudge with `message_fudge`. A `.skills/` path that `read_guide` can't open is a guide or tool contract Fudge uses while building.
- To run one of Fudge's eight reviews (SEO, AI search visibility, conversion, speed, landing page opportunities, design and brand, content and blog, offers and AOV), follow the review table in the manage-store skill.
- Storefront changes, whether Fudge builds them through `message_fudge` or you build them in a draft (see the manage-store skill), go live only after the merchant approves them in Fudge.
