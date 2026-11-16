# Modulo Market 1.0.0

A World of Warcraft Forever Auction House snapshot browser and profession-economics companion. Modulo Market is an optional addon in the MODULO suite; it does not replace specialist addons such as Auctionator.

## Requirements and compatibility

- World of Warcraft Forever, client interface `16001`; the 1.0.0 candidate is prepared from source milestone 0.12.20 and runtime-tested on build `70938`.
- **MODULO is required** and must be installed and enabled first. MODULO does not depend on Modulo Market.
- `LibProfessionDB` is optional; the addon does not require it to load.
- Retail compatibility is not claimed.

## Installation

1. Download [Modulo Market 1.0.0](https://github.com/moonlitfarewell/modulo-market-releases/raw/refs/heads/main/Modulo-Market-1.0.0.zip).
2. Extract the `ModuloMarket` folder into your WoW Forever `Interface/AddOns/` directory.
3. Confirm the folder layout is `.../Interface/AddOns/ModuloMarket/ModuloMarket.toc`.
4. Enable **MODULO** and **Modulo Market** in the AddOns list.
5. Open the Market with `/mm`. Use `/mmversion` to confirm the installed version and client build.

For upgrades, exit the client or reload the UI before replacing the `ModuloMarket` folder. Do not delete `WTF` or `ModuloMarketDB` SavedVariables; snapshots, history and settings are intended to persist across upgrades.

## Features

- Full Market auction-house snapshots with item price and depth information from the player's completed in-client scan.
- All Items browsing, item-type filtering including Equipment, search and item detail/tooltip inspection.
- Profession and recipe catalogue, craft economics, materials, turn-in analysis and price history views.
- Blizz-like and Modern presentation modes.
- Build-aware snapshot compatibility checks and explicit diagnostics.
- Incremental view building and sorting for large catalogues.
- Persistent settings and market history.

## Commands

- `/mm` — open or close the Market.
- `/mmscan` — open or close Browse Scan / Snapshot tools.
- `/mmcompat` — read-only client/API/snapshot compatibility diagnostics.
- `/mmversion` — show addon version, client build and data status.
- `/mmdebug` — open diagnostic tools.
- `/mmsearchdebug` — print tooltip-search diagnostics.
- `/mmtooltipdebug itemID` — inspect extracted tooltip text for an item.
- `/mmreplicatedebug` — inspect Full Market acquisition diagnostics.
- `/mmtabperf on`, `/mmtabperf`, `/mmtabperf reset`, `/mmtabperf off` — opt-in tab-build and sort performance counters.

## Market data and limitations

- Auction prices and listing depth come from a completed, player-initiated Full Market snapshot. They are not supplied by ForeverDB.
- Profession, recipe and acquisition catalogue metadata is bundled from a filtered ForeverDB-derived projection, with provenance labels and visible provider credit in the addon. It is not a live auction-price feed.
- Craft profitability requires a complete Full Market snapshot compatible with the running client build and sufficient price depth. A Browse snapshot is narrower and does not replace a complete Full Market snapshot.
- Recipe and acquisition coverage is bounded by the retained dataset and its evidence. Missing or unconfirmed records must not be treated as proof that an item or recipe is unavailable in game.
- This addon is an optional companion to MODULO and does not replace Auctionator's specialist economy workflows.

## Runtime testing status

The 1.0.0 candidate is based on Modulo Market 0.12.20. On Forever 1.60.1 build `70938`, the player confirmed that tab switching and list repopulation felt smooth with no noticeable hitching. The captured diagnostics reported 18 tab selections, 22 completed sorts, zero sort restarts, no catalogue rebuilds during the capture, no item-event-triggered refreshes, and successful Instant item-class resolution for all 6,390 lookups. Earlier runtime evidence also covers specific Full Market refresh and cancellation paths; it does not establish that every feature, tab, dataset entry or sort mode has been exhaustively tested. Retail runtime testing is NOT RUN.

## Third-party data, attribution and licence scope

The bundled `ForeverDBData.lua` contains a filtered ForeverDB-derived profession/catalogue projection. Modulo Market follows ForeverDB's published developer workflow for approved developers: fetch data and bundle it with releases. The published conditions relevant here are to show visible credit and a link wherever the data is displayed (on the free tier), not to resell the data or present it as our own, and never to ship an API key in a distributed addon. Modulo Market displays `Data from ForeverDB.net` with a link in the addon, bundles the filtered catalogue locally, includes no API key, and does not sell or claim ownership of the data. See [ForeverDB's developer instructions](https://foreverdb.net/developers).

This is reliance on ForeverDB's published fetch-and-bundle workflow subject to its stated conditions; it is not a general open-data licence, an ownership transfer, or permission for us to relicense or resell the dataset. The bundled provider-derived data is not covered by the MIT licence below.

ForeverDB states that data from the WoW Forever client is Blizzard's and that ForeverDB is not affiliated with Blizzard Entertainment. Its bundling workflow does not grant rights on Blizzard's behalf. Modulo Market does not claim ownership or an independent licence over Blizzard client data, game assets or trademarks; those remain subject to their respective rights and terms. The filtered projection excludes speculative, Classic-borrowed and unknown acquisition records as documented in the development repository's [third-party notices](https://github.com/moonlitfarewell/modulo-market/blob/main/THIRD-PARTY-NOTICES.md) and [data projection audit](https://github.com/moonlitfarewell/modulo-market/blob/main/MODULOMARKET-DATA-CLEANUP-0.12.8.md).

The MIT licence applies broadly to original Modulo Market source code and the six project-authored UI glyphs, to the extent contributors hold the rights to license them. It does not apply to provider-derived datasets, Blizzard material, third-party code/assets, trademarks or dependencies. See [LICENSE](LICENSE), the development repository's [asset provenance](https://github.com/moonlitfarewell/modulo-market/blob/main/ASSET-PROVENANCE.md), and [third-party notices](https://github.com/moonlitfarewell/modulo-market/blob/main/THIRD-PARTY-NOTICES.md).

## License

MIT for the original project source and project-authored assets within the stated scope. The bundled third-party/provider-derived data is excluded. See [LICENSE](LICENSE) and the provenance notices above.
