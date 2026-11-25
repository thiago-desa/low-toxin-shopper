# low-toxin-shopper

Public snapshot of the naturopath Grok Bot. It makes it easier to avoid toxic chemicals in everyday products for yourself and your children. It checks ingredients, flags known problem chemicals, points to current certifications and tests, and suggests lower-toxin swaps, starting with the option to skip a product altogether.

**Not medical advice.** This bot is not a doctor, naturopathic physician, dentist, or any other clinician. It does not diagnose, treat, or prescribe. Product and ingredient notes are consumer information only. For symptoms, dosing, or a health decision, talk to a licensed clinician or your local official health service.

## Problem it solves

Ingredient lists are long, marketing is loud, and independent tests go stale. A useful answer has to say whether you need the product at all, which chemicals matter for the way the product is used (mouth, skin, or air), what a current label, certification, or lab test actually shows, and what to verify before you buy. This design leads with that path, dates every source, discloses parent companies, and stays quiet when nobody asked for a check.

## How to use with Grok Bot

1. The easiest path is to copy the published template (see Import below) once the share link is added.
2. Or create a new Grok Bot (suggested name: `naturopath`) and paste the contents of `agents/naturopath.md` (the **Description / system instructions** section) into the bot description / instructions.
3. Pack the three skills in `skills/`. Their `naturopath-` prefixes exist because the Grok Bot skill library is shared.
4. On first run, follow `skills/naturopath-getting-started.md`: who the products are for (adults, children, age bands), which category to start with, where they shop, any ingredients they already avoid, and the no-advice and writing rules.
5. There is no standing routine in this snapshot. Do not invent a recall watch or a scheduled briefing unless a later owner asks for one.

## Import into Grok Bot

The published template link will be added here after the owner exports the bot and pastes the share URL.

## Template parity

The template should pack:

- **Skills:** `naturopath-getting-started` (the getting-started skill), `naturopath-shopper` (the operating shopper skill), and `naturopath-grounding` (source, date, and no-invention rules).
- **Routine:** none. The live design has no packed morning brief, recall watch, or other standing automation. One-off reminders happen only if an owner asks.
- **Memories:** not medical advice, and no diagnosis or prescribing; never invent ingredient lists, lab results, prices, stock, or a track record; disclose parent companies on product picks; product verdicts are dated and sourced and must be re-checked; no em dashes; highest caution for ages 0 to 3.

`graphs/schema.md` is the reasoning schema behind the shopper skill. Keep the skill self-contained so an importer does not need the repo path.

## Disclaimer

Nothing in this repository, its skills, examples, or any answer produced from this design is medical, dental, nutritional, or legal advice, or a substitute for a licensed clinician. Examples are fictional. Ingredient lists, lab results, certifications, prices, and regulatory lists age quickly and must be re-checked against primary sources, with the date of the check shown. A past test of one SKU is not a brand-wide verdict. Do not treat a product pick as a treatment plan.

## Key files

| Path | What it is |
|------|------------|
| `agents/naturopath.md` | Full sanitized agent definition |
| `skills/naturopath-getting-started.md` | First-conversation setup (getting-started skill) |
| `skills/naturopath-shopper.md` | Operating skill: priorities, toxin classes, category trees, protocol |
| `skills/naturopath-grounding.md` | Source, date, parent-company disclosure, and inline failure handling |
| `graphs/schema.md` | Nodes, edges, and how a product query walks the graph |
| `docs/architecture.md` | Design: graph-first shopping, verification, no packed routine |
| `docs/workflow.md` | Intake through recommendation and escalation |
| `docs/failure-modes.md` | Offline, stale or missing ingredient data, quiet path, and no-advice paths |
| `docs/sources.md` | Regulatory and testing sources, with a re-check policy (November 2026) |
| `examples/fictional-product-check.md` | Fully fictional product check |
| `ATTRIBUTION.md` | Design influences and source notes |
| `LICENSE` | MIT |
| `AGENTS.md` | Short agent instructions, boundaries, definition of done |
| `CONTRIBUTING.md` | How to propose changes safely |
| `evals/` | Golden-set behavioral regressions |
| `scripts/check.py` | Secrets / PII / em dash / link hygiene checks |
| `scripts/github-workflow-checks.yml` | GitHub Actions workflow (copy to `.github/workflows/checks.yml` when the token has `workflow` scope) |

## Proof-of-work notes

This repository is a cleaned public snapshot of a working Grok Bot design, staged with the portfolio review fixes from the first commit:

- The owner's goal for people who import this bot is to make it easier to avoid toxic chemicals in products they use on themselves and their children.
- A shopper skill is the core operating model: skip the product when you can, prefer food and habits over more stuff, rank exposure by mouth then skin then air, require a full ingredient list and current verification, and use the highest caution for ages 0 to 3.
- Live work on the source bot, which started in mid-November 2026, has been concentrated on ingredient review for children's oral care: reading labels, citing dated independent heavy-metal tests, disclosing parent companies, and checking current retail listings. Related questions, such as whether municipal drinking water is fluoridated, are in scope when they change the product picture. Fluoride in toothpaste is treated as a parental choice, with sourced context, not as a lecture.
- Answers must say when a pick is only the best of imperfect options, not a verified-clean product. They must say what to confirm on the live listing and the physical label.
- The bot does not diagnose illness or prescribe treatment. When a medical question arrives, it points the owner to official care and stays inside product and ingredient information.
- This snapshot does not pack a standing routine, and it does not claim a long public track record. Do not invent cases, tests, or categories the source bot has not actually worked.

## Review findings

This snapshot applies the portfolio review notes from the start: [docs/review-2026-11-09.md in repo-operational-head](https://github.com/thiago-desa/repo-operational-head/blob/main/docs/review-2026-11-09.md).

## License and attribution

MIT License. Copyright (c) 2026 Thiago De Sa.

Design influences and source notes are listed in `ATTRIBUTION.md`.
