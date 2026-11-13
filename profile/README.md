<div align="center">

# Tilttek

### Game and gamification tools for PHP and Symfony
*Les outils de jeu et de ludification pour PHP et Symfony*

[![Licence: MIT](https://img.shields.io/badge/licence-MIT-blue)](https://opensource.org/license/mit)
[![PHP 8.5+](https://img.shields.io/badge/PHP-8.5%2B-777BB4?logo=php&logoColor=white)](https://www.php.net)
[![Symfony 8.2+](https://img.shields.io/badge/Symfony-8.2%2B-000000?logo=symfony&logoColor=white)](https://symfony.com)
[![tilttek.com](https://img.shields.io/website?url=https%3A%2F%2Ftilttek.com&label=tilttek.com)](https://tilttek.com)

**[English](#what-tilttek-is)** · **[Français](#version-française)**

</div>

---

## What Tilttek is

**Tilttek makes a site more playful without every site reinventing the game.** It is the family of game and
gamification packages of the [PHIL](https://github.com/parler-haut-interagir-librement) platform (phil-ip): PHP
libraries and their Symfony bundles to roll dice, generate random text, count points, award badges, trade rewards,
level up, offer quests, collect, rank — and to run the table itself, from safety tools to character sheets.

We built it first for the websites of Le Gnome Archiviste, a game shop and creator from Québec. **The tools are
open source; the data belongs to the sites that use them.**

Two families of packages:

1. **Game tools** — dice, the text generator, table-safety tools, and the tools of the table, the characters, the
   game master, campaigns and live-action role-play: a roll, a random table, a tavern name, an X-card, a character
   sheet.
2. **Gamification** — activity, points, badges, exchange, progression, quests, collections and leaderboards, which
   reward what the members of a site do.

[tilttek.com](https://tilttek.com) presents the project and will publish the package catalogue, one page per
package, generated from its documentation.

## Principles

Tilttek follows every rule of the PHIL packages:

- **Original code.** Third-party code enters a Tilttek package only as a declared Composer dependency. Other tools
  are studied for their ideas.
- **MIT, all of it.**
- **A modern floor:** PHP 8.5+ and Symfony 8.2+.
- **The next versions, early.** The next PHP and Symfony enter the test matrix at their first release candidate
  (today: PHP 8.6); a deprecation on the next PHP fails the build. The floor moves up at the next version's x.y.1 for
  a Symfony minor, x.0.3 for a Symfony major and x.y.3 for PHP, always in a new version of our packages.
- **Strict quality gates.** PHPStan at its maximum level with strict rules, PHP-CS-Fixer with the Symfony rules and
  strict types, Rector, Deptrac, Arkitect, PHPUnit failing on any deprecation, and every package tested on its own.
- **A perfect mutation score.** Infection must kill every mutant; the bar is never lowered.
- **Accessible by default.** Keyboard and screen readers, reduced motion, contrast — and dice whose faces are never
  told by colour alone.
- **Every language, not only ours.** The generator already speaks French, English, Spanish, German, Italian and
  Portuguese; nothing is limited to the languages of our own sites.
- **Privacy by design** (Loi 25, GDPR), no tracking.

And three rules of its own:

1. **A member is an opaque reference** supplied by the site: Tilttek reads no name, no email, no account. Nothing is
   public without the member's choice, and erasing a member erases their activity, points and badges.
2. **Everything replays.** A gain, a badge or a rank follows from recorded activity: change a rule, replay the
   activity, and you get the state the new rule would have given.
3. **Randomness is injectable and verifiable.** Dice, generators and draws take their source of randomness as a
   parameter: a secure generator in production, a fixed seed in tests, and a verifiable roll when the site asks.

Fair play is part of the design: points are never money, referrals and predictions are rewarded in points only,
raffles never sell chances, packs publish their odds, and leaderboards are opt-in.

## How the packages are organised

- **A pure PHP library and its Symfony bundle:** `tilttek/points` and `tilttek/points-bundle`.
- **Built on PHIL:** Tilttek packages use PHIL libraries (`phil/resource`, `phil/almanac`, `phil/privacy-bundle`…), never
  the other way round.
- **Incubation** in a private monorepo, `tilttek-prerelease`, the permanent incubator.
- **Release:** a finished package moves to the public monorepo
  [`TiltTek/tilttek`](https://github.com/TiltTek/tilttek), from which each package is split into
  its own read-only repository and published on [Packagist](https://packagist.org).
- **Tooling:** the same `phil/dev-tools` as PHIL.

## Tilttek UX kit

| Repository | What it holds | State |
|---|---|---|
| [ux-kit](https://github.com/TiltTek/ux-kit) | Gamification recipes for the Symfony UX Toolkit — achievement showcase, level gauge, streak flame, quest board, leaderboard, dice roller, collection binder — built on the Shadcn-compatible components and styled with phil-ux. `php bin/console ux:install <recipe> --kit=github.com/TiltTek/ux-kit` | 🧪 in incubation |
| [ux-kit-shadcn](https://github.com/TiltTek/ux-kit-shadcn) | The same recipes in Tailwind, in the Shadcn style | 🧪 in incubation |

## The packages

✅ **released** · 🧪 **in incubation**

**130 packages:** 36 released, 94 in incubation. The released packages are developed in the public monorepo
[`tilttek`](https://github.com/TiltTek/tilttek), each split into its own read-only repository.

<details>
<summary><b>Gamification core</b> — ✅ 18 · 🧪 16</summary>

- [`tilttek/activity`](https://github.com/TiltTek/activity) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/activity)) — The common entry: member activity recorded once, its totals and replayable projections
- [`tilttek/activity-bundle`](https://github.com/TiltTek/activity-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/activity-bundle)) — Activity recording in Symfony, with optional asynchronous projections
- [`tilttek/points`](https://github.com/TiltTek/points) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/points)) — A double-entry points ledger: currencies, earning rules, caps, FIFO expiry, never negative
- [`tilttek/points-bundle`](https://github.com/TiltTek/points-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/points-bundle)) — Points ledgers and rules configured in Symfony
- [`tilttek/badges`](https://github.com/TiltTek/badges) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/badges)) — Badges and achievements: criteria, tiers, hidden achievements, titles, showcase
- [`tilttek/badges-bundle`](https://github.com/TiltTek/badges-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/badges-bundle)) — Badges in Symfony: awarding, showcase, sharing with the member's consent
- [`tilttek/progression`](https://github.com/TiltTek/progression) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/progression)) — Experience and levels on a curve, several tracks, streaks in the member's time zone, seasons
- [`tilttek/progression-bundle`](https://github.com/TiltTek/progression-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/progression-bundle)) — Progression in Symfony, with streak freezes and milestone rewards
- [`tilttek/quests`](https://github.com/TiltTek/quests) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/quests)) — Quests and challenges in steps: personal, community, team and duels
- [`tilttek/quests-bundle`](https://github.com/TiltTek/quests-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/quests-bundle)) — Quests in Symfony, with seasonal dates computed
- [`tilttek/collections`](https://github.com/TiltTek/collections) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/collections)) — Collectibles: rarity, sets, duplicates, item of the day, packs with published, verifiable odds
- [`tilttek/collections-bundle`](https://github.com/TiltTek/collections-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/collections-bundle)) — Collections and dice sets in Symfony
- [`tilttek/exchange`](https://github.com/TiltTek/exchange) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/exchange)) — Trade points for rewards in two steps, and swap collectibles between members
- [`tilttek/leaderboards`](https://github.com/TiltTek/leaderboards) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/leaderboards)) — Leaderboards by measure and period, opt-in, pseudonyms, friend circles, snapshots
- [`tilttek/seasonal-events`](https://github.com/TiltTek/seasonal-events) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/seasonal-events)) — Yearly seasons by RFC 5545 rule, with announced content and multipliers
- [`tilttek/stickers`](https://github.com/TiltTek/stickers) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/stickers)) — Stickers placed on surfaces, with limits and moderation
- [`tilttek/advent-calendar`](https://github.com/TiltTek/advent-calendar) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/advent-calendar)) — An advent calendar: one box a day, one surprise a box
- [`tilttek/sets`](https://github.com/TiltTek/sets) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/sets)) — Versioned sets with tiers and rewards, a neutral building block
- `tilttek/exchange-bundle` · 🧪 in incubation — Reward shops and member trades in Symfony
- `tilttek/leaderboards-bundle` · 🧪 in incubation — Leaderboards configured and shown in Symfony
- `tilttek/kudos` · 🧪 in incubation — Thanks between members, with no public count or ranking
- `tilttek/referrals` · 🧪 in incubation — Referrals rewarded in points, never in money
- `tilttek/guilds` · 🧪 in incubation — Member guilds and their shared goals
- `tilttek/check-in-rewards` · 🧪 in incubation — Rewards for showing up, at a shop booth or a convention
- `tilttek/predictions` · 🧪 in incubation — Predictions staked in points only
- `tilttek/raffle` · 🧪 in incubation — Verifiable draws, with no buying of chances
- `tilttek/fan-awards` · 🧪 in incubation — Fan awards: categories, nominations, votes
- `tilttek/geek-dates` · 🧪 in incubation — Geek culture dates, as data
- `tilttek/rpg-calendar-events` · 🧪 in incubation — Role-playing calendar events, as data
- `tilttek/celebrations` · 🧪 in incubation — A rewards box that receives every package's achievements and shows each once
- `tilttek/bounties` · 🧪 in incubation — Playful bounties prepaid in points, time-limited, never in money
- `tilttek/friend-challenges` · 🧪 in incubation — Member-made challenges, between friends too, with a points prize held in escrow
- `tilttek/gamification-insights` · 🧪 in incubation — An aggregated, anonymous dashboard to balance gamification
- `tilttek/play-insights-bundle` · 🧪 in incubation — Play measures shared by quests and progression, in aggregate

</details>

<details>
<summary><b>Dice &amp; randomness</b> — ✅ 9 · 🧪 7</summary>

- [`tilttek/dice`](https://github.com/TiltTek/dice) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/dice)) — Dice notation parsed, validated and rolled: pools, custom faces, verifiable and replayable rolls
- [`tilttek/dice-bundle`](https://github.com/TiltTek/dice-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/dice-bundle)) — Dice rolls in Symfony: replayable rolls, macros, a form field and Twig
- [`tilttek/generator`](https://github.com/TiltTek/generator) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/generator)) — Random generators written as data: weighted lists, Markov names, sandboxed Twig templates, grammar in six languages, maps, tables with a memory
- [`tilttek/generator-bundle`](https://github.com/TiltTek/generator-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/generator-bundle)) — Generators in Symfony: commands, Twig, a Stimulus controller and a rate-limited draw API
- [`tilttek/dice-probability`](https://github.com/TiltTek/dice-probability) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/dice-probability)) — Exact dice statistics: distributions, at least / at most, mean, events
- [`tilttek/loot-tables`](https://github.com/TiltTek/loot-tables) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/loot-tables)) — Loot tables that declare their dice, drawn verifiably once (provisional name)
- [`tilttek/accessible-dice`](https://github.com/TiltTek/accessible-dice) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/accessible-dice)) — Dice read without seeing colours or aiming at small buttons, announced to screen readers
- [`tilttek/secret-rolls`](https://github.com/TiltTek/secret-rolls) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/secret-rolls)) — Hidden GM rolls, committed in advance and verifiable after the reveal
- [`tilttek/heraldry`](https://github.com/TiltTek/heraldry) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/heraldry)) — Coats of arms drawn from a seed, blazoned in English and French, as safe SVG
- `tilttek/dice-probability-bundle` · 🧪 in incubation — Dice statistics as tables and charts in Live Components
- `tilttek/loot-tables-bundle` · 🧪 in incubation — Loot tables in Symfony, with published commitments to the draws
- `tilttek/dice-tower` · 🧪 in incubation — A table's shared dice tower: every roll seen by all, in order
- `tilttek/dice-jail` · 🧪 in incubation — Dice jail for unlucky dice, and the statistics behind it
- `tilttek/dice-skins` · 🧪 in incubation — The look of a member's dice
- `tilttek/luck-tokens` · 🧪 in incubation — Luck, inspiration or fate tokens a table gives and spends
- `tilttek/card-deck` · 🧪 in incubation — Card decks shuffled, drawn and discarded

</details>

<details>
<summary><b>At the table</b> — ✅ 1 · 🧪 17</summary>

- [`tilttek/table-safety`](https://github.com/TiltTek/table-safety) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/table-safety)) — Safety tools for tabletop games: lines and veils, anonymous signals, credits
- `tilttek/table-safety-bundle` · 🧪 in incubation — Safety tools in Symfony, with session-zero templates
- `tilttek/table-presence` · 🧪 in incubation — Who is at the online table, away or on a break
- `tilttek/table-rules` · 🧪 in incubation — House rules written and accepted, and the rule variants a table picks
- `tilttek/spotlight` · 🧪 in incubation — Share playing time fairly and see who is waiting
- `tilttek/initiative-cards` · 🧪 in incubation — Initiative tracking with cards
- `tilttek/gm-screen` · 🧪 in incubation — A GM screen, on screen or printed
- `tilttek/session-prep` · 🧪 in incubation — Session preparation: scenes, NPCs, notes
- `tilttek/gm-tips` · 🧪 in incubation — Tips for the GM, by situation
- `tilttek/player-knowledge` · 🧪 in incubation — What players know, kept apart from what their characters know
- `tilttek/handouts` · 🧪 in incubation — Handouts given to players during play
- `tilttek/soundboard` · 🧪 in incubation — Ambiences and sound effects for a session
- `tilttek/rpg-systems` · 🧪 in incubation — A registry of game systems: attributes, dice, terms
- `tilttek/reference-tables` · 🧪 in incubation — A system's reference tables
- `tilttek/rules-lookup` · 🧪 in incubation — Search a system's rules, SRDs included
- `tilttek/flashcards` · 🧪 in incubation — Learn a system's rules with spaced-repetition cards
- `tilttek/encounter` · 🧪 in incubation — Encounters composed and balanced for the system
- `tilttek/grid` · 🧪 in incubation — Square, hex, isometric or no grid, alignment and DPI reading; tools, never a virtual tabletop

</details>

<details>
<summary><b>Characters</b> — 🧪 10</summary>

- `tilttek/character-sheet` · 🧪 in incubation — Character sheets per system: computed attributes, equipment
- `tilttek/inventory` · 🧪 in incubation — A character's inventory and encumbrance
- `tilttek/conditions` · 🧪 in incubation — Conditions and effects: poisons, diseases, mutations, lost limbs
- `tilttek/party` · 🧪 in incubation — A campaign's party, what it shares, and a balanced line-up
- `tilttek/random-character` · 🧪 in incubation — A random character, ready to play
- `tilttek/token-maker` · 🧪 in incubation — Virtual tabletop tokens from an image
- `tilttek/relationships` · 🧪 in incubation — Links between characters and NPCs, and how they evolve
- `tilttek/polyglot` · 🧪 in incubation — The languages a character speaks and reads, and what they understand of a text
- `tilttek/character-retirement` · 🧪 in incubation — A character's retirement or death, and their memorial
- `tilttek/crafting` · 🧪 in incubation — Item recipes that combine or evolve items

</details>

<details>
<summary><b>Campaigns &amp; worlds</b> — ✅ 2 · 🧪 14</summary>

- [`tilttek/weather`](https://github.com/TiltTek/weather) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/weather)) — In-world weather: seasons and climate zones, conditions that follow the day before, reproducible from a seed
- [`tilttek/puzzle-builder`](https://github.com/TiltTek/puzzle-builder) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/puzzle-builder)) — Puzzles checked on the server: normalised answers, bounded guesses, tiered hints, an unlock graph
- `tilttek/session-scheduler` · 🧪 in incubation — Campaign sessions: recurrence, absences, rescheduling
- `tilttek/campaign-wiki` · 🧪 in incubation — A campaign wiki and the GM's secrets
- `tilttek/journal` · 🧪 in incubation — Journals of many kinds: session recaps, character and solo journals
- `tilttek/campaign-stats` · 🧪 in incubation — A campaign's statistics
- `tilttek/factions` · 🧪 in incubation — Factions, their reputation and their clocks
- `tilttek/downtime` · 🧪 in incubation — Downtime between adventures: crafting, research, training
- `tilttek/in-character-mail` · 🧪 in incubation — In-character letters between sessions, read by the GM
- `tilttek/legacy-campaign` · 🧪 in incubation — Legacy campaigns and their permanent changes
- `tilttek/west-marches` · 🧪 in incubation — Open campaigns with several GMs and changing tables
- `tilttek/pbp` · 🧪 in incubation — Play-by-post, in scene threads
- `tilttek/homebrew-hub` · 🧪 in incubation — House rules shared, rated and reused from table to table
- `tilttek/fantasy-calendar` · 🧪 in incubation — Fantasy calendars
- `tilttek/travel` · 🧪 in incubation — Journeys, their duration and their hazards
- `tilttek/player-handbook` · 🧪 in incubation — A campaign's player handbook

</details>

<details>
<summary><b>Finding players &amp; game nights</b> — 🧪 8</summary>

- `tilttek/game-catalog` · 🧪 in incubation — One game catalogue each site switches on: BoardGameGeek, RPGGeek, manual entries, errata
- `tilttek/looking-for-group` · 🧪 in incubation — Find players by system, by place or online
- `tilttek/game-night` · 🧪 in incubation — Game nights for a club or a shop: tables, games, sign-ups
- `tilttek/tournament` · 🧪 in incubation — Swiss or elimination tournaments and their pairings
- `tilttek/math-trade` · 🧪 in incubation — Chain game trades: the longest chain computed, everyone gives one and gets one
- `tilttek/game-shelf` · 🧪 in incubation — A member's game shelf and prioritized wishlist
- `tilttek/play-log` · 🧪 in incubation — A log of games played, players anonymous by default
- `tilttek/rating` · 🧪 in incubation — Per-game Elo rating, private by default, with an unrated friendly mode

</details>

<details>
<summary><b>Games &amp; contests</b> — ✅ 4 · 🧪 10</summary>

- [`tilttek/bingo`](https://github.com/TiltTek/bingo) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/bingo)) — Bingo with cards drawn from a server secret, printed cards that can be verified
- [`tilttek/deck-builder`](https://github.com/TiltTek/deck-builder) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/deck-builder)) — Card decks built to a format's declared rules, every breach readable, no publisher catalogue
- [`tilttek/game-engine`](https://github.com/TiltTek/game-engine) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/game-engine)) — Turn-based games as a move log, randomness committed in advance, replay
- [`tilttek/game-engine-bundle`](https://github.com/TiltTek/game-engine-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/game-engine-bundle)) — Game tables in Symfony: opaque seats, DBAL, a lock, private Mercure
- `tilttek/quiz` · 🧪 in incubation — Quizzes: questions, timer, score
- `tilttek/mini-games` · 🧪 in incubation — Small games played on the site
- `tilttek/tavern-games` · 🧪 in incubation — Tavern games from a game world, playable online
- `tilttek/escape-room` · 🧪 in incubation — Escape rooms: chained puzzles, hints, timer
- `tilttek/murder-mystery` · 🧪 in incubation — Murder-mystery nights: roles, clues, reveal
- `tilttek/cosplay-contest` · 🧪 in incubation — Cosplay contests: entries, walk-on, jury and public vote
- `tilttek/cosplay-progress` · 🧪 in incubation — A costume's build log, step by step
- `tilttek/score-sheets` · 🧪 in incubation — Score sheets
- `tilttek/turn-clock` · 🧪 in incubation — Turn clocks: initial time, time per move, moves per day
- `tilttek/jam` · 🧪 in incubation — Themed creation jams with deadlines: entries, votes and jury

</details>

<details>
<summary><b>Hobbies</b> — ✅ 2 · 🧪 4</summary>

- [`tilttek/wargame-army`](https://github.com/TiltTek/wargame-army) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/wargame-army)) — Army lists on a generic engine, against a catalogue the application provides
- [`tilttek/writing-goals`](https://github.com/TiltTek/writing-goals) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/writing-goals)) — An author's writing goals: a plan that bends to the days they write, and no streak to break
- `tilttek/minis-tracker` · 🧪 in incubation — Track miniatures bought, built and painted
- `tilttek/paint-recipes` · 🧪 in incubation — Miniature paint recipes: colours, steps, photos
- `tilttek/reading-quests` · 🧪 in incubation — Reading quests for a book
- `tilttek/geocache-quests` · 🧪 in incubation — Geocache quests

</details>

<details>
<summary><b>Live-action role-play</b> — 🧪 8</summary>

- `tilttek/larp-characters` · 🧪 in incubation — LARP characters and their sheets
- `tilttek/larp-checkin` · 🧪 in incubation — Player check-in on site
- `tilttek/larp-economy` · 🧪 in incubation — A LARP's currency and trade
- `tilttek/larp-crafting` · 🧪 in incubation — LARP crafting
- `tilttek/larp-spells` · 🧪 in incubation — LARP spells
- `tilttek/larp-timeline` · 🧪 in incubation — The timeline of a LARP's world and events
- `tilttek/larp-rules-quiz` · 🧪 in incubation — A rules quiz before the first game
- `tilttek/larp-plots` · 🧪 in incubation — Writing a LARP's plots, linked to its characters

</details>


## Get involved

- 💬 Questions and ideas: [Discussions](https://github.com/orgs/TiltTek/discussions)
- 🐛 Bugs and feature requests: an issue in the repository concerned
- 🤝 [Contributing](https://github.com/TiltTek/.github/blob/main/CONTRIBUTING.md) ·
  [Code of conduct](https://github.com/TiltTek/.github/blob/main/CODE_OF_CONDUCT.md) ·
  [Security](https://github.com/TiltTek/.github/blob/main/SECURITY.md) ·
  [Support](https://github.com/TiltTek/.github/blob/main/SUPPORT.md)
- 🌐 [tilttek.com](https://tilttek.com) · sister project: [PHIL](https://github.com/parler-haut-interagir-librement)

---

## Version française

**Tilttek** — les outils de jeu et de ludification pour PHP et Symfony

### Ce qu'est Tilttek

**Tilttek rend un site plus joueur sans que chaque site réinvente le jeu.** C'est la famille des paquets de jeu et
de ludification de la plateforme [PHIL](https://github.com/parler-haut-interagir-librement) (phil-ip) : des
librairies PHP et leurs bundles Symfony pour lancer des dés, générer des textes au hasard, compter des points,
décerner des badges, échanger des récompenses, monter de niveau, proposer des quêtes, collectionner, classer — et pour
mener la table elle-même, des outils de sécurité aux fiches de personnage.

Nous l'avons d'abord bâti pour les sites du Gnome Archiviste, boutique et créateur de jeux du Québec. **Les outils
sont en code ouvert ; les données appartiennent aux sites qui les utilisent.**

Deux familles de paquets :

1. **Les outils de jeu** — les dés, le générateur de textes, les outils de sécurité à la table, et ceux de la table,
   des personnages, du meneur, des campagnes et du grandeur nature : un lancer, une table aléatoire, un nom de
   taverne, une carte X, une fiche de personnage.
2. **La ludification** — l'activité, les points, les badges, les échanges, la progression, les quêtes, les
   collections et les classements, qui récompensent ce que font les membres d'un site.

[tilttek.com](https://tilttek.com) présente le projet et publiera le catalogue des paquets, une page par paquet,
générée de sa documentation.

### Principes

Tilttek suit toutes les règles des paquets PHIL :

- **Du code original.** Le code tiers n'entre dans un paquet Tilttek que comme dépendance Composer déclarée. D'autres
  outils sont étudiés pour leurs idées.
- **MIT, en entier.**
- **Un plancher moderne :** PHP 8.5+ et Symfony 8.2+.
- **Les versions suivantes, tôt.** Le PHP et le Symfony suivants entrent dans la matrice de tests dès leur première
  version candidate (aujourd'hui : PHP 8.6) ; une dépréciation du PHP suivant fait échouer les tests. Le plancher
  monte au x.y.1 d’une mineure de Symfony, au x.0.3 d’une majeure de Symfony et au x.y.3 de PHP, toujours dans une
  nouvelle version de nos paquets.
- **Des barrières de qualité strictes.** PHPStan au niveau maximal avec les règles strictes, PHP-CS-Fixer aux règles
  de Symfony et types stricts, Rector, Deptrac, Arkitect, PHPUnit qui échoue à la moindre dépréciation, et chaque
  paquet testé seul.
- **Un score de mutation parfait.** Infection doit tuer chaque mutant ; la barre ne baisse jamais.
- **Accessible d'office.** Clavier et lecteurs d'écran, mouvement réduit, contraste — et des dés dont une face n'est
  jamais dite par la seule couleur.
- **Toutes les langues, pas seulement les nôtres.** Le générateur parle déjà français, anglais, espagnol, allemand,
  italien et portugais ; rien n'est limité aux langues de nos propres sites.
- **La vie privée dès la conception** (Loi 25, RGPD), aucun pistage.

Et trois règles à lui :

1. **Un membre est une référence opaque** fournie par le site : Tilttek ne lit ni nom, ni courriel, ni compte. Rien
   n'est public sans le choix du membre, et l'effacement d'un membre efface son activité, ses points et ses badges.
2. **Tout se rejoue.** Un gain, un badge ou un rang découle d'une activité enregistrée : changez une règle, rejouez
   l'activité, et vous obtenez l'état que la nouvelle règle aurait donné.
3. **Le hasard est injectable et vérifiable.** Les dés, les générateurs et les tirages prennent leur source de hasard
   en paramètre : un générateur sûr en production, une graine fixe dans les tests, et un lancer vérifiable quand le
   site le demande.

Le franc-jeu fait partie de la conception : les points ne sont jamais de l'argent, le parrainage et les prédictions se
récompensent en points seulement, les tirages ne vendent jamais de chances, les pochettes publient leurs
probabilités, et les classements se font sur accord.

### L'organisation des paquets

- **Une librairie PHP pure et son bundle Symfony :** `tilttek/points` et `tilttek/points-bundle`.
- **Bâti sur PHIL :** les paquets Tilttek utilisent des librairies PHIL (`phil/resource`, `phil/almanac`,
  `phil/privacy-bundle`…), jamais l'inverse.
- **L'incubation** dans un monodépôt privé, `tilttek-prerelease`, l'incubateur permanent.
- **La sortie :** un paquet fini passe au monodépôt public [`TiltTek/tilttek`](https://github.com/TiltTek/tilttek),
  d'où chaque paquet est scindé dans son propre dépôt en lecture seule et publié sur [Packagist](https://packagist.org).
- **L'outillage :** le même `phil/dev-tools` que PHIL.

### Le kit UX de Tilttek

| Dépôt | Ce qu'il contient | État |
|---|---|---|
| [ux-kit](https://github.com/TiltTek/ux-kit) | Des recettes de ludification pour le Toolkit de Symfony UX — vitrine des réussites, jauge de niveau, flamme de série, tableau des quêtes, classement, lanceur de dés, classeur de collection — bâties sur les composants compatibles Shadcn et habillées par phil-ux. `php bin/console ux:install <recette> --kit=github.com/TiltTek/ux-kit` | 🧪 en incubation |
| [ux-kit-shadcn](https://github.com/TiltTek/ux-kit-shadcn) | Les mêmes recettes en Tailwind, à la façon de Shadcn | 🧪 en incubation |

### Les paquets

✅ **publié** · 🧪 **en incubation**

**130 paquets :** 36 publiés, 94 en incubation. Les paquets publiés sont développés dans
le monodépôt public [`tilttek`](https://github.com/TiltTek/tilttek), scindés chacun dans son propre dépôt en lecture seule.

<details>
<summary><b>Cœur de la ludification</b> — ✅ 18 · 🧪 16</summary>

- [`tilttek/activity`](https://github.com/TiltTek/activity) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/activity)) — L'entrée commune : l'activité d'un membre enregistrée une fois, ses totaux et ses projections rejouables
- [`tilttek/activity-bundle`](https://github.com/TiltTek/activity-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/activity-bundle)) — L'enregistrement de l'activité dans Symfony, avec projections asynchrones facultatives
- [`tilttek/points`](https://github.com/TiltTek/points) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/points)) — Un grand livre de points à double entrée : devises, règles de gain, plafonds, expiration FIFO, jamais négatif
- [`tilttek/points-bundle`](https://github.com/TiltTek/points-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/points-bundle)) — Les grands livres et règles de points configurés dans Symfony
- [`tilttek/badges`](https://github.com/TiltTek/badges) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/badges)) — Badges et succès : critères, paliers, succès cachés, titres, vitrine
- [`tilttek/badges-bundle`](https://github.com/TiltTek/badges-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/badges-bundle)) — Les badges dans Symfony : décernement, vitrine, partage avec l'accord du membre
- [`tilttek/progression`](https://github.com/TiltTek/progression) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/progression)) — Expérience et niveaux sur une courbe, plusieurs pistes, séries au fuseau du membre, saisons
- [`tilttek/progression-bundle`](https://github.com/TiltTek/progression-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/progression-bundle)) — La progression dans Symfony, avec gel des séries et paliers récompensés
- [`tilttek/quests`](https://github.com/TiltTek/quests) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/quests)) — Quêtes et défis à étapes : personnels, communautaires, d'équipe et duels
- [`tilttek/quests-bundle`](https://github.com/TiltTek/quests-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/quests-bundle)) — Les quêtes dans Symfony, aux dates saisonnières calculées
- [`tilttek/collections`](https://github.com/TiltTek/collections) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/collections)) — Objets à collectionner : rareté, ensembles, doubles, objet du jour, pochettes aux probabilités publiées et vérifiables
- [`tilttek/collections-bundle`](https://github.com/TiltTek/collections-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/collections-bundle)) — Les collections et les sets de dés dans Symfony
- [`tilttek/exchange`](https://github.com/TiltTek/exchange) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/exchange)) — Échanger des points contre des récompenses en deux temps, et des objets entre membres
- [`tilttek/leaderboards`](https://github.com/TiltTek/leaderboards) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/leaderboards)) — Classements par mesure et période, sur accord, pseudonymes, cercles d'amis, instantanés
- [`tilttek/seasonal-events`](https://github.com/TiltTek/seasonal-events) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/seasonal-events)) — Des saisons annuelles par règle RFC 5545, avec contenus et multiplicateurs annoncés
- [`tilttek/stickers`](https://github.com/TiltTek/stickers) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/stickers)) — Des autocollants posés sur des surfaces, avec limites et modération
- [`tilttek/advent-calendar`](https://github.com/TiltTek/advent-calendar) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/advent-calendar)) — Le calendrier de l'Avent : une case par jour, une surprise par case
- [`tilttek/sets`](https://github.com/TiltTek/sets) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/sets)) — Des ensembles versionnés à paliers et récompenses, une brique neutre
- `tilttek/exchange-bundle` · 🧪 en incubation — Boutiques de récompenses et échanges entre membres dans Symfony
- `tilttek/leaderboards-bundle` · 🧪 en incubation — Les classements configurés et montrés dans Symfony
- `tilttek/kudos` · 🧪 en incubation — Les remerciements entre membres, sans décompte public ni classement
- `tilttek/referrals` · 🧪 en incubation — Le parrainage récompensé en points, jamais en argent
- `tilttek/guilds` · 🧪 en incubation — Les guildes de membres et leurs objectifs communs
- `tilttek/check-in-rewards` · 🧪 en incubation — La récompense d'une présence, au kiosque d'une boutique ou en convention
- `tilttek/predictions` · 🧪 en incubation — Les prédictions misées en points seulement
- `tilttek/raffle` · 🧪 en incubation — Les tirages au sort vérifiables, sans achat de chances
- `tilttek/fan-awards` · 🧪 en incubation — Les prix des fans : catégories, mises en nomination, votes
- `tilttek/geek-dates` · 🧪 en incubation — Les dates de la culture geek, en données
- `tilttek/rpg-calendar-events` · 🧪 en incubation — Les événements du calendrier rôliste, en données
- `tilttek/celebrations` · 🧪 en incubation — La boîte des récompenses, qui reçoit les réussites de chaque paquet et montre chacune une fois
- `tilttek/bounties` · 🧪 en incubation — Les primes ludiques prépayées en points, limitées dans le temps, jamais en argent
- `tilttek/friend-challenges` · 🧪 en incubation — Les défis créés par les membres, entre amis aussi, avec un prix en points gardé en dépôt
- `tilttek/gamification-insights` · 🧪 en incubation — Un tableau de bord agrégé et anonyme pour équilibrer la ludification
- `tilttek/play-insights-bundle` · 🧪 en incubation — Les mesures de jeu partagées par les quêtes et la progression, en agrégat

</details>

<details>
<summary><b>Dés et hasard</b> — ✅ 9 · 🧪 7</summary>

- [`tilttek/dice`](https://github.com/TiltTek/dice) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/dice)) — La notation des dés lue, validée et lancée : réserves, faces propres, lancers vérifiables et rejouables
- [`tilttek/dice-bundle`](https://github.com/TiltTek/dice-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/dice-bundle)) — Les lancers de dés dans Symfony : lancers rejouables, macros, champ de formulaire et Twig
- [`tilttek/generator`](https://github.com/TiltTek/generator) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/generator)) — Des générateurs aléatoires écrits comme des données : listes pondérées, noms de Markov, gabarits Twig en bac à sable, grammaire en six langues, cartes, tables à mémoire
- [`tilttek/generator-bundle`](https://github.com/TiltTek/generator-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/generator-bundle)) — Les générateurs dans Symfony : commandes, Twig, contrôleur Stimulus et API de tirage sous limite de débit
- [`tilttek/dice-probability`](https://github.com/TiltTek/dice-probability) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/dice-probability)) — Les statistiques exactes des dés : distributions, au moins / au plus, moyenne, événements
- [`tilttek/loot-tables`](https://github.com/TiltTek/loot-tables) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/loot-tables)) — Des tables de butin qui déclarent leurs dés, tirées de façon vérifiable une seule fois (nom provisoire)
- [`tilttek/accessible-dice`](https://github.com/TiltTek/accessible-dice) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/accessible-dice)) — Des dés lisibles sans voir les couleurs ni viser de petits boutons, annoncés aux lecteurs d'écran
- [`tilttek/secret-rolls`](https://github.com/TiltTek/secret-rolls) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/secret-rolls)) — Les jets cachés du meneur, engagés d'avance et vérifiables après le dévoilement
- [`tilttek/heraldry`](https://github.com/TiltTek/heraldry) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/heraldry)) — Des armoiries tirées d'une graine, blasonnées en anglais et en français, en SVG sûr
- `tilttek/dice-probability-bundle` · 🧪 en incubation — Les statistiques des dés en tableaux et graphiques en Live Component
- `tilttek/loot-tables-bundle` · 🧪 en incubation — Les tables de butin dans Symfony, avec les engagements publiés des tirages
- `tilttek/dice-tower` · 🧪 en incubation — La tour de dés commune d'une table : chaque jet vu par tous, dans l'ordre
- `tilttek/dice-jail` · 🧪 en incubation — La prison des dés malchanceux, et les statistiques qui la justifient
- `tilttek/dice-skins` · 🧪 en incubation — L'apparence des dés d'un membre
- `tilttek/luck-tokens` · 🧪 en incubation — Les jetons de chance, d'inspiration ou de destin qu'une table distribue et dépense
- `tilttek/card-deck` · 🧪 en incubation — Des paquets de cartes mélangés, tirés et défaussés

</details>

<details>
<summary><b>À la table</b> — ✅ 1 · 🧪 17</summary>

- [`tilttek/table-safety`](https://github.com/TiltTek/table-safety) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/table-safety)) — Des outils de sécurité pour les jeux de table : lignes et voiles, signaux anonymes, crédits
- `tilttek/table-safety-bundle` · 🧪 en incubation — Les outils de sécurité dans Symfony, avec modèles de séance zéro
- `tilttek/table-presence` · 🧪 en incubation — Qui est à la table en ligne, absent ou en pause
- `tilttek/table-rules` · 🧪 en incubation — Les règles maison écrites et acceptées, et les variantes qu'une table choisit
- `tilttek/spotlight` · 🧪 en incubation — Partager le temps de jeu et voir qui attend son tour
- `tilttek/initiative-cards` · 🧪 en incubation — Le suivi d'initiative en cartes
- `tilttek/gm-screen` · 🧪 en incubation — L'écran du meneur, à l'écran ou imprimé
- `tilttek/session-prep` · 🧪 en incubation — La préparation d'une séance : scènes, PNJ, notes
- `tilttek/gm-tips` · 🧪 en incubation — Les conseils au meneur, selon la situation
- `tilttek/player-knowledge` · 🧪 en incubation — Ce que savent les joueurs, séparé de ce que savent leurs personnages
- `tilttek/handouts` · 🧪 en incubation — Les documents remis aux joueurs pendant la partie
- `tilttek/soundboard` · 🧪 en incubation — Les ambiances et les effets sonores d'une séance
- `tilttek/rpg-systems` · 🧪 en incubation — Le référentiel des systèmes de jeu : caractéristiques, dés, termes
- `tilttek/reference-tables` · 🧪 en incubation — Les tables de référence d'un système
- `tilttek/rules-lookup` · 🧪 en incubation — La recherche dans les règles d'un système, SRD compris
- `tilttek/flashcards` · 🧪 en incubation — Apprendre les règles d'un système par cartes à répétition espacée
- `tilttek/encounter` · 🧪 en incubation — Une rencontre composée et équilibrée selon le système
- `tilttek/grid` · 🧪 en incubation — Grilles carrées, hexagonales, isométriques ou absentes, alignement et DPI ; des outils, jamais une table virtuelle

</details>

<details>
<summary><b>Personnages</b> — 🧪 10</summary>

- `tilttek/character-sheet` · 🧪 en incubation — La fiche de personnage selon le système : caractéristiques calculées, équipement
- `tilttek/inventory` · 🧪 en incubation — L'inventaire d'un personnage et son encombrement
- `tilttek/conditions` · 🧪 en incubation — Les états et les effets : poisons, maladies, mutations, membres perdus
- `tilttek/party` · 🧪 en incubation — Le groupe d'une campagne, ce qu'il partage, et sa composition équilibrée
- `tilttek/random-character` · 🧪 en incubation — Le personnage tiré au hasard, prêt à jouer
- `tilttek/token-maker` · 🧪 en incubation — Les jetons de table virtuelle tirés d'une image
- `tilttek/relationships` · 🧪 en incubation — Les liens entre personnages et PNJ, et leur évolution
- `tilttek/polyglot` · 🧪 en incubation — Les langues qu'un personnage parle et lit, et ce qu'il comprend d'un texte
- `tilttek/character-retirement` · 🧪 en incubation — La retraite ou la mort d'un personnage, et son mémorial
- `tilttek/crafting` · 🧪 en incubation — Les recettes d'objets qui combinent ou font évoluer des objets

</details>

<details>
<summary><b>Campagnes et mondes</b> — ✅ 2 · 🧪 14</summary>

- [`tilttek/weather`](https://github.com/TiltTek/weather) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/weather)) — La météo du monde du jeu : saisons et zones climatiques, conditions qui suivent la veille, reproductible à partir d'une graine
- [`tilttek/puzzle-builder`](https://github.com/TiltTek/puzzle-builder) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/puzzle-builder)) — Des énigmes vérifiées sur le serveur : réponses normalisées, propositions bornées, indices par paliers, graphe de déverrouillage
- `tilttek/session-scheduler` · 🧪 en incubation — Les séances d'une campagne : récurrence, absences, report
- `tilttek/campaign-wiki` · 🧪 en incubation — Le wiki d'une campagne et les secrets du meneur
- `tilttek/journal` · 🧪 en incubation — Un journal à genres : résumés de séance, journaux de personnage et de jeu solo
- `tilttek/campaign-stats` · 🧪 en incubation — Les statistiques d'une campagne
- `tilttek/factions` · 🧪 en incubation — Les factions, leur réputation et leurs horloges
- `tilttek/downtime` · 🧪 en incubation — Les activités entre deux aventures : métier, recherche, entraînement
- `tilttek/in-character-mail` · 🧪 en incubation — Le courrier en personnage entre les séances, lu par le meneur
- `tilttek/legacy-campaign` · 🧪 en incubation — Les campagnes héritage et leurs changements permanents
- `tilttek/west-marches` · 🧪 en incubation — Les campagnes ouvertes à plusieurs meneurs et à des tables changeantes
- `tilttek/pbp` · 🧪 en incubation — La partie par messages, en fils de scène
- `tilttek/homebrew-hub` · 🧪 en incubation — Les règles maison partagées, notées et reprises d'une table à l'autre
- `tilttek/fantasy-calendar` · 🧪 en incubation — Les calendriers imaginaires
- `tilttek/travel` · 🧪 en incubation — Les voyages, leurs durées et leurs aléas
- `tilttek/player-handbook` · 🧪 en incubation — Le manuel du joueur d'une campagne

</details>

<details>
<summary><b>Trouver des joueurs et soirées de jeux</b> — 🧪 8</summary>

- `tilttek/game-catalog` · 🧪 en incubation — Un catalogue de jeux unique que chaque site active : BoardGameGeek, RPGGeek, saisie, errata
- `tilttek/looking-for-group` · 🧪 en incubation — Trouver des joueurs par système, par lieu ou en ligne
- `tilttek/game-night` · 🧪 en incubation — Les soirées de jeux d'un club ou d'une boutique : tables, jeux, inscriptions
- `tilttek/tournament` · 🧪 en incubation — Les tournois en rondes suisses ou à élimination, et leurs appariements
- `tilttek/math-trade` · 🧪 en incubation — L'échange de jeux en chaîne : la plus longue chaîne calculée, chacun donne un jeu et en reçoit un
- `tilttek/game-shelf` · 🧪 en incubation — L'étagère de jeux d'un membre et sa liste de souhaits priorisée
- `tilttek/play-log` · 🧪 en incubation — Le journal des parties jouées, aux joueurs anonymes par défaut
- `tilttek/rating` · 🧪 en incubation — Le classement Elo par jeu, privé par défaut, avec un mode amical sans cote

</details>

<details>
<summary><b>Jeux et concours</b> — ✅ 4 · 🧪 10</summary>

- [`tilttek/bingo`](https://github.com/TiltTek/bingo) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/bingo)) — Le bingo aux cartes tirées d'un secret du serveur, cartes imprimées vérifiables
- [`tilttek/deck-builder`](https://github.com/TiltTek/deck-builder) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/deck-builder)) — Des paquets de cartes selon les règles déclarées d'un format, chaque infraction lisible, sans catalogue d'éditeur
- [`tilttek/game-engine`](https://github.com/TiltTek/game-engine) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/game-engine)) — Des jeux au tour par tour en journal de coups, hasard engagé d'avance, rejeu
- [`tilttek/game-engine-bundle`](https://github.com/TiltTek/game-engine-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/game-engine-bundle)) — Des tables de jeu dans Symfony : sièges opaques, DBAL, verrou, Mercure privé
- `tilttek/quiz` · 🧪 en incubation — Les jeux-questionnaires : questions, minuterie, score
- `tilttek/mini-games` · 🧪 en incubation — Les petits jeux qui se jouent dans le site
- `tilttek/tavern-games` · 🧪 en incubation — Les jeux de taverne d'un univers de jeu, jouables en ligne
- `tilttek/escape-room` · 🧪 en incubation — Les jeux d'évasion : énigmes enchaînées, indices, chronomètre
- `tilttek/murder-mystery` · 🧪 en incubation — Les soirées meurtre et mystère : rôles, indices, révélation
- `tilttek/cosplay-contest` · 🧪 en incubation — Le concours de costumes : inscriptions, passage, jury et vote du public
- `tilttek/cosplay-progress` · 🧪 en incubation — Le journal d'un costume en cours, étape par étape
- `tilttek/score-sheets` · 🧪 en incubation — Les feuilles de score
- `tilttek/turn-clock` · 🧪 en incubation — Les horloges de tour : temps initial, temps par coup, coups par jour
- `tilttek/jam` · 🧪 en incubation — Les concours de création à thème et à échéance : soumissions, votes et jury

</details>

<details>
<summary><b>Loisirs</b> — ✅ 2 · 🧪 4</summary>

- [`tilttek/wargame-army`](https://github.com/TiltTek/wargame-army) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/wargame-army)) — Des listes d'armée sur un moteur générique, contre un catalogue que fournit l'application
- [`tilttek/writing-goals`](https://github.com/TiltTek/writing-goals) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/writing-goals)) — Les objectifs d'écriture d'un auteur : un plan qui suit les jours où il écrit, sans série à briser
- `tilttek/minis-tracker` · 🧪 en incubation — Le suivi des figurines achetées, montées et peintes
- `tilttek/paint-recipes` · 🧪 en incubation — Les recettes de peinture des figurines : couleurs, étapes, photos
- `tilttek/reading-quests` · 🧪 en incubation — Les quêtes de lecture d'un livre
- `tilttek/geocache-quests` · 🧪 en incubation — Les quêtes de géocache

</details>

<details>
<summary><b>Grandeur nature</b> — 🧪 8</summary>

- `tilttek/larp-characters` · 🧪 en incubation — Les personnages d'un grandeur nature et leurs fiches
- `tilttek/larp-checkin` · 🧪 en incubation — L'accueil des joueurs sur le terrain
- `tilttek/larp-economy` · 🧪 en incubation — La monnaie et les échanges d'un grandeur nature
- `tilttek/larp-crafting` · 🧪 en incubation — L'artisanat d'un grandeur nature
- `tilttek/larp-spells` · 🧪 en incubation — Les sorts d'un grandeur nature
- `tilttek/larp-timeline` · 🧪 en incubation — La ligne du temps de l'univers et des événements d'un grandeur nature
- `tilttek/larp-rules-quiz` · 🧪 en incubation — Le questionnaire sur les règles avant le premier jeu
- `tilttek/larp-plots` · 🧪 en incubation — L'écriture des intrigues d'un grandeur nature, liées à ses personnages

</details>


### Participer

- 💬 Questions et idées : [Discussions](https://github.com/orgs/TiltTek/discussions)
- 🐛 Bogues et demandes de fonctions : un ticket dans le dépôt concerné
- 🤝 [Contribuer](https://github.com/TiltTek/.github/blob/main/CONTRIBUTING.md) ·
  [Code de conduite](https://github.com/TiltTek/.github/blob/main/CODE_OF_CONDUCT.md) ·
  [Sécurité](https://github.com/TiltTek/.github/blob/main/SECURITY.md) ·
  [Soutien](https://github.com/TiltTek/.github/blob/main/SUPPORT.md)
- 🌐 [tilttek.com](https://tilttek.com) · projet frère : [PHIL](https://github.com/parler-haut-interagir-librement)
