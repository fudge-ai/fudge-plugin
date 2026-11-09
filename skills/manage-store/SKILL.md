---
name: manage-store
description: Brief a Shopify merchant on their store with Fudge, measure how the store or a product is doing, review Fudge's findings and work, ask Fudge to build or revise pages, articles and other drafts, or build and edit them yourself in a Fudge draft, and follow that work through to the merchant's publish review, keep the store's Plans and design guide up to date, list the audits Fudge can run and run its free store diagnostics, and find design references in Fudge's Lookbook. Use when the merchant asks what is happening in their store, how something is selling or performing, what needs their review, what to work on next, to build or change something with Fudge or in a draft, to publish a draft, to remember a decision, how other stores handle a page or component, which audits are available, or to check the store's AI readiness, catalog data or Knowledge Base answers.
---

# Manage my store with Fudge

Fudge is the merchant's growth team for their Shopify stores. It keeps each store's priorities, Plans, work, findings and measurements. Read them before advising; never guess store facts.

## Store

When several stores are connected and the merchant has not said which one, ask, then pass `store` on every store tool. Keep using the store that a ref came from. To add another store, call `connect_store` and give the merchant its link. Before any store is connected, design references, page checks and free reports work on a storefront's `domain`.

## Brief

1. Call `get_store_overview` for the business context, standing memory, Google connection, work needing the merchant (`needsYou`), Plans, recommendations and recent results.
2. Call `get_store_insights` for saved findings and recommendations (pass a `ref` to read one in full), and `get_store_performance` for the numbers you cite. For one area, such as SEO or conversion, `get_store_overview` with `area` gives its findings, Plans, work and headline numbers.
3. Lead with what needs the merchant: drafts to review, questions waiting, and stuck or failed work. Call `read_work` before describing an item's state; its `execution.status` is live, while list statuses can lag.
4. Then results that changed, then the next useful step from an active Plan or recommendation.
5. Show the items you mention with `show_resources` so the merchant can open them in Fudge. The rows appear above your reply, so don't list them again in text.

When the merchant asks to open Fudge or see their store at a glance, call `open_fudge_home`: it shows what needs them, the next step and the four growth areas, so keep your reply short.

When the merchant wants a brief every day or week, offer to schedule it in this assistant, using its own scheduled tasks, with a prompt such as “Brief me on <store> with Fudge”. Create it only after they agree and choose when; if this assistant can't schedule tasks, tell them to ask any time.

`get_store_performance` takes a product, collection, page, article or URL as `subject`, plain metric names for headline values, and a `breakdown` for ranked rows such as Search Console queries, landing pages, channels or AI assistants. When it lists several matching items, ask which one. Google Analytics, Search Console and Shopify numbers are separate measurements of different things; never add them together or treat one as the cause of another. State each measurement's period and source. Say when data is missing or Google is not connected. Recommendations and findings are Fudge's reviewed work; label your own reading of the numbers as a hypothesis.

## Plan and review work

- `list_work` finds work across Fudge, including work started in Fudge itself. `view: "needs_you"` lists exactly what Home’s “Needs you” shows; `read_work` adds `waitingFor`, the question Fudge is waiting on.
- `read_work` with a `ref` returns live execution, progress, the latest result, and draft or publication state with preview and live links. With `about` it returns what changed on a page, product, discount or the whole store (see Remember).
- `list_store_audits` lists the three diagnostics and eight agent reviews with any existing result. Listing starts nothing.
- Run a diagnostic with its free run tool (`run_ai_readiness_check`, `run_catalog_data_audit`, `run_knowledge_base_check`). It returns a run already in progress or a result from the last day instead of starting another; pass `fresh: true` only when the merchant wants a new run after changing the store. Reports take a few minutes: when one is still running, tell the merchant and read it later with `get_store_audit_result`. Share the report link and summarize the score and top fixes.

### Run a review

You run the eight reviews yourself, with the guide below and Fudge's data tools; they don't use Fudge's credits. First check `list_store_audits` for a recent review Fudge already ran, and `get_store_insights` for its saved findings on the same topic, so you build on them rather than repeat them. Open the guides with `read_guide`, gather the evidence, then report findings ranked by impact, each with its evidence (page, numbers with period and source, screenshot) and a concrete fix. Keep it to what the store's own data supports.

| Review | Guides | Data to gather |
| --- | --- | --- |
| SEO | `seo/audit.md` | `check_store_technical`; `check_page` for the homepage and one product, collection and article; `check_catalog_data`; `get_store_performance` with `search_queries` and `search_pages`; `get_ranked_keywords` |
| AI search visibility | `seo/audit.md` (its AI-visibility checks) | `check_store_technical` (AI crawler rules, llms.txt); `check_page` for structured data; `check_catalog_data`; `get_store_performance` with `ai_assistants` and `ai_landing_pages`; the free `run_ai_readiness_check` |
| Conversion | `conversion/audit.md` | `capture_page` on the homepage, a top product and a collection; `get_store_performance` with `landing_pages` and `devices`; `list_offers`; `search_design_references` for better patterns |
| Speed and Core Web Vitals | `workspace/auditing.md` | `check_page_speed` on the homepage, a product and a collection (find them with `search_catalog`); `capture_page` to see what loads first |
| Landing page opportunities | `workspace/next-steps.md`, `content/formats.md` | `search_catalog`; `get_store_performance` with `search_queries` and `landing_pages`; `get_keyword_metrics` or `find_keyword_ideas` for demand |
| Design and brand | `workspace/auditing.md`, `storefront/design.md` | `get_design_guide`; `capture_page` on the homepage, a product and a collection, desktop and mobile; `search_design_references` |
| Content and blog | `workspace/auditing.md`, `seo/content.md`, `blog/index.md` | `search_catalog` for articles and pages; `get_store_performance` with `search_pages`; `find_keyword_ideas`; `get_search_results` for what ranks today |
| Offers and AOV | `workspace/auditing.md`, `discounts-bundles/index.md`, `discounts-bundles/presentation.md`, `discounts-bundles/bundles/index.md` | `list_offers`; `get_store_performance` with `products` and `discount_codes`; `capture_page` on a product page |

- The keyword tools (`get_keyword_metrics`, `find_keyword_ideas`, `get_search_results`, `get_ranked_keywords`) have a daily limit per store. Use them to size a shortlist, not for every idea.
- `check_catalog_data` returns a summary first; ask for offenders by `type` only when you will name them.
- End by asking which findings the merchant wants to act on. Record the agreed ones as a Plan with `create_plan`, one milestone per fix with what it should change, and offer to have Fudge build them with `message_fudge`.

### Delegate to Fudge

When the merchant wants Fudge to build or change something (a landing page, an article, a product finder, a storefront change) or a step needs Fudge's own tools, agree the brief first, then call `message_fudge` with the whole brief: the goal, the page or products, decisions already made, and any Lookbook ref or Plan it follows. Omit `ref` for new work; pass the work's ref to continue it, answer what it is `waitingFor`, or revise its draft. Give every new message its own `requestId` and reuse it only to retry that same message.

- Fudge works in the background and uses the store's Fudge credits. Tell the merchant it has started and show the work with `show_resources`.
- When `read_work` shows `waitingFor`, Fudge is asking the merchant. Put the question to them in your own words and send their answer with `message_fudge`. Answer for them only when they already decided it in this conversation; never make up product facts, prices or choices Fudge asked them to confirm.
- Follow progress with `read_work(ref, waitSeconds: 30)` rather than calling it in a tight loop. A build takes minutes; if the merchant moves on, check again when they come back.
- Fudge's conversation often passes a build to an editor. When `read_work` shows `continuedIn`, the editor now owns that work and the conversation won't report back: follow and revise the `continuedIn` ref from then on. `delegated` lists every piece of work the conversation started; those with `reportsBack: true` report to the conversation when they finish.
- For changes to an existing draft, pass its `fudge://project/…` ref. Fudge delivers the message to whichever of its agents owns that work.
- While Fudge is working, `delivery: "steer"` (the default) reaches it at its next step, for corrections like “use the darker hero instead”; `delivery: "queue"` waits until it finishes, for follow-ups like “afterwards, draft a second version”.
- `stop_work` with the `runId` from `read_work` stops only that run. Saved drafts stay.
- Keep using the ref `message_fudge` returned. If you no longer have it, `list_work` lists everything Fudge is working on under `ongoing`, checked live; never tell the merchant nothing is running without checking it.
- `needsMerchantInFudge` means only the merchant can unblock the work, in Fudge: choosing a Fudge plan, confirming several pieces of work at once, or adding credits. Give them its `note` and `href`. Once the store has a plan, Fudge continues the build by itself; after credits are added, ask Fudge to continue.

### Build in a draft yourself

You can also make storefront and catalogue changes yourself, in a Fudge draft. Fudge copies the store's theme into the draft, keeps its preview and its record of every change, and the merchant still reviews and publishes in Fudge. It uses none of the store's Fudge credits. Build it yourself when the merchant asks you to, or for a precise change you can make well (copy, SEO fields, a small section, a template tweak); offer `message_fudge` for larger builds that need Fudge's design, imagery and verification.

1. `start_draft` with a short title and the storefront `page` the work is about. To change existing work, pass its ref as `work`: you get its open draft, or a new revision of published work. Give each new call its own `requestId` and reuse it only to retry that call; a retry returns the same draft, and `DRAFT_STILL_STARTING` means Fudge is still copying the theme, so retry with the same `requestId`. Each piece of work keeps one ref, through every draft and publish: keep the returned ref and pass it as `draft` from then on.
2. Read before you change: `search_draft_files` to find theme files (`pattern` searches their contents), `read_draft_file` to read one. `get_design_guide` and the guide `storefront/design.md` (`read_guide`) describe the store's design rules.
3. Change theme files with `edit_draft_file` (exact text replacements; pass the `revision` you read) or `write_draft_file` for a new file. New filenames include the draft's file prefix from `start_draft`; every section keeps a `{% schema %}` with a `name`. To show a new section, add it to the page's template JSON under `sections` and `order` in one edit.
4. Change products, collections, pages, articles and their metafields with `edit_draft_content`, after reading the item (`read_draft_file` on `.entities/product/<id>.jsonc`; list items with `.entities/product?query=…`). These changes are staged: they show on Fudge's review page and apply when the merchant publishes, not in the preview.
5. Create new items only when the merchant asks, with `create_draft_product`, `create_draft_collection`, `create_draft_page` or `create_draft_article`. New products and collections start hidden; when a result says previewing them needs consent, call `show_preview_consent` and wait for the merchant's choice before setting `visibility: "unlisted"`.
6. Check your work: `capture_page` with `draft` shows the page as the draft renders it, on desktop and mobile. Fix what looks wrong before showing the merchant.
7. Show the draft with `show_resources` and its ref, then follow "Review and publish" below.

Fudge validates every change as it does its own and refuses edits that would break the theme; read its error and fix the cause rather than working around it. When a write fails with `DRAFT_BUSY`, Fudge is working on that draft: wait with `read_work`, or steer it with `message_fudge`. When the draft has a conversation in Fudge, Fudge notes there what you changed, so either of you can carry on later.

Your assistant app may ask the merchant to approve each change to the draft. The first time it does, tell them in one sentence that these changes stay in a private draft and nothing reaches their live store until they approve it on Fudge's review page, so they can let `start_draft`, `edit_draft_file`, `write_draft_file`, `delete_draft_file` and `edit_draft_content` run without asking (for example “Always allow” on the approval prompt) if they'd rather not confirm every edit. Say it once and leave the choice to them. Don't suggest it for the create tools: they add hidden items to the Shopify store straight away.

### Review and publish

Only the merchant can publish, in Fudge. When a draft is ready, describe what changed and call `request_publish_review`: its card shows Fudge's screenshot of the actual draft with a button to Fudge's review page, so don't repeat the link. Also offer the live preview link (`draft.previewUrl` from `read_work`). Show Fudge's work only through its own cards and links; never illustrate a draft with images from the web. When `ready` is false, tell the merchant why. Fudge asks them to start a plan before publishing when `plan.required` is set. Never say something is published or live until `read_work` shows `draft.publication.phase: "done"`, `publishedAt` or `liveUrl`; report a failed publish with its `failureDetail`. If the draft changes after review, the merchant reviews again.

After publishing, record what to measure in the work's Plan, and later pass `measure.subject` from `read_work` to `get_store_performance` and `get_store_insights` to see how it did.

## Design references

`search_design_references` searches Fudge's Lookbook of analysed store pages and patterns. Search by the shopper problem or page element, such as "size guidance on mobile product pages", not by brand. A reference shows how another store solved a problem, not that it worked; check that it fits this store's products and brand before recommending it.

Show the 3–8 references you recommend with `show_design_references`, best first, each with a one-sentence note on why it suits this store. The merchant sees the gallery before your reply, so keep the reply to a few sentences: the overall recommendation and a next step, without describing each reference again. Tell them they can tap a reference to see it larger. When the merchant picks one, use that exact ref.

When the merchant asks to build a reference, call `message_fudge` with a short brief that includes the exact ref, then show the resulting work with `show_resources` so a card links to the draft.

## Remember

Fudge keeps one memory per store, shared with Fudge's own agent and every assistant the merchant connects. Start each conversation from `get_store_overview`: its `memory` holds the store's standing preferences and about text, the merchant's personal preferences, and the guides to open before related work. Follow them as Fudge would, and open the relevant guide with `read_store_document` before writing copy, designing, briefing imagery or touching the theme.

- **Recall:** `find_context` searches guides, Plans, projects, findings, recorded changes and past conversations, including conversations held in Fudge. Published work and guides rank first. A conversation result is evidence of intent, not of what is live: its note says whether the work is a draft, was published (and may have changed since) or was only discussed. Check `read_work` history before relying on it.
- **Save:** when the merchant states how things should be done from now on, a correction or a lesson learned (including what was tried and rejected, and why), call `remember` with the rule written as it should apply in future work. Fudge picks the right memory file: `about.md` for store identity, `preferences.json` for rules every task needs, the `writing.md`, `design.md`, `imagery.md` and `technical.md` guides, or a subject document. It edits neatly and changes nothing for a duplicate. Pass `personal: true` for the merchant's own working preferences. If it returns a conflict, ask the merchant which rule applies, then call it again with `replaces: true` if they confirm the change.
- **What is not memory:** one-off requests, volatile facts, guesses, copies of what the store, Plans or reports already hold, and details that only matter to the current draft. Ask: would this matter in a different project? If not, keep it with that work.
- **Plans:** a campaign decision goes in its Plan's brief or notes with `edit_store_document`. Copy the exact text you replace from a fresh read. When the merchant agrees a new goal that no existing Plan covers, start one with `create_plan`, then show it with `show_resources`. Schedules are approved in Fudge.
- **Change timeline:** for "what have we changed on this page, product or discount?", call `read_work` with `about` and `view: "history"`, or `view: "summary"` for one compact page. `about: "fudge://store"` with `view: "history"` is the store-wide timeline. When the merchant mentions a change made outside Fudge, such as ad budgets, prices, apps, email or theme edits in Shopify, add it with `record_change`, saying what changed, when, and what they expect it to do. Fudge's own publishes are recorded automatically.
- **Links:** refer to products, pages and Fudge items by reference (Shopify GIDs, `fudge://` refs, `.memory/workspace/` paths). Fudge rejects links that don't resolve. `?view=history` on a memory file shows its saved revisions and where each came from.

## Send Fudge feedback

When a Fudge tool is broken, leaves you stuck, or makes a task much harder than it should be, or the task needs something Fudge's tools can't do, tell the Fudge team with `send_feedback`. Send each one once, when it happens, then carry on with what you can do. When the merchant asks you to pass feedback on to Fudge, send their words with `send_feedback` as `merchant`, and only then.

## Using these guides

Fudge's guides are the reference articles its own agent works from: criteria, examples and checklists for each kind of work. Find one with `search_guides`, or open one by path with `read_guide` (paths look like `seo/audit.md`, and guides link each other the same way). Adapt the one that fits the merchant's goal to the store; they describe outcomes and judgment, not a script to follow step by step.

- `.plans/`, `.playbooks/`, `.memory/`, `.brand/` and `.projects/` are the store's documents. Read them with `read_store_document`.
- Take numbers and report rows from `get_store_performance` (a `breakdown` gives queries, pages, channels and similar rows), Fudge's saved findings and recommendations from `get_store_insights`, an area's current state from `get_store_overview` with an `area`, and work from `list_work` and `read_work`.
- Where a guide inspects pages or the catalogue (`inspect_page`, `.entities/` records), use `check_page`, `capture_page`, `check_page_speed`, `check_catalog_data` and `search_catalog`.
- When you build in a draft, a guide's `file_view`, `file_edit`, `file_create`, `file_delete` and `grep_files` are `read_draft_file`, `edit_draft_file`, `write_draft_file`, `delete_draft_file` and `search_draft_files`, and `edit_entities` is `edit_draft_content`. Skip steps that name tools you don't have, such as `call_tool`, `agent_script` or a handoff to the Editor; they are internal to Fudge. If the merchant wants that outcome, describe it to Fudge with `message_fudge`. A `.skills/` path that `read_guide` can't open is a guide or tool contract Fudge uses while building.
- To run one of Fudge's eight reviews (SEO, AI search visibility, conversion, speed, landing page opportunities, design and brand, content and blog, offers and AOV), follow the review table in the manage-store skill.
- Storefront changes, whether Fudge builds them through `message_fudge` or you build them in a draft (see the manage-store skill), go live only after the merchant approves them in Fudge.
