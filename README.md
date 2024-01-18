# Vivliostyleサンプル『植物一日一題』（牧野富太郎）

## 使い方

Vivliostyle CLI で preview:

```sh
vivliostyle preview shokubutsu_ichinichi.md
```

Vivliostyle CLI でPDF生成:

```sh
vivliostyle build shokubutsu_ichinichi.md -o shokubutsu_ichinichi.pdf
```

Vivliostyle CLI でEPUB生成:

```sh
vivliostyle build shokubutsu_ichinichi.md -o shokubutsu_ichinichi.epub
```

## 青空文庫版『植物一日一題』とVivliostyleサンプル版のための改変について

このVivliostyleサンプル版の『植物一日一題』（牧野富太郎）は、[青空文庫で公開されているファイル](https://www.aozora.gr.jp/cards/001266/card46820.html)を加工して、Vivliostyle・CSS組版用のMarkdown形式（VFM: Vivliostyle Flavored Markdown）にしたものです。青空文庫のファイルからVivliostyle・CSS組版用のMarkdown形式（VFM）への機械的な変換のほか、以下の変更を加えています。

- 外字は注釈でJIS X 0213の面区点番号かUnicodeの記載があるものはそのUnicode文字に置換し、それがなかった以下のものは近い漢字（異体字と思われる）に置換：
  - `※［＃「くさかんむり／（夷－十）」、231-11］` → 苐 (U+82D0)
  - `※［＃「さんずい＋（嗇／一）」、248-17］` → 濇 (U+6FC7)
- 図版をフロート配置したとき、まわりのテキストとの位置関係がより適切になるように、原稿ファイル内での図版の位置を調整
- その他、CSS組版で扱いやすいようにMarkdown＋HTMLタグでマークアップ

## このVivliostyleサンプルで使用されているCSSの機能

このVivliostyleサンプルのスタイルシート [css/style.css](css/style.css) では、Vivliostyleがサポートする以下のCSSの機能が使われています。

- 約物の詰めと和欧文間のスペースの設定：[text-spacing プロパティ](https://drafts.csswg.org/css-text-4/#text-spacing-property)
- 句読点のぶら下げ：[hanging-punctuation プロパティ](https://drafts.csswg.org/css-text-4/#hanging-punctuation-property)
- 長さの単位
  - [lh：当該要素のline-heightを基準とする長さの単位](https://drafts.csswg.org/css-values-4/#lh)
  - [rlh：ルート要素のline-heightを基準とする長さの単位](https://drafts.csswg.org/css-values-4/#rlh)
  - [rem：ルート要素のfont-sizeを基準とする長さの単位](https://drafts.csswg.org/css-values-4/#rem)
- [論理プロパティ](https://drafts.csswg.org/css-logical-1/)
  - margin-block-start, margin-block-end, margin-block, margin-inline, padding-inline-start, inset-block-start プロパティなど
- 圏点（傍点）：[text-emphasis プロパティ](https://drafts.csswg.org/css-text-decor-3/#text-emphasis-property)
- 縦書き
  - 組方向（縦書き／横書き）：[writing-mode プロパティ](https://drafts.csswg.org/css-writing-modes-3/#block-flow)
  - 縦書きでの文字の向き：[text-orientation プロパティ](https://drafts.csswg.org/css-writing-modes-3/#text-orientation)
  - 縦中横：[text-combine-upright プロパティ](https://drafts.csswg.org/css-writing-modes-3/#text-combine-upright)
- [ページフロート](https://drafts.csswg.org/css-page-floats/)
- [脚注](https://drafts.csswg.org/css-gcpm/#footnotes)
- [改ページの制御](https://drafts.csswg.org/css-break/#breaking-controls)
  - break-before, break-after, break-inside プロパティ
- 目次関連
  - [target-counter() 関数](https://drafts.csswg.org/css-content-3/#target-counter)
  - [leader() 関数](https://drafts.csswg.org/css-content-3/#leader-function)
- ページの設定
  - [@page ルール](https://drafts.csswg.org/css-page-3/#at-page-rule)
  - [ページセレクタ](https://drafts.csswg.org/css-page-3/#at-page-rule)
  - [ページサイズ](https://drafts.csswg.org/css-page-3/#page-size-prop)
  - [ページマージンボックス](https://drafts.csswg.org/css-page-3/#margin-boxes)
  - [ページカウンター](https://drafts.csswg.org/css-page-3/#page-based-counters)
- 柱の設定：[名前付き文字列](https://drafts.csswg.org/css-gcpm/#named-strings)
