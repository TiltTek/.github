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
  (today: PHP 8.6); a deprecation on the next PHP fails the build. The floor moves up at the next version's x.y.3,
  always in a new version of our packages.
- **Strict quality gates.** PHPStan at its maximum level with strict rules, PHP-CS-Fixer with the Symfony rules and
  strict types, Rector, Deptrac, Arkitect, PHPUnit failing on any deprecation, and every package tested on its own.
- **A 100 % mutation score.** Infection must kill every mutant; the bar is never lowered.
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
| [ux-kit](https://github.com/TiltTek/ux-kit) | Gamification recipes for the Symfony UX Toolkit — achievement showcase, level gauge, streak flame, quest board, leaderboard, dice roller, collection binder — built on the Shadcn-compatible components and styled with phil-ux. `php bin/console ux:install <recipe> --kit=github.com/TiltTek/ux-kit` | 🗓️ skeleton |
| [ux-kit-shadcn](https://github.com/TiltTek/ux-kit-shadcn) | The same recipes in Tailwind, in the Shadcn style | 🗓️ skeleton |

## The packages

✅ **released** · 🧪 **written, in incubation** (approximate completion) · 🦴 **skeleton in incubation** (the package
exists, its code is not written yet: ≈ 0 %) · 🗓️ **planned**

**129 packages:** 17 released, 112 in incubation (7 written, 105 skeletons near 0 %), 0 planned. Percentages are estimates from our
latest status report (11 November 2026). The released packages are developed in the public monorepo
[`tilttek`](https://github.com/TiltTek/tilttek), each split into its own read-only repository.

<details>
<summary><b>Gamification core</b> — ✅ 13 · 🧪 3 · 🦴 18</summary>

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
- `tilttek/exchange-bundle` · 🧪 90% — Reward shops and member trades in Symfony
- `tilttek/leaderboards` · 🧪 85% — Leaderboards by measure and period, opt-in, pseudonyms, friend circles, snapshots
- `tilttek/leaderboards-bundle` · 🧪 85% — Leaderboards configured and shown in Symfony
- `tilttek/kudos` · 🦴 skeleton, ≈ 0% — Thanks between members, with no public count or ranking
- `tilttek/referrals` · 🦴 skeleton, ≈ 0% — Referrals rewarded in points, never in money
- `tilttek/guilds` · 🦴 skeleton, ≈ 0% — Member guilds and their shared goals
- `tilttek/seasonal-events` · 🦴 skeleton, ≈ 0% — Seasons and their events: quests, items and decor of a period
- `tilttek/check-in-rewards` · 🦴 skeleton, ≈ 0% — Rewards for showing up, at a shop booth or a convention
- `tilttek/stickers` · 🦴 skeleton, ≈ 0% — Virtual stickers for profiles and messages
- `tilttek/advent-calendar` · 🦴 skeleton, ≈ 0% — An advent calendar: one box a day, one surprise a box
- `tilttek/predictions` · 🦴 skeleton, ≈ 0% — Predictions staked in points only
- `tilttek/raffle` · 🦴 skeleton, ≈ 0% — Verifiable draws, with no buying of chances
- `tilttek/fan-awards` · 🦴 skeleton, ≈ 0% — Fan awards: categories, nominations, votes
- `tilttek/geek-dates` · 🦴 skeleton, ≈ 0% — Geek culture dates, as data
- `tilttek/rpg-calendar-events` · 🦴 skeleton, ≈ 0% — Role-playing calendar events, as data
- `tilttek/sets` · 🦴 skeleton, ≈ 0% — Shared code for badge sets and collection sets, a neutral building block
- `tilttek/celebrations` · 🦴 skeleton, ≈ 0% — A rewards box that receives every package's achievements and shows each once
- `tilttek/bounties` · 🦴 skeleton, ≈ 0% — Playful bounties prepaid in points, time-limited, never in money
- `tilttek/friend-challenges` · 🦴 skeleton, ≈ 0% — Member-made challenges, between friends too, with a points prize held in escrow
- `tilttek/gamification-insights` · 🦴 skeleton, ≈ 0% — An aggregated, anonymous dashboard to balance gamification
- `tilttek/play-insights-bundle` · 🦴 skeleton, ≈ 0% — Play measures shared by quests and progression, in aggregate

</details>

<details>
<summary><b>Dice &amp; randomness</b> — ✅ 4 · 🧪 4 · 🦴 8</summary>

- [`tilttek/dice`](https://github.com/TiltTek/dice) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/dice)) — Dice notation parsed, validated and rolled: pools, custom faces, verifiable and replayable rolls
- [`tilttek/dice-bundle`](https://github.com/TiltTek/dice-bundle) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/dice-bundle)) — Dice rolls in Symfony: replayable rolls, macros, a form field and Twig
- [`tilttek/dice-probability`](https://github.com/TiltTek/dice-probability) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/dice-probability)) — Exact dice statistics: distributions, at least / at most, mean, events
- [`tilttek/loot-tables`](https://github.com/TiltTek/loot-tables) · ✅ released ([Packagist](https://packagist.org/packages/tilttek/loot-tables)) — Loot tables that declare their dice, drawn verifiably once (provisional name)
- `tilttek/generator` · 🧪 92% — A grammar engine for random text, with French, English, Spanish, German, Italian and Portuguese grammars
- `tilttek/generator-bundle` · 🧪 93% — Generators in Symfony, served by an API
- `tilttek/dice-probability-bundle` · 🧪 90% — Dice statistics as tables and charts in Live Components
- `tilttek/loot-tables-bundle` · 🧪 85% — Loot tables in Symfony, with published commitments to the draws
- `tilttek/accessible-dice` · 🦴 skeleton, ≈ 0% — Dice read without seeing colours or aiming at small buttons, announced to screen readers
- `tilttek/dice-tower` · 🦴 skeleton, ≈ 0% — A table's shared dice tower: every roll seen by all, in order
- `tilttek/secret-rolls` · 🦴 skeleton, ≈ 0% — Hidden GM rolls, kept verifiable and revealed later
- `tilttek/dice-jail` · 🦴 skeleton, ≈ 0% — Dice jail for unlucky dice, and the statistics behind it
- `tilttek/dice-skins` · 🦴 skeleton, ≈ 0% — The look of a member's dice
- `tilttek/luck-tokens` · 🦴 skeleton, ≈ 0% — Luck, inspiration or fate tokens a table gives and spends
- `tilttek/card-deck` · 🦴 skeleton, ≈ 0% — Card decks shuffled, drawn and discarded
- `tilttek/heraldry` · 🦴 skeleton, ≈ 0% — Coats of arms generated and blazoned

</details>

<details>
<summary><b>At the table</b> — 🦴 18</summary>

- `tilttek/table-safety` · 🦴 skeleton, ≈ 0% — Safety tools: lines and veils, consent checklist, session zero, X-card, anonymous by default
- `tilttek/table-safety-bundle` · 🦴 skeleton, ≈ 0% — Safety tools in Symfony, with session-zero templates
- `tilttek/table-presence` · 🦴 skeleton, ≈ 0% — Who is at the online table, away or on a break
- `tilttek/table-rules` · 🦴 skeleton, ≈ 0% — House rules written and accepted, and the rule variants a table picks
- `tilttek/spotlight` · 🦴 skeleton, ≈ 0% — Share playing time fairly and see who is waiting
- `tilttek/initiative-cards` · 🦴 skeleton, ≈ 0% — Initiative tracking with cards
- `tilttek/gm-screen` · 🦴 skeleton, ≈ 0% — A GM screen, on screen or printed
- `tilttek/session-prep` · 🦴 skeleton, ≈ 0% — Session preparation: scenes, NPCs, notes
- `tilttek/gm-tips` · 🦴 skeleton, ≈ 0% — Tips for the GM, by situation
- `tilttek/player-knowledge` · 🦴 skeleton, ≈ 0% — What players know, kept apart from what their characters know
- `tilttek/handouts` · 🦴 skeleton, ≈ 0% — Handouts given to players during play
- `tilttek/soundboard` · 🦴 skeleton, ≈ 0% — Ambiences and sound effects for a session
- `tilttek/rpg-systems` · 🦴 skeleton, ≈ 0% — A registry of game systems: attributes, dice, terms
- `tilttek/reference-tables` · 🦴 skeleton, ≈ 0% — A system's reference tables
- `tilttek/rules-lookup` · 🦴 skeleton, ≈ 0% — Search a system's rules, SRDs included
- `tilttek/flashcards` · 🦴 skeleton, ≈ 0% — Learn a system's rules with spaced-repetition cards
- `tilttek/encounter` · 🦴 skeleton, ≈ 0% — Encounters composed and balanced for the system
- `tilttek/grid` · 🦴 skeleton, ≈ 0% — Square, hex, isometric or no grid, alignment and DPI reading; tools, never a virtual tabletop

</details>

<details>
<summary><b>Characters</b> — 🦴 10</summary>

- `tilttek/character-sheet` · 🦴 skeleton, ≈ 0% — Character sheets per system: computed attributes, equipment
- `tilttek/inventory` · 🦴 skeleton, ≈ 0% — A character's inventory and encumbrance
- `tilttek/conditions` · 🦴 skeleton, ≈ 0% — Conditions and effects: poisons, diseases, mutations, lost limbs
- `tilttek/party` · 🦴 skeleton, ≈ 0% — A campaign's party, what it shares, and a balanced line-up
- `tilttek/random-character` · 🦴 skeleton, ≈ 0% — A random character, ready to play
- `tilttek/token-maker` · 🦴 skeleton, ≈ 0% — Virtual tabletop tokens from an image
- `tilttek/relationships` · 🦴 skeleton, ≈ 0% — Links between characters and NPCs, and how they evolve
- `tilttek/polyglot` · 🦴 skeleton, ≈ 0% — The languages a character speaks and reads, and what they understand of a text
- `tilttek/character-retirement` · 🦴 skeleton, ≈ 0% — A character's retirement or death, and their memorial
- `tilttek/crafting` · 🦴 skeleton, ≈ 0% — Item recipes that combine or evolve items

</details>

<details>
<summary><b>Campaigns &amp; worlds</b> — 🦴 16</summary>

- `tilttek/session-scheduler` · 🦴 skeleton, ≈ 0% — Campaign sessions: recurrence, absences, rescheduling
- `tilttek/campaign-wiki` · 🦴 skeleton, ≈ 0% — A campaign wiki and the GM's secrets
- `tilttek/journal` · 🦴 skeleton, ≈ 0% — Journals of many kinds: session recaps, character and solo journals
- `tilttek/campaign-stats` · 🦴 skeleton, ≈ 0% — A campaign's statistics
- `tilttek/factions` · 🦴 skeleton, ≈ 0% — Factions, their reputation and their clocks
- `tilttek/downtime` · 🦴 skeleton, ≈ 0% — Downtime between adventures: crafting, research, training
- `tilttek/in-character-mail` · 🦴 skeleton, ≈ 0% — In-character letters between sessions, read by the GM
- `tilttek/legacy-campaign` · 🦴 skeleton, ≈ 0% — Legacy campaigns and their permanent changes
- `tilttek/west-marches` · 🦴 skeleton, ≈ 0% — Open campaigns with several GMs and changing tables
- `tilttek/pbp` · 🦴 skeleton, ≈ 0% — Play-by-post, in scene threads
- `tilttek/homebrew-hub` · 🦴 skeleton, ≈ 0% — House rules shared, rated and reused from table to table
- `tilttek/fantasy-calendar` · 🦴 skeleton, ≈ 0% — Fantasy calendars
- `tilttek/weather` · 🦴 skeleton, ≈ 0% — In-world weather
- `tilttek/travel` · 🦴 skeleton, ≈ 0% — Journeys, their duration and their hazards
- `tilttek/puzzle-builder` · 🦴 skeleton, ≈ 0% — Riddles and puzzles for a scenario
- `tilttek/player-handbook` · 🦴 skeleton, ≈ 0% — A campaign's player handbook

</details>

<details>
<summary><b>Finding players &amp; game nights</b> — 🦴 8</summary>

- `tilttek/game-catalog` · 🦴 skeleton, ≈ 0% — One game catalogue each site switches on: BoardGameGeek, RPGGeek, manual entries, errata
- `tilttek/looking-for-group` · 🦴 skeleton, ≈ 0% — Find players by system, by place or online
- `tilttek/game-night` · 🦴 skeleton, ≈ 0% — Game nights for a club or a shop: tables, games, sign-ups
- `tilttek/tournament` · 🦴 skeleton, ≈ 0% — Swiss or elimination tournaments and their pairings
- `tilttek/math-trade` · 🦴 skeleton, ≈ 0% — Chain game trades: the longest chain computed, everyone gives one and gets one
- `tilttek/game-shelf` · 🦴 skeleton, ≈ 0% — A member's game shelf and prioritized wishlist
- `tilttek/play-log` · 🦴 skeleton, ≈ 0% — A log of games played, players anonymous by default
- `tilttek/rating` · 🦴 skeleton, ≈ 0% — Per-game Elo rating, private by default, with an unrated friendly mode

</details>

<details>
<summary><b>Games &amp; contests</b> — 🦴 13</summary>

- `tilttek/quiz` · 🦴 skeleton, ≈ 0% — Quizzes: questions, timer, score
- `tilttek/bingo` · 🦴 skeleton, ≈ 0% — Bingo cards for a convention or a session, ticked by events
- `tilttek/mini-games` · 🦴 skeleton, ≈ 0% — Small games played on the site
- `tilttek/tavern-games` · 🦴 skeleton, ≈ 0% — Tavern games from a game world, playable online
- `tilttek/escape-room` · 🦴 skeleton, ≈ 0% — Escape rooms: chained puzzles, hints, timer
- `tilttek/murder-mystery` · 🦴 skeleton, ≈ 0% — Murder-mystery nights: roles, clues, reveal
- `tilttek/cosplay-contest` · 🦴 skeleton, ≈ 0% — Cosplay contests: entries, walk-on, jury and public vote
- `tilttek/cosplay-progress` · 🦴 skeleton, ≈ 0% — A costume's build log, step by step
- `tilttek/score-sheets` · 🦴 skeleton, ≈ 0% — Score sheets
- `tilttek/deck-builder` · 🦴 skeleton, ≈ 0% — Build a card deck to a game's rules
- `tilttek/game-engine` · 🦴 skeleton, ≈ 0% — A generic state machine for online tabletop games, with Mercure and no game rules
- `tilttek/turn-clock` · 🦴 skeleton, ≈ 0% — Turn clocks: initial time, time per move, moves per day
- `tilttek/jam` · 🦴 skeleton, ≈ 0% — Themed creation jams with deadlines: entries, votes and jury

</details>

<details>
<summary><b>Hobbies</b> — 🦴 6</summary>

- `tilttek/wargame-army` · 🦴 skeleton, ≈ 0% — Army lists for miniature games
- `tilttek/minis-tracker` · 🦴 skeleton, ≈ 0% — Track miniatures bought, built and painted
- `tilttek/paint-recipes` · 🦴 skeleton, ≈ 0% — Miniature paint recipes: colours, steps, photos
- `tilttek/reading-quests` · 🦴 skeleton, ≈ 0% — Reading quests for a book
- `tilttek/writing-goals` · 🦴 skeleton, ≈ 0% — An author's writing goals
- `tilttek/geocache-quests` · 🦴 skeleton, ≈ 0% — Geocache quests

</details>

<details>
<summary><b>Live-action role-play</b> — 🦴 8</summary>

- `tilttek/larp-characters` · 🦴 skeleton, ≈ 0% — LARP characters and their sheets
- `tilttek/larp-checkin` · 🦴 skeleton, ≈ 0% — Player check-in on site
- `tilttek/larp-economy` · 🦴 skeleton, ≈ 0% — A LARP's currency and trade
- `tilttek/larp-crafting` · 🦴 skeleton, ≈ 0% — LARP crafting
- `tilttek/larp-spells` · 🦴 skeleton, ≈ 0% — LARP spells
- `tilttek/larp-timeline` · 🦴 skeleton, ≈ 0% — The timeline of a LARP's world and events
- `tilttek/larp-rules-quiz` · 🦴 skeleton, ≈ 0% — A rules quiz before the first game
- `tilttek/larp-plots` · 🦴 skeleton, ≈ 0% — Writing a LARP's plots, linked to its characters

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
  monte au x.y.3 de la version suivante, toujours dans une nouvelle version de nos paquets.
- **Des barrières de qualité strictes.** PHPStan au niveau maximal avec les règles strictes, PHP-CS-Fixer aux règles
  de Symfony et types stricts, Rector, Deptrac, Arkitect, PHPUnit qui échoue à la moindre dépréciation, et chaque
  paquet testé seul.
- **Un score de mutation de 100 %.** Infection doit tuer chaque mutant ; la barre ne baisse jamais.
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
| [ux-kit](https://github.com/TiltTek/ux-kit) | Des recettes de ludification pour le Toolkit de Symfony UX — vitrine des réussites, jauge de niveau, flamme de série, tableau des quêtes, classement, lanceur de dés, classeur de collection — bâties sur les composants compatibles Shadcn et habillées par phil-ux. `php bin/console ux:install <recette> --kit=github.com/TiltTek/ux-kit` | 🗓️ squelette |
| [ux-kit-shadcn](https://github.com/TiltTek/ux-kit-shadcn) | Les mêmes recettes en Tailwind, à la façon de Shadcn | 🗓️ squelette |

### Les paquets

✅ **publié** · 🧪 **écrit, en incubation** (avancement approximatif) · 🦴 **squelette en incubation** (le paquet
existe, son code n'est pas encore écrit : ≈ 0 %) · 🗓️ **prévu**

**129 paquets :** 17 publiés, 112 en incubation (7 écrits, 105 squelettes à près de 0 %), 0 prévus. Les pourcentages sont des
estimations tirées de notre dernier rapport d'avancement (11 novembre 2026). Les paquets publiés sont développés dans
le monodépôt public [`tilttek`](https://github.com/TiltTek/tilttek), scindés chacun dans son propre dépôt en lecture seule.

<details>
<summary><b>Cœur de la ludification</b> — ✅ 13 · 🧪 3 · 🦴 18</summary>

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
- `tilttek/exchange-bundle` · 🧪 90 % — Boutiques de récompenses et échanges entre membres dans Symfony
- `tilttek/leaderboards` · 🧪 85 % — Classements par mesure et période, sur accord, pseudonymes, cercles d'amis, instantanés
- `tilttek/leaderboards-bundle` · 🧪 85 % — Les classements configurés et montrés dans Symfony
- `tilttek/kudos` · 🦴 squelette, ≈ 0 % — Les remerciements entre membres, sans décompte public ni classement
- `tilttek/referrals` · 🦴 squelette, ≈ 0 % — Le parrainage récompensé en points, jamais en argent
- `tilttek/guilds` · 🦴 squelette, ≈ 0 % — Les guildes de membres et leurs objectifs communs
- `tilttek/seasonal-events` · 🦴 squelette, ≈ 0 % — Les saisons et leurs événements : quêtes, objets et décors d'une période
- `tilttek/check-in-rewards` · 🦴 squelette, ≈ 0 % — La récompense d'une présence, au kiosque d'une boutique ou en convention
- `tilttek/stickers` · 🦴 squelette, ≈ 0 % — Les autocollants virtuels des profils et des messages
- `tilttek/advent-calendar` · 🦴 squelette, ≈ 0 % — Le calendrier de l'Avent : une case par jour, une surprise par case
- `tilttek/predictions` · 🦴 squelette, ≈ 0 % — Les prédictions misées en points seulement
- `tilttek/raffle` · 🦴 squelette, ≈ 0 % — Les tirages au sort vérifiables, sans achat de chances
- `tilttek/fan-awards` · 🦴 squelette, ≈ 0 % — Les prix des fans : catégories, mises en nomination, votes
- `tilttek/geek-dates` · 🦴 squelette, ≈ 0 % — Les dates de la culture geek, en données
- `tilttek/rpg-calendar-events` · 🦴 squelette, ≈ 0 % — Les événements du calendrier rôliste, en données
- `tilttek/sets` · 🦴 squelette, ≈ 0 % — Le code commun des ensembles de badges et de collection, une brique neutre
- `tilttek/celebrations` · 🦴 squelette, ≈ 0 % — La boîte des récompenses, qui reçoit les réussites de chaque paquet et montre chacune une fois
- `tilttek/bounties` · 🦴 squelette, ≈ 0 % — Les primes ludiques prépayées en points, limitées dans le temps, jamais en argent
- `tilttek/friend-challenges` · 🦴 squelette, ≈ 0 % — Les défis créés par les membres, entre amis aussi, avec un prix en points gardé en dépôt
- `tilttek/gamification-insights` · 🦴 squelette, ≈ 0 % — Un tableau de bord agrégé et anonyme pour équilibrer la ludification
- `tilttek/play-insights-bundle` · 🦴 squelette, ≈ 0 % — Les mesures de jeu partagées par les quêtes et la progression, en agrégat

</details>

<details>
<summary><b>Dés et hasard</b> — ✅ 4 · 🧪 4 · 🦴 8</summary>

- [`tilttek/dice`](https://github.com/TiltTek/dice) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/dice)) — La notation des dés lue, validée et lancée : réserves, faces propres, lancers vérifiables et rejouables
- [`tilttek/dice-bundle`](https://github.com/TiltTek/dice-bundle) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/dice-bundle)) — Les lancers de dés dans Symfony : lancers rejouables, macros, champ de formulaire et Twig
- [`tilttek/dice-probability`](https://github.com/TiltTek/dice-probability) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/dice-probability)) — Les statistiques exactes des dés : distributions, au moins / au plus, moyenne, événements
- [`tilttek/loot-tables`](https://github.com/TiltTek/loot-tables) · ✅ publié ([Packagist](https://packagist.org/packages/tilttek/loot-tables)) — Des tables de butin qui déclarent leurs dés, tirées de façon vérifiable une seule fois (nom provisoire)
- `tilttek/generator` · 🧪 92 % — Un moteur de grammaire pour le texte au hasard, avec les grammaires française, anglaise, espagnole, allemande, italienne et portugaise
- `tilttek/generator-bundle` · 🧪 93 % — Les générateurs dans Symfony, servis par une API
- `tilttek/dice-probability-bundle` · 🧪 90 % — Les statistiques des dés en tableaux et graphiques en Live Component
- `tilttek/loot-tables-bundle` · 🧪 85 % — Les tables de butin dans Symfony, avec les engagements publiés des tirages
- `tilttek/accessible-dice` · 🦴 squelette, ≈ 0 % — Des dés lisibles sans voir les couleurs ni viser de petits boutons, annoncés aux lecteurs d'écran
- `tilttek/dice-tower` · 🦴 squelette, ≈ 0 % — La tour de dés commune d'une table : chaque jet vu par tous, dans l'ordre
- `tilttek/secret-rolls` · 🦴 squelette, ≈ 0 % — Les jets cachés du meneur, gardés vérifiables et révélés ensuite
- `tilttek/dice-jail` · 🦴 squelette, ≈ 0 % — La prison des dés malchanceux, et les statistiques qui la justifient
- `tilttek/dice-skins` · 🦴 squelette, ≈ 0 % — L'apparence des dés d'un membre
- `tilttek/luck-tokens` · 🦴 squelette, ≈ 0 % — Les jetons de chance, d'inspiration ou de destin qu'une table distribue et dépense
- `tilttek/card-deck` · 🦴 squelette, ≈ 0 % — Des paquets de cartes mélangés, tirés et défaussés
- `tilttek/heraldry` · 🦴 squelette, ≈ 0 % — Les blasons générés et décrits

</details>

<details>
<summary><b>À la table</b> — 🦴 18</summary>

- `tilttek/table-safety` · 🦴 squelette, ≈ 0 % — Outils de sécurité : lignes et voiles, liste de consentement, séance zéro, carte X, anonymes par défaut
- `tilttek/table-safety-bundle` · 🦴 squelette, ≈ 0 % — Les outils de sécurité dans Symfony, avec modèles de séance zéro
- `tilttek/table-presence` · 🦴 squelette, ≈ 0 % — Qui est à la table en ligne, absent ou en pause
- `tilttek/table-rules` · 🦴 squelette, ≈ 0 % — Les règles maison écrites et acceptées, et les variantes qu'une table choisit
- `tilttek/spotlight` · 🦴 squelette, ≈ 0 % — Partager le temps de jeu et voir qui attend son tour
- `tilttek/initiative-cards` · 🦴 squelette, ≈ 0 % — Le suivi d'initiative en cartes
- `tilttek/gm-screen` · 🦴 squelette, ≈ 0 % — L'écran du meneur, à l'écran ou imprimé
- `tilttek/session-prep` · 🦴 squelette, ≈ 0 % — La préparation d'une séance : scènes, PNJ, notes
- `tilttek/gm-tips` · 🦴 squelette, ≈ 0 % — Les conseils au meneur, selon la situation
- `tilttek/player-knowledge` · 🦴 squelette, ≈ 0 % — Ce que savent les joueurs, séparé de ce que savent leurs personnages
- `tilttek/handouts` · 🦴 squelette, ≈ 0 % — Les documents remis aux joueurs pendant la partie
- `tilttek/soundboard` · 🦴 squelette, ≈ 0 % — Les ambiances et les effets sonores d'une séance
- `tilttek/rpg-systems` · 🦴 squelette, ≈ 0 % — Le référentiel des systèmes de jeu : caractéristiques, dés, termes
- `tilttek/reference-tables` · 🦴 squelette, ≈ 0 % — Les tables de référence d'un système
- `tilttek/rules-lookup` · 🦴 squelette, ≈ 0 % — La recherche dans les règles d'un système, SRD compris
- `tilttek/flashcards` · 🦴 squelette, ≈ 0 % — Apprendre les règles d'un système par cartes à répétition espacée
- `tilttek/encounter` · 🦴 squelette, ≈ 0 % — Une rencontre composée et équilibrée selon le système
- `tilttek/grid` · 🦴 squelette, ≈ 0 % — Grilles carrées, hexagonales, isométriques ou absentes, alignement et DPI ; des outils, jamais une table virtuelle

</details>

<details>
<summary><b>Personnages</b> — 🦴 10</summary>

- `tilttek/character-sheet` · 🦴 squelette, ≈ 0 % — La fiche de personnage selon le système : caractéristiques calculées, équipement
- `tilttek/inventory` · 🦴 squelette, ≈ 0 % — L'inventaire d'un personnage et son encombrement
- `tilttek/conditions` · 🦴 squelette, ≈ 0 % — Les états et les effets : poisons, maladies, mutations, membres perdus
- `tilttek/party` · 🦴 squelette, ≈ 0 % — Le groupe d'une campagne, ce qu'il partage, et sa composition équilibrée
- `tilttek/random-character` · 🦴 squelette, ≈ 0 % — Le personnage tiré au hasard, prêt à jouer
- `tilttek/token-maker` · 🦴 squelette, ≈ 0 % — Les jetons de table virtuelle tirés d'une image
- `tilttek/relationships` · 🦴 squelette, ≈ 0 % — Les liens entre personnages et PNJ, et leur évolution
- `tilttek/polyglot` · 🦴 squelette, ≈ 0 % — Les langues qu'un personnage parle et lit, et ce qu'il comprend d'un texte
- `tilttek/character-retirement` · 🦴 squelette, ≈ 0 % — La retraite ou la mort d'un personnage, et son mémorial
- `tilttek/crafting` · 🦴 squelette, ≈ 0 % — Les recettes d'objets qui combinent ou font évoluer des objets

</details>

<details>
<summary><b>Campagnes et mondes</b> — 🦴 16</summary>

- `tilttek/session-scheduler` · 🦴 squelette, ≈ 0 % — Les séances d'une campagne : récurrence, absences, report
- `tilttek/campaign-wiki` · 🦴 squelette, ≈ 0 % — Le wiki d'une campagne et les secrets du meneur
- `tilttek/journal` · 🦴 squelette, ≈ 0 % — Un journal à genres : résumés de séance, journaux de personnage et de jeu solo
- `tilttek/campaign-stats` · 🦴 squelette, ≈ 0 % — Les statistiques d'une campagne
- `tilttek/factions` · 🦴 squelette, ≈ 0 % — Les factions, leur réputation et leurs horloges
- `tilttek/downtime` · 🦴 squelette, ≈ 0 % — Les activités entre deux aventures : métier, recherche, entraînement
- `tilttek/in-character-mail` · 🦴 squelette, ≈ 0 % — Le courrier en personnage entre les séances, lu par le meneur
- `tilttek/legacy-campaign` · 🦴 squelette, ≈ 0 % — Les campagnes héritage et leurs changements permanents
- `tilttek/west-marches` · 🦴 squelette, ≈ 0 % — Les campagnes ouvertes à plusieurs meneurs et à des tables changeantes
- `tilttek/pbp` · 🦴 squelette, ≈ 0 % — La partie par messages, en fils de scène
- `tilttek/homebrew-hub` · 🦴 squelette, ≈ 0 % — Les règles maison partagées, notées et reprises d'une table à l'autre
- `tilttek/fantasy-calendar` · 🦴 squelette, ≈ 0 % — Les calendriers imaginaires
- `tilttek/weather` · 🦴 squelette, ≈ 0 % — La météo du monde du jeu
- `tilttek/travel` · 🦴 squelette, ≈ 0 % — Les voyages, leurs durées et leurs aléas
- `tilttek/puzzle-builder` · 🦴 squelette, ≈ 0 % — Les énigmes et casse-têtes d'un scénario
- `tilttek/player-handbook` · 🦴 squelette, ≈ 0 % — Le manuel du joueur d'une campagne

</details>

<details>
<summary><b>Trouver des joueurs et soirées de jeux</b> — 🦴 8</summary>

- `tilttek/game-catalog` · 🦴 squelette, ≈ 0 % — Un catalogue de jeux unique que chaque site active : BoardGameGeek, RPGGeek, saisie, errata
- `tilttek/looking-for-group` · 🦴 squelette, ≈ 0 % — Trouver des joueurs par système, par lieu ou en ligne
- `tilttek/game-night` · 🦴 squelette, ≈ 0 % — Les soirées de jeux d'un club ou d'une boutique : tables, jeux, inscriptions
- `tilttek/tournament` · 🦴 squelette, ≈ 0 % — Les tournois en rondes suisses ou à élimination, et leurs appariements
- `tilttek/math-trade` · 🦴 squelette, ≈ 0 % — L'échange de jeux en chaîne : la plus longue chaîne calculée, chacun donne un jeu et en reçoit un
- `tilttek/game-shelf` · 🦴 squelette, ≈ 0 % — L'étagère de jeux d'un membre et sa liste de souhaits priorisée
- `tilttek/play-log` · 🦴 squelette, ≈ 0 % — Le journal des parties jouées, aux joueurs anonymes par défaut
- `tilttek/rating` · 🦴 squelette, ≈ 0 % — Le classement Elo par jeu, privé par défaut, avec un mode amical sans cote

</details>

<details>
<summary><b>Jeux et concours</b> — 🦴 13</summary>

- `tilttek/quiz` · 🦴 squelette, ≈ 0 % — Les jeux-questionnaires : questions, minuterie, score
- `tilttek/bingo` · 🦴 squelette, ≈ 0 % — Les cartes de bingo d'une convention ou d'une séance, cochées par les événements
- `tilttek/mini-games` · 🦴 squelette, ≈ 0 % — Les petits jeux qui se jouent dans le site
- `tilttek/tavern-games` · 🦴 squelette, ≈ 0 % — Les jeux de taverne d'un univers de jeu, jouables en ligne
- `tilttek/escape-room` · 🦴 squelette, ≈ 0 % — Les jeux d'évasion : énigmes enchaînées, indices, chronomètre
- `tilttek/murder-mystery` · 🦴 squelette, ≈ 0 % — Les soirées meurtre et mystère : rôles, indices, révélation
- `tilttek/cosplay-contest` · 🦴 squelette, ≈ 0 % — Le concours de costumes : inscriptions, passage, jury et vote du public
- `tilttek/cosplay-progress` · 🦴 squelette, ≈ 0 % — Le journal d'un costume en cours, étape par étape
- `tilttek/score-sheets` · 🦴 squelette, ≈ 0 % — Les feuilles de score
- `tilttek/deck-builder` · 🦴 squelette, ≈ 0 % — Construire un paquet de cartes selon les règles d'un jeu
- `tilttek/game-engine` · 🦴 squelette, ≈ 0 % — Une machine à états générique pour les jeux de table en ligne, avec Mercure et sans règles de jeu
- `tilttek/turn-clock` · 🦴 squelette, ≈ 0 % — Les horloges de tour : temps initial, temps par coup, coups par jour
- `tilttek/jam` · 🦴 squelette, ≈ 0 % — Les concours de création à thème et à échéance : soumissions, votes et jury

</details>

<details>
<summary><b>Loisirs</b> — 🦴 6</summary>

- `tilttek/wargame-army` · 🦴 squelette, ≈ 0 % — Les listes d'armée d'un jeu de figurines
- `tilttek/minis-tracker` · 🦴 squelette, ≈ 0 % — Le suivi des figurines achetées, montées et peintes
- `tilttek/paint-recipes` · 🦴 squelette, ≈ 0 % — Les recettes de peinture des figurines : couleurs, étapes, photos
- `tilttek/reading-quests` · 🦴 squelette, ≈ 0 % — Les quêtes de lecture d'un livre
- `tilttek/writing-goals` · 🦴 squelette, ≈ 0 % — Les objectifs d'écriture d'un auteur
- `tilttek/geocache-quests` · 🦴 squelette, ≈ 0 % — Les quêtes de géocache

</details>

<details>
<summary><b>Grandeur nature</b> — 🦴 8</summary>

- `tilttek/larp-characters` · 🦴 squelette, ≈ 0 % — Les personnages d'un grandeur nature et leurs fiches
- `tilttek/larp-checkin` · 🦴 squelette, ≈ 0 % — L'accueil des joueurs sur le terrain
- `tilttek/larp-economy` · 🦴 squelette, ≈ 0 % — La monnaie et les échanges d'un grandeur nature
- `tilttek/larp-crafting` · 🦴 squelette, ≈ 0 % — L'artisanat d'un grandeur nature
- `tilttek/larp-spells` · 🦴 squelette, ≈ 0 % — Les sorts d'un grandeur nature
- `tilttek/larp-timeline` · 🦴 squelette, ≈ 0 % — La ligne du temps de l'univers et des événements d'un grandeur nature
- `tilttek/larp-rules-quiz` · 🦴 squelette, ≈ 0 % — Le questionnaire sur les règles avant le premier jeu
- `tilttek/larp-plots` · 🦴 squelette, ≈ 0 % — L'écriture des intrigues d'un grandeur nature, liées à ses personnages

</details>


### Participer

- 💬 Questions et idées : [Discussions](https://github.com/orgs/TiltTek/discussions)
- 🐛 Bogues et demandes de fonctions : un ticket dans le dépôt concerné
- 🤝 [Contribuer](https://github.com/TiltTek/.github/blob/main/CONTRIBUTING.md) ·
  [Code de conduite](https://github.com/TiltTek/.github/blob/main/CODE_OF_CONDUCT.md) ·
  [Sécurité](https://github.com/TiltTek/.github/blob/main/SECURITY.md) ·
  [Soutien](https://github.com/TiltTek/.github/blob/main/SUPPORT.md)
- 🌐 [tilttek.com](https://tilttek.com) · projet frère : [PHIL](https://github.com/parler-haut-interagir-librement)
