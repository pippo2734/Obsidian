---
title: "NotebookLM のスライドを「編集できる資料」にするーGemini で YAML 化 → Google Slide 生成"
source: "https://zenn.dev/hirokita117/articles/24c42f407dc9b9"
author:
  - "[[Zenn]]"
published: 2025-12-14
created: 2026-01-12
description:
tags:
  - "clippings"
---
118

81[tech](https://zenn.dev/tech-or-idea)

## はじめに：NotebookLM の「スライド資料」、便利だけどかゆい所に手が届かない

NotebookLM の「スライド資料」生成によって作成されるスライドがクオリティ高いと専らの話題のことと思います。

- 雑なメモや社内ドキュメントから、いい感じの構成を勝手に組んでくれる
- それなりに見栄えするので、たたき台として強い
- Google Workspace を契約していれば、社内で共有も安心

個人的に「スライドの構成能力がすごいな」と思うのが、 **入力が一文でもスライドになる** ところです。

例えば、

> 「カレーはシチューより美味しい」

みたいな雑な一文でも、NotebookLM は「主張 → 根拠 → まとめ」みたいな **プレゼンの型** に寄せてスライドを立ち上げにいきます。  
もちろん内容の正しさは別として、 **話の順番を作るのが上手い** なと思います。  
正直スライド作成業務のコアな悩みごとって、このプロットを考えるところだと思うので、それをフォローしてくれるのはすごいです。  
以下そのスライドの一例です。

![](https://storage.googleapis.com/zenn-user-upload/d10555dcb378-20251214.gif)

ただ、NotebookLM で作成したスライドを業務に用いる上で困りごともあります。

- 「この一文だけ直したい」
- 「フォントや余白、会社テンプレに合わせたい」
- 「ロゴを入れたい、注釈を足したい」

NotebookLM の生成スライドは PDF として作成され、そのままだと"編集できない"ので、「やっぱり手作業か…」になりがちです。

この記事は、 Google Workspace 環境で働いていて、会社都合で Gemini 以外の LLM が使えない人向けに、NotebookLM の「スライド資料」機能を **最大限に活用するためのステップを考察した記事** となっています。

以下、考察ポイントです

- NotebookLM は **構成と初稿の生成に全振り**
- Gemini は **スライド PDF を設計図（YAML）に変換**
	- canvas ツールを利用して Google Slides も作成
- スライド生成後は、Google Slides のサイドパネルの **Nano Banana Pro** と **スクショ切り貼り** の両輪で回す

## 想定読者

- Google Workspace を契約している環境で仕事をしている
- 社内ポリシーで、使える生成AIが NotebookLM / Gemini に寄っている（他のLLMは使えない）
- NotebookLM でスライド作成をしてみたが、編集できないので上手く活用できない

## 本題

## 概要：3つのツールで「編集できる資料」を効率良く作成

1. **NotebookLM** ：雑メモ → 「スライド資料」で構成付きのたたき台を作る
2. **Gemini** ：PDF（またはスクショ）を読ませて「設計図（YAML）」に変換する
3. **Google Slides** ：YAML を元に生成されたスライドをブラッシュアップ

## NotebookLM の真価は「構成と流れを整える力」

ビジネスの実務上、スライド作りで一番重い & 大事なのは、綺麗なデザインを作るよりも「構成を考え、それを分かりやすい表現でスライドに落とし込む」ことではないでしょうか。  
NotebookLM はここを上手くフォローしてくれます。

### 実践：大まかな構成文章から 「スライド資料」 を起こす

例えば、社内で「生成 AI ツール導入」を提案する資料を作るとします。  
提案資料作成時に、以下のような大雑把なメモを用意したとしましょう。

```
こんな悩みありませんか？
- どんな資料だったらクオリティの高いものになるのか、考えるのに時間がかかる
- 資料に添付する画像などの調整作業が面倒

NotebookLM は、そんな悩みを解決します。
PDF や Web 記事、Google ドキュメント等を取り込み、スライド生成まで支援する AI パートナーです。

また、取り込んだソースはチームで共有できるので、
チームの情報探索負担を減らし、要点を短時間で共有資産化できます。
```

これを NotebookLM のソースに登録して「スライド資料」生成をします。

### ポイント

スライドを生成するとき、以下のようなプロンプトを設定します。  
また、 **プレゼンターのスライド** モードでスライドを生成することを推奨します。

```
背景は白でお願いします。
ピクトグラムを中心とした、シンプルな図解をメインにしてください
```

**理由**

- 後工程で、スクショの切り抜きとかをする場合、白の方が取り回ししやすい
	- 自社のスライドのトンマナに合わせるのが最善です
- ピクトグラムを指定しないと、画像の中に文字が入ったりして切り抜きがしにくい or Google Slide として変換する際に複雑になりがち
	- ピクトグラムだと表現の幅が狭くなってしまうのですが、画像の中の文字フォントとスライドのフォントを合わせるのが難しい場合があるので、いっそのこと諦める形です
- ピクトグラム指定と似た理由で、「詳細なスライド」モードで作成すると取り回しがしにくいものが生成されてしまったりするので、「プレゼンターのスライド」モードを利用します
	- 簡素にはなるものの、スライドの構成能力自体は「詳細なスライド」モードと変わりないと思います

以上のプロンプトと、上述したスライド構成のメモ書きを元にして生成されたスライドは以下のようになります。

![](https://storage.googleapis.com/zenn-user-upload/92afc62f7971-20251214.gif)

## NotebookLM で作成したスライドは編集できない問題

NotebookLM のスライド生成が便利でも、実務で詰まるのはこの点です。

- 微修正したいのに、要素単位で直しづらい
- フォント、余白を **社内テンプレに合わせたい**
	- 社内のテンプレートレイアウトに沿うことができないのが一番痛い所ではないでしょうか
- ロゴ、注釈、ページ番号などを入れたい

つまり「たたき台 → 仕上げ」へ移行する作業が必要です。

そこで、

1. NotebookLM の出力を「完成品」として扱わない
2. いったん言語化された「設計図」に表現して、それを元にスライド生成する

という作業をおこないます。

この「設計図」として扱いやすいのが **YAML** という記法です。  
※ここでは YAML 自体に関する説明は省きます。ご自身でお調べください。

## Gemini に「スライド設計図（YAML）」を書かせるプロンプト

手順はシンプルです。

1. NotebookLM で生成したスライドをダウンロード
2. Gemini にアップロード
3. 下記のプロンプトをそのままコピペして投げる

こうすることで得られるメリットは以下の通りです。

- スライドを言語化して **編集可能な部品の集合** として再定義する
- 図やレイアウトは"意図"と"関係性"を残して再現できるようにする

### 設計図作成プロンプト（YAML 生成プロンプト）

スライドをアップロードした状態で、下記プロンプトを入力してください。

下記プロンプトのポイントとしては、 **スライドに無用のコンテナ（背景として白いボックスを生成するなど）を含めるのを禁止していることです。**  
理由としては、社内のテンプレートを適用したい時に、そういったコンテナがあるといちいち削除しないとダメだからです（テンプレートレイアウトは最背面に表示されるので）。

```markdown
コンテナ禁止 (No Containers)
```

例えばこんな感じの出力がされます

```yml
- slide_id: 1
  title: "表紙：課題の提起"
  layout_type: "中央配置"
  design_intent: "シンプルで問いかけるようなコピーにより、視聴者の共感を誘う導入。"
  color_theme:
    primary: "#000000 (Black)"
    secondary: "#FFFFFF (White)"
    emphasis: "なし"
  elements:
    - id: text_main_question
      type: "text_block"
      position: "center"
      content:
        text: "こんな悩みありませんか?"
        heading_level: "h1"
        style: "bold, medium-size"
      visual_description: "スライド中央に配置されたシンプルな問いかけ。"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"
        style: "brand-font, small"
      visual_description: "右下のブランドロゴ署名"

- slide_id: 2
  title: "課題1：思考の迷路"
  layout_type: "2カラム (左：図解, 右：テキスト)"
  design_intent: "脳内の混乱を視覚化し、思考整理の難しさを表現する。"
  color_theme:
    primary: "#0055FF (Blue)"
    secondary: "#333333 (Dark Grey)"
    emphasis: "迷路の青いライン"
  elements:
    - id: icon_brain_maze
      type: "image"
      position: "left"
      visual_description: "人間の横顔のシルエットの中に、青と黒の線で描かれた複雑な迷路があるイラスト。"
    - id: text_problem_1_title
      type: "text_block"
      position: "top-right"
      content:
        text: "資料作成に潜む、見えない時間コスト"
        heading_level: "h2"
        style: "bold"
    - id: text_problem_1_desc
      type: "text_block"
      position: "right-center"
      content:
        text: "質の高いアウトプットを求めて、思考の迷路に迷い込む。"
        heading_level: "body"
        style: "normal"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"

- slide_id: 3
  title: "課題2：作業コスト"
  layout_type: "2カラム (左：図解, 右：テキスト)"
  design_intent: "本質的でない作業によるストレスと時間の浪費を表現。"
  color_theme:
    primary: "#333333 (Dark Grey)"
    secondary: "#FFFFFF (White)"
    emphasis: "なし"
  elements:
    - id: icon_stressed_worker
      type: "image"
      position: "left"
      visual_description: "頭を抱えて震えている棒人間。目の前には整理されていないドキュメントの山がある。"
    - id: icon_clock
      type: "icon"
      position: "top-right-of-image"
      visual_description: "針が高速回転している時計のアイコン。時間の経過を表現。"
    - id: text_problem_2_title
      type: "text_block"
      position: "top-right"
      content:
        text: "資料作成に潜む、見えない時間コスト"
        heading_level: "h2"
        style: "bold"
    - id: text_problem_2_desc
      type: "text_block"
      position: "right-center"
      content:
        text: "本質的でない画像調整などの作業に、貴重な時間が奪われていく。"
        heading_level: "body"
        style: "normal"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"

- slide_id: 4
  title: "課題3：情報の散逸"
  layout_type: "中央拡散型"
  design_intent: "情報がまとまらず、あちこちに散らばっているカオスな状態を可視化。"
  color_theme:
    primary: "#666666 (Grey)"
    secondary: "#CCCCCC (Light Grey)"
    emphasis: "なし"
  elements:
    - id: icon_cluster_documents
      type: "image"
      position: "center"
      visual_description: "PDF、画像、ドキュメントなどのアイコンが無秩序に散乱している様子。"
    - id: text_problem_result
      type: "text_block"
      position: "bottom-center"
      content:
        text: "その結果、生まれるのは「知の散逸」。"
        heading_level: "h2"
        style: "bold, center-align"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"
  diagram_structure:
    - from: "center-cluster"
      to: "outward"
      type: "arrow"
      label: ""
      direction: "radial"
  reproduction_note: "アイコンを放射状に配置し、遠心力が働いているように見せることで「散逸」を表現する。"

- slide_id: 5
  title: "解決策：NotebookLMの提示"
  layout_type: "中央一点集中"
  design_intent: "前のスライドのカオスに対し、強力な解決策としてロゴを大きく提示。"
  color_theme:
    primary: "#0055FF (Blue)"
    secondary: "#FF0000 (Red Accent)"
    emphasis: "ロゴの赤"
  elements:
    - id: logo_large
      type: "image"
      position: "center"
      visual_description: "NotebookLMのロゴマーク。青い本の形状で、右上の角が赤く折れ曲がっている（Nの形）。"
    - id: text_solution_claim
      type: "text_block"
      position: "bottom-center"
      content:
        text: "NotebookLMが、そんな悩みを解決します。"
        heading_level: "h2"
        style: "bold, center-align"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"

- slide_id: 6
  title: "NotebookLMの定義"
  layout_type: "数式型 (A + B = Value)"
  design_intent: "人間とAIの協調関係をシンプルな足し算で表現する。"
  color_theme:
    primary: "#333333 (Dark Grey)"
    secondary: "#0055FF (Blue Icons)"
    emphasis: "プラス記号"
  elements:
    - id: icon_human
      type: "icon"
      position: "left"
      visual_description: "考え事をしている人のアイコン（線画）。"
    - id: icon_plus
      type: "icon"
      position: "center"
      visual_description: "太い青色のプラス記号。"
    - id: icon_robot
      type: "icon"
      position: "right"
      visual_description: "ロボットのアイコン。胸にスクリーンがあり、アンテナがついている。"
    - id: text_definition_title
      type: "text_block"
      position: "bottom-center-top"
      content:
        text: "NotebookLMとは?"
        heading_level: "h2"
        style: "bold"
    - id: text_definition_body
      type: "text_block"
      position: "bottom-center"
      content:
        text: "あなたの思考を加速させる、AIリサーチパートナーです。"
        heading_level: "body"
        style: "normal"
  diagram_structure:
    - from: "icon_human"
      to: "icon_robot"
      type: "symbol"
      label: "+"
      direction: "horizontal"

- slide_id: 7
  title: "機能：情報の集約"
  layout_type: "ファンネル（左から右への収束）"
  design_intent: "多様なソースが一つにまとまる「集約」のプロセスを可視化。"
  color_theme:
    primary: "#0055FF (Blue)"
    secondary: "#333333 (Grey)"
    emphasis: "青い合流矢印"
  elements:
    - id: icon_source_pdf
      type: "icon"
      position: "left-top"
      visual_description: "PDFファイルのアイコン。"
    - id: icon_source_web
      type: "icon"
      position: "left-middle"
      visual_description: "ブラウザ/Web記事のアイコン。"
    - id: icon_source_drive
      type: "icon"
      position: "left-bottom"
      visual_description: "Googleドライブ/ドキュメントのアイコン。"
    - id: arrow_merge
      type: "diagram"
      position: "center"
      visual_description: "3つの始点から始まり、1つの大きな矢印に合流して右へ向かう青い曲線矢印。"
    - id: icon_notebooklm_small
      type: "icon"
      position: "right"
      visual_description: "NotebookLMのロゴ。"
    - id: text_step1
      type: "text_block"
      position: "top-left"
      content:
        text: "Step 1: あらゆる情報を、ひとつの場所に集約"
        heading_level: "h2"
        style: "bold"
    - id: text_instruction
      type: "text_block"
      position: "bottom-center"
      content:
        text: "PDF、Web記事、Googleドキュメントなどを、ドラッグ&ドロップで取り込むだけ。"
        heading_level: "caption"
        style: "small"
  diagram_structure:
    - from: "icon_group_sources"
      to: "icon_notebooklm_small"
      type: "merge-arrow"
      label: ""
      direction: "left-to-right"

- slide_id: 8
  title: "価値転換：個人からチームへ"
  layout_type: "左から右への変化"
  design_intent: "個人の作業がチーム全体の価値に変わるスケーラビリティを表現。"
  color_theme:
    primary: "#0055FF (Blue)"
    secondary: "#CCCCCC (Grey)"
    emphasis: "中央の大きな青い矢印"
  elements:
    - id: icon_individual
      type: "icon"
      position: "left"
      visual_description: "一人の人間のアイコン。"
    - id: arrow_big_right
      type: "diagram"
      position: "center"
      visual_description: "左から右へ向かう太く大きな青い矢印。"
    - id: icon_team
      type: "icon"
      position: "right"
      visual_description: "3人の人間が並んでいるチームのアイコン。"
    - id: text_value_shift
      type: "text_block"
      position: "bottom-center"
      content:
        text: "そして、価値は個人からチーム全体へ。"
        heading_level: "h2"
        style: "bold"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"

- slide_id: 9
  title: "チーム価値1：共有知"
  layout_type: "ハブ＆スポーク (ネットワーク型)"
  design_intent: "NotebookLMを中心として、チーム全員が情報にアクセスできる様子を描く。"
  color_theme:
    primary: "#0055FF (Blue)"
    secondary: "#333333 (Grey)"
    emphasis: "接続ライン"
  elements:
    - id: icon_center_app
      type: "icon"
      position: "center"
      visual_description: "中央のNotebookLMロゴ。"
    - id: group_users
      type: "icon-group"
      position: "surrounding"
      visual_description: "中央を取り囲むように五角形に配置された5人のユーザーアイコン。"
    - id: text_value_1_title
      type: "text_block"
      position: "top-left"
      content:
        text: "チームの価値 #1: 共有"
        heading_level: "h2"
        style: "bold"
    - id: text_value_1_desc
      type: "text_block"
      position: "bottom-center"
      content:
        text: "取り込んだソースは、ワンクリックでチームの共有知になります。"
        heading_level: "body"
        style: "normal"
  diagram_structure:
    - from: "icon_center_app"
      to: "each_user_icon"
      type: "line"
      label: ""
      direction: "radial"

- slide_id: 10
  title: "チーム価値2：探索コスト削減"
  layout_type: "シンボル強調"
  design_intent: "「探す」という行為自体を禁止/排除することを記号で直感的に伝える。"
  color_theme:
    primary: "#FF0000 (Red)"
    secondary: "#333333 (Black)"
    emphasis: "禁止マーク"
  elements:
    - id: icon_search_ban
      type: "image"
      position: "center"
      visual_description: "虫眼鏡（検索）のアイコンの上に、赤色の太い禁止マーク（斜線付き円）が重ねられている。"
    - id: text_value_2_title
      type: "text_block"
      position: "top-left"
      content:
        text: "チームの価値 #2: 効率化"
        heading_level: "h2"
        style: "bold"
    - id: text_value_2_desc
      type: "text_block"
      position: "bottom-center"
      content:
        text: "「あの資料どこだっけ?」をなくし、チームの情報探索負担を劇的に減らします。"
        heading_level: "body"
        style: "normal"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"

- slide_id: 11
  title: "チーム価値3：資産化"
  layout_type: "プロセス変容 (Before -> After)"
  design_intent: "情報（種）が価値ある資産（宝石）に成長・変換される様子をメタファーで表現。"
  color_theme:
    primary: "#0055FF (Blue)"
    secondary: "#333333 (Black)"
    emphasis: "宝石の輝き"
  elements:
    - id: icon_sprout
      type: "icon"
      position: "left"
      visual_description: "土から生えた小さな双葉のアイコン（情報の芽生え）。"
    - id: arrow_process
      type: "diagram"
      position: "center"
      visual_description: "左から右へのシンプルな細い矢印。"
    - id: icon_diamond
      type: "icon"
      position: "right"
      visual_description: "輝きを放つダイヤモンドのアイコン（価値ある資産）。"
    - id: text_value_3_title
      type: "text_block"
      position: "top-left"
      content:
        text: "チームの価値 #3: 資産化"
        heading_level: "h2"
        style: "bold"
    - id: text_value_3_desc
      type: "text_block"
      position: "bottom-center"
      content:
        text: "要点を短時間で共有資産化し、未来のチームのために知識を育てます。"
        heading_level: "body"
        style: "normal"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"
  diagram_structure:
    - from: "icon_sprout"
      to: "icon_diamond"
      type: "arrow"
      label: ""
      direction: "left-to-right"

- slide_id: 12
  title: "結論：チームの強化"
  layout_type: "エコシステム（ツリー型）"
  design_intent: "情報共有によってチーム全体が有機的に成長し、輝く様子を大樹のメタファーで締めくくる。"
  color_theme:
    primary: "#0055FF (Blue)"
    secondary: "#FFD700 (Yellow/Gold)"
    emphasis: "電球（アイデア）と葉"
  elements:
    - id: image_knowledge_tree
      type: "image"
      position: "center"
      visual_description: "中央に太い青い幹を持つ大きな木。枝が広がり、そこに「人」と「電球（アイデア）」が実のように繋がり合っている。"
    - id: text_conclusion_main
      type: "text_block"
      position: "bottom-center-large"
      content:
        text: "情報が、チームを強くする。"
        heading_level: "h1"
        style: "bold, large-size"
    - id: text_logo_footer
      type: "text_block"
      position: "bottom-right"
      content:
        text: "NotebookLM"
        heading_level: "caption"
  diagram_structure:
    - from: "tree_branches"
      to: "people_and_ideas"
      type: "connection"
      label: ""
      direction: "organic"
  reproduction_note: "ネットワーク図の変形として、木（Tree）構造を使用。根幹システムから個々のアイデアへ栄養が行き渡るイメージ。"
```

## canvas ツールで Google Slide を生成

上記のプロンプトの出力で YAML が出たら、あとは Google Slide を生成する工程に移ります。  
以下のようなプロンプトを canvas ツールを指定して入力してみましょう。

```
以下の yaml に従って、google slide を作成してください。

（出力された yaml をここにコピペ）
```

そうすると、例えばこんな感じのスライドが生成されます。

![](https://storage.googleapis.com/zenn-user-upload/3ec9fc95847f-20251214.gif)

生成が完了したら、スライドをエクスポートします。

## エクスポートされた Google Slide を編集

ここまで来たら後は普段のスライド作成業務に移る形です。

- 会社テンプレを適用させる
- Gemini が生成したスライドに付いているデザインだと物足りないなら、以下のいずれかで対応
	- NotebookLM が作成したスライド資料から切り抜き
	- Google Slide のサイドパネルの Nano Banana Pro でブラッシュアップ

## まとめ：NotebookLM は「完成品メーカー」ではなく「構成エンジン」

スライド作成で最も時間がかかるのは、デザインではなく「構成を考え、話の流れを整える」作業だと思います。  
NotebookLM の「スライド資料」機能は、この構成づくりの部分を強力にサポートしてくれます。  
一文だけでもスライドの形に持っていけるのは、NotebookLM が構成づくりに特化している証拠ではないでしょうか。

一方で、NotebookLM が生成するスライドは PDF として出力されるため、そのままでは編集できません。  
社内テンプレートに合わせたり、細かい文言を調整したりできないなら、実務で活用するのは難しい場面もあります。

この記事で紹介した手法は、NotebookLM の構成力を活かしつつ、編集可能なスライドに落とし込むための方法です。

1. **NotebookLM** ：雑メモやドキュメントから「スライド資料」を生成し、構成付きのたたき台を作る
2. **Gemini** ：生成された PDF を読み込ませて、編集可能な「設計図（YAML）」に変換する
3. **Google Slides** ：YAML から canvas ツールでスライドを生成し、社内テンプレートを適用してブラッシュアップ
4. **画像の調整** ：Nano Banana Pro とスクショ切り貼りを組み合わせて時短

白紙から構成を考えるよりも、この手法で作成した方が楽ではないでしょうか？

## 付録1：もし ChatGPT が社内で使えるなら

会社のポリシー的に OK なら、ChatGPT（GPT-5.2 系）はスライド作成・編集の体験がさらに良いケースがあります。  
ChatGPT の利用ができる方は、是非 ChatGPT も活用してみると面白いと思います！

参考例：

## 付録2：NotebookLM の開発ロードマップ

将来的には、NotebookLM 上で（？）スライド編集ができるみたいなので、この記事で紹介した手法は不要になると思われます。

> @NotebookLMと@stevenbjohnsonに、心から感謝します。スライド機能をこんなに洗練されていて、ほとんど不気味なほど完璧に展開してくれて、私自身の認知労働が、生産性の悲しい小さなコミュニティ劇場公演みたいに感じてしまいます。  
> でも一つ引っかかることがあります：なぜ編集できないスライドを発明するのか？ まるで火を授けておいて、それで料理するなと言っているようなものです。

> 編集機能は次のステップの最優先事項です！🫡🫡🫡

118

81

118

81