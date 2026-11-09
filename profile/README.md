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

- **Written from scratch.** No third-party code is copied into a Tilttek package; other tools are studied for ideas,
  never pasted.
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
  [`TiltTek/tilttek`](https://github.com/TiltTek/tilttek) (not created yet), from which each package is split into
  its own read-only repository and published on [Packagist](https://packagist.org).
- **Tooling:** the same `phil/dev-tools` as PHIL.

## Tilttek UX kit

| Repository | What it holds | State |
|---|---|---|
| [ux-kit](https://github.com/TiltTek/ux-kit) | Gamification recipes for the Symfony UX Toolkit — achievement showcase, level gauge, streak flame, quest board, leaderboard, dice roller, collection binder — built on the Shadcn-compatible components and styled with phil-ux. `php bin/console ux:install <recipe> --kit=github.com/TiltTek/ux-kit` | 🗓️ skeleton |
| [ux-kit-shadcn](https://github.com/TiltTek/ux-kit-shadcn) | The same recipes in Tailwind, in the Shadcn style | 🗓️ skeleton |

## The packages

✅ **released** · 🧪 **written, in incubation** (approximate completion) · 🗓️ **planned**

**114 packages:** 24 in incubation, 90 planned; none released yet. Percentages are estimates from our
latest status report ((8 November 2026)).

<details>
<summary><b>Gamification core</b> — 🧪 16 · 🗓️ 12</summary>

- `tilttek/activity` · 🧪 95% — The common entry: member activity recorded once, its totals and replayable projections
- `tilttek/activity-bundle` · 🧪 95% — Activity recording in Symfony, with optional asynchronous projections
- `tilttek/points` · 🧪 95% — A double-entry points ledger: currencies, earning rules, caps, FIFO expiry, never negative
- `tilttek/points-bundle` · 🧪 95% — Points ledgers and rules configured in Symfony
- `tilttek/badges` · 🧪 90% — Badges and achievements: criteria, tiers, hidden achievements, titles, showcase
- `tilttek/badges-bundle` · 🧪 92% — Badges in Symfony: awarding, showcase, sharing with the member's consent
- `tilttek/progression` · 🧪 95% — Experience and levels on a curve, several tracks, streaks in the member's time zone, seasons
- `tilttek/progression-bundle` · 🧪 95% — Progression in Symfony, with streak freezes and milestone rewards
- `tilttek/quests` · 🧪 95% — Quests and challenges in steps: personal, community, team and duels
- `tilttek/quests-bundle` · 🧪 95% — Quests in Symfony, with seasonal dates computed
- `tilttek/collections` · 🧪 90% — Collectibles: rarity, sets, duplicates, item of the day, packs with published, verifiable odds
- `tilttek/collections-bundle` · 🧪 90% — Collections and dice sets in Symfony
- `tilttek/exchange` · 🧪 85% — Trade points for rewards in two steps, and swap collectibles between members
- `tilttek/exchange-bundle` · 🧪 90% — Reward shops and member trades in Symfony
- `tilttek/leaderboards` · 🧪 85% — Leaderboards by measure and period, opt-in, pseudonyms, friend circles, snapshots
- `tilttek/leaderboards-bundle` · 🧪 85% — Leaderboards configured and shown in Symfony
- `tilttek/kudos` · 🗓️ planned — Thanks between members, with no public count or ranking
- `tilttek/referrals` · 🗓️ planned — Referrals rewarded in points, never in money
- `tilttek/guilds` · 🗓️ planned — Member guilds and their shared goals
- `tilttek/seasonal-events` · 🗓️ planned — Seasons and their events: quests, items and decor of a period
- `tilttek/check-in-rewards` · 🗓️ planned — Rewards for showing up, at a shop booth or a convention
- `tilttek/stickers` · 🗓️ planned — Virtual stickers for profiles and messages
- `tilttek/advent-calendar` · 🗓️ planned — An advent calendar: one box a day, one surprise a box
- `tilttek/predictions` · 🗓️ planned — Predictions staked in points only
- `tilttek/raffle` · 🗓️ planned — Verifiable draws, with no buying of chances
- `tilttek/fan-awards` · 🗓️ planned — Fan awards: categories, nominations, votes
- `tilttek/geek-dates` · 🗓️ planned — Geek culture dates, as data
- `tilttek/rpg-calendar-events` · 🗓️ planned — Role-playing calendar events, as data

</details>

<details>
<summary><b>Dice &amp; randomness</b> — 🧪 8 · 🗓️ 8</summary>

- `tilttek/dice` · 🧪 90% — Dice notation parsed, validated and rolled: pools, custom faces, verifiable and replayable rolls
- `tilttek/dice-bundle` · 🧪 85% — Dice rolls in Symfony, Twig and the API
- `tilttek/generator` · 🧪 85% — A grammar engine for random text, with French, English, Spanish, German, Italian and Portuguese grammars
- `tilttek/generator-bundle` · 🧪 90% — Generators in Symfony, served by an API
- `tilttek/dice-probability` · 🧪 92% — Exact dice statistics: distributions, at least / at most, mean, events
- `tilttek/dice-probability-bundle` · 🧪 90% — Dice statistics as tables and charts in Live Components
- `tilttek/loot-tables` · 🧪 90% — Loot tables that declare their dice, drawn verifiably once (provisional name)
- `tilttek/loot-tables-bundle` · 🧪 85% — Loot tables in Symfony, with published commitments to the draws
- `tilttek/accessible-dice` · 🗓️ planned — Dice read without seeing colours or aiming at small buttons, announced to screen readers
- `tilttek/dice-tower` · 🗓️ planned — A table's shared dice tower: every roll seen by all, in order
- `tilttek/secret-rolls` · 🗓️ planned — Hidden GM rolls, kept verifiable and revealed later
- `tilttek/dice-jail` · 🗓️ planned — Dice jail for unlucky dice, and the statistics behind it
- `tilttek/dice-skins` · 🗓️ planned — The look of a member's dice
- `tilttek/luck-tokens` · 🗓️ planned — Luck, inspiration or fate tokens a table gives and spends
- `tilttek/card-deck` · 🗓️ planned — Card decks shuffled, drawn and discarded
- `tilttek/heraldry` · 🗓️ planned — Coats of arms generated and blazoned

</details>

<details>
<summary><b>At the table</b> — 🗓️ 17</summary>

- `tilttek/table-safety` · 🗓️ planned — Safety tools: lines and veils, consent checklist, session zero, X-card, anonymous by default
- `tilttek/table-safety-bundle` · 🗓️ planned — Safety tools in Symfony, with session-zero templates
- `tilttek/table-presence` · 🗓️ planned — Who is at the online table, away or on a break
- `tilttek/table-rules` · 🗓️ planned — House rules written and accepted, and the rule variants a table picks
- `tilttek/spotlight` · 🗓️ planned — Share playing time fairly and see who is waiting
- `tilttek/initiative-cards` · 🗓️ planned — Initiative tracking with cards
- `tilttek/gm-screen` · 🗓️ planned — A GM screen, on screen or printed
- `tilttek/session-prep` · 🗓️ planned — Session preparation: scenes, NPCs, notes
- `tilttek/gm-tips` · 🗓️ planned — Tips for the GM, by situation
- `tilttek/player-knowledge` · 🗓️ planned — What players know, kept apart from what their characters know
- `tilttek/handouts` · 🗓️ planned — Handouts given to players during play
- `tilttek/soundboard` · 🗓️ planned — Ambiences and sound effects for a session
- `tilttek/rpg-systems` · 🗓️ planned — A registry of game systems: attributes, dice, terms
- `tilttek/reference-tables` · 🗓️ planned — A system's reference tables
- `tilttek/rules-lookup` · 🗓️ planned — Search a system's rules, SRDs included
- `tilttek/flashcards` · 🗓️ planned — Learn a system's rules with spaced-repetition cards
- `tilttek/encounter` · 🗓️ planned — Encounters composed and balanced for the system

</details>

<details>
<summary><b>Characters</b> — 🗓️ 9</summary>

- `tilttek/character-sheet` · 🗓️ planned — Character sheets per system: computed attributes, equipment
- `tilttek/inventory` · 🗓️ planned — A character's inventory and encumbrance
- `tilttek/conditions` · 🗓️ planned — Conditions and effects: poisons, diseases, mutations, lost limbs
- `tilttek/party` · 🗓️ planned — A campaign's party, what it shares, and a balanced line-up
- `tilttek/random-character` · 🗓️ planned — A random character, ready to play
- `tilttek/token-maker` · 🗓️ planned — Virtual tabletop tokens from an image
- `tilttek/relationships` · 🗓️ planned — Links between characters and NPCs, and how they evolve
- `tilttek/polyglot` · 🗓️ planned — The languages a character speaks and reads, and what they understand of a text
- `tilttek/character-retirement` · 🗓️ planned — A character's retirement or death, and their memorial

</details>

<details>
<summary><b>Campaigns &amp; worlds</b> — 🗓️ 16</summary>

- `tilttek/session-scheduler` · 🗓️ planned — Campaign sessions: recurrence, absences, rescheduling
- `tilttek/campaign-wiki` · 🗓️ planned — A campaign wiki and the GM's secrets
- `tilttek/journal` · 🗓️ planned — Journals of many kinds: session recaps, character and solo journals
- `tilttek/campaign-stats` · 🗓️ planned — A campaign's statistics
- `tilttek/factions` · 🗓️ planned — Factions, their reputation and their clocks
- `tilttek/downtime` · 🗓️ planned — Downtime between adventures: crafting, research, training
- `tilttek/in-character-mail` · 🗓️ planned — In-character letters between sessions, read by the GM
- `tilttek/legacy-campaign` · 🗓️ planned — Legacy campaigns and their permanent changes
- `tilttek/west-marches` · 🗓️ planned — Open campaigns with several GMs and changing tables
- `tilttek/pbp` · 🗓️ planned — Play-by-post, in scene threads
- `tilttek/homebrew-hub` · 🗓️ planned — House rules shared, rated and reused from table to table
- `tilttek/fantasy-calendar` · 🗓️ planned — Fantasy calendars
- `tilttek/weather` · 🗓️ planned — In-world weather
- `tilttek/travel` · 🗓️ planned — Journeys, their duration and their hazards
- `tilttek/puzzle-builder` · 🗓️ planned — Riddles and puzzles for a scenario
- `tilttek/player-handbook` · 🗓️ planned — A campaign's player handbook

</details>

<details>
<summary><b>Finding players &amp; game nights</b> — 🗓️ 5</summary>

- `tilttek/game-catalog` · 🗓️ planned — One game catalogue each site switches on: BoardGameGeek, RPGGeek, manual entries, errata
- `tilttek/looking-for-group` · 🗓️ planned — Find players by system, by place or online
- `tilttek/game-night` · 🗓️ planned — Game nights for a club or a shop: tables, games, sign-ups
- `tilttek/tournament` · 🗓️ planned — Swiss or elimination tournaments and their pairings
- `tilttek/math-trade` · 🗓️ planned — Chain game trades: the longest chain computed, everyone gives one and gets one

</details>

<details>
<summary><b>Games &amp; contests</b> — 🗓️ 10</summary>

- `tilttek/quiz` · 🗓️ planned — Quizzes: questions, timer, score
- `tilttek/bingo` · 🗓️ planned — Bingo cards for a convention or a session, ticked by events
- `tilttek/mini-games` · 🗓️ planned — Small games played on the site
- `tilttek/tavern-games` · 🗓️ planned — Tavern games from a game world, playable online
- `tilttek/escape-room` · 🗓️ planned — Escape rooms: chained puzzles, hints, timer
- `tilttek/murder-mystery` · 🗓️ planned — Murder-mystery nights: roles, clues, reveal
- `tilttek/cosplay-contest` · 🗓️ planned — Cosplay contests: entries, walk-on, jury and public vote
- `tilttek/cosplay-progress` · 🗓️ planned — A costume's build log, step by step
- `tilttek/score-sheets` · 🗓️ planned — Score sheets
- `tilttek/deck-builder` · 🗓️ planned — Build a card deck to a game's rules

</details>

<details>
<summary><b>Hobbies</b> — 🗓️ 6</summary>

- `tilttek/wargame-army` · 🗓️ planned — Army lists for miniature games
- `tilttek/minis-tracker` · 🗓️ planned — Track miniatures bought, built and painted
- `tilttek/paint-recipes` · 🗓️ planned — Miniature paint recipes: colours, steps, photos
- `tilttek/reading-quests` · 🗓️ planned — Reading quests for a book
- `tilttek/writing-goals` · 🗓️ planned — An author's writing goals
- `tilttek/geocache-quests` · 🗓️ planned — Geocache quests

</details>

<details>
<summary><b>Live-action role-play</b> — 🗓️ 7</summary>

- `tilttek/larp-characters` · 🗓️ planned — LARP characters and their sheets
- `tilttek/larp-checkin` · 🗓️ planned — Player check-in on site
- `tilttek/larp-economy` · 🗓️ planned — A LARP's currency and trade
- `tilttek/larp-crafting` · 🗓️ planned — LARP crafting
- `tilttek/larp-spells` · 🗓️ planned — LARP spells
- `tilttek/larp-timeline` · 🗓️ planned — The timeline of a LARP's world and events
- `tilttek/larp-rules-quiz` · 🗓️ planned — A rules quiz before the first game

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

- **Écrit de zéro.** Aucun code tiers n'est copié dans un paquet Tilttek ; d'autres outils sont étudiés pour leurs
  idées, jamais recopiés.
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
- **La sortie :** un paquet fini passe au monodépôt public [`TiltTek/tilttek`](https://github.com/TiltTek/tilttek)
  (pas encore créé), d'où chaque paquet est scindé dans son propre dépôt en lecture seule et publié sur
  [Packagist](https://packagist.org).
- **L'outillage :** le même `phil/dev-tools` que PHIL.

### Le kit UX de Tilttek

| Dépôt | Ce qu'il contient | État |
|---|---|---|
| [ux-kit](https://github.com/TiltTek/ux-kit) | Des recettes de ludification pour le Toolkit de Symfony UX — vitrine des réussites, jauge de niveau, flamme de série, tableau des quêtes, classement, lanceur de dés, classeur de collection — bâties sur les composants compatibles Shadcn et habillées par phil-ux. `php bin/console ux:install <recette> --kit=github.com/TiltTek/ux-kit` | 🗓️ squelette |
| [ux-kit-shadcn](https://github.com/TiltTek/ux-kit-shadcn) | Les mêmes recettes en Tailwind, à la façon de Shadcn | 🗓️ squelette |

### Les paquets

✅ **publié** · 🧪 **écrit, en incubation** (avancement approximatif) · 🗓️ **prévu**

**114 paquets :** 24 en incubation, 90 prévus ; aucun n'est encore publié. Les pourcentages sont des
estimations tirées de notre dernier rapport d'avancement ((8 novembre 2026)).

<details>
<summary><b>Cœur de la ludification</b> — 🧪 16 · 🗓️ 12</summary>

- `tilttek/activity` · 🧪 95 % — L'entrée commune : l'activité d'un membre enregistrée une fois, ses totaux et ses projections rejouables
- `tilttek/activity-bundle` · 🧪 95 % — L'enregistrement de l'activité dans Symfony, avec projections asynchrones facultatives
- `tilttek/points` · 🧪 95 % — Un grand livre de points à double entrée : devises, règles de gain, plafonds, expiration FIFO, jamais négatif
- `tilttek/points-bundle` · 🧪 95 % — Les grands livres et règles de points configurés dans Symfony
- `tilttek/badges` · 🧪 90 % — Badges et succès : critères, paliers, succès cachés, titres, vitrine
- `tilttek/badges-bundle` · 🧪 92 % — Les badges dans Symfony : décernement, vitrine, partage avec l'accord du membre
- `tilttek/progression` · 🧪 95 % — Expérience et niveaux sur une courbe, plusieurs pistes, séries au fuseau du membre, saisons
- `tilttek/progression-bundle` · 🧪 95 % — La progression dans Symfony, avec gel des séries et paliers récompensés
- `tilttek/quests` · 🧪 95 % — Quêtes et défis à étapes : personnels, communautaires, d'équipe et duels
- `tilttek/quests-bundle` · 🧪 95 % — Les quêtes dans Symfony, aux dates saisonnières calculées
- `tilttek/collections` · 🧪 90 % — Objets à collectionner : rareté, ensembles, doubles, objet du jour, pochettes aux probabilités publiées et vérifiables
- `tilttek/collections-bundle` · 🧪 90 % — Les collections et les sets de dés dans Symfony
- `tilttek/exchange` · 🧪 85 % — Échanger des points contre des récompenses en deux temps, et des objets entre membres
- `tilttek/exchange-bundle` · 🧪 90 % — Boutiques de récompenses et échanges entre membres dans Symfony
- `tilttek/leaderboards` · 🧪 85 % — Classements par mesure et période, sur accord, pseudonymes, cercles d'amis, instantanés
- `tilttek/leaderboards-bundle` · 🧪 85 % — Les classements configurés et montrés dans Symfony
- `tilttek/kudos` · 🗓️ prévu — Les remerciements entre membres, sans décompte public ni classement
- `tilttek/referrals` · 🗓️ prévu — Le parrainage récompensé en points, jamais en argent
- `tilttek/guilds` · 🗓️ prévu — Les guildes de membres et leurs objectifs communs
- `tilttek/seasonal-events` · 🗓️ prévu — Les saisons et leurs événements : quêtes, objets et décors d'une période
- `tilttek/check-in-rewards` · 🗓️ prévu — La récompense d'une présence, au kiosque d'une boutique ou en convention
- `tilttek/stickers` · 🗓️ prévu — Les autocollants virtuels des profils et des messages
- `tilttek/advent-calendar` · 🗓️ prévu — Le calendrier de l'Avent : une case par jour, une surprise par case
- `tilttek/predictions` · 🗓️ prévu — Les prédictions misées en points seulement
- `tilttek/raffle` · 🗓️ prévu — Les tirages au sort vérifiables, sans achat de chances
- `tilttek/fan-awards` · 🗓️ prévu — Les prix des fans : catégories, mises en nomination, votes
- `tilttek/geek-dates` · 🗓️ prévu — Les dates de la culture geek, en données
- `tilttek/rpg-calendar-events` · 🗓️ prévu — Les événements du calendrier rôliste, en données

</details>

<details>
<summary><b>Dés et hasard</b> — 🧪 8 · 🗓️ 8</summary>

- `tilttek/dice` · 🧪 90 % — La notation des dés lue, validée et lancée : réserves, faces propres, lancers vérifiables et rejouables
- `tilttek/dice-bundle` · 🧪 85 % — Les lancers de dés dans Symfony, Twig et l'API
- `tilttek/generator` · 🧪 85 % — Un moteur de grammaire pour le texte au hasard, avec les grammaires française, anglaise, espagnole, allemande, italienne et portugaise
- `tilttek/generator-bundle` · 🧪 90 % — Les générateurs dans Symfony, servis par une API
- `tilttek/dice-probability` · 🧪 92 % — Les statistiques exactes des dés : distributions, au moins / au plus, moyenne, événements
- `tilttek/dice-probability-bundle` · 🧪 90 % — Les statistiques des dés en tableaux et graphiques en Live Component
- `tilttek/loot-tables` · 🧪 90 % — Des tables de butin qui déclarent leurs dés, tirées de façon vérifiable une seule fois (nom provisoire)
- `tilttek/loot-tables-bundle` · 🧪 85 % — Les tables de butin dans Symfony, avec les engagements publiés des tirages
- `tilttek/accessible-dice` · 🗓️ prévu — Des dés lisibles sans voir les couleurs ni viser de petits boutons, annoncés aux lecteurs d'écran
- `tilttek/dice-tower` · 🗓️ prévu — La tour de dés commune d'une table : chaque jet vu par tous, dans l'ordre
- `tilttek/secret-rolls` · 🗓️ prévu — Les jets cachés du meneur, gardés vérifiables et révélés ensuite
- `tilttek/dice-jail` · 🗓️ prévu — La prison des dés malchanceux, et les statistiques qui la justifient
- `tilttek/dice-skins` · 🗓️ prévu — L'apparence des dés d'un membre
- `tilttek/luck-tokens` · 🗓️ prévu — Les jetons de chance, d'inspiration ou de destin qu'une table distribue et dépense
- `tilttek/card-deck` · 🗓️ prévu — Des paquets de cartes mélangés, tirés et défaussés
- `tilttek/heraldry` · 🗓️ prévu — Les blasons générés et décrits

</details>

<details>
<summary><b>À la table</b> — 🗓️ 17</summary>

- `tilttek/table-safety` · 🗓️ prévu — Outils de sécurité : lignes et voiles, liste de consentement, séance zéro, carte X, anonymes par défaut
- `tilttek/table-safety-bundle` · 🗓️ prévu — Les outils de sécurité dans Symfony, avec modèles de séance zéro
- `tilttek/table-presence` · 🗓️ prévu — Qui est à la table en ligne, absent ou en pause
- `tilttek/table-rules` · 🗓️ prévu — Les règles maison écrites et acceptées, et les variantes qu'une table choisit
- `tilttek/spotlight` · 🗓️ prévu — Partager le temps de jeu et voir qui attend son tour
- `tilttek/initiative-cards` · 🗓️ prévu — Le suivi d'initiative en cartes
- `tilttek/gm-screen` · 🗓️ prévu — L'écran du meneur, à l'écran ou imprimé
- `tilttek/session-prep` · 🗓️ prévu — La préparation d'une séance : scènes, PNJ, notes
- `tilttek/gm-tips` · 🗓️ prévu — Les conseils au meneur, selon la situation
- `tilttek/player-knowledge` · 🗓️ prévu — Ce que savent les joueurs, séparé de ce que savent leurs personnages
- `tilttek/handouts` · 🗓️ prévu — Les documents remis aux joueurs pendant la partie
- `tilttek/soundboard` · 🗓️ prévu — Les ambiances et les effets sonores d'une séance
- `tilttek/rpg-systems` · 🗓️ prévu — Le référentiel des systèmes de jeu : caractéristiques, dés, termes
- `tilttek/reference-tables` · 🗓️ prévu — Les tables de référence d'un système
- `tilttek/rules-lookup` · 🗓️ prévu — La recherche dans les règles d'un système, SRD compris
- `tilttek/flashcards` · 🗓️ prévu — Apprendre les règles d'un système par cartes à répétition espacée
- `tilttek/encounter` · 🗓️ prévu — Une rencontre composée et équilibrée selon le système

</details>

<details>
<summary><b>Personnages</b> — 🗓️ 9</summary>

- `tilttek/character-sheet` · 🗓️ prévu — La fiche de personnage selon le système : caractéristiques calculées, équipement
- `tilttek/inventory` · 🗓️ prévu — L'inventaire d'un personnage et son encombrement
- `tilttek/conditions` · 🗓️ prévu — Les états et les effets : poisons, maladies, mutations, membres perdus
- `tilttek/party` · 🗓️ prévu — Le groupe d'une campagne, ce qu'il partage, et sa composition équilibrée
- `tilttek/random-character` · 🗓️ prévu — Le personnage tiré au hasard, prêt à jouer
- `tilttek/token-maker` · 🗓️ prévu — Les jetons de table virtuelle tirés d'une image
- `tilttek/relationships` · 🗓️ prévu — Les liens entre personnages et PNJ, et leur évolution
- `tilttek/polyglot` · 🗓️ prévu — Les langues qu'un personnage parle et lit, et ce qu'il comprend d'un texte
- `tilttek/character-retirement` · 🗓️ prévu — La retraite ou la mort d'un personnage, et son mémorial

</details>

<details>
<summary><b>Campagnes et mondes</b> — 🗓️ 16</summary>

- `tilttek/session-scheduler` · 🗓️ prévu — Les séances d'une campagne : récurrence, absences, report
- `tilttek/campaign-wiki` · 🗓️ prévu — Le wiki d'une campagne et les secrets du meneur
- `tilttek/journal` · 🗓️ prévu — Un journal à genres : résumés de séance, journaux de personnage et de jeu solo
- `tilttek/campaign-stats` · 🗓️ prévu — Les statistiques d'une campagne
- `tilttek/factions` · 🗓️ prévu — Les factions, leur réputation et leurs horloges
- `tilttek/downtime` · 🗓️ prévu — Les activités entre deux aventures : métier, recherche, entraînement
- `tilttek/in-character-mail` · 🗓️ prévu — Le courrier en personnage entre les séances, lu par le meneur
- `tilttek/legacy-campaign` · 🗓️ prévu — Les campagnes héritage et leurs changements permanents
- `tilttek/west-marches` · 🗓️ prévu — Les campagnes ouvertes à plusieurs meneurs et à des tables changeantes
- `tilttek/pbp` · 🗓️ prévu — La partie par messages, en fils de scène
- `tilttek/homebrew-hub` · 🗓️ prévu — Les règles maison partagées, notées et reprises d'une table à l'autre
- `tilttek/fantasy-calendar` · 🗓️ prévu — Les calendriers imaginaires
- `tilttek/weather` · 🗓️ prévu — La météo du monde du jeu
- `tilttek/travel` · 🗓️ prévu — Les voyages, leurs durées et leurs aléas
- `tilttek/puzzle-builder` · 🗓️ prévu — Les énigmes et casse-têtes d'un scénario
- `tilttek/player-handbook` · 🗓️ prévu — Le manuel du joueur d'une campagne

</details>

<details>
<summary><b>Trouver des joueurs et soirées de jeux</b> — 🗓️ 5</summary>

- `tilttek/game-catalog` · 🗓️ prévu — Un catalogue de jeux unique que chaque site active : BoardGameGeek, RPGGeek, saisie, errata
- `tilttek/looking-for-group` · 🗓️ prévu — Trouver des joueurs par système, par lieu ou en ligne
- `tilttek/game-night` · 🗓️ prévu — Les soirées de jeux d'un club ou d'une boutique : tables, jeux, inscriptions
- `tilttek/tournament` · 🗓️ prévu — Les tournois en rondes suisses ou à élimination, et leurs appariements
- `tilttek/math-trade` · 🗓️ prévu — L'échange de jeux en chaîne : la plus longue chaîne calculée, chacun donne un jeu et en reçoit un

</details>

<details>
<summary><b>Jeux et concours</b> — 🗓️ 10</summary>

- `tilttek/quiz` · 🗓️ prévu — Les jeux-questionnaires : questions, minuterie, score
- `tilttek/bingo` · 🗓️ prévu — Les cartes de bingo d'une convention ou d'une séance, cochées par les événements
- `tilttek/mini-games` · 🗓️ prévu — Les petits jeux qui se jouent dans le site
- `tilttek/tavern-games` · 🗓️ prévu — Les jeux de taverne d'un univers de jeu, jouables en ligne
- `tilttek/escape-room` · 🗓️ prévu — Les jeux d'évasion : énigmes enchaînées, indices, chronomètre
- `tilttek/murder-mystery` · 🗓️ prévu — Les soirées meurtre et mystère : rôles, indices, révélation
- `tilttek/cosplay-contest` · 🗓️ prévu — Le concours de costumes : inscriptions, passage, jury et vote du public
- `tilttek/cosplay-progress` · 🗓️ prévu — Le journal d'un costume en cours, étape par étape
- `tilttek/score-sheets` · 🗓️ prévu — Les feuilles de score
- `tilttek/deck-builder` · 🗓️ prévu — Construire un paquet de cartes selon les règles d'un jeu

</details>

<details>
<summary><b>Loisirs</b> — 🗓️ 6</summary>

- `tilttek/wargame-army` · 🗓️ prévu — Les listes d'armée d'un jeu de figurines
- `tilttek/minis-tracker` · 🗓️ prévu — Le suivi des figurines achetées, montées et peintes
- `tilttek/paint-recipes` · 🗓️ prévu — Les recettes de peinture des figurines : couleurs, étapes, photos
- `tilttek/reading-quests` · 🗓️ prévu — Les quêtes de lecture d'un livre
- `tilttek/writing-goals` · 🗓️ prévu — Les objectifs d'écriture d'un auteur
- `tilttek/geocache-quests` · 🗓️ prévu — Les quêtes de géocache

</details>

<details>
<summary><b>Grandeur nature</b> — 🗓️ 7</summary>

- `tilttek/larp-characters` · 🗓️ prévu — Les personnages d'un grandeur nature et leurs fiches
- `tilttek/larp-checkin` · 🗓️ prévu — L'accueil des joueurs sur le terrain
- `tilttek/larp-economy` · 🗓️ prévu — La monnaie et les échanges d'un grandeur nature
- `tilttek/larp-crafting` · 🗓️ prévu — L'artisanat d'un grandeur nature
- `tilttek/larp-spells` · 🗓️ prévu — Les sorts d'un grandeur nature
- `tilttek/larp-timeline` · 🗓️ prévu — La ligne du temps de l'univers et des événements d'un grandeur nature
- `tilttek/larp-rules-quiz` · 🗓️ prévu — Le questionnaire sur les règles avant le premier jeu

</details>


### Participer

- 💬 Questions et idées : [Discussions](https://github.com/orgs/TiltTek/discussions)
- 🐛 Bogues et demandes de fonctions : un ticket dans le dépôt concerné
- 🤝 [Contribuer](https://github.com/TiltTek/.github/blob/main/CONTRIBUTING.md) ·
  [Code de conduite](https://github.com/TiltTek/.github/blob/main/CODE_OF_CONDUCT.md) ·
  [Sécurité](https://github.com/TiltTek/.github/blob/main/SECURITY.md) ·
  [Soutien](https://github.com/TiltTek/.github/blob/main/SUPPORT.md)
- 🌐 [tilttek.com](https://tilttek.com) · projet frère : [PHIL](https://github.com/parler-haut-interagir-librement)
