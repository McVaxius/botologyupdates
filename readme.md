  This is container repo for constantly updated .json files for BOTOLOGY and other stuff maybe

## Botology catalog ownership

- `plugin-repository-links.json` is the master catalog and keeps using the `Plugins` array.
- Botology stores user additions and overrides in its local overlay `Entries` array.
- Local overlays may include an optional `DeletedIds` string array to suppress stale master ids.
- A prepared effective catalog omits suppressed rows; the master file in this repository is not rewritten by that local operation.
- Plugin row changes remain explicit catalog-maintainer edits.

## Catalog schema

- The catalog remains schema version 3. `IsAiAttributed` is an optional boolean row field; omitted means `false`.
- Source catalogs include `IsAiAttributed` only when it is `true`. Local Botology overlays may persist an explicit `false` so a local override can clear a master attribution.
- The flag means likely AI-written code based on Aetherfeed contributor and coding-pattern attribution. It is not definitive, and an unflagged plugin is not proven human-only.
- The frozen source is `https://raw.githubusercontent.com/Aetherfeed/aetherfeed.github.io/main/public/data/plugins.json`, snapshot date 2026-07-22, SHA-256 `28e98ec13f5c2feabd9166c8a4cd3749ee42b81b6a9638175106da97ec27f7f5`. Matching lowercases and removes non-alphanumeric characters from Botology `Id`, `DisplayName`, and `MatchTokens` and Aetherfeed plugin `Name`/`InternalName`; exact normalized matches are used, and any matching attributed occurrence sets the flag. This is a one-time snapshot, not an ongoing synchronization.

## Changelog schema

- `changelog.json` uses schema version 1 with newest-first `Releases`.
- Every release has `Id`, ISO UTC `PublishedUtc`, `Title`, `AffectedPluginIds`, and ordered `Sections`; every section has `Heading` and string `Items`.
- Release IDs must be unique, and every affected plugin ID must exist in the current master catalog.

## DDuck trap data

`dduck/traps.ddt` is the reviewed DDuck-owned DDT v1 curated trap collection.
The October 17, 2026 collection has 14,986 unique locations across all four deep
dungeons / 50 territories. Updates preserve existing valid locations.

DDuck downloads this file by explicit request. It validates and merges additions
locally, preserving existing curated data and the separate `usertraplog` contribution
file. No player identifiers or contributions are uploaded.

## ADS object-rule data

- `ads/territories/index.json` and its listed `*_rule_objects.json` files are the source of truth for current ADS builds.
- `GLOBAL_rule_objects.json` contains rules without duty scope. Numeric shard filenames contain the complete replacement context for that TerritoryType id.
- `ads/duty-object-rules.json` is frozen legacy compatibility data for older ADS builds. Current ADS builds do not read it, and shard updates must not regenerate it.
- `ads/duty-object-rules-mature-proposals.json` is also frozen for older builds. Current ADS builds do not fetch or expose MATURE proposals.

---

[XA and I have created some Plugins and Guides here at -> aethertek.io](https://aethertek.io/)

### Repo URL:
```
https://aethertek.io/x.json
```

### Discord:
```
https://discord.gg/g2NmYxPQCa
```

---

### ADS published presets

The optional `Presets` array in `ads/territories/index.json` declares published
preset names and each folder's canonical `Files` list. Its existing flat `Files`
list remains the base DEFAULT package. Updated ADS downloads both forms using its
existing 24-hour/manual refresh. A bare folder is not a discovery contract; old
ADS builds retain the flat package and ignore the named-preset declarations.

The selected names are `DEFAULT - SYNC - Crystal Tower x 3` and
`DEFAULT - UNSYNC - Crystal Tower x 3`. Both contain territory shards 151, 174 and
372 (CFCs 111, 92 and 102). SYNC uses ordinary add-aware kill priorities; UNSYNC
adds boss focus for burst play. Nearby optional Labyrinth shortcuts use a
2-second SYNC arrival wait and no extra UNSYNC wait. Missing contexts inherit
DEFAULT; the name groups the three raids without creating a queue sequence.

ADS protects presets it installed through this declaration and keeps the user's
active selection. Its installed per-preset index records updater ownership;
matching a `DEFAULT - ` name alone grants no overwrite permission. Pre-existing
personal-name collisions and unrelated personal copies are preserved. Use the
existing New Preset workflow for edits and sharing.

Rules were source-reviewed on 2026-10-18 against public BossMod/BossMod Reborn
encounter OIDs and AutoDuty's Labyrinth shortcut IDs/positions. No unreviewed
`_maybe` file was copied wholesale. The rules supply targeting/shortcut assistance;
alliance lanes, pads, surviving mechanics, entry mode, combat setup and DAD
coordination still require the configured provider/participants. ADS's existing
Operator Guide has the concrete suite setup. Synced/unsynced clears remain
unverified; these local data changes still require publication before clients can
fetch them.