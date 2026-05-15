# Pitch Deck Coach

A Claude skill that helps founders build, critique, and improve startup pitch decks.

Built on the published guidance of Kevin Hale (Y Combinator) and practical pitch-deck principles from Charles Hope at [Your Startup Advisor](https://www.yourstartupadvisor.com).

---

## What this skill does

When you ask Claude for help with a pitch deck, this skill kicks in and helps you:

- **Critique a deck** you have already built
- **Plan a deck** from scratch based on context you provide
- **Coach you through** a specific slide you are stuck on

It covers the common pitch deck slides (intro, problem, solution, demo, traction, market, competition, why now, team, ask, close), live versus emailed deck rules, the four standard live-pitch lengths (1, 3, 5, and 10 minutes), audience-specific guidance for investors, accelerators, customers, and partners, and design principles for keeping the deck legible, simple, and obvious.

The skill works for any startup pitch deck. The same principles apply whether you are pitching to seed investors, demo day, an accelerator interview, a customer, or a partner.

---

## Who this is for

- Founders building their first pitch deck and not sure where to start
- Founders who have been rejected before and want a sharper deck this time
- Advisors and mentors helping founders prepare for fundraising or demo days
- Programs and accelerators that want to give their cohort a consistent baseline

---

## What makes this different

Most pitch decks fall into the same traps: too many slides, too much text per slide, marketing language, inflated claims, AI-generated framing that reads like every other deck, and confusion between decks meant to be emailed and decks meant to be pitched live. This skill is built around the rules that investors and program readers actually care about:

- Less is more
- One topic per slide
- Ask, do not invent
- Slide titles tell the story (for emailed decks)
- Sound like the founder, not like a marketing brochure

It also covers the rules that change everything depending on how the deck is delivered: an emailed deck and a live pitch deck are different artefacts, and the skill treats them that way.

The skill includes a bundled humanizer guide to strip AI writing patterns out of any drafted slide content before you use it.

---

## How to install

Each release publishes a clean install zip on the [Releases page](https://github.com/betahope/pitch-deck-coach/releases/latest). The zip is named `pitch-deck-coach-vX.Y.Z.zip` and is listed under **Assets** at the bottom of the release. Use that zip rather than cloning the repo. It contains only the files the skill needs.

### On Claude.ai (Pro, Team, or Enterprise plans)

1. Open the [latest release](https://github.com/betahope/pitch-deck-coach/releases/latest), scroll to **Assets**, and download `pitch-deck-coach-vX.Y.Z.zip`.
2. Unzip it on your computer. You should see a folder called `pitch-deck-coach` with `SKILL.md` inside it.
3. Go to [claude.ai](https://claude.ai). Open **Customize** from the top of the sidebar, then select **Skills**.
4. Click **Upload skill**. Select the `pitch-deck-coach` folder.
5. The skill is now active. Claude will use it automatically whenever you ask for help with a pitch deck.

Note: Skills are personal to your Claude account. If you want teammates to use it too, they need to install it themselves.

### In Claude Code

1. Open the [latest release](https://github.com/betahope/pitch-deck-coach/releases/latest), scroll to **Assets**, and download `pitch-deck-coach-vX.Y.Z.zip`.

2. Unzip it.

3. Copy the `pitch-deck-coach` folder into your personal skills directory:

   ```
   cp -r pitch-deck-coach ~/.claude/skills/
   ```

   Or into a project-specific skills directory if you want it scoped to one project:

   ```
   cp -r pitch-deck-coach /your-project/.claude/skills/
   ```

---

## How to use it

Once installed, you do not need to invoke the skill by name. Just start a normal Claude conversation and mention what you are working on.

Examples that will trigger the skill:

- "Help me plan a 3-minute pitch deck for an accelerator demo day."
- "Can you review this deck I am sending to investors?"
- "I am stuck on the problem slide. Can you coach me through it?"
- "What should go on the traction slide if I have no paying customers yet?"
- "Is this deck the right length for an emailed investor pitch?"

The skill will pick the right mode (critique, plan, or coach) based on what you ask.

---

## What is inside

```
pitch-deck-coach/
├── SKILL.md                         (main skill file)
└── references/
    ├── deck-types.md                (live vs. emailed decks, 1/3/5/10 minute structures, appendix guidance)
    ├── slide-by-slide.md            (every standard slide, with weak vs. strong examples)
    ├── design-principles.md         (legibility, brand colours, typography, charts, no animations)
    ├── audience-asks.md             (investor ask vs. accelerator ask vs. customer ask)
    └── humanizer.md                 (bundled humanizer guide)
```

---

## Need more help?

This skill is designed to get you a long way on your own, but it is not a substitute for a human advisor when you are genuinely stuck or working through something strategic.

If you want deeper help on your deck, your pitch, your founder story, or your startup strategy, you can reach Charles Hope at Your Startup Advisor:

- Email: <charles@yourstartupadvisor.com>
- WhatsApp: +353 87 372 6050
- Web: [yourstartupadvisor.com](https://www.yourstartupadvisor.com)

---

## Updates

This skill is maintained here on GitHub. The [latest release](https://github.com/betahope/pitch-deck-coach/releases/latest) is always the version to install. See [CHANGELOG.md](https://github.com/betahope/pitch-deck-coach/blob/main/CHANGELOG.md) for a history of changes.

Claude does not auto-update installed skills, so to pick up an update, download the latest release zip and re-install over the previous version.

---

## License

MIT. See [LICENSE](https://github.com/betahope/pitch-deck-coach/blob/main/LICENSE) for details. You are free to use, modify, and redistribute this skill, including commercially. Attribution is appreciated but not required by the license.

---

## Credits

Built by Charles Hope at [Your Startup Advisor](https://www.yourstartupadvisor.com), drawing on published guidance from:

- Kevin Hale (Y Combinator), "How to design a better pitch deck"

The legible / simple / obvious framing in the live pitch section, and several specific rules around screenshots, slide density, and Hick's Law on diagrams, are adapted from Kevin Hale's essay. Thanks to him for making that guidance public.

This skill is a compilation and practical application of his guidance, layered with additional principles from Charles Hope's work with over 650 founders and 14+ startup programs.

The bundled humanizer guide in `references/humanizer.md` is created and maintained by **blader** and published at [github.com/blader/humanizer](https://github.com/blader/humanizer) under the MIT License. It is included here under those terms for convenience so users do not need to install it separately. The humanizer's own underlying source is [Wikipedia's "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide, maintained by WikiProject AI Cleanup.
