# Attribution

This proof-of-work repository (`low-toxin-shopper`) documents the naturopath Grok Bot, a low-toxin product shopper design by Thiago De Sa (2026).

## Design influences (ideas, not code)

- Graph-style reasoning: nodes (product, ingredient, toxin class, certification, test, retailer), edges (found in, restricted by, verified by, available via), and a cited path behind each recommendation.
- Super-agent harness ideas: a continuous shopper identity, verification before a pick, and a quiet path when nobody asked for a check.
- Andrew Ng's AI Engineering skills framing: grounding, evaluation, and production hygiene.
- Agent-repo practice: short `AGENTS.md`, golden Must / Must-not evals, documented failure modes, and a hygiene check from the first commit.

## Regulatory and testing sources

The November 2026 source notes in `docs/sources.md`, and the packed `naturopath-grounding` and `naturopath-shopper` skills, point at public regulatory lists and consumer testing tools. None of the following are copied as proprietary text or databases. Any score, list entry, or lab figure taken from them must be dated and re-checked:

- Health Canada Cosmetic Ingredient Hotlist (prohibited and restricted cosmetic ingredients in Canada).
- European Union cosmetics rules and the CosIng ingredient database, including annexes of prohibited and restricted substances.
- California Proposition 65 chemical list and warning rules.
- EWG Skin Deep and EWG Verified (consumer scoring and a verified-product program, not a regulator).
- Clean Label Project, MADE SAFE, GOTS, OEKO-TEX, Canada Organic, USDA Organic, and the Non-GMO Project (certification or testing programs, each with its own scope).
- EPA Safer Choice for cleaning products.
- Independent consumer lab reports (for example public heavy-metal tests of a named SKU). These are not regulation. Cite the test date, the lab, and the exact SKU, and never promote a single result into a brand-wide claim.

If a citation is wrong or outdated, fix it with a new primary source and an `as-of` date rather than leaving a stale claim.

## License

MIT License. Copyright (c) 2026 Thiago De Sa. See `LICENSE`.
