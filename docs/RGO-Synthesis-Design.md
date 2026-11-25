# RGO - Synthesis Phase 1 design

## Status and scope

This document records the Phase 1 design currently described in the RGO
Synthesis Workshop draft, together with the previously identified compatibility
and production-chain questions. The Phase 1 RGO categories below are the
intended design direction; definitions, map assignments, balancing, and
implementation details still need to be researched and built.

The former Concordia `rgo-synthesis` profile targeted EU5 1.4.5 and reused
RGO Harmony's compatibility payload unchanged. This standalone repository
contains no Synthesis goods, location assignments, consolidation rules, or
production changes yet. RGO Synthesis is intended to replace Fruits Expanded
integration in the playset; Fruits Expanded is not a dependency.

## Objective and design rationale

Develop a standalone agricultural RGO overhaul that improves historical
geographic representation while reducing unnecessary commodity granularity.
RGOs should represent distinct agricultural systems, economic activities, or
historically meaningful geographic differences—not every botanical species.
The intended timeframe is 1337–1836, including the Columbian Exchange and
subsequent crop spread between the Old and New Worlds.

The design responds to two issues with vanilla EU5:

- Generic `fruit` is unusually abstract compared with foodstuffs such as
  wheat, maize, potatoes, and rice, whose RGOs distinguish climate and
  geographic origin.
- Some vanilla RGOs are anachronistic for the game's timeframe, assigning
  specialized, developed agricultural activity to places where it was not
  historically significant. RGOs remain useful abstractions of agricultural
  potential and historical output, but their assignments should reflect that
  distinction.

The design also responds to Fruits Expanded's species-level granularity:

- It adds more botanical granularity than the broader RGO system supports,
  such as separate apple and pear varieties and separate plums, peaches, and
  cherries.

Tuber goods are outside this fruit-focused project's scope; cassava, taro, and
sweet potato are tracked separately in Just Tubers.

Synthesis therefore groups related fruit crops into economically meaningful
categories while separately representing distinctive fruit crops and Old
World / New World agricultural origins.

## Phase 1 RGO design

### Changes from Fruits Expanded

| Synthesis category                | Fruits Expanded RGOs represented                                                                          | Design intent                                                                                             |
| --------------------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Africa orchards (`africa_orchard`) | Safou, baobab, marula, African star apple, and similar indigenous African tree crops | Represent indigenous African orchard and agroforestry systems without treating them as part of the Asia tropical orchard category. |
| Temperate fruit orchards          | Apples, Western Pears, Eastern Pears, Persimmons                                                          | Combine temperate orchard fruits into one economic category.                                              |
| Stone fruit orchards              | Plums, Peaches, Cherries                                                                                  | Combine related stone-fruit orchard crops.                                                                |
| Mediterranean fruit orchards      | Figs, Pomegranates                                                                                        | Represent distinctive Mediterranean and semi-arid fruit cultivation together.                             |
| Citrus orchards                   | Lemons, both Orange types, Mandarins                                                                      | Consolidate related citrus crops.                                                                         |
| Asia tropical orchards (`asia_tropical_orchard`) | Jackfruit, breadfruit, durian, rambutan, mangosteen, lychees, and similar indigenous Asian tree crops | Represent diverse Asian tropical orchards and agroforestry without individual goods for each species.      |
| America tropical orchards (`america_tropical_orchard`) | Avocado, guava, sapote, cherimoya, and similar indigenous American tree crops                  | Represent diverse tropical orchards and agroforestry of the Americas without individual goods for each species. |
| Date palms                        | Date-palm agriculture                                                                                     | Represent the distinctive date-palm economy.                                                              |
| Coconuts                          | Coconut agriculture                                                                                       | Represent a distinctive tropical staple and coconut-palm economy.                                         |
| Mango                             | Mango                                                                                                     | Keep mango as a distinct crop in historically supported regions; do not subsume it into Asia tropical orchards. |
| Tamarind (`tamarind`)             | Tamarind                                                                                                  | Keep tamarind as a distinct high-value crop whose African origin, early Old World diffusion, and later expansion can be modeled explicitly. |
| Grapes                            | Grapes                                                                                                    | Track grape cultivation as an explicit RGO; its production-chain relationship to wine remains a separate open question. |
| Bananas                           | Bananas                                                                                                  | Keep banana as a distinct Old World tropical crop; model its spread to the Americas through the Columbian Exchange. |
| Pineapples                        | Pineapples                                                                                               | Keep pre-contact New World cultivation distinct; model its spread to the Old World through the Columbian Exchange. |

The tropical orchard categories do not absorb goods that are already
historically distinctive in the design: mango, tamarind, and banana for the
Old World; pineapple, cocoa, and chili for the New World. Africa orchards
remain distinct from Asia tropical orchards. Persimmons and lychees remain
within their respective broad orchard categories. Nuts are not a separate
RGO; they are abstracted within the appropriate tree-fruit categories.

### Differences from vanilla EU5

Synthesis divides vanilla `fruit` into geographically and climatically
meaningful agricultural categories:

- Temperate fruit orchards for continental or temperate apples and pears.
- Stone fruit orchards for regionally appropriate plums, peaches, and
  cherries.
- Mediterranean fruit orchards for figs and pomegranates.
- Citrus orchards for lemons, oranges, mandarins, and similar citrus.
- Africa orchards for indigenous African orchard and agroforestry systems.
- Asia tropical orchards for suitable tropical Asian regions.
- America tropical orchards for suitable tropical regions of the Americas.
- Date palms and coconuts as distinctive agricultural systems.
- Tuber crops are outside this project's scope; see Just Tubers for cassava,
  taro, and sweet potato.
- Mango as a standalone Old World crop in historically supported regions.
- Tamarind as a standalone high-value crop with its origin and diffusion
  modeled explicitly.
- Grapes as a distinct agricultural RGO; its relationship to vanilla's
  directly extracted wine remains a separate production-chain question.
- Bananas as an Old World crop, with Columbian Exchange introduction to the
  Americas.
- Pineapples as a New World crop, with subsequent Columbian Exchange
  introduction to the Old World.

The specific locations and their final RGO assignments require a separate
geographic review; these categories do not by themselves authorize a
location-by-location change.

## Crop diffusion and RGO switching

Just Fruits should provide specific player-facing options for switching
eligible locations to appropriate fruit RGOs. These choices should make crop
adoption deliberate rather than allowing unrestricted conversion: eligibility,
costs, timing, climate, ownership, market access, and required crop exposure
must be designed against the final game mechanics.

Scripted AI events should provide a parallel path for historically plausible
global fruit diffusion. The system should especially support:

- introduction of Old World temperate fruits and orchard systems to suitable
  New World locations after sustained contact;
- transfer of distinctive crops between the Old and New Worlds during the
  Columbian Exchange; and
- development of colonial plantation monocultures for crops such as pineapple
  and mango where climate, colonial control, and market conditions support
  them.

Player options and AI events should use the same eligibility principles and
should not overwrite historically important RGOs without meaningful
conditions. Exact triggers, effects, pacing, and AI weighting must be verified
against installed vanilla definitions before implementation.

### America tropical orchard placeholder policy

For some New World locations, especially in Cuba, surviving evidence does not
support assigning a specific pre-colonial orchard or cash crop with confidence.
This uncertainty should not be described as proof that Indigenous communities
had no agriculture. Where a location later became strongly oriented toward
fruit or cash-crop production under colonial rule,
`america_tropical_orchard` may serve as a broad starting abstraction for
mixed cultivation, agroforestry, agricultural potential, or incomplete
location-specific evidence.

These assignments also act as design signals for the crop-diffusion system:
they identify locations where the player or scripted AI may later replace the
broad orchard RGO with a historically and climatically appropriate plantation
monoculture or other specialized cash crop. The initial placeholder does not
authorize an automatic conversion; later specialization must still satisfy
the switching system's contact, timing, ownership, climate, market, and cost
conditions.

### Date-palm compatibility

An earlier compatibility direction was to use the existing generic `fruit`
identifier for date palms where practical, retaining that identifier for
compatibility rather than introducing a new date-palm key. Confirm this
against the Phase 1 goods definitions and compatibility requirements before
implementation.

## Playset and compatibility baseline

This version uses vanilla EU5's map and location set as its baseline; More
Locations is intentionally not a dependency. The planned upstream requirements
and load order are:

1. Community Mod Framework (required by Just Goods)
2. Historical RGOs - Global
3. Just Goods
4. RGO - Synthesis

Just Goods 1.1 and EU5 1.4.5 are the current design targets. Just Goods
requires Community Mod Framework, making CMF a transitive dependency of
Synthesis. The exact precedence and compatibility treatment among vanilla,
Historical RGOs - Global, and Just Goods must be established through a fresh
source audit; no map assignments are implemented yet. Synthesis is intended
to take Fruits Expanded's place, and Fruits Expanded should not be required
or included in this playset.

## Production-chain question: grapes and wine

Vanilla EU5 has `wine` as a directly extracted RGO, while Fruits Expanded
adds grapes as a separate agricultural good. A possible broader reform is:

`Grape RGO → Winery Building → Wine Good`

This could replace directly extracted wine RGOs, make wine exclusively
manufactured, and require wineries to consume grapes and employ workers.
This production-chain change is separate from the Phase 1 agricultural
taxonomy. Inspect the vanilla winery and orchard building definitions before
deciding whether or how to implement it.

## Production methods: monastic fruit cultivation

Just Fruits should include new production methods that let monasteries
specialize in fruit cultivation and receive appropriate fruit-production
bonuses. This represents the recurring historical role of monasteries in
orchard cultivation without requiring every monastic site to receive a fruit
RGO.

The exact production methods, eligible monastery buildings, outputs, and
bonuses remain to be designed and balanced. Inspect the installed vanilla
monastery, orchard, and production-method definitions before implementation,
and keep the feature compatible with the final fruit-good taxonomy.

## Implementation principles

1. Favor broad, economically meaningful agricultural categories over
   botanical specificity.
2. Preserve historically meaningful Old World versus New World crop
   distinctions.
3. Represent pre-1337 cultivation accurately and account for later crop
   introductions through appropriate geographic or chronological mechanics.
4. Prefer food-producing RGOs where historically appropriate.
5. Avoid introducing additional commodities when existing broader goods
   adequately represent their agricultural economies.
6. Treat location mapping and any consolidation beyond the Phase 1 taxonomy
   as separately reviewable decisions.
7. Maintain compatibility with EU5 1.4.5, Just Goods 1.1, Historical RGOs -
   Global, and Just Goods' transitive Community Mod Framework dependency.
   Keep the vanilla map as the base; More Locations is out of scope for this
   version.

## Desired outcome

The goal is greater historical and economic differentiation with fewer
unnecessary commodity types—not simply increasing the total number of RGOs.
The intended system distinguishes European temperate orchards, Mediterranean
fruit cultivation, Middle Eastern and Saharan date palms, Asia tropical
orchards and Old World tubers, America tropical orchards and New World tubers,
and Pacific coconut-based agricultural economies.
