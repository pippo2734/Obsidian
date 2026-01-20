---
title: "【完全ガイド】Manus×LINE連携｜Bot作成→情報収集→コンテンツ生成→配信までを自動化する全手順を徹底解説｜みんなのニュースレター"
source: "https://tetumemo.m-newsletter.com/posts/b548c936424edc06?utm_medium=social&utm_campaign=af20128421e41599&utm_source=x"
author:
published:
created: 2026-01-19
description: "毎日の情報収集に疲れていませんか？今回は、AIエージェントManusとLINEを連携させ、自分だけのAIニュースBotを作る方法を徹底解説。プログラミングは不要！自然言語だけでOK。今日からあなたのLINEが最強の情報収集ツールに変わります | みんなのニュースレター"
tags:
  - "clippings"
---
[![user](https://storage.jabba.cloud/500r6l654tyi57abctunl9p4qseu)](https://tetumemo.m-newsletter.com/users/f6e7540837c2bb5b) [【週刊】今日から始めるAI生活](https://tetumemo.m-newsletter.com/) [ログイン](https://tetumemo.m-newsletter.com/login)

【完全ガイド】Manus×LINE連携｜Bot作成→情報収集→コンテンツ生成→配信までを自動化する全手順を徹底解説

毎日の情報収集に疲れていませんか？今回は、AIエージェントManusとLINEを連携させ、自分だけのAIニュースBotを作る方法を徹底解説。プログラミングは不要！自然言語だけでOK。今日からあなたのLINEが最強の情報収集ツールに変わります

11

i

y

c

r

m

![user](https://storage.jabba.cloud/500r6l654tyi57abctunl9p4qseu)

[テツメモ｜tetumemo](https://tetumemo.m-newsletter.com/users/f6e7540837c2bb5b)

2025/11/18

こんにちは！テツメモです。

皆さんは、こんな悩みを抱えていませんか？

- **最新のAIニュース、追いかけるだけで一日が終了…**
- **有益な情報だけを効率よく集めて、チームや顧客に届けたい**
- **自分専用の情報収集アシスタントがいたら、もっと本質的な仕事に集中できるのに…**

このような悩みを抱えているビジネスパーソンやクリエイターは、本当に多いです。私も、以前は毎日大量のニュースに目を通し、情報の取捨選択に疲弊していました。

  

今回は、これらの課題を解決するため、 **ManusとLINEを連携させた「自分専用AI情報収集Bot」の作り方** を、基本から応用まで分かりやすく解説します。

この方法を実践すれば、AIがあなたの代わりに最新情報を収集・要約し、毎朝LINEに届けてくれるようになります。実際に私も、LINEに送るようにしてから通勤途中に最新AI情報を収集できるようになりました。

メールだと埋もれてしまう情報でも、LINEなら通知の瞬間にパッと確認して読めるのが良いですね♪

## 📖 この記事を読むことで得られる3つのメリット

この記事を読むことで、以下の3つのメリットが得られます。

### 1\. Bot作成の基本を無理なくマスターできる

無料エリアでは、ManusとLINEの連携設定から、テキスト情報を自動でLINEに流すシンプルなBotの作り方まで、手を動かしながら学べます。専門知識がなくても、この記事通りに進めれば誰でも自分専用のBotを作成できます。

### 2\. 応用的な使い方とプロンプト設計の考え方が学べる

有料エリアでは、単なるテキストだけでなく、見た目がリッチな「カルーセル型メッセージ」で情報を届ける応用テクニックを紹介します。

さらに、AIに意図した通りの調査や整形をさせるための、プロンプト設計の考え方を丁寧に解説。ご自身の目的に合わせてカスタマイズしていくためのヒントが得られます。

### 3\. 実用的なAI情報収集メタプロンプトが手に入る

有料エリアの特典として、コピー＆ペーストして少し書き換えるだけで、国内外のAI情報を効率的に収集・要約し、LINEに届けるための「メタプロンプト」を公開します。情報収集の質と効率を大きく引き上げてくれる、実用的なプロンプトです。

## 🎙️ニュースレターの内容をAI音声でキャッチアップ！

記事の内容を、有料購読エリアの概要も含めて紹介しています。　

ぜひこちらも一緒にフォローしていただき、”ながら聴き”も楽しんでみてください♪

## 🎯 この記事の対象読者

この記事は、以下のような方に特におすすめです。

- **企業のマーケティング担当者** ：競合や業界の最新動向を効率的にキャッチアップしたい
- **コンテンツクリエイター、ブロガー** ：ネタ探しの時間を短縮し、コンテンツ制作に集中したい
- **最新のAIトレンドを追いかけたいビジネスパーソン** ：情報の洪水から解放されたい
- **業務効率化を目指すすべての人** ：単純な情報収集作業を自動化したい

もし、あなたが「情報収集に時間を取られすぎている」「もっと効率的にインプットしたい」と感じているなら、ぜひ最後まで読んで、一緒に手を動かして実践していきましょう！

## 📌 この記事の使い方

毎回私の記事はかなりの長文です。本一冊分くらいのボリュームがあるかもしれません。一度に全部読むのは大変だと思いますので、 **ブックマークして、時間があるときに少しずつ読み進める** ことをおすすめします。

特に、有料エリアは実際に手を動かしながら試すことで、何倍も理解が深まります。ぜひ、あなただけの情報収集Botを育ててみてください。

  

🔗 [Manus：招待コード](https://manus.im/redeem?c=njexode)

  

> ワンポイントTip：この記事で紹介するBotは、まず自分専用で試すのがおすすめです。安定して有益な情報が届くようになったら、チームのLINEグループや、運営しているLINE公式アカウントに応用していくと、効果を最大化できますよ。

## 💡 導入：なぜ今、ManusとLINEなのか？

![Manus_LINE_002.png.webp](https://storage.jabba.cloud/2pz9b22tf5tkibtzh9u9ekkzg01h) まずはじめに、 **「なぜ数あるツールの中で、ManusとLINEを組み合わせるのか？」** その理由とメリットについて、深く掘り下げていきましょう。

## 情報過多の時代における「賢い」情報収集術

私たちは今、情報の海の中にいます。次々と新しいAIツールが登場し、X（旧Twitter）のタイムラインは瞬く間に流れ去り、有益なニュースレターも受信箱に溜まっていく一方…。本当に重要な情報を見極め、インプットするだけでも一苦労です。

この課題を解決するために必要なのは、情報を「たくさん」集めることではなく、自分にとって本当に価値のある情報を「賢く」集める仕組みです。そして、 **その情報を、最も確認しやすい場所に届けること。** この2つを同時に実現する最適な組み合わせが、ManusとLINEなのです。

## 「自律型AIエージェント」Manusとは？

皆さんは「Manus」と聞くと、「何か色々できて便利そうだけど結局何ができるの？？」と思うかもしれません。

しかし、Manusの本質はそこにありません。Manusは、単に質問に答えるだけでなく、与えられた目標を達成するために、自ら計画を立て、必要なツール（Webブラウザ、コード実行環境など）を使いこなし、タスクを遂行する **「自律型AIエージェント」** です。

まるで、優秀なアシスタントを一人雇うようなもの。一度指示を出せば、あとはAIエージェントが自律的に作業を進めてくれます。今回のように「最新のAIニュースを集めて、要約して、LINEに送って」とお願いすれば、その一連の流れを全て自動で実行してくれるのです。

  

**💡1テーマ→10コンテンツをManusで自動化する方法　↓**[「1テーマ→10コンテンツ」が15分で完成！画像付き記事などManusで実現するコンテンツ制作自動化の魔法のメタプロンプト](https://tetumemo.m-newsletter.com/posts/a414b5f8ad06d37f)

[![post](https://storage.jabba.cloud/jd6cqw5eypcst4cb3rnbwq2lqux1)

「記事書いたら力尽きた...SNS投稿は明日でいいか」そんな日々、ありませんか？でも、1つのテーマから調査・アジェンダ・記事・画像・画像付き記事・Xポスト文・対談＆1人音声台本・動画プロンプトまで自動生成できたら？Manusの10段階ワークフローで、コンテンツ制作が驚くほど変わります　

テツメモ｜tetumemo

2025-10-06

](https://tetumemo.m-newsletter.com/posts/a414b5f8ad06d37f)[【革命】AIエージェント時代の始まり：招待制廃止のManus AI完全攻略とX用バズスレッド自動生成プロンプトの作り方](https://tetumemo.m-newsletter.com/posts/2dd0f9149a888267)

[![post](https://storage.jabba.cloud/1sfjct2g7btomso8vm42pg09dv5m)

AIツールの新しいニュース、もううんざりしていませんか？「また新しいサービス？」「結局何が違うの？」そんな疑問をお持ちの方にこそ読んでほしい内容です。招待制が廃止されたManus AIで実際に記事を自動生成してみたら、想像以上の結果に。あわせてManusに生成させた、X用バズスレッド生成プロンプト付きでお届けします

テツメモ｜tetumemo

2025-06-23

](https://tetumemo.m-newsletter.com/posts/2dd0f9149a888267)

## なぜ「LINE」で情報を受け取るのか？

では、なぜその情報の届け先がLINEなのでしょうか？

答えはシンプルで、 **LINEが私たちの生活に最も深く根付いているコミュニケーションツール** だからです。

  

メールやSlack、専門のニュースアプリなど、情報をチェックする場所が増えれば増えるほど、私たちの可処分時間は奪われていきます。しかし、家族や友人とのやり取りで日常的に開くLINEに、仕事や学習に必要な情報も集約できたらどうでしょう？

あちこちのアプリを開く必要がなくなり、重要な情報を見逃すことも減ります。日常のコミュニケーションの流れの中で、自然に最新情報をインプットできるようになる。これこそが、LINEを情報の「受け取り場所」として活用する最大のメリットです。

  

Manusという強力な情報収集エンジンと、LINEという最も身近なインターフェース。この2つを組み合わせることで、私たちは情報収集に振り回される生活から解放され、本当に価値のある仕事に集中する時間を手に入れることができるのです。

  

🔗 [Manus：招待コード](https://manus.im/redeem?c=njexode)

  

> ワンポイントTip：ManusとLINEの連携は、単なる「通知機能」ではありません。LINEのトーク画面が、あなた専用にカスタマイズされた「情報ダッシュボード」に変わる、とイメージすると分かりやすいかもしれません。

## 🧩 Manusの基本知識：外部サービス連携の仕組み

前のセクションでは、情報収集の自動化におけるManusとLINEの組み合わせの優位性についてお話ししました。ここからは、その強力な連携を実現するManusの「心臓部」とも言える機能について、さらに詳しく見ていきましょう。

## Manusの強み：様々な外部サービスと連携できる「コネクタ機能」

![Manus_LINE_003.png.webp](https://storage.jabba.cloud/edkrlupaux0kji4820k6qudgvjoc) Manusが単なるAIチャットツールと一線を画す最大の理由は、その **「コネクタ機能」** にあります。これは、Manusが他の様々な外部サービスと連携し、それらを自在に操作するための機能です。

多くのツールは、そのアプリの中だけで機能が完結してしまいます。しかしManusは、私たちが普段から使っているGmail、Googleカレンダー、Notion、そして今回主役となるLINEといったサービスと「接続」し、それらを横断したタスクを自動化できるのです。しかもプログラミングは一切不要！

これにより、Manusは単体のツールとしてではなく、 **あらゆるサービスを繋ぐ「司令塔」** としての役割を果たします。

## 連携の核となる技術「MCP（Model Context Protocol）」とは？

![Manus_LINE_005.png.webp](https://storage.jabba.cloud/unvsf3na5pbl8485xgtqhgxzi31l) ※Manusは紹介しきれないレベルで接続できるサービスが多い

  

この強力な連携を支えているのが、「MCP（Model Context Protocol）」 **という技術です。少し専門的に聞こえるかもしれませんが、心配はいりません。簡単に言えば、これは** 「AIのためのUSBポート」のようなものです。

  

私たちがパソコンにマウスやキーボード、プリンターなど、どんなメーカーの機器でもUSBポートに挿せば使えるように、MCPという共通の規格があることで、Manusは様々な外部サービスと簡単かつ安全に接続できます。

開発者は、このMCPという「接続口」さえ用意すれば、自分のサービスをManusに対応させることができます。この開かれた設計思想こそが、Manusの可能性を無限に広げているのです。

  

💡 **今でこそMCP接続は簡単になりましたが、数ヶ月前は接続して使うまでにちょっとしたスキルが必要でした　↓**[驚異の生産性革命！Claude MCPとNotionで実現するビジネス効率化の新時代](https://tetumemo.m-newsletter.com/posts/ed4b603725322f97)

[![post](https://storage.jabba.cloud/t9v32o2cy2wd7yhe6d0zwlqmg3ox)

Web検索からナレッジ管理まで、すべての情報をシームレスにつなぐ時代が到来。Claude MCPとNotionの連携により、情報収集と管理の課題を一気に解決。この記事では、Windows環境での導入から実践的な活用法まで、業務効率を劇的に向上させる最新テクニックを徹底解説します。AIとの新しい協働スタイルを、ぜひ体験してください！

テツメモ｜tetumemo

2024-12-09

](https://tetumemo.m-newsletter.com/posts/ed4b603725322f97)

## 具体的な連携事例とプロンプト紹介

では、実際にどのような連携が可能なのでしょうか。ここでは、具体的な指示（プロンプト）の例と共に、代表的な連携事例をご紹介します。これらのプロンプトをコピーして少し変えるだけで、すぐにでもあなたの業務を自動化できます。

### Gmail連携：メール処理を自動化する

![Manus_LINE_004.png.webp](https://storage.jabba.cloud/sbi2xfy56sgtd9fv4gffv5rrbxw5) ※接続したいサービスを追加しておき、ONしておくだけでOK

  

特定の差出人から届いたメールの内容を自動で要約させ、重要なものだけを通知する、といった作業が可能です。

> **プロンプト例：**
> 
> `毎朝9時にGmailを確認し、"株式会社Example"から届いている未読メールがあれば、その内容を3行で要約してLINEに送ってください。`

### Googleカレンダー連携：スケジュール管理を効率化する

Manusとの会話で決まった予定を、自動でGoogleカレンダーに登録させることができます。

> **プロンプト例：**
> 
> `来週の水曜日、15時から16時まで「山田様との定例ミーティング」をGoogleカレンダーに登録してください。場所はオンラインです。`

### Notion連携：情報収集と整理を自動化する

Webでリサーチした内容を、自動でNotionのデータベースに整理・保存させることができます。

> **プロンプト例：**
> 
> `最新のAIに関するニュースを3つ探し、それぞれの「タイトル」「URL」「概要」をNotionの「リサーチデータベース」に新しいページとして追加してください。`

Tweet Loading...

### Canva連携：デザイン作成を効率化する

簡単な指示で、SNS投稿用の画像などをCanvaで作成させることも可能です。

> **プロンプト例：**
> 
> `「夏のセール開催中！」というテキストを入れた、Instagram投稿用の正方形の画像をCanvaで作成してください。背景は青空の写真で、爽やかなデザインにしてください。`

  

そして、今回のテーマである **LINE連携** も、このコネクタ機能の一つです。Manusが収集・分析した結果を、最も身近なLINEに届ける。この一連の流れが、コネクタ機能によって初めて実現します。

  

このように、Manusはそれ自体がパワフルなだけでなく、他のサービスと連携することで、その能力を何倍にも増幅させることができるのです。

  

🔗 [Manus：招待コード](https://manus.im/redeem?c=njexode)

  

> ワンポイントTip：Manusにログインしたら、まずはどのような「コネクタ」が用意されているか一覧を眺めてみるのがおすすめです。「自分が普段使っているあのサービスと連携させたら、こんな自動化ができるかも？」と、新しいアイデアが湧いてくるはずです。

## 📱 LINE公式アカウントの基本知識：Bot作成に必要な情報を取得しよう

![Manus_LINE_014.png.webp](https://storage.jabba.cloud/5khdseheob5bok9odra0psncdktg) ※Manus×LINE連携で必要な情報は2点ですが、  
自分専用でしたらチャネルアクセストークンだけでもOKです

  

Manusの強力なコネクタ機能についてご理解いただけたかと思います。Manusが情報を集める「頭脳」だとしたら、次はその情報を受け取る「手足」となるLINE側の準備です。

ここでは、私たちのBotの「ガワ」となるLINE公式アカウントを作成し、Manusとの連携に必須となる **2つの重要情報（チャネルアクセストークンとデフォルト受信者ユーザーID）** を取得するまでの手順を、画像付きのイメージで分かりやすく解説します。専門知識は不要で、すべて無料で始められますのでご安心ください。

## STEP1: LINE公式アカウントを作成する

![Manus_LINE_006.png.webp](https://storage.jabba.cloud/gtddlr232rjouwgpkaf92atjw3nv) まず、LINE公式アカウントを作成しましょう。これにより、企業や店舗が情報発信に使うものと同じ仕組みを、個人で利用できます。

1. [**LINE for Business**](https://www.linebiz.com/jp/service/line-official-account/) のサイトにアクセスします。
2. サイト中央にある「アカウントの開設（無料）」ボタンをクリックします。
3. 「アカウントを作成」画面で、 **「個人のLINEアカウント」** または「メールアドレス」で登録を選びます。普段お使いのLINEアカウントでログインするのが一番簡単です。  
	![Manus_LINE_007.png.webp](https://storage.jabba.cloud/16wroiyv57tyeafx32ziaszpy5qv)
4. 画面の指示に従い、アカウント名（例：Manus\_AI News）、業種（例：個人）などを入力すれば、公式アカウント作成は完了です。これで、あなたの「LINE Business ID」とが作成されました。  
	![Manus_LINE_009.png.webp](https://storage.jabba.cloud/qzgdsajyctqrgfa0ujvocwvpox3d) ![Manus_LINE_010.png.webp](https://storage.jabba.cloud/su5kwzo1ept2by8br8gr5tf9fdcu)
5. LINE Official Account Managerにアクセスすると管理ページが表示  
	![Manus_LINE_011.png.webp](https://storage.jabba.cloud/ssnu48w0pitxaf2qc38qnrn3r1vs)
6. 自分のLINEを確認すると自動的に友だち追加されています。  
	これで公式アカウントの開設は完了です。 ![IMG_7162.jpeg.webp](https://storage.jabba.cloud/scz4pr2fhshhshfog25hvcibjj87)

料金プランはいくつかありますが、 **まずは「フリープラン」で十分です。** 月間200通まで無料でメッセージを送れるので、個人で使う分には問題ありません。　

## STEP2: LINE Developersで「チャネル」を作成するし、チャネルアクセストークンへを取得する

次に、作成した公式アカウントをプログラム（今回はManus）から操作できるようにするための設定を行います。その舞台となるのが **「LINE Developers」** という開発者向けの管理画面です。「 **LINE Official Account Manager** 」と2つ管理画面があって少し混乱すると思いますが、Manusに必要な設定を取得していきましょう！

1. [**LINE Developersコンソール**](https://developers.line.biz/console/) にアクセスし、先ほど作成したアカウントでログインします。  
	![Manus_LINE_013.png.webp](https://storage.jabba.cloud/c94s5f48g5p0y757msss0uu8hf87)
2. ログインして、「プロバイダー」の作成をします。プロバイダー名はあなたの名前や会社名など、管理しやすい名前を入力してください（例：Manus AI NewsでもOK）。  
	![Manus_LINE_015.png.webp](https://storage.jabba.cloud/g9y9l9fbqmktth4hgp01o6f3t0zi) ![Manus_LINE_016.png.webp](https://storage.jabba.cloud/2kivmqdorkckgccus22emrlm68cv)
3. プロバイダーを作成したら、「 [**LINE Official Account Manager**](https://manager.line.biz/account/) 」へアクセスし、作成したアカウントを選択します。  
	![Manus_LINE_018.png.webp](https://storage.jabba.cloud/qv3frw8wkp3qny1t6gwjsjnfi17r)
4. 右上の「設定」を選択  
	![Manus_LINE_019.png.webp](https://storage.jabba.cloud/l4eopdeljjqsh9g02fsog4yqjn6g)
5. 「Messaging APIを利用する」をクリック  
	![Manus_LINE_020.png.webp](https://storage.jabba.cloud/5a654p1srsumh7rajt2oxsvrdlpj)
6. [**LINE Developersコンソール**](https://developers.line.biz/console/) で作成したプロバイダーを選択します。  
	![Manus_LINE_021.png.webp](https://storage.jabba.cloud/c0l4jk4e4ihovlhzhas5023cczw7) ![Manus_LINE_022.png.webp](https://storage.jabba.cloud/7bnl5sraxoz2h57wiav4islxr6lo) ![Manus_LINE_023.png.webp](https://storage.jabba.cloud/p6u32mcncmwh4rdeneinhi9s9eiz)
7. Messaging APIの準備が完了です。 [LINE Developersコンソール](https://developers.line.biz/console) かに移動します。  
	![Manus_LINE_024.png.webp](https://storage.jabba.cloud/75bp46jgb9c5b5ky8zhn1a02dboe)
8. [**LINE Developersコンソール**](https://developers.line.biz/console) のManus AI Newsのプロバイダーに「Manus AI News」のチャネルが設定されています。  
	![Manus_LINE_025.png.webp](https://storage.jabba.cloud/vr0od6aj7tr4382j4fz790rxp1ou)
9. Manus AI Newsのチャネルを開き、Messaging API設定を開きます  
	![Manus_LINE_026.png.webp](https://storage.jabba.cloud/mvgrig5btptsem9r3nyh112nso25)
10. 下にスクロールして「チャネルアクセストークン」を「発行」すると、トークンが表示されますのでコピーして保管しましょう。これを後ほどManusへ設定します。  
	![Manus_LINE_027.png.webp](https://storage.jabba.cloud/6l7i07cjr13677ob6kmjyyoq5p0k)
11. Manusのコネクタ管理からLINEを選択し、チャネルアクセストークンは貼り付けて保存します。  
	実は、これだけで自分専用のbotなら設定は完了です！  
	![Manus_LINE_028.png.webp](https://storage.jabba.cloud/stizqbppshbiuzmao3ye6a8xqdjr)
12. 「試してみる」を押して、実際に送信テストをすることができます。
13. デフォルトで入力されているプロンプト  
	「LINE コネクタのテストを手伝い、その機能の使い方を教えてください（例えば、それを使用して取得したデータを表示してください）。その機能について簡単に説明してください。」  
	![Manus_LINE_031.png.webp](https://storage.jabba.cloud/5wzj5wtp4da70n8re5zqmvtxvg3i)
14. もしLINE×Googleカレンダー連携等を試すなら  
	「11月18日の予定をGoogleカレンダーから取得し、場所や持ち物などの詳細情報を含めてLINEに送信してください。1つ目のポストには重要事項(予定重複、提出期限など)をまとめ、2つ目以降に各予定の詳細を時系列順に配置してください。予定ごとに異なるアイコンを使用し、重要な情報は強調してください。」  
	![Manus_LINE_030.png.webp](https://storage.jabba.cloud/rv3d1nig38wav08u564zdyfajf6a)
15. LINE×Googleカレンダーの予定がLINEに送られてきました！Manusが気を利かせてカルーセル型のFlexメッセージとして送ってくれました。（※表示されている内容は架空の予定です）  
	![Manus_LINE_032.png.webp](https://storage.jabba.cloud/z0lt4wq4klfz8cshv9jany84tia7)

これで最低限Manus×LINE連携の設定は完了です！

## STEP3: デフォルト受信者ユーザーIDを取得する

上記で自分専用のbotは完了していますが、せっかくなのでManusにある残りの「デフォルト受信者ユーザーID」もしちゃいましょう！

  

これは作成した公式チャネルへ友だちが複数登録されている際に役立ちます。

  

具体的には、友だちが200人登録している場合、何も考えずに送信してしまうと一気に200通送ってしまい月の無料枠を一気に使ってしまいます。

そうならないためにも、テスト用に送るデフォルトの受信用ユーザーを設定しておくことで、Manusから指示する際「LINEのデフォルト受信用ユーザーに送って」と指示すれば、1通のみの送信で済みます。

”間違いを防ぐ保険”の意味でも、今は使わなくても設定しておきましょう！

### デフォルト受信者ユーザーID

これは、Botがメッセージを送る先の「住所」にあたります。今回は自分自身に送るので、あなた自身のユーザーIDを確認します。

1. 同じく [**LINE Developersコンソール**](https://developers.line.biz/console) のManus AI Newsの「チャネル基本設定」へ遷移します。  
	![Manus_LINE_033.png.webp](https://storage.jabba.cloud/5dgnuvo1rrsk5y01dv7b46ihzlrz)
2. ページの一番下までスクロールすると、「あなたのユーザーID」という項目があります。  
	![Manus_LINE_034.png.webp](https://storage.jabba.cloud/qbxcmoqslzfys93dgjdup68r6x2o)
3. `U` から始まる33桁の英数字が表示されています。これが **あなたのユーザーID** です。これも同様にコピーして保管しておきましょう。
4. 最後にManusへ貼り付けて完了です。  
	![Manus_LINE_035.png.webp](https://storage.jabba.cloud/6f6krxno8h2u88evlgdg8rdzymbg)

お疲れ様でした！LINE Official Account Managerや LINE Developersを行き来して混乱したと思いますが、つまづきポイントも含めすべて画面を貼り付けておきましたのでなんとか設定できると思います！

  

これで、LINE側の準備はすべて完了です。 **「チャネルアクセストークン」と「デフォルト受信者ユーザーID」** 、この2つ設定が完了しましたので後はManus×LINE連携を楽しみましょう！

  

🔗 [Manus：招待コード](https://manus.im/redeem?c=njexode)

  

> ワンポイントTip：LINE Developersコンソールは少し複雑に見えるかもしれませんが、今回触るのは「Messaging API設定」と「チャネル基本設定」の2つのタブだけです。この2つの場所さえ覚えておけば、迷うことはありません。

## 🛠️【実践】基本編：テキスト情報をLINEに流してみよう！

お待たせしました！ここからはいよいよ実践編です。前のセクションで取得した情報を使って設定が完了していますので、紹介するプロンプトで色々試してみましょう！

このセクションを読み終える頃には、あなたのLINEにAIが自動でメッセージを送ってくれる、未来のような体験が待っています。一つずつ、丁寧に進めていきます。

## Manusで定期実行タスクを作成する

接続が完了したら、次はManusに「何をしてほしいか」を具体的にお願いするタスクを作成します。今回は、 **「24時間以内のAI関連重要ニュース5件をLINEデフォルトユーザーへ配信してください。各ニュースには、カテゴリアイコン、見出し、要約（50文字程度）、詳細記事へのリンクを含めてください。」** というタスクを、定期的に実行するよう設定してみましょう。

1. Manusの画面左側のメニューから「定期タスク」を選択します。
2. 「＋ 新しいスケジュール」ボタンをクリックします。  
	![Manus_LINE_036.png.webp](https://storage.jabba.cloud/0vqom0us93rkf3p6yz1uum0xh699)
3. タスク作成画面で、プロンプト、スケジュール等を設定します。コネクタは「LINE」を選択しておきましょう。  
	![Manus_LINE_037.png.webp](https://storage.jabba.cloud/nusujgt9o22x5gtpyf6320f88nke)

これで、毎週の火曜、土曜のAM8時にに自動でタスクが実行されるようになりました。

## タスクの実行テスト

設定したタスクはすぐに実行して試すことができます。

![Manus_LINE_038.png.webp](https://storage.jabba.cloud/elvarbmbhqr3ikgq5mknt26mw72j) ✅️ **設定済みのプロンプト**

`24時間以内のAI関連重要ニュース5件をLINEデフォルトユーザーへ配信してください。各ニュースには、カテゴリアイコン、見出し、要約（50文字程度）、詳細記事へのリンクを含めてください。`

これでManusが自動でWebを検索し、見つけたニュースをあなたのLINEに届けてくれるはずです。

**✅️LINEへ配信された情報　↓**

LINEに5つのニュースが無事に届きました！

![Manus_LINE_041.png.webp](https://storage.jabba.cloud/i1l1eghcfcdzmf3twvzn7s5j3u0t)  

✅️ **オシャレなカルーセル型で配信する場合のプロンプト**

`24時間以内のAI関連重要ニュース5件をLINEデフォルトユーザーへカルーセル型のFlexメッセージとして配信してください。各ニュースには、カテゴリアイコン、見出し、要約（50文字程度）、詳細記事へのリンクを含めてください。`

![Manus_LINE_040.png.webp](https://storage.jabba.cloud/g133aj9496tnqcuy8foqzzccw2se)  

このように **「カルーセル型のFlexメッセージとして」** と入力するだけでリッチなメッセージを送ってくれるようになります。

## 【特典】すぐに使えるプロンプト事例集（10選）

![Manus_LINE_039.png.webp](https://storage.jabba.cloud/53swo03ms98nwa95apyqw5dxnyyf) 基本のBotが作れたら、次はプロンプトを色々変えて、自分好みにカスタマイズしてみましょう。以下に簡単ですが、コピーしてすぐに使えるプロンプトの事例を10個用意しました。ぜひ試してみてください。  
※すべて定期タスク登録する必要はなく、新規タスクから実行してみましょう！

### 1\. 特定キーワードのニュースを収集

`「自動運転」に関する最新ニュースを3つ探し、それぞれのタイトルとURLをLINEに送って。`

### 2\. X（旧Twitter）の特定アカウントの投稿を監視

`イーロン・マスクのXアカウント（@elonmusk）が24時間以内に新しい投稿をしていたら、その投稿内容とURLをLINEに送って。`

### 3\. 株価を定時でチェック

`今日のマーケット終了後、トヨタ自動車（7203.T）の終値を調べてLINEで教えて。`

### 4\. 天気予報を取得

`明日の東京の天気と最高気温、降水確率を調べてLINEに送って。`

### 5\. 特定ブログの更新をチェック

`Google AIの公式ブログ（URL）に新しい記事が投稿されていないか確認し、もしあればタイトルとURLをLINEに送って。`

### 6\. 毎日の学びの習慣化

`今日の「コンピュータサイエンスに関する豆知識」を一つ見つけて、LINEで教えて。`

### 7\. 競合サイトの更新をチェック

`（競合のURL）のWebサイトに、先週から何か更新があったか確認して、変更点があればLINEで報告して。`

### 8\. 好きなメディアのトップ記事を取得

`ITmediaのトップページにある記事の中から、アクセスランキング1位の記事のタイトルとURLをLINEに送って。`

### 9\. 今日の最初の予定をリマインド

`私のGoogleカレンダーを確認して、今日の最初の予定は何時からで、何の予定かLINEで教えて。`

### 10\. 気になる言葉をWikipediaで要約

`Wikipediaで「大規模言語モデル」について調べて、その概要を3行で要約してLINEに送って。`

  

Manusは実行にトークンを消費しますので、テストの際は上記のように短文程度で確認してみるのをオススメします。送られてきたアウトプットの内容や形式に納得ができたら、送る情報量、調査するプロンプトなどを調整し仕上げていくのが効率的でコスパも良いです。

  

🔗 [Manus：招待コード](https://manus.im/redeem?c=njexode)

  

> ワンポイントTip：最初のうちは、スケジュール設定を「毎日」ではなく「1回のみ」にして、色々なプロンプトを試してみるのがおすすめです。期待通りの結果が返ってくるようになったら、お気に入りのプロンプトを「毎日」や「毎週」のスケジュールに設定し、自動化の恩恵を享受しましょう。

## 📖 ここからのコンテンツは有料です

ここまでお読みいただき、ありがとうございます！

無料エリアでは、ManusとLINEを連携させ、あなただけの情報収集Botを作成するための基本的な手順と、すぐに使えるプロンプト事例をご紹介しました。

これだけでも、あなたの毎日の情報収集は格段に効率化されるはずです。しかし、Manusの真価は、ここからさらに発揮されます。

この先の有料エリアでは、

- **プロンプト一つで、調査からリッチなカルーセルメッセージの送信までを完結させる方法**
- **ビジネスや学習を劇的に加速させる、10個の実践的な自動化タスク事例**
- **一度設定したら二度と手放せなくなる、AI情報収集を極めるための「メタプロンプト」完全版**

など、あなたのBotを単なる情報収集ツールから、ビジネスや学習における強力な「パートナー」へと進化させるための、より高度で具体的なテクニックを余すところなく解説します。

もしあなたが、

- **他の誰よりも早く、質の高い情報をキャッチアップしたい**
- **コンテンツ制作や情報発信の手間を劇的に削減したい**
- **AIを本当の意味で「使いこなし」、ライバルに差をつけたい**

と本気で考えているなら、この先のコンテンツは価値ある内容だと確信しています。

あなたのAI活用レベルを、もう一段階上へと引き上げる準備はよろしいでしょうか？

一緒に楽しんで行きましょう！

  

**🔗** [**有料エリアで作成できるLINE配信形式の紹介ページ**](https://note.com/preview/nb6451865c076?prev_access_key=fb43eef001f1c80096f2e88222e9cd40)

![Manus_LINE_067.png.webp](https://storage.jabba.cloud/nj5rg1q8lxgr2hrt9eof0610uwag) ※情報の取得方法からリッチなデザインでの配信までをセットにしたプロンプトを紹介します

  

## 📝 発行者

📝 [**テツメモ｜tetumemo（Xアカウント）**](https://twitter.com/tetumemo)

📝 [**テツメモ｜tetumemo（Xのハイライト）**](https://x.com/tetumemo/highlights)

**📝** [**テツメモ｜tetumemo（リンク集）**](https://lit.link/tetumemo)

**🎤** [**Spotify：AI QUEST（今日から始めるAI生活）**](https://open.spotify.com/show/6k8BkUSo2UgnWJSXwtWL92)

**🎤** [**Apple Podcasts**](https://podcasts.apple.com/jp/podcast/ai%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88-%E4%BB%8A%E6%97%A5%E3%81%8B%E3%82%89%E5%A7%8B%E3%82%81%E3%82%8Bai%E7%94%9F%E6%B4%BB/id1811798055) [**：AI QUEST（今日から始めるAI生活）**](https://)

**📹️** [**YouTube：AI QUEST（今日から始めるAI生活）**](https://www.youtube.com/playlist?list=PL3heyLk12PWGg-c9iw0tFzliV5LjV3hiQ)  
**📝** [**noteでも、たまにAIなどの記事を書いています。**](https://note.com/tetumemo)

## 🎟️お得な招待コード

💡 [**Manus（1,000クレジットが獲得できる限定招待コード）**](https://manus.im/redeem?c=njexode)

💡 [**AIエージェント「Felo」（月額100円引きの招待コード）**](https://felo.ai/?invite=R7y9Kzjpd1kk0)

💡 [**Perplexity Pro**](https://perplexity.ai/pro?referral_code=RZJUP5FH) **（初月10ドルの招待コード）**

💡 [**Genspark**](https://www.genspark.ai/?utm_source=tetumemo)

**💡** [**LilysAI（7日間有料プランが使える招待コード）**](https://lilys.ai/?code=4BE1FB25)

**💡** [**YouWare（アプリを作ってUPして稼ぐ新しい仕組み）**](https://www.youware.com/?via=tetumemo)

**💡** [**リアルタイム翻訳「Felo字幕」（15分無料で試せる招待コード）**](https://subtitles.felo.me/activity-invite?code=R7y9Kzjpd1kk0)

コメントするにはログインが必要です

ここから先は有料コンテンツです

この続き：6,610文字 / 画像31枚

有料購読を開始する

980 円/月

購読を開始すると有料記事が 閲覧できるようになります。バックナンバーは別途購入が必要です。

※ 価格はすべて税込です

11

i

y

c

r

m

11