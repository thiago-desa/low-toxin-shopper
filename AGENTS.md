# AGENTS.md

Short, high-signal instructions for coding agents working in `naturopath`.

## What this repo is

A sanitized proof-of-work snapshot of a low-toxin product shopper Grok Bot. Markdown skills, a reasoning-graph schema, evals, and docs are the product. There is no service binary to compile.

## Layout

| Path | Role |
|------|------|
| `agents/` | Sanitized bot definition |
| `skills/` | Prefixed skills that the published template should pack |
| `graphs/` | Reasoning schema for product, toxin, and source relationships |
| `docs/` | Architecture, workflow, failure modes, sources |
| `evals/` | Golden set of fictional shopping and safety cases |
| `examples/` | Fictional product check only |
| `scripts/check.py` | Hygiene CI entrypoint |

## Commands

```bash
python scripts/check.py
```

## Hard boundaries

- Not medical advice. Never add a diagnosis, a treatment plan, a supplement dose, or a claim that a product will cure or prevent disease.
- Never invent ingredient lists, lab results, certifications, prices, stock, capabilities, or a track record. If a label, test, or registry is missing or stale, say so.
- Never commit secrets, personal data, real family or child details, health records, purchases, addresses, emails, or live shopping logs.
- Examples and evals must stay clearly fictional. Do not use real household cases.
- No em dashes or en dashes in prose.
- Do not claim capabilities the source bot does not have (no packed recall watch, no clinical practice, no long public case archive in this snapshot).
- Leave dated sources with a provenance date. Re-check aging facts (ingredient lists, lab tests, regulatory hotlists, certifications, prices) before treating them as current.
- Keep skill filenames prefixed (`naturopath-...`). The shared Grok Bot skill library requires unique names. Skills must stay self-contained and must not point at repo-only paths.
- Do not treat a past test of one SKU as a brand-wide verdict, and do not defame a brand without a dated, linked source.
- The published template packs no standing routine.

## Definition of done

- New shopping behavior is reflected in the matching `skills/naturopath-*.md` file and has a golden-set case (Must / Must-not).
- Offline, stale or missing ingredient data, and quiet (no unsolicited ping) paths stay documented in `docs/failure-modes.md` and `evals/golden-set.md`.
- `python scripts/check.py` passes. README import link is either a placeholder with no broken relative path, or the published `https://x.ai/bot/...` URL.
- Template parity holds: skill names, no packed routine, and the memories listed in the README still match the template.
- No medical-advice language slipped into examples or skills. No real personal or family data.

## Ownership

Maintained by Thiago De Sa. Irreversible git / GitHub actions (new public repo, first push, force-push, delete, visibility change) need the owner's explicit approval even when an agent stages the work. Normal pushes of small improvements to this existing repo are fine once it is public.
