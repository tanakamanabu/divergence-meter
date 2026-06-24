# 部品ライブラリ 入手先メモ

回路設計に必要なシンボル／フットプリントの入手先一覧。
**再配布が許可されているもの**は `hardware/lib/third-party/`（[NOTICE.md](hardware/lib/third-party/NOTICE.md) に記録）へ同梱、
**禁止・不明なもの**は同梱せず、ここの入手先からダウンロードして使う。

## 主要部品

| 部品 | 用途 | 入手先 | 備考 |
|---|---|---|---|
| **XIAO ESP32-C3** | マイコン | **同梱済み**（`hardware/lib/third-party/Seeed_XIAO/`, CC-BY-SA-4.0） | Seeed OPL_Kicad_Library より。symbol/footprint 登録済み |
| **74141 / K155ID1** | カソードドライバ | KiCad 標準（DIP-16）／ SnapEDA | ピン配置は要確認 |
| **74HCT595** | シフトレジスタ | KiCad 標準（DIP/SOIC-16） | |
| **MAX1771** | 昇圧コントローラ | SnapEDA（SOIC-8） | |
| **MPSA42 / MPSA92** | 高耐圧 Tr | KiCad 標準（TO-92） | |
| **IN-14 / IN-シリーズ ニキシー管** | ニキシー管 | **同梱済み**（`hardware/lib/third-party/Nixie_judge2005/`） | judge2005 [Eagle-and-KiCAD-Nixie-Libs](https://github.com/judge2005/Eagle-and-KiCAD-Nixie-Libs) より。`nixies-us`（IN-1〜IN-19）/`mynixies`/`nixiemisc` を収録。ライセンス注記は [NOTICE.md](hardware/lib/third-party/NOTICE.md) |
| **IN-14（代替）** | ニキシー管 | **自作**（`hardware/lib/custom`） | judge2005 を使わない場合のフォールバック。ソケット/ワイヤパッドのフットプリントを自作 |
| インダクタ / 抵抗 / コンデンサ | 受動部品 | KiCad 標準 | 高圧部は耐圧・沿面距離に注意 |

## judge2005 ニキシー管ライブラリ（同梱・再変換手順）

`hardware/lib/third-party/Nixie_judge2005/` に変換済みで同梱している。
元データを更新したい／変換を再現したい場合は、以下を実行する
（KiCad 付属の `kicad-cli` でレガシー Eagle/KiCad 形式を現行形式へ変換）。

```bash
git clone --depth 1 https://github.com/judge2005/Eagle-and-KiCAD-Nixie-Libs.git /tmp/nixie
DEST=hardware/lib/third-party/Nixie_judge2005
mkdir -p "$DEST"
CLI="/c/Program Files/KiCad/10.0/bin/kicad-cli.exe"   # 環境に合わせて調整
for lib in nixies-us mynixies nixiemisc; do
  "$CLI" sym upgrade /tmp/nixie/$lib.lib -o "$DEST/$lib.kicad_sym"
  "$CLI" fp  upgrade /tmp/nixie/$lib.mod -o "$DEST/$lib.pretty"
done
```

`sym-lib-table` / `fp-lib-table` には `Nixie_judge2005_nixies-us` 等として登録済みなので、
ファイルを置けばそのまま KiCad で使える（IN-14 シンボル/フットプリントを含む）。

## 入手元（汎用）

- M5Stack 公式: https://docs.m5stack.com/
- SnapEDA: https://www.snapeda.com/
- Ultra Librarian: https://www.ultralibrarian.com/
- Component Search Engine: https://componentsearchengine.com/

## ライセンス上の注意

- ダウンロード品は各自の利用規約に従う。再配布可否は必ず確認。
- このリポジトリ（MIT）に同梱する場合も、third-party 部品は元ライセンスを維持する。
