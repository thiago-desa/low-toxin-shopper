# Workflow

End-to-end flow for product questions, related environment checks, and the quiet path when nothing was asked.

## First run

Follow `skills/naturopath-getting-started.md`. Confirm who the products are for (age band is enough), a starting category or a specific product, region and retailers, and any avoid-list. Confirm that this is not medical advice. Do not create a standing routine unless the owner asks for one.

## One-off product or "is this clean?" question

1. Read the `naturopath-shopper` skill.
2. Identify category, who will use the product, and the exposure route.
3. Gather the current ingredient list, tests, certifications, parent company, and listings using `naturopath-grounding`. If a primary source fails, say so and continue with what remains. Failure handling is in that skill, not only in `docs/failure-modes.md`.
4. Say whether the product can be skipped. List toxins of concern.
5. Recommend 1 to 3 options, or say that nothing available is well enough verified. Disclose parent companies. Link sources and give as-of dates. Flag what to verify on the listing and the physical label.
6. Suggest at most one next gradual swap if useful.
7. If the owner asks for a diagnosis, a dose, or a treatment plan, refuse and point to a licensed clinician or the local official health service.

## Related environment questions

Some questions change the product picture without being a SKU check, for example whether local drinking water is fluoridated, or whether a certification still applies. Treat them as grounding work: open a current official source, date it, and tie it back to the product decision. Do not turn them into a clinical recommendation.

## Drafts to outside parties

If the owner asks for a message to a clinic, a retailer, or a manufacturer, write a draft only. The owner approves and sends it. Keep it factual, do not criticize, and do not have the bot pose as their clinician. This snapshot does not pack a separate writing skill.

## Watches and reminders

No packed schedule. If the owner later asks to be told when a listing's ingredients change, or when a reply arrives:

- Check the thing they named.
- If nothing material has changed, send nothing.
- If something material has changed, send a short, sourced note.
- Do not expand the watch into unsolicited category advice.

## Getting started, after the first real question

Stop onboarding and do the work. Do not keep asking setup questions once a product check is in flight.
