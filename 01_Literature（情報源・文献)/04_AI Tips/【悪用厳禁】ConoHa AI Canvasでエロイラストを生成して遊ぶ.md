---
title: "【悪用厳禁】ConoHa AI Canvasでエロイラストを生成して遊ぶ"
source: "https://ai-illust-conoha-ai-canvas.com/how-to-nsfw-ai-illust/"
author:
  - "[[Conoha AI Canvasで始めるAIイラスト作成ガイド]]"
published: 2025-05-16
created: 2025-09-21
description: "Conoha AI Canvasで起動したStable Diffusion XLでNSFWイラストを生成する方法を解説します。"
tags:
  - "clippings"
---
NSFWコンテンツ(性的なコンテンツ)に嫌悪感のある方は、この記事の閲覧はお控えください。

この記事はConoHa AI CanvasでStable Diffusion XLを使用し、エロイラストを生成する方法を纏めたものです。

**免責事項**

この記事は、生成AIにおけるNSFW（Not Safe For Work）表現に関する情報を提供することを目的としています。記事内では、NSFW表現を生成する可能性のあるプロンプトを紹介していますが、これらのプロンプトの使用を推奨するものではありません。

当記事で紹介する情報を活用する際は、あくまで読者自身の責任において行ってください。当ブログおよび管理人は、以下について一切の責任を負いません。

- 読者が、当記事の情報を利用したことによって生じたいかなる損害、損失、トラブル
- 生成されたコンテンツが、第三者の権利（著作権、肖像権など）を侵害した場合
- 生成されたコンテンツが、法令や公序良俗に反する場合
- 読者が利用するプラットフォームの利用規約に違反した場合

特に児童ポルノを連想させる写実的なコンテンツは絶対に生成しないでください。

ConoHa AI Canvasの利用に際しては解説記事を書いていますので、興味がある方は以下のリンクからぜひお読みください。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/01/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-2025-01-28-101439-e1740782679259-160x90.png)

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/01/p-samune-160x90.jpg)

![ConoHa AI Canvas アフィリエイトバナー](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/01/202412271017474221.png)

ConoHa AI Canvas アフィリエイトバナー

## 生成手順の概要

1. まずt2iで元画像を生成する。
2. 生成した画像でi2iを行う。

本当はテンプレとして汎用プロンプトを提示したかったのですが、実際には生成しながら調整をすることが多いため、ここでは共通する大まかな構成だけを示します。

### t2iプロンプトサンプル

**\[Prompt\]**  
1girl, explicit, newest, very aesthetic,  
コンセプト （ なるべく 短く ）,  
キャラ、ポーズなど,  
looking at viewer, white background,  
masterpiece, best quality, absurdres,  
numbered,

**\[Negative Prompt\]**  
worst quality, bad quality

Steps: 20  
Sampler: Euler a  
Schedule type: Automatic  
CFG scale: 7  
Size: 1050×1400  
Model: waiNSFWIllustrious\_v140

1girlは好きな人数に変えてください。looking at viewerは性行為のイラストの際は消した方が良いかもしれません。

この時点ではネガティブプロンプトは最小限とします。プロンプトの解釈をなるべく広く保てるようにするためです。同様の理由で、ここでは胸のサイズなどの身体特徴は指定しない方が良い結果になりやすい気がします。

画像サイズは好みで変えてください、私はiPadの画面比率に合わせるために1050×1400または1400×1050にしています。

赤字の部分はi2iプロンプトにコピーして使います。

### i2iプロンプトテンプレ

**\[Prompt\]**  
1girl, explicit, newest, very aesthetic,  
コンセプト（なるべく短く）,  
キャラ、ポーズなど,  
looking at viewer, white background,  
masterpiece, best quality, absurdres,  
curvy, huge breasts,smile, blush, sweat, pussy juice, ass visible through thighs, navel, grin,  
< Lora>

**\[Negative Prompt\]**  
worst quality, bad quality, sketch, comic, (monochrome, empty eyes:0.5),

Steps: 20  
Sampler: Euler a  
Schedule type: Automatic  
CFG scale: 7  
Size: 1050×1400  
Model: waiNSFWIllustrious\_v140  
Denoising strength: 0.85,

t2iからコピーした部分の下に、好みの身体特徴を記載します。blush（顔を赤らめる）, sweat（汗）あたりは汎用性が高いと思います。また、Loraを使用するなら末尾に入れます。

ネガティブプロンプトは上記のものを基本として、生成されたイラストに不要な要素があれば末尾に書き足します。

Denoising strengthは0.85で試して、元画像に消したい要素が多い場合は0.90くらいに、全く違うポーズが出るときは0.80とか0.75にします。

ではこの内容を踏まえて、実際に画像を生成してみます。

![ConoHa AI Canvas アフィリエイトバナー](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/01/202412271017474221.png)

ConoHa AI Canvas アフィリエイトバナー

## サンプル

今回は逆バニー＋エロスクワットで生成してみます（実際の生成物はモザイク無しです）。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/nsfw02-1-767x1024.jpg)

今回はこのイラストをどのように生成したかを解説します。

Conoha AI CanvasおよびStable Diffusion Web UIの細かい操作方法は省略するので、完全初心者の方は以前書いた [解説記事](https://ai-illust-conoha-ai-canvas.com/conoha-ai-canvas-stable-diffusion-guide/) をご覧いただけると分かりやすいかもしれません。

## 使用モデル

モデルは『WAI-NSFW-illustrious-SDXL』を使用しています。

[WAI-NSFW-illustrious-SDXL – v14.0 | Illustrious Checkpoint | Civitai](https://civitai.com/models/827184/wai-nsfw-illustrious-sdxl?modelVersionId=1761560)

記事執筆時点での最新バージョンはv14.0です。最新のものを選んでおけば良いと思います。導入の仕方が分からない方はをどうぞ。

## 初期設定

WAI-NSFWではEuler aが推奨されているので変更します。Hires. fixは使いません。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-62.png)

## t2iでの生成

今回はt2iで生成したイラストを、更にi2iするという方法で生成しました。

まずt2iです。以下のプロンプトで生成します。

**\[Prompt\]**  
1girl, explicit, newest, very aesthetic,  
reverse bunnysuit, squatting,  
gyaru, presenting pussy, v over eye, rabbit ears, cleft of venus, bowtie, ribbon, nipples,  
looking at viewer, white background,  
masterpiece, best quality, absurdres,  
numbered,

**\[Negative prompt\]**  
worst quality, bad quality

Steps: 20  
Sampler: Euler a  
Schedule type: Automatic  
CFG scale: 7  
Size: 1050×1400  
Model: waiNSFWIllustrious\_v140

一応シード値は非公開とします。今回は次のような画像が生成されました（修正済）。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/nsfw01-1-767x1024.jpg)

これを使用してi2iをします。

## i2iでの生成

img2imgのタブに移動して、初期設定をします。

Sampling methodをEuler aにして、Denoising strengthを0.85にします。画像サイズは先ほど生成したイラストと同じ値にしてください（今回は1050×1400）。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-63.png)

左側の余白に先ほど生成したイラストをドラッグ&ドロップし、プロンプトを入力します。

**\[Prompt\]**  
1girl, explicit, newest, very aesthetic,  
reverse bunnysuit, squatting,  
gyaru, presenting pussy, v over eye, rabbit ears, cleft of venus, bowtie, ribbon, nipples,  
looking at viewer, white background,  
masterpiece, best quality, absurdres,  
curvy, huge breasts,smile, blush, sweat, pussy juice, ass visible through thighs, navel, grin,

**\[Negative prompt\]**  
worst quality, bad quality, sketch, comic, (monochrome, empty eyes:0.5), piercing

Steps: 20  
Sampler: Euler a  
Schedule type: Automatic  
CFG scale: 7  
Size: 1050×1400  
Model: waiNSFWIllustrious\_v140  
Denoising strength: 0.85

gyaruに反応してピアスが生成されることが多かったので、ネガティブにpiercingを追記しています。

これで生成すると、先ほど紹介したイラストが生成されました。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/nsfw02-2-767x1024.jpg)

末尾に記載したプロンプトが反映されたイラストが生成されました。肌の塗りなど、全体的なクオリティが向上しています。

t2iで叩き台を作り、詳細をi2iで詰めるといったイメージです。t2iのみで生成するよりもクオリティが上がりやすく、細かいニュアンスを反映させやすいのでおすすめです。

![ConoHa AI Canvas アフィリエイトバナー](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/01/202412271017474221.png)

ConoHa AI Canvas アフィリエイトバナー

## 補足情報

### 補足情報① キャラクター性の反映

gyaruの部分にjirai keiと入れるとこんな感じになります。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/nsfw3-767x1024.jpg)

要するにキャラクター性を反映させることができます。 つまり版権キャラのプロンプトをここに入力すると…

### 補足情報② 人数変更

1girlを2girlsにして、gyaru, jirai keiとした場合です。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/nsfw4-767x1024.jpg)

こんな感じで、複数キャラでも今のモデルは割と分離して描画してくれます。 つまり版権キャラを 二人 書くと…

### 補足情報③ 性行為イラストの場合

プロンプトにsex,体位,1boy,penis辺りを記載すると良いです。

例として、『sex, on side, 1boy penis』を記載した場合です。

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/nsfw5-1024x767.jpg)

性行為のイラストの場合は横長も試してみると良いかもしれません。

### 補足情報④ プロンプトの探し方

WAI-NSFWのようにDanbooruタグで学習されているモデルを使うときは、こちらのサイトが超絶便利です。

[Danbooru タグ検索](https://dskjal.com/deeplearning/danbooru-tag-search.html)

nsfwだけでなく、健全イラストを生成する際にも大変参考になります。いつもお世話になっております。

![ConoHa AI Canvas アフィリエイトバナー](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/01/202412271017474221.png)

ConoHa AI Canvas アフィリエイトバナー

## おまけ

### おまけ① プロンプトに使える単語メモ

割とマイナーな単語もメモしてあったので一応紹介します。danbooruタグに対応しています。

| cleft of venus             | すじマンコ           |
| -------------------------- | --------------- |
| presenting pussy           | マンコ見せつけ         |
| ass visible through thighs | 前から見えるお尻        |
| orgasm                     | 絶頂              |
| revealing clothes          | 性交衣装 裸 エロ衣装 情趣服 |
| torogao                    | トロ顔             |
| reverse bunnysuit          | 逆バニー            |
| blindfold                  | 目隠し             |
| cover page                 | 表紙絵             |
| rabbit pose                | うさみみポーズ 手で耳     |
| v over eye                 | 目の横でピース         |
| curvy                      | むちむち グラマラス      |
| female ejaculation         | 潮吹き             |
| bouncing breasts           | 乳揺れ             |
| spread pussy               | くぱぁ             |
| spread ass                 | 尻くぱぁ            |
| huge ass                   | デカ尻             |
| cupless bra                | カップのないブラ        |
| crotchless                 | クロッチのないパンツ      |
| sex machine                | 機械姦             |
| tiptoes                    | 爪先立ち            |
| bowlegged pose             | 蟹股ポージング がに股     |
| arms up                    | 脇見せのポーズ         |
| lying                      | 寝そべり            |
| kneeling                   | 跪く 膝立ち          |
| undressing                 | 脱ぎかけ            |
| panty pull                 | パンツ脱ぎ           |

### おまけ② 他サンプル

ぱっと見た中で割と出来が良かったものをピックアップして紹介します。作成してから結構時間が経っており、プロンプトの構成が上で紹介したものとは異なっているため、あくまでプロンプトに使用する単語の参考例としてご覧ください。

また掲載しているプロンプトはi2iのものなので、流用する場合はt2iのテンプレに落とし込んで使用してください。

#### 01

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/02-767x1024.jpg)

2girls, explicit, newest, very aesthetic, white, analogous colors,  
gyaru, jirai kei, spread ass, anus, cleft of venus, backless outfit, bowtie, ribbon, frills, undressing, white panties, bra lift, nipples,  
looking at viewer, white background,  
masterpiece, best quality, absurdres,  
huge breasts, huge ass, smile, blush, sweat, pussy juice, ass visible through thighs, navel, grin,

Negative prompt: worst quality, bad quality, sketch, comic, monochrome, (empty eyes:0.5), piercing

#### 02

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/03-767x1024.jpg)

2girls, explicit, newest, very aesthetic, white, analogous colors,  
gyaru, jirai kei, lying, armpit, cleft of venus, thigh strap, bowtie, ribbon, nipples, cow print, crotchless, bra lift, bikini, school unifrom,  
looking at viewer, white background,  
masterpiece, best quality, absurdres,  
huge breasts, huge ass, smile, blush, sweat, pussy juice, ass visible through thighs, navel, grin,

Negative prompt: worst quality, bad quality, sketch, comic, monochrome, (empty eyes:0.5), piercing

#### 03

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/04-1024x767.jpg)

1girl, penis, sex, explicit, newest, very aesthetic, white, analogous colors,  
folded, clothed female nude male,  
gyaru, school uniform, pussy, bra peek, thigh strap, bowtie, ribbon, nipples, cow print, bra lift, bikini,  
white background,  
masterpiece, best quality, absurdres,  
huge breasts, blush, sweat, pussy juice, ass visible through thighs, torogao, clitoris, anus,

Negative prompt: worst quality, bad quality, sketch, comic, monochrome, (empty eyes:0.5), piercing

#### 04

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/01-767x1024.jpg)

1girl, 1boy, sex, explicit, newest, very aesthetic, white, analogous colors,  
clothed female nude male, kneeling,  
jirai kei, school uniform, bra peek, thigh strap, bowtie, ribbon, nipples, cow print, crotchless, bra lift, bikini,  
white background,  
masterpiece, best quality, absurdres,  
huge breasts, blush, sweat, pussy juice, ass visible through thighs, torogao,

Negative prompt: worst quality, bad quality, sketch, comic, monochrome, (empty eyes:0.5), piercing

#### 05

![](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/05/05-1024x767.jpg)

2girls, explicit, newest, very aesthetic, white, analogous colors,  
presenting pussy, bdsm, sitting, restrained, sex machine, stationary restraints, object insertion, anal beads, (orgasm:1.4), folded, presenting pussy,  
jirai kei, gyaru, school unifrom, pussy, bottomless, bra lift, thigh strap, bowtie, ribbon, nipples, cow print,  
white background,  
masterpiece, best quality, absurdres,  
curvy, huge breasts, blush, sweat, pussy juice, torogao, moaning, clitoris, female ejaculation, spread legs,

Negative prompt: worst quality, bad quality, sketch, comic, (monochrome, empty eyes:0.5),

## おわりに

取り扱いには気を付けて、楽しく生成しましょう。

この記事を読んでConoha AI Canvasを利用開始しようと思った方は、ぜひ当記事のリンクからサービス開始してください。私が喜びます（ダイマ

![ConoHa AI Canvas アフィリエイトバナー](https://ai-illust-conoha-ai-canvas.com/wp-content/uploads/2025/01/202412271017474221.png)

ConoHa AI Canvas アフィリエイトバナー