# RAPPcards

**Digital twin of the [RAR](https://github.com/kody-w/RAR) card collection** — 138 single-file AI agents rendered as MTG-style cards, fetched live from the registry on every page load.

**Live:** [https://kody-w.github.io/RAPPcards/](https://kody-w.github.io/RAPPcards/)

## What this is

A zero-dependency, single-file static site that reflects the real state of the [RAPP Agent Registry](https://kody-w.github.io/RAR). No build step. No backend. The page fetches:

- `cards/holo_cards.json` — card visuals (name, mana cost, type, abilities, flavor, inline SVG art)
- `registry.json` — agent metadata (publisher, version, category, quality tier, seed, file path, line count)

...both directly from `raw.githubusercontent.com/kody-w/RAR/main/` on load. When RAR updates, this twin updates on the next refresh.

## Not a fork

This is the **experiential twin** — the contractual truth lives at [kody-w/RAR](https://github.com/kody-w/RAR). If the twin and RAR disagree, RAR wins. The SDK, the validators, the submission pipeline, the seed→incantation mapping — all of that is and remains in RAR proper.

## What you can do here

- 🔍 **Search** across 138 cards by name, ability, publisher, flavor text, or tag
- 🎨 **Filter** by rarity, color (R/W/U/B/G/N), category, or publisher
- 📇 **Click** any card for full details: abilities, flavor, stats, seed, and links back to the source `.py` on GitHub
- 🔗 **Jump** to the card's entry in the RAR binder or view the raw agent source

## Related

- [RAR](https://kody-w.github.io/RAR) — the registry itself
- [RAPP Stack](https://kody-w.com) — Brainstem → Hippocampus → Copilot Studio
- [RAPP v1 SPEC](https://kody-w.github.io/RAPP/SPEC.md) — the contract
- [Single File Agents doctrine](https://kody-w.github.io/rappterhub/single-file-agents.html) — the philosophy

## License

The twin code in this repo is MIT. Card data is pulled live from kody-w/RAR and is governed by RAR's terms.
