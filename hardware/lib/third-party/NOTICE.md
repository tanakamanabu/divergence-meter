# third-party ライブラリについて

このフォルダには、外部から入手したシンボル・
フットプリントを置く。**プロジェクト本体の MIT ライセンスは適用されない** ——
各ファイルは入手元のライセンスを維持する。

## 同梱してよいか判断するルール

1. **入手元のライセンス・利用規約を確認**する。
2. **再配布が許可されている**場合のみ、このフォルダに同梱する。
   - 下の一覧に「部品名 / 入手元 URL / ライセンス / 入手日」を必ず記録する。
3. **再配布が禁止・不明**な場合は同梱しない。代わりに
   リポジトリ直下の [`LIBRARIES.md`](../../../LIBRARIES.md) に入手先を書いておく。

## 同梱物の記録

| 部品 | 入手元 URL | ライセンス | 入手日 | ファイル |
|---|---|---|---|---|
| XIAO ESP32-C3 シンボル/フットプリント | https://github.com/Seeed-Studio/OPL_Kicad_Library （Seeed Studio XIAO Series Library） | CC-BY-SA-4.0 | 2026-06-22 | `Seeed_XIAO/`（`Seeed_Studio_XIAO_Series.kicad_sym`, `Seeed_Studio_XIAO_Series.pretty/`, `LICENSE`） |

> 帰属: © Seeed Studio, "OPL_Kicad_Library"（CC-BY-SA-4.0）。ライセンス全文は `Seeed_XIAO/LICENSE`。
> CC-BY-SA のため、これらのファイルを**改変して再配布する場合は同一ライセンス（CC-BY-SA-4.0）**で。
