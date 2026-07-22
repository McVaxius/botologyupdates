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
