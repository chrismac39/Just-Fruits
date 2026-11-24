# Just Fruits

Just Fruits is the project repository for the EU5 **RGO - Synthesis** mod.
It contains synthesis-specific artwork, design notes, and Workshop draft
materials. The project is an early scaffold: new goods, location assignments,
consolidation rules, and production changes have not yet been implemented.

The planned playset is more vanilla-friendly: vanilla EU5 remains the map
baseline, with Historical RGOs - Global and Just Goods. Just Goods requires
Community Mod Framework, so CMF is an indirect dependency. More Locations is
intentionally out of scope for this version.

The art files are stored under `main_menu/gfx/` in EU5's game-content layout.
The Workshop description and thumbnail are under `workshop/`. See
[the design notes](docs/RGO-Synthesis-Design.md) and
[asset workflow](docs/assets.md) before changing these materials.

The repository includes a two-stage RGO research workflow for the 769-location
fruit inventory. It creates place-resolution candidates and historical
evidence reports for human review; it does not change game assignments. See
[the research workflow](docs/rgo-research.md) for setup and usage.

Cassava, taro, and sweet potato are tracked separately in the sibling
Just Tubers project; they are not part of this fruit mod's roster.

The earlier Concordia profile used a shared RGO Harmony compatibility map.
That shared map and Concordia's package snapshots are intentionally not
included here; compatibility work must be separately reviewed and its source
permissions documented before distribution.

## Contributing

Use the installed EU5 files as the source of truth for game syntax and
definitions. Treat vanilla files as read-only, follow `.editorconfig` for
game-content encoding, and validate the final assembled mod before release.
No Workshop upload is performed by repository or build operations.
