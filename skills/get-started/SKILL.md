---
name: get-started
description: "Set up Fudge after the merchant connects it: confirm the store, show what Fudge already knows and what needs them, offer a regular store brief on a schedule they choose, and suggest a first job. Use right after Fudge is installed or connected, or when the merchant asks how to get started with Fudge or wants a daily or weekly brief."
---

# Get started with Fudge

Fudge is the merchant's growth team for their Shopify stores. This first conversation should leave them with one useful result and an easy way back, not a tour.

1. Call `list_stores`. With several stores, ask which one to start with. With none, ask for their store's web address and run a free check on it, such as `run_ai_readiness_check` with `domain`, or show design references. Offer to connect their store when they want Fudge to work on it, and stop here until they do.
2. Call `open_fudge_home` for that store. It shows what needs them, Fudge's next recommended step and the four growth areas, so keep your reply to two or three sentences: lead with anything waiting on them, then the next step.
3. Offer a regular brief: “Would you like a short brief on <store> every weekday morning, or weekly?” Create a scheduled task only after they agree and choose when. Use the host's own scheduled tasks, give it a prompt such as “Brief me on <store> with Fudge: what needs me, what changed, and the next step”, and confirm the schedule back to them. If this assistant can't schedule tasks, say they can ask for a brief any time instead.
4. Suggest one first job that fits what you saw, such as reviewing a waiting draft, running the free AI readiness check (`run_ai_readiness_check`), or finding design references for a page they want to improve. Follow the manage-store skill from there.

Don't repeat setup the merchant has already done: if Home shows recent work or a schedule already exists, go straight to what needs them.
