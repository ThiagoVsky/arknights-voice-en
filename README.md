# Arknights operator voice lines, English

Game assets from Arknights, extracted from the **EN** game server. This repository is
generated and refreshed by machine; do not edit its contents by hand.

## What is here

Source: `audio/sound_beta_2/voice_en/**` on the EN game server.

One directory per voice pack. Operator packs are `char_<operator_id>/`, holding that operator's clips as `cn_001.mp3`, `cn_024.mp3` and so on. Non-operator packs are `extra_<n>/`.

The clip numbers are the game's own dialogue keys, matching `charword_table.json` in ArknightsGameDataEN; the `cn_` prefix is an artefact of the original recording order and does not indicate the Chinese set.

## Format

MP3, 96 kbps mono

The EN server ships every voice language, so this set is complete even though the download source is the EN server.

## Updating

`.github/workflows/update.yml` runs once a day. Incremental state lives in
`.state/voice-en.json`, so only bundles that are new or whose hash changed are downloaded
and extracted again; a rerun with nothing new is a no-op.

Run it locally:

```bash
python -m pip install "arkprts[all]" lameenc
python tools/assets_sync.py --out . --flat --state .state
python tools/assets_sync.py --verify --out . --flat
```

`tools/assets_sync.py` in this repository is a self-contained copy whose default group is
`voice-en`. The canonical copy lives in [ArknightsGameDataEN](https://github.com/ThiagoVsky/ArknightsGameDataEN) under
`tools/assets_sync.py`; the download uses
[arkprts](https://github.com/thesadru/arkprts) and the extraction uses
[UnityPy](https://github.com/K0lb3/UnityPy) with the LZ4AK decompressor that arkprts
registers in place of the LZHAM that UnityPy does not implement.

