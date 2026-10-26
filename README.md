# LoreRim 5.0.4.8 日本語化データ

Wabbajack の Mod リスト **LoreRim 5.0.4.8** を日本語で遊ぶための翻訳データです。ゲームの言語設定は英語のまま、Dynamic String Distributor（DSD、Nexus Mods で配布）で起動時に日本語へ差し替えます。プラグイン（esp/esm）は書き換えないので、FormID やセーブには影響しません。

| 中身 | 数 |
|---|---|
| `SKSE/Plugins/DynamicStringDistributor/overwrite/*.json`（Mod ごとの日本語訳） | 1,056 ファイル / 165,380 行 |
| `Interface/Translations/*_english.txt`（MCM の日本語訳） | 104 ファイル |
| `Interface/creatures/`（Dragonborn's Bestiary の図鑑） | 1,002 ファイル |
| `SKSE/Plugins/NPCsNamesDistributor/*.json`（NPCs Names Distributor の名前。カタカナ） | 36 ファイル |
| `SKSE/Plugins/po3_SimpleActivateSKSE.ini`、`Dragonborns Bestiary.ini`（LoreRim の設定のまま、表示する文だけ日本語にしたもの） | 2 ファイル |

## このリポジトリに含まれていないもの

権利の関係で、自分で翻訳したもの以外は入れていません。日本語で遊ぶには、次のものを各自で用意してください。

1. **公式の日本語テキスト**：本編・DLC・Creation Club の公式日本語訳（STRINGS）と、画面表示の翻訳ファイル（`translate_japanese.txt`）。
   - どれも LoreRim の `Stock Game\Data` に最初から入っています。本編と DLC の分は `Skyrim - Interface.bsa`、Creation Club の分は各 `cc*.bsa` の中です。
   - 名前の `_japanese` を `_english` に変えて置いてください（例：`Strings/skyrim_japanese.strings` → `Strings/skyrim_english.strings`、`Interface/translate_japanese.txt` → `Interface/translate_english.txt`）。
   - 翻訳データからも、公式と同じ文の行（147,152 行）は除いてあります。そのため、Mod が公式と同じ英文を使っている所は、英語のまま表示されることがあります。
2. **作者が日本語を同梱している Mod の訳**：次の Mod は、本体に日本語のファイルが入っています。名前の `_japanese` を `_english` に変えてコピーしてください。BSA の中にあるものは、取り出してからコピーします。
   - STRINGS：Dismembering Framework（BSA）、The Frozen Heart - Quest Mod、Sanguine Symphony（BSA）、Unofficial Skyrim Creation Club Content Patch（BSA）
   - MCM：Audio Overhaul for Skyrim、B.O.O.B.I.E.S、Dismembering Framework（BSA）、Extended UI - Settings Loader、Norden UI 16x9（`skyui_se_japanese.txt`）、RaceMenu（BSA）、Sanguine Symphony（BSA）、SkyParkour、XP32 Maximum Skeleton Special Extended
   - `_japanese.txt` という名前でも中身が英語の Mod は多くあります。それらの日本語訳は、このリポジトリに入っています。
3. **他の Mod のデータを含むもの**：Mod のスクリプト（`.pex`）と、場所の名前を日本語にするプラグインは、翻訳だけを切り出せないので入れていません。そのため、スクリプトが出す通知やメッセージと、一部の場所の名前は英語のまま表示されます。
4. **Dynamic String Distributor 本体**と、**日本語フォント**（日本語対応のフォント Mod）。
   - LoreRim では、操作アイコン（Oblivion Interaction Icons）用のフォントを `fontconfig.txt` で読み込んでいます。日本語フォント Mod の `fontconfig.txt` を使うときは、次の 2 行も入れてください。入れないと、アイコンの代わりにアルファベットが表示されます。

     ```
     fontlib "Interface\Fonticon.swf"
     map "$Iconographia" = "Iconographia" Normal
     ```

## 導入

1. Mod Organizer 2 で、このリポジトリの中身を 1 つの Mod として追加します。
2. 他の Mod より優先されるように、左側の一覧のいちばん下に置きます。
3. 上記の「含まれていないもの」をそろえます。
4. ゲームの言語は英語（`sLanguage=ENGLISH`。LoreRim の初期設定）のままにします。

## 翻訳について

- 公式の用語（地名、種族名、ゲーム用語）に合わせ、AI で翻訳しました。使ったのは Claude Opus 5.5 と DeepSeek V4.1 Flash です。タグや `<Alias=...>` などの記号は、原文と一致することを機械的に確認しています。
- [Gate to Sovngarde 版](https://github.com/Rimcat-JA/GtS-Japanese-Translation)と同じ版のプラグインは、その訳を使っています。
- 人の手で全文を確認したわけではありません。不自然な訳もあると思います。
- 英語のまま残している文もあります。タグだけのページ、特殊フォントの文字、作中の架空言語、内部 ID などです。
- **対象は LoreRim 5.0.4.8（2026 年 10 月時点）です。** 翻訳は FormID と結び付いているので、別のバージョンでは合わない行が出ます。

## 権利について

元の文章の権利は、各 Mod の作者とベセスダにあります。このリポジトリは、自分で作った翻訳の部分だけを公開しています。Mod の作者の方から削除の依頼があれば、該当するファイルを削除します。Issue でご連絡ください。
