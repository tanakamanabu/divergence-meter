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
| **IN-14** | ニキシー管 | **自作**（`hardware/lib/custom`） | 専用品。ソケット/ワイヤパッドのフットプリントを作成 |
| インダクタ / 抵抗 / コンデンサ | 受動部品 | KiCad 標準 | 高圧部は耐圧・沿面距離に注意 |

## 入手元（汎用）

- M5Stack 公式: https://docs.m5stack.com/
- SnapEDA: https://www.snapeda.com/
- Ultra Librarian: https://www.ultralibrarian.com/
- Component Search Engine: https://componentsearchengine.com/

## ライセンス上の注意

- ダウンロード品は各自の利用規約に従う。再配布可否は必ず確認。
- このリポジトリ（MIT）に同梱する場合も、third-party 部品は元ライセンスを維持する。
