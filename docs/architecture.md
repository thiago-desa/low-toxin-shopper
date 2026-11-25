# Architecture

`low-toxin-shopper` is the public snapshot of the naturopath bot, a low-toxin product shopper Grok Bot. The design is a dated reasoning graph plus a verification layer. The public goal is to make it easier to avoid toxic chemicals in everyday products for the owner and their children. There is no packed standing routine in this snapshot.

## Goals

When the owner asks about a product, an ingredient, or a category:

1. Say whether the product can be skipped, before adding a new one
2. Rank the chemical concern by exposure route and by the age of the person who will use it
3. Quantify and name ingredients, tests, and certifications only with sources found in the current run
4. Disclose parent companies, and say when a pick is only the best of imperfect options
5. Stay silent when nobody asked for a check
6. Never give medical advice

## Super-agent characteristics (where they fit)

- **Continuous:** one persistent shopper identity that re-reads the `naturopath-shopper` skill before a recommendation.
- **Proactive:** only on request (for example a one-off reminder). No packed morning brief or recall watch.
- **Event-filtered:** if an owner later asks to watch a listing, the quiet path is to send nothing when the ingredients and the material facts have not changed.
- **Persistent:** memories about region, age band, and avoid-lists survive across days; the shopper skill is the durable overlay.
- **Not claimed here:** a multi-worker router, a live product database, a private lab, or clinical coverage. This snapshot is a single shopper bot.

## Two loops

### Conversational loop

The owner asks a question (including "is this product clean?"). The bot loads `naturopath-shopper`, gathers the current label, tests, certifications, and listings with `naturopath-grounding`, walks the product graph, and answers in that protocol.

### Scheduled loops

None are packed. Do not invent one on import. If a later owner asks to watch a listing or a recall feed, document the trigger, keep the quiet path, and add an eval.

## Grounding and verification

- Physical labels, official regulator lists, and dated SKU tests are first-class sources.
- Consumer scores and marketing badges are a secondary layer, not a substitute for a list or a test.
- Contradictions are surfaced, not averaged away.
- Aging lists and tests carry a November 2026 re-check rule (`docs/sources.md` and the failure handling in `naturopath-grounding`).

## Context budget

Keep the active product or category, the exposure route, the toxins that matter, the facts fetched this run, and their links. Do not paste the entire shopper skill into an answer.

## Tools

- Web search and fetch of public product pages, regulator lists, certification records, and published lab reports.
- Retail search for current availability and prices in the owner's region.
- The packed skills. This repo also keeps the reasoning schema in `graphs/schema.md`.

No clinical system, no private lab API, and no automatic purchase log are part of this design. If the running host can also add items to a cart, that is an optional convenience the owner controls, not a claimed capability of this snapshot.

## What this repo is

A public-ready snapshot of the agent definition, skills, schema, evals, and a fictional product check, meant to stay in parity with a published Grok Bot template. It is not a clinic, not a store, and not an archive of real household cases.
