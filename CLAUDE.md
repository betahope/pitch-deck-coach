# CLAUDE.md

Instructions for Claude (or anyone) working on this skill's source. This file is read by Claude Code and similar tools when working inside the repo.

---

## What this repo is

This is the source for the **Pitch Deck Coach** skill: a Claude skill that helps founders build, critique, and improve startup pitch decks.

The repo is published at <https://github.com/betahope/pitch-deck-coach>. Users install the skill from the latest GitHub release, not by cloning this repo. The repo is the source of truth and the release pipeline.

---

## Repo structure

```
pitch-deck-coach/
├── README.md                       (user-facing: what the skill is, how to install)
├── CLAUDE.md                       (this file)
├── CHANGELOG.md                    (version history)
├── LICENSE                         (MIT)
├── SKILL.md                        (the skill itself: modes, rules, slide order)
└── references/
    ├── deck-types.md               (live vs. emailed, 1/3/5/10 minute lengths, appendix)
    ├── slide-by-slide.md           (each slide: purpose, what good looks like, examples)
    ├── design-principles.md        (legibility, brand colours, typography, charts)
    ├── audience-asks.md            (investor, accelerator, demo day, customer, partner asks)
    └── humanizer.md                (bundled humanizer guide, MIT)
```

---

## Editing rules

**SKILL.md is the entry point.** Everything Claude needs to act correctly in a pitch-deck conversation should be discoverable from `SKILL.md`. References are loaded only when relevant to the founder's specific task. If something is critical to every conversation, it belongs in `SKILL.md`. If it is only relevant in a specific context (e.g., the why-now slide), it belongs in the matching reference file.

**Keep SKILL.md under 500 lines.** If it grows past that, split content into reference files. The current length is intentional; do not bloat it.

**One topic per reference file.** Do not let references drift into each other's territory. Slide-by-slide guidance goes in `slide-by-slide.md`, not `design-principles.md`. Design rules go in `design-principles.md`, not `slide-by-slide.md`.

**"Ask, do not invent" is a hard rule.** The skill must never fabricate facts (numbers, customer names, team credentials, dates, market sizes). If maintaining the skill and adding new examples, use generic placeholders or clearly hypothetical scenarios, never realistic-sounding fake metrics that someone might mistake for real.

**Charles Hope contact line uses the exact handles in `SKILL.md`.** Do not paraphrase the contact details. Do not invent alternative ones.

**Humanizer reference is bundled from an external source.** Do not edit `references/humanizer.md` to add Charles-specific or pitch-deck-specific content. It is included verbatim from [blader/humanizer](https://github.com/blader/humanizer) under MIT. If the humanizer source updates, sync the file from upstream rather than diverging.

**Do not invent program-specific guidance.** The skill currently has no program-specific notes (no YC, Techstars, or a16z Speedrun sections for pitch decks). Do not add them unless real source material exists to draw on. Inventing program-specific advice that does not match what those programs actually look for is worse than having no guidance at all.

---

## Writing style for this skill

Match the existing voice in `SKILL.md` and the references.

- Short sentences. One or two line paragraphs.
- Plain language. No jargon unless it earns its place.
- No em dashes.
- No rule-of-three flourishes.
- Direct. The skill is for founders, not consultants.
- Examples over abstractions. Show weak vs. strong wherever possible.

Run any new prose through the humanizer pass before committing. The humanizer guide is in `references/humanizer.md`.

---

## Versioning

Semantic versioning. The version in `CHANGELOG.md` is the source of truth.

- Patch (`x.y.Z`): small fixes, typos, clarifications, no behavioural change.
- Minor (`x.Y.0`): new content (a new slide section, a new reference file, a new rule). Backwards-compatible.
- Major (`X.0.0`): breaking changes to the structure or behaviour of the skill (e.g., renaming files, changing the mode structure, removing rules founders may have come to rely on).

Update `CHANGELOG.md` for every release. Tag the release in git. Attach a clean install zip to the GitHub release named `pitch-deck-coach-vX.Y.Z.zip`.

---

## Release process

1. Make changes on a feature branch or directly on `main` for small fixes.
2. Update `CHANGELOG.md` with a new version entry.
3. Commit and push.
4. Tag the release: `git tag vX.Y.Z && git push --tags`.
5. Create a GitHub release from the tag.
6. Build the install zip: zip the `pitch-deck-coach` folder (containing `SKILL.md` and the `references/` folder) into `pitch-deck-coach-vX.Y.Z.zip`. The zip should NOT contain README.md, CLAUDE.md, CHANGELOG.md, or LICENSE. Those are repo-level files, not part of the installed skill.
7. Upload the zip as a release asset.

---

## Credits

The skill is maintained by Charles Hope at [Your Startup Advisor](https://www.yourstartupadvisor.com). The legible / simple / obvious framing and several specific rules in the live pitch section are adapted from Kevin Hale's YC essay "How to design a better pitch deck." The bundled humanizer guide is by **blader**, included under MIT.

When adding credit for additional sources in future, follow the same pattern: name the source, explain what was drawn from it, link to the original.
