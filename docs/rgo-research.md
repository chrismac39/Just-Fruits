# Fruit-location RGO research workflow

The research workflow prepares evidence and reviewable RGO candidates for
every location in [the fruit-location inventory](../decisions/fruit-location-review.md).
It never changes an assignment in game files. Candidate suggestions are
discovery leads, not historical conclusions.

The inventory contains 769 effective `fruit` locations for its documented
EU5 1.4.9, Historical RGOs - Global 1.4.0, and Just Goods 1.1.0 baseline.
That baseline does not change the design document's stated target game version.
Historical RGOs - Global is used to establish the current fruit-location set;
it is not a source of candidate goods.

## Local setup

Install the project's development dependencies with `npm install`. Configure
the installed EU5 game directory and local Just Goods source directory in the
ignored `.local/rgo-research.json` file:

```json
{
  "gamePath": "C:\\path\\to\\Europa Universalis V\\game",
  "justGoodsGoodsDirectory": "C:\\path\\to\\Just Goods\\game\\in_game\\common\\goods"
}
```

The game path must be the `game` directory containing `in_game`; the Just Goods
path must contain its raw-material definition `.txt` files. Alternatively, set
`EU5_GAME_PATH` and `JUST_GOODS_GOODS_PATH`, or pass `--game-path` and
`--just-goods-goods-path`. Machine-specific paths and API cache data remain
under ignored `.local/`.

## Three-stage workflow

1. Run `npm run rgo:research -- resolve`. The default input is the full
   769-location decision inventory. The resolver reads each location's region,
   area, and province from the installed game's
   `in_game/map_data/definitions.txt`, then queries Wikidata for geographic
   place candidates and their Wikipedia sitelinks. It writes:
   - `reports/rgo-research/pilot-resolution.json`
   - `reports/rgo-research/pilot-resolution.md`
   - `reports/rgo-research/pilot-resolution.csv`
2. Review every location and candidate in the CSV. Set `correct` to `TRUE` for
   one confirmed place candidate per location; leave all candidates `FALSE`
   when uncertain. The tool does not automatically choose a place.
3. Run `npm run rgo:research -- discover`. This checks exact-title availability
   for locally linked Wikipedia pages, falling back to linked English
   Wikipedia only when no local page is linked. Wikipedia existence checks are
   batched by language, with at most 50 titles per request. It also checks
   Grokipedia using the English Wikipedia title when available, or the
   resolved place label otherwise. Grokipedia's public page route is tried
   first; its public search page is used only as a fallback, and a result is
   accepted only when its title exactly matches. The workflow does not use
   Grokipedia's internal API. The discovery pass writes
   `reports/rgo-research/pilot-discovery.json` and a page-availability
   Markdown report, and caches discovered Grokipedia HTML for the next stage.
4. Run `npm run rgo:research -- research`. It reads the discovery JSON, fetches
   Wikipedia revision content in batches of at most 50 titles, and extracts
   history, economy, agriculture, trade, and industry sections. The workflow
   records page and section citations plus numeric year signals, and matches
   configured RGO aliases. Grokipedia content is read from the cached public
   page discovered in the previous stage.
5. Review the generated JSON, Markdown, and
   `reports/rgo-research/pilot-research.rgo-review.csv`. The CSV includes a
   row for every researched location, including locations with no keyword
   matches. Every `valid_rgo` value starts `FALSE`.

Use `--output path.json` to select another report name. The resolution
`discover` command accepts `--resolution path.json` and `--review path.csv`;
`research` accepts `--discovery path.json`. Paths are resolved from the
repository root. To work on a custom subset, pass `--input locations.json` to
`resolve`; provide an array of objects with stable `id`, `englishName`, and
`context` strings.

## Candidate goods and preference

Selectable candidates are only:

- Raw-material goods defined by installed vanilla EU5.
- Raw-material goods defined by the local Just Goods source.
- The ten planned Just Fruits goods configured in
  `config/rgo-research-crops.json`: cassava, citrus orchard, coconut, date
  palm, Mediterranean orchard, New World tropical orchard, Old World tropical
  orchard, stonefruit orchard, taro, and temperate orchard.

Generic `fruit` is always excluded. Historical RGOs - Global, RGO Harmony, and
other mods are not candidate sources. The candidate preference order is:

1. Planned Just Fruits RGO.
2. Existing vanilla or Just Goods raw material with a positive EU5 `food`
   output.
3. Any other available vanilla or Just Goods raw material.

The EU5 `food` output is only a mechanical preference signal; it is not proof
that a good was historically consumed or cultivated at a particular location.
Keyword occurrence counts also do not establish suitability. The report and
CSV include candidate source, preference tier, and food output so these
signals remain visible during review. If the same good ID occurs in both
source catalogs, its Just Goods definition supplies the food-output value used
for ranking, while both source names remain visible.

## Historical interpretation

EU5's starting date is 1337. Numeric years earlier than 1337 are surfaced as
signals, alongside 1300–1899 year signals, but the tool does not infer a crop's
historical range from them. Review the cited passages for crop-specific,
location-specific evidence and distinguish a local claim from a regional one.
Modern cultivation is not evidence for the 1337 starting RGO.

For American locations, evaluate cultivation and use before sustained
European contact separately from later crop diffusion. For Sub-Saharan
locations, do not assume that a crop mention justifies an orchard RGO at the
territorial scale represented by EU5. A suitable non-fruit food or other
raw-material RGO may be preferable. Evidence from a later period or from a
nearby location should be explicitly treated as uncertain.

The configured keywords are literal matches in selected Wikipedia and
Grokipedia article sections. Wikidata resolves place names and linked
Wikipedia articles; Grokipedia lookup uses its public pages, not its internal
API. This workflow does not perform semantic classification. Coverage and
historical detail vary by source and article. A missing match is not evidence
that a good was absent.

Wikipedia excerpts are attributed to the linked page and revision in the
report. Wikipedia text is available under CC BY-SA; retain attribution and
follow the applicable license terms if redistributing excerpts. Grokipedia
content is AI-generated: treat its claims as leads and verify them against
its linked references. Grokipedia material is subject to the SpaceXSI
Community License Agreement, and some material may also be CC BY-SA. Check
the applicable terms and permissions before redistributing any excerpts.

## Other commands and source notes

- `npm test` runs the focused research workflow tests.
- `npm run typecheck` checks the TypeScript scripts and tests.
- `npm run rgo:research:index` regenerates the country administrative-scale
  hints in `config/rgo-research-admin-scales.json`.
- Successful API responses are cached in ignored
  `.local/rgo-research/api-cache.json`; successful public-page responses and
  404 responses are cached there as well. Wikimedia requests use a
  project-identifying User-Agent, a shared cap of three in-flight requests,
  and a minimum 300 ms between request starts (at most 200 starts per minute).
  They also use API batching and `maxlag=10`; maxlag responses trigger a
  shared cooldown and exponential backoff that honors `Retry-After`. See the
  [Wikimedia rate limits](https://www.mediawiki.org/wiki/Wikimedia_APIs/Rate_limits)
  and [API etiquette](https://www.mediawiki.org/wiki/API:Etiquette/en).
  Grokipedia requests use public page/search routes only and remain serial,
  with at least one second between requests; its `robots.txt` disallows
  `/api/`.

Vanilla game files are read-only inputs. The research scripts read map
definitions and raw-material definitions but never copy or modify them.
Generated reports are local review artifacts and are not source decisions.
