# RAPPcards

**The digital twin of the [RAPP Agent Registry (RAR)](https://kody-w.github.io/RAR) card collection.**

Live at **[kody-w.github.io/RAPPcards](https://kody-w.github.io/RAPPcards/)**.

138 single-file AI agents rendered as Pokémon-style cards, pulled live from
`raw.githubusercontent.com/kody-w/RAR/main/` on every page load. No fork, no copy,
no build step — the twin reflects whatever RAR currently says.

## Full compatibility with RAR

- **Visual parity.** Cards render with the exact same layout, colors, stats (HP / ATK / DEF /
  SPD / INT), type badges, rarity tiers (Starter / Core / Elite / Legendary), and weakness /
  resistance chart as `binder.html` in the RAR repo.
- **Authoritative incantation.** The 1024-word `MNEMONIC_WORDS` list from `rapp_sdk.py` is
  embedded verbatim. 10 bits × 7 words = 70 bits covers the 64-bit seed losslessly.
  Every displayed incantation round-trips exactly through `wordsToSeed` ↔ `seedToWords`.
- **BigInt seeds.** 64-bit seeds (`seed > 2⁵³`) are parsed from raw JSON text as BigInts to
  avoid floating-point precision loss — identical to the SDK's behavior.
- **Download as `*_agent.py`.** One click downloads the raw source from RAR, or scaffolds a
  fresh spec-compliant single-file agent with a pre-filled `__manifest__`.
- **Summon by incantation.** Speak any 7-word incantation → resolve to card (if registered)
  or to a raw seed (if unclaimed, with a mint link).

## The twin doctrine

> **RAPPcards are self-sufficient. RAR is the optional central mint.**

The cards here **work without RAR**. Download a `*_agent.py`, drop it in your project, run
it — the file conforms to the [RAPP v1 SPEC](https://kody-w.github.io/RAPP/SPEC.md) and
runs anywhere the RAPP runtime does. RAR is only required when you want a card *canonical*:
publicly listed, verified, searchable, collectible, minted with a seed that belongs to you.

- The **agent contract** lives in RAPP: `BasicAgent` + `name` + `metadata` + `perform()`.
- The **registry contract** lives in RAR: `__manifest__`, publisher namespace, schema
  validation, submission pipeline, seed allocation.

RAPPcards honors both. You can browse, download, and fork cards with no RAR interaction.
Or you can click "✨ Mint new card to RAR" and submit one through the registry's pipeline.

## Not a fork

This repo contains only `index.html` + `README.md`. All card data is fetched live from
`kody-w/RAR`. The contractual truth — SDK, validators, submission pipeline, seed→incantation
wordlist — remains in RAR. We copy the wordlist for offline encoding only; the registry
remains the source of truth for what a canonical card *is*.

## Related

- [RAR registry](https://kody-w.github.io/RAR) · 138 agents, 7 publishers, 19 categories
- [RAPP stack](https://kody-w.com) · brainstem → hippocampus → Copilot Studio
- [RAPP v1 SPEC](https://kody-w.github.io/RAPP/SPEC.md) · the agent contract
- [rapp-installer](https://github.com/kody-w/rapp-installer) · Copilot Studio harness
