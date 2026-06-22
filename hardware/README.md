# hardware（KiCad プロジェクト）

ダイバージェンスメーターの回路図・基板設計（KiCad 10）。

## 構成

```
hardware/
  divergence-meter.kicad_pro / .kicad_sch / .kicad_pcb   # 本体（コミット対象）
  sym-lib-table / fp-lib-table                           # プロジェクトのライブラリ登録
  lib/
    custom.kicad_sym       # 自作シンボル（IN-14 等）→ コミット
    custom.pretty/         # 自作フットプリント（.kicad_mod）→ コミット
    third-party/           # 外部入手の部品（ライセンス確認の上で同梱）
      NOTICE.md            # 同梱物の出典・ライセンス記録
```

> `*.kicad_prl`（個人ごとの表示設定）と `.history/`、各種バックアップ／自動保存ファイルは
> `.gitignore` で除外している。

## ライブラリの登録について

`custom` ライブラリは `sym-lib-table` / `fp-lib-table` に **登録済み** なので、
プロジェクトを開けばそのまま使える（Symbol/Footprint Editor で `custom` を選択）。

外部部品を追加するときは:

1. 入手元のライセンスを確認（[../LIBRARIES.md](../LIBRARIES.md) 参照）。
2. 再配布可なら `lib/third-party/` に置き、`lib/third-party/NOTICE.md` に記録。
3. `sym-lib-table` / `fp-lib-table` に行を追加して登録。

## 自作が必要な部品

- **IN-14**: 専用品。13 ピンの円形配置に合わせたフットプリント（ソケット or ワイヤパッド）を
  `lib/custom.pretty/` に作成する。
