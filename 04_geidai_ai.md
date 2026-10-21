---
marp: true
theme: tadokoro
paginate: true
---

# 何を渡して描かせるか<br>画像生成AIの50年
東京藝術大学芸術情報センター
田所 淳

---

## 今日の内容

- 前回の振り返り
  - ボタンの奥だけで書かれた文章、「使いこなす」とは
- 「AIが描いた絵」の歴史
  - ハロルド・コーエン「AARON」(1973-) から現在まで
- 技術の進化: ルールから学習へ
  - AARON → 画風変換 → GAN → 拡散モデル → 対話で描く
- 現在の主要な画像生成AIサービス
- まとめ: 何を渡して描かせるか
- 実習: 生成自画像 - カメラには写らない本当の私

---

<!-- _class: bigtxt -->

# 前回の振り返り

---

## ボタンの奥だけで書かれた文章

- 同じテーマで2つの文章を書き、どちらがAIかを当て合った
  - 文章1: AI補完なしで書く / 文章2: AI補完だけで書く
- 文章2で人間が入力したのは、**書き出しだけ**
  - 構想する「手前」の仕事も、吟味して手を加える「向こう」の仕事もほとんどない
  - いわば **ボタンの奥だけで書かれた文章**
- **使いこなす = AIの提案を受け入れる・書き換える・断るを、自分で選べること**
  - 次週までの課題で、AIの文章を自分の作品に仕上げた

---

## 今日の問い: 何を渡して描かせるか

![height:300](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-1_button_zones.svg)

- AIに絵を描かせるとき、人間はボタンの手前で **何を渡している** のか?
- 50年の歴史を、人間が渡してきたものに注目してたどる
  - ルール → 画像 → データ → 言葉 → 対話
- 渡すものが変わるたびに、「描いたのは誰か」への答えも変わってきた

---

<!-- _class: bigtxt -->

# 「AIが描いた絵」の歴史

---

## ハロルド・コーエン「AARON」(1973-)

- ハロルド・コーエン (Harold Cohen, 1928-2016)
  - 1960年代のイギリスを代表する画家の一人
  - 1966年、ヴェネチア・ビエンナーレのイギリス館の代表作家に
- 1968年、カリフォルニア大学サンディエゴ校へ
  - コンピュータに絵を描かせる研究を始める
- 1970年代前半にプログラムを **「AARON」** と名づけ、スタンフォード大学の人工知能研究所で開発
  - 絵を描くための **最も初期のAIプログラム** とされる

<!-- _footer: '[Whitney Museum of American Art「Harold Cohen: AARON」](https://whitney.org/exhibitions/harold-cohen-aaron) / [AARON (Wikipedia)](https://en.wikipedia.org/wiki/AARON)' -->

---

## AARON: ルールで描く

- データから学習するAIでは **ない**
  - 線の引き方、形の閉じ方、人物や植物の配置など
  - **コーエン自身の描くための知識を、ルールとしてプログラムに書き込んだ**
- プロッターや描画ロボットで、抽象的な線画から人物や植物へ
  - 筆で色を塗る機械も自作
- 2016年に亡くなるまで、40年以上にわたって改良を続けた
- コーエンは AARON との制作を **共同作業 (コラボレーション)** と考えていた
- 2024年、ホイットニー美術館で展覧会「Harold Cohen: AARON」
  - 再現されたプロッターが、展示室で実際に絵を描いた

<!-- _footer: '作品の画像は [Whitney Museum of American Art「Harold Cohen: AARON」](https://whitney.org/exhibitions/harold-cohen-aaron) で見られる' -->

---

## Google「DeepDream」(2015)

![bg right:35% contain](https://upload.wikimedia.org/wikipedia/commons/d/d0/%22Mona_Lisa%22_with_DeepDream_effect_using_VGG16_network_trained_on_ImageNet.jpg)

- 2015年6月、Google の研究者たちが発表
- 画像認識のニューラルネットワークが、画像のなかに「見ている」ものを **逆に強調して描き出す**
  - 雲や風景から、犬の顔や目が次々と湧き出す
- 描き出されたのは、学習した大量の写真の **記憶** のようなもの
- インターネットで大流行し、多くの人が初めて「AIが描いた絵」を目にした

<!-- _footer: '画像出典: [P.J. Finlay「"Mona Lisa" with DeepDream effect」](https://commons.wikimedia.org/wiki/File:%22Mona_Lisa%22_with_DeepDream_effect_using_VGG16_network_trained_on_ImageNet.jpg) (CC0) / [Google Research Blog「Inceptionism」](https://research.google/blog/inceptionism-going-deeper-into-neural-networks/)' -->

---

## Obvious「Edmond de Belamy」(2018)

![bg right:40% contain](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Edmond_de_Belamy.png/1280px-Edmond_de_Belamy.png)

- 2018年10月、クリスティーズ (ニューヨーク) で **43万2500ドル** で落札
  - 予想落札価格 (7000〜1万ドル) の40倍以上
- パリのアート集団 **Obvious** の作品
- 14〜20世紀の肖像画 **1万5000点** を GAN に学習させて生成
- AIによる作品が大手オークションハウスで競売にかけられたのは初めてと話題に

<!-- _footer: '画像出典: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Edmond_de_Belamy.png) (Public domain) / [Christie''s の解説記事](https://www.christies.com/features/A-collaboration-between-two-artists-one-human-one-a-machine-9332-1.aspx)' -->

---

## 署名は数式: 描いたのは誰か?

![bg right:40% contain](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Edmond_de_Belamy.png/1280px-Edmond_de_Belamy.png)

- 右下には、画家のサインの代わりに **GAN の学習に使われる数式**
  - まるでAI自身が作者であるかのような演出
- 実際には、当時19歳の Robbie Barrat が公開していたコードを土台にしていた
- 作品を生んだのは?
  - Obvious? Barrat? それとも GAN?
- この落札をきっかけに、**「描いたのは誰か」** が広く議論されるように

<!-- _footer: '画像出典: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Edmond_de_Belamy.png) (Public domain)' -->

---

## Anna Ridler「Mosaic Virus」(2018-2019)

![bg right:35% contain](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d1/Mosaic_Virus%2C_Anna_Ridler%2C_2019._%2849845627646%29.jpg/1280px-Mosaic_Virus%2C_Anna_Ridler%2C_2019._%2849845627646%29.jpg)

- GAN で生成した、姿を変え続けるチューリップの映像
  - 花びらの縞模様が **ビットコインの価格** に連動
  - 17世紀のチューリップ投機と、暗号資産の投機を重ねる
- 学習データは **自作**
  - 約3か月かけて **約1万本を自分で撮影し、手作業でラベル付け**
  - データセット自体も「Myriad (Tulips)」(2018) という作品に
- **データを作る段階** に、作家の手仕事がある

<!-- _footer: '画像出典: [art_inthecity (Wikimedia Commons)](https://commons.wikimedia.org/wiki/File:Mosaic_Virus,_Anna_Ridler,_2019._%2849845627646%29.jpg) (CC BY 2.0) / [Anna Ridler「Mosaic Virus」](https://annaridler.com/mosaic-virus)' -->

---

## Refik Anadol「Unsupervised」(2022-2023)

![height:230](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7f/Unsupervised_by_Refik_Anadol.jpg/1280px-Unsupervised_by_Refik_Anadol.jpg)

- 2022年11月から約1年間、ニューヨーク近代美術館 (MoMA) のロビーで展示
- MoMA の所蔵作品のデータを学習させ、200年以上の近代美術の歴史を **絶えず変化する映像として「夢見させる」**
  - 展示室の光、人の動き、外の天気も映像に影響
- のちに、生成AIを使った作品として初めて MoMA が所蔵。一方で「美化されたラバランプ」との酷評も → **賛否両論**

<!-- _footer: '画像出典: [Refik Anadol (Wikimedia Commons)](https://commons.wikimedia.org/wiki/File:Unsupervised_by_Refik_Anadol.jpg) (CC BY-SA 4.0) / [MoMA「Refik Anadol: Unsupervised」](https://www.moma.org/calendar/exhibitions/5535) / [NPR (2026)](https://www.npr.org/2026/07/29/nx-s1-5894941/ai-art-dataland-refik-anadol)' -->

---

## 誰でも言葉で描ける時代へ (2022-)

![bg right:35% contain](https://upload.wikimedia.org/wikipedia/commons/d/d3/A_depiction_of_an_astronaut_riding_a_horse_2022-08-28.png)

- 2022年、画像生成AIが一気に広まる
  - 4月 **DALL·E 2** / 7月 **Midjourney** / 8月 **Stable Diffusion**
- 言葉 (プロンプト) を入力するだけで、誰でも数秒で画像を生成
- Stable Diffusion はモデルが公開され、家庭のパソコンでも動く
- 「馬に乗る宇宙飛行士」= 当時のデモの定番
  - ありえない組み合わせを、もっともらしい写真として描く
- 同じ年、Jason Allen の作品が美術コンテストで最優秀賞 (第2回で紹介)

<!-- _footer: '画像出典: Stable Diffusion で生成, [Asanagi (Wikimedia Commons)](https://commons.wikimedia.org/wiki/File:A_depiction_of_an_astronaut_riding_a_horse_2022-08-28.png) (Public domain)' -->

---

## 対話で描く時代へ (2025-)

- 2025年3月、ChatGPT に新しい画像生成機能
  - 言語モデルの GPT-4o そのものが画像を生成する
  - 「ジブリ風にして」の画像が SNS にあふれ、画風の模倣をめぐる議論も
- 2025年8月、Google の **Nano Banana** (Gemini 2.5 Flash Image)
  - 人物の特徴を保ったまま、言葉で何度でも修正できる
- 2026年も新しいモデルが続々
  - ChatGPT Images 2.0 (4月) / 2.5 (9月)、Nano Banana 2 (2月) / 2.1 (10月)
  - 日本語の文字を正確に描く、ウェブで調べた情報を図解する
- 一度で出力する道具から、**言葉で指示し、対話しながら直していく道具** へ

---

## Herndon & Dryhurst「xhairymutantx」(2024)

- 2024年のホイットニー・ビエンナーレで発表
- Herndon は有名なミュージシャン → 名前を入れるだけで、AIは彼女に似た画像を生成する
  - AIは、すでに彼女の姿を学習していた
- 体の形をゆがめ、赤い髪を大げさにした Herndon の画像で、画像生成モデルを学習
  - どんなプロンプトでも、ゆがめられた「Holly」が返ってくる
  - 生成された画像は美術館のサイトに保存され、**これからのAIの学習データ** になりうる
- **自分の姿を、どこまで自分で決められるのか?** を問う

> 👉 AIに描かせる側ではなく、AIに描かれる側から「AIのなかのわたし」を扱った作品

<!-- _footer: '[Whitney Museum of American Art「Holly Herndon and Mat Dryhurst: xhairymutantx」](https://whitney.org/exhibitions/xhairymutantx)' -->

---

## Christie's「Augmented Intelligence」(2025)

- 2025年2〜3月、AIを使った作品だけを集めた **初めてのオークション** (オンライン)
  - 落札総額は約73万ドル、最高額は Refik Anadol の作品 (27万7200ドル)
  - コーエンが AARON で描いた1987年のドローイングも出品 (1万1340ドル)
- 開催前に、約6500人のアーティストが中止を求める公開書簡に署名
  - 著作権のある作品を許可なく学習したAIで作った作品を売るのは、人間のアーティストの搾取だ
- クリスティーズは予定どおり開催
- Edmond de Belamy から7年: 売買される一方で、**学習データのあり方** が正面から問われる

<!-- _footer: '[Christie''s「Augmented Intelligence」](https://onlineonly.christies.com/s/augmented-intelligence/overview/3837) / [TechCrunch (2025)](https://techcrunch.com/2025/03/06/christies-ai-art-auction-reportedly-exceeds-expectations)' -->

---

## Refik Anadol「DATALAND」(2026)

- 2026年6月、ロサンゼルスに開館した **AIを使ったアートのための美術館**
  - Refik Anadol と Efsun Erkılıç が設立
- 最初の展覧会「Machine Dreams: Rainforest」(2027年1月まで)
  - アーカイブの画像と音、アマゾンで集めた素材を独自のAIモデルに学習させる
  - 来場者の身体のデータに反応して変化する映像も
- Anadol: 人間と機械が半分ずつ担う共同作業
- 批判も: 大手IT企業との近い関係、無料公開のアーカイブを営利の美術館に使うこと

<!-- _footer: '[NPR「Machines are collaborators at this new museum of AI art」(2026)](https://www.npr.org/2026/07/29/nx-s1-5894941/ai-art-dataland-refik-anadol)' -->

---

## 年表 (1) 1973-2019

| 年 | 出来事 |
| :--- | :--- |
| 1973 | ハロルド・コーエンが AARON の開発を本格化 |
| 2014 | Ian Goodfellow らが GAN を発表 |
| 2015 | Google の DeepDream (6月)、ニューラル画風変換の論文 (8月) |
| 2018 | 「Edmond de Belamy」がクリスティーズで落札 (10月)、StyleGAN 発表 (12月) |
| 2019 | 実在しない人物の顔を生成する「This Person Does Not Exist」 |

---

## 年表 (2) 2020-2026

| 年 | 出来事 |
| :--- | :--- |
| 2020 | 拡散モデル (DDPM) の論文 |
| 2021 | OpenAI が DALL·E と CLIP を発表 (1月) |
| 2022 | DALL·E 2、Midjourney、Stable Diffusion。MoMA で「Unsupervised」 |
| 2024 | ホイットニー美術館で「Harold Cohen: AARON」展、「xhairymutantx」 |
| 2025 | Christie's 初のAIアートのオークション、GPT-4o 画像生成、Nano Banana |
| 2026 | ChatGPT Images 2.0 / 2.5、Nano Banana 2 / 2.1、Midjourney V8、DATALAND 開館 |

---

<!-- _class: bigtxt -->

# 技術の進化<br>ルールから学習へ

---

## ルールで描く: AARON (1973-)

- AARON の中身は、コーエンが書いた **ルールの集まり**
- 他人の絵を一枚も学習していない
  - 描ける絵は、コーエンの知識の範囲に限られる
  - その代わり、描かれるもののすべてに、コーエンが考えた描き方の筋道が通っている

> 👉 **人間が渡すもの**: 描き方の知識を書き込んだルール (プログラム)

---

## AARON に書き込まれたルール

- **線**: 全体を計画せず、目標と比べながら少しずつ修正して引く (手で描くように)
- **初期** (1970年代): 「図と地」「内と外」「類似・分割・反復」だけで描く。閉じた形は重ねない
- **子どもの絵に学ぶ** (1980年〜): 骨組みを作り、なぐり描きを囲むように輪郭を付ける
- **ものの知識** (1980年代〜)
  - 「人には頭、胴体、2本の腕、2本の脚」「植物には幹、枝、葉の茂み」
  - 関節の位置と、それぞれが動く範囲。「頭を大きく」などは標準の寸法の表に当てはめる
- **構図**: 空いている場所に置く。人や木の数は「いくつか」、理由がなければランダム
- **描き分け**: 太ももはゆるく、手は細かく

<!-- _footer: '[Cohen「How to Draw Three People in a Botanical Garden」(AAAI-88, 1988)](https://cdn.aaai.org/AAAI/1988/AAAI88-150.pdf)' -->

---

## AARON は一枚ごとの注文を受けない

- AARON には、**一枚ごとの指示を受け取るしくみがない**
  - コーエンが書いたのは、どんな絵にも通じる「描き方の知識」
  - AARON は、知っていることをもとに、毎回ちがう絵を自分で描く
- 調和やバランスといった「美的な原則」は、一切教えていない
  - 作風は、多くの処理が絡み合った結果として生まれる (コーエン)
- 1988年の時点で、C 言語で約1万4000行。1枚を描くのに約1時間

> 👉 現在の画像生成AIは、一枚ごとに言葉で注文する。**「指示」の性質がまったく違う**

<!-- _footer: '[Cohen「How to Draw Three People in a Botanical Garden」(AAAI-88, 1988)](https://cdn.aaai.org/AAAI/1988/AAAI88-150.pdf)' -->

---

## 画風を移す: ニューラル画風変換 (2015-)

![bg right:35% contain](https://upload.wikimedia.org/wikipedia/commons/7/75/Jimmy_Wales_in_France%2C_with_the_style_of_Munch%27s_%22The_Scream%22_applied_using_neural_style_transfer.jpg)

- 2015年8月、Leon Gatys らが発表 ([Gatys et al. 2015](https://arxiv.org/abs/1508.06576))
- ニューラルネットワークの内部で、2つを分けて取り出す
  - **内容**: 何が描かれているか
  - **画風**: 色や筆致のくせ
- 写真の内容を保ったまま、別の絵の画風を当てはめる
  - 右は、人物写真にムンク「叫び」の画風を当てはめたもの
- 2016年、スマホアプリ Prisma が世界中で流行

> 👉 **人間が渡すもの**: 2枚の画像 (内容の写真と、画風の絵)

<!-- _footer: '画像出典: [Kira Wales (Wikimedia Commons)](https://commons.wikimedia.org/wiki/File:Jimmy_Wales_in_France,_with_the_style_of_Munch%27s_%22The_Scream%22_applied_using_neural_style_transfer.jpg) (CC BY-SA 3.0)' -->

---

## 競い合って描く: GAN (2014-)

![bg right:35% contain](https://upload.wikimedia.org/wikipedia/commons/1/1c/This_Person_Does_Not_Exist_example.jpg)

- **GAN (敵対的生成ネットワーク)**: 2014年に Ian Goodfellow らが提案
- 2つのネットワークを競わせる
  - **生成器**: 偽の画像を作る
  - **識別器**: 本物か偽物かを見破る
  - 偽札を作る人と鑑定士のように腕を磨き合い、本物と見分けのつかない画像へ
- 2018年、NVIDIA の **StyleGAN** が実在しない人物の顔を生成
  - 2019年「This Person Does Not Exist」: 開くたびに新しい「存在しない人」

<!-- _footer: '画像出典: StyleGAN2 による生成画像, [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:This_Person_Does_Not_Exist_example.jpg) (Public domain) / [Goodfellow et al. 2014](https://arxiv.org/abs/1406.2661) / [Karras et al. 2018](https://arxiv.org/abs/1812.04948)' -->

---

## GAN: 作家の仕事はデータへ

- GAN は、学習したデータに似た画像を生み出すのが得意
- 一方で、苦手なことも
  - 顔なら顔、チューリップならチューリップと、**学習したジャンルの外は描けない**
  - **言葉で指示することもできない**
- 作家の仕事の中心は、**何を集めて学習させるか** に移った
  - Edmond de Belamy: 1万5000点の肖像画
  - Mosaic Virus: 自分で撮影した1万本のチューリップ

> 👉 **人間が渡すもの**: 学習させるデータセット

---

## 言葉とつなぐ: CLIP (2021-)

- 2021年1月、OpenAI が **CLIP** を発表 ([Radford et al. 2021](https://arxiv.org/abs/2103.00020))
  - インターネット上の約4億組の画像と説明文から、**画像と言葉の対応関係** を学習
  - 「この画像は、この言葉にどれくらい合っているか」を測れる
- 同時に発表された DALL·E とあわせて、**言葉で画像を指示する** 道が開かれた
- 2021年、CLIP と GAN を組み合わせて言葉から画像を生成する試みが、アーティストや愛好家のあいだで広がる

> 👉 **人間が渡すもの**: 言葉 (プロンプト)

---

## ノイズから描く: 拡散モデル (2020-)

![height:230](https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/X-Y_plot_of_algorithmically-generated_AI_art_of_European-style_castle_in_Japan_demonstrating_DDIM_diffusion_steps.png/1280px-X-Y_plot_of_algorithmically-generated_AI_art_of_European-style_castle_in_Japan_demonstrating_DDIM_diffusion_steps.png)

- 第2回で見たとおり: ノイズを少しずつ取り除き、砂嵐のなかから像を浮かび上がらせる
- 2020年の論文で画質が向上、2021年末の **潜在拡散モデル** が Stable Diffusion のもとに
- GAN と違ってジャンルを問わず、言葉で指示したものなら何でも描こうとする

> 👉 **人間が渡すもの**: 言葉 (プロンプト) と、シード値などの設定

<!-- _footer: '画像出典: [Benlisquare (Wikimedia Commons)](https://commons.wikimedia.org/wiki/File:X-Y_plot_of_algorithmically-generated_AI_art_of_European-style_castle_in_Japan_demonstrating_DDIM_diffusion_steps.png) (CC BY-SA 4.0) / [Ho et al. 2020](https://arxiv.org/abs/2006.11239) / [Rombach et al. 2022](https://arxiv.org/abs/2112.10752) / [Diffusion Explainer](https://poloclub.github.io/diffusion-explainer/)' -->

---

## 対話で描く: 言語モデルとの一体化 (2025-)

- GPT-4o の画像生成について、OpenAI は次のように説明
  - 拡散モデルである DALL·E とは違い、ChatGPT に組み込まれた **自己回帰モデル**
- 自己回帰 = **それまでの並びから、次の要素を順番に予測していく** 方式
  - 第2回・第3回で見た言語モデルの「次の言葉の予測」と同じ考え方
- 画像を生成するしくみが、言語モデルと一体になった
  - 会話の流れを理解し、前の画像を覚えたまま修正に応じる
  - 画像のなかに文字を正確に描く、言語モデルが持つ世界の知識を生かす

> 👉 **人間が渡すもの**: 対話 (言葉、参考にする画像、修正の指示)

<!-- _footer: '[OpenAI「Addendum to GPT-4o System Card: 4o image generation」(2025)](https://cdn.openai.com/11998be9-5319-4302-bfbf-1167e093f1fb/Native_Image_Generation_System_Card.pdf)' -->

---

## 人間はボタンの手前で何を渡してきたか

| 時期 | 方式 | 人間が渡すもの | 主な例 |
| :--- | :--- | :--- | :--- |
| 1973- | ルール | 描き方の知識を書いたルール | AARON |
| 2015- | 画風変換 | 内容の写真と画風の絵 | Prisma |
| 2014- | GAN | 学習させるデータセット | Edmond de Belamy、Mosaic Virus |
| 2021- | CLIP + 拡散モデル | 言葉 (プロンプト) | DALL·E 2、Midjourney、Stable Diffusion |
| 2025- | 言語モデルとの一体化 | 対話 (言葉、画像、修正の指示) | ChatGPT、Gemini |

---

## 渡すものは軽く、AIが抱えるものは重く

- 人間が渡すものは、どんどん **軽く** なった
  - コーエン: 何十年もかけて、描き方の知識をルールに
  - Ridler: 3か月かけて、1万枚の写真を撮影
  - いま: 数秒で書いた言葉だけで、絵が返ってくる
- AIの側が抱えるものは、どんどん **重く** なった
  - AARON が知っていたのは、コーエン一人の知識だけ
  - 現在の画像生成AIは、LAION-5B (約58億組) のような **無数の他人が撮り、描いた画像** から学習
- 渡すものが軽くなるほど、AIは足りない部分を **学習した画像の「平均」で埋める**

---

<!-- _class: bigtxt -->

# 現在の主要な<br>画像生成AIサービス

---

## 主なサービス (2026年10月時点)

| サービス | 主なモデル | 無料での利用 | 特徴 |
| :--- | :--- | :--- | :--- |
| **[ChatGPT](https://chatgpt.com/)** (OpenAI) | ChatGPT Images 2.5 | 可 | 対話で生成・修正、文字の描画 |
| **[Gemini](https://gemini.google.com/)** (Google) | Nano Banana 2 / 2.1 | 可 (2.1 は有料) | 対話で編集、写真の合成 |
| **[Google Flow](https://flow.google.com/)** (Google) | Nano Banana ほか | 可 | 画像と動画をまとめて制作 |
| **[Midjourney](https://www.midjourney.com/)** | V8.2 | 不可 (月額$10〜) | 美的な質感、好みの学習 |
| **[Adobe Firefly](https://firefly.adobe.com/)** | Firefly Image 5 ほか | 一部 (回数制限) | 商用利用への配慮、他社モデルも |
| **[Stable Diffusion](https://stability.ai/stable-image)、[FLUX](https://bfl.ai/)** など | 公開されたモデル | 可 (自分のPC) | 自由にカスタマイズ、要GPU |

> > ⚠️ モデル名や料金、無料の範囲は頻繁に変わる。利用前に公式情報を確認

---

## ChatGPT (OpenAI)

- https://chatgpt.com/
- 会話のなかで「〜の画像を作って」と頼むか、メニューの「画像」から生成
- 2026年9月公開の **ChatGPT Images 2.5**
  - 細部の描写や、部分的な修正の精度が向上
- アップロードした写真の修正、範囲を選んでの描き直し、手描きスケッチからの生成 (スマホアプリ)
- 無料プランでも利用可
  - 生成前に考えを深める「思考 (thinking)」モードは有料プラン向け

<!-- _footer: '[OpenAI Help Center「Images in ChatGPT」](https://help.openai.com/en/articles/11084440-chatgpt-images)' -->

---

## Gemini (Google)

- https://gemini.google.com/
- ツールメニューから画像の作成 (🍌) を選んで生成
- 無料の **Nano Banana 2** と、有料プランで使える最上位の **Nano Banana 2.1** (2026年10月)
  - 学割プラン (Google AI Plus) で 2.1 を使えるかは、Gemini の画面で確認
- 人物の特徴を保ったままの編集、複数の写真の合成が得意
- 画像生成は **18歳以上** が対象
- 生成した画像には、AIで作られたことを示す電子透かし (SynthID) が入る

<!-- _footer: '[Gemini「Nano Banana 2」](https://gemini.google/jp/overview/image-generation/) / [Google Gemini 学割プラン](https://gemini.google/jp/students/?hl=ja)' -->

---

## Google Flow (Google)

- https://flow.google.com/
- 画像生成の Nano Banana と、動画生成の Veo などを、**一つのプロジェクトのなかで使える制作スタジオ**
- 画像は、標準で無料の **Nano Banana 2 Lite** で生成・編集 (Nano Banana 2.1、Pro にも切り替え可)
- 「エージェント」に、「ライティングを変えたバリエーションを20枚」のように頼める
- 「履歴」パネルに、以前のバージョンと生成に使ったプロンプトが残る → 制作の記録に便利
- 無料でも1日50クレジット (動画の生成などに使う)。**18歳以上** が対象、英語のプロンプト推奨

> > ⚠️ 自分の見た目と声にそっくりな「アバター」(`@me`) も作れるが、顔と声を記録することになる。顔や声は大切な個人情報なので、使うかどうかは慎重に

<!-- _footer: '[Google Flow ヘルプ「画像を作成、編集する」](https://support.google.com/flow/answer/16729550?hl=ja) / [「クレジットを管理する」](https://support.google.com/flow/answer/16526234?hl=ja) / [「アバターを作成、使用する」](https://support.google.com/flow/answer/17102997?hl=ja)' -->

---

## Midjourney

- https://www.midjourney.com/
- 絵画的で美しい質感に定評
- 現在のデフォルトは、2026年7月公開の **V8.2**
- 生成した画像を評価していくと、自分の好みを学習した「パーソナライズ」が使える
- Web ブラウザか Discord で利用
- **無料プランはなし** (月額$10の Basic プランから)

> > ⚠️ 画像を非公開にする「Stealth Mode」は Pro プラン以上のみ。それ以外のプランでは、生成した画像がほかの利用者からも見える

<!-- _footer: '[Midjourney Docs「Version」](https://docs.midjourney.com/hc/en-us/articles/32199405667853-Version) / [Midjourney Docs「Comparing Midjourney Plans」](https://docs.midjourney.com/hc/en-us/articles/27870484040333-Comparing-Midjourney-Plans)' -->

---

## Adobe Firefly

- https://firefly.adobe.com/
- Adobe 独自のモデル **Firefly Image 5** に加えて、他社のモデルも一つの画面で切り替えて使える
  - OpenAI、Google、Black Forest Labs など
- Adobe 独自のモデルは、Adobe Stock など **利用の許諾を得た画像** で学習
  - 商用利用への配慮を打ち出している
- Photoshop の「生成塗りつぶし」など、Creative Cloud のアプリと連携
- 無料プランでは、使えるモデルや生成回数が限られる

---

## オープンなモデル: Stable Diffusion、FLUX など

- モデルそのものが公開されていて、**自分のパソコンで動かせる**
  - Stability AI の **Stable Diffusion**
  - その開発者たちが設立した Black Forest Labs の **FLUX** など
- [ComfyUI](https://www.comfy.org/) などのツールで、自由にカスタマイズ
  - 生成の手順を部品のように組み合わせる
  - 追加学習したモデルで、特定の画風を加える
- 画像やプロンプトが外部に送られない
- ただし、**高性能なGPU** と、ある程度の技術的な知識が必要

> 💡 そのほか、ByteDance の Seedream、文字の描画に強い Ideogram など

---

## サービスを選ぶときに確認したいこと

- **学習への利用**
  - 入力した文章や画像が、モデルの改善に使われるか。オフにできるか
- **公開範囲**
  - 生成した画像が、ほかの利用者に公開されないか
- **透かしと来歴**
  - AIで作られたことを示す情報 (SynthID、C2PA など) が埋め込まれるか
- **年齢制限と利用規約**
  - 利用できる年齢や、禁止されている使い方
- **商用利用の条件**
  - 作品として発表したり、販売したりできるか

---

<!-- _class: bigtxt -->

# まとめ

---

## 何を渡して描かせるか

- AIに描かせるために人間が渡すものは、時代とともに軽くなった
  - ルール → 画像 → データ → 言葉 → 対話
- 反対に、AIの側は無数の他人の画像を抱え込むようになった
- それでも、「描いたのは誰か」の答えを左右するのは **ボタンを押す前と後で、人間が何をしたか**
  - コーエンのルール作り、Ridler の撮影、Allen のプロンプトの書き直し

---

## 「誰かの絵」から自分の作品へ

![bg right:42% contain](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig00-1_prompt_cycle.svg)

- 言葉だけを渡して生成すると、AIは伝えきれなかった部分を学習した画像の平均で埋める
  - そこにあるのは、ありそうな **「誰かの絵」**
- 自分の作品にしていくのは、ボタンの手前と向こうの仕事
  - 何を渡し、何を選び、どこに手を加えるか
- 前回の「使いこなす」は、絵の場合にも当てはまる

---

<!-- _class: bigtxt -->

![bg right:50%](https://raw.githubusercontent.com/tado/geidai-ai/main/img/04_aigen_portrate03.jpg)

# 実習: 生成自画像<br>カメラには写らない<br>本当の私

---

## 生成自画像 - カメラには写らない本当の私

- カメラは「見た目」を正確に写す
  - でも、何を大事にし、何にこだわり、何に迷い、どんな記憶を抱えているかは写らない
- 画像生成AIで、**カメラには写らない「本当の私」** を表現する
  - 言葉だけ? 自分で描いた絵や持ち物の写真も? **AIに何を渡して描かせるか** を考える

### 条件

- **サービスは自由**: 今日紹介した画像生成AIから選ぶ (ChatGPT や Gemini の無料プランで十分)
- **自分の写真は使わない**: 自分の写真はアップロードしない
  - それ以外の画像 (自分で描いた絵、持ち物や風景の写真など) はアップロードしてOK
- **表現は自由**: 写実的に、デフォルメして、抽象的に。人の姿がなくてもよい
- **考察を書く**: 使った画像生成AIサービスと、どのようなプロンプトを用いたのか

---

## 参考文献 (1)

- [Mordvintsev, A., Olah, C., and Tyka, M. "Inceptionism: Going Deeper into Neural Networks." Google Research Blog.](https://research.google/blog/inceptionism-going-deeper-into-neural-networks/) 2015.
- [Gatys, L. A., Ecker, A. S., and Bethge, M. "A Neural Algorithm of Artistic Style." arXiv:1508.06576.](https://arxiv.org/abs/1508.06576) 2015.
- [Goodfellow, I. et al. "Generative Adversarial Networks." arXiv:1406.2661.](https://arxiv.org/abs/1406.2661) 2014.
- [Karras, T., Laine, S., and Aila, T. "A Style-Based Generator Architecture for Generative Adversarial Networks." arXiv:1812.04948.](https://arxiv.org/abs/1812.04948) 2018.
- [Ho, J., Jain, A., and Abbeel, P. "Denoising Diffusion Probabilistic Models." arXiv:2006.11239.](https://arxiv.org/abs/2006.11239) 2020.
- [Radford, A. et al. "Learning Transferable Visual Models From Natural Language Supervision." arXiv:2103.00020.](https://arxiv.org/abs/2103.00020) 2021.

---

## 参考文献 (2)

- [Cohen, H. "How to Draw Three People in a Botanical Garden." Proceedings of AAAI-88.](https://cdn.aaai.org/AAAI/1988/AAAI88-150.pdf) 1988.
- [Rombach, R. et al. "High-Resolution Image Synthesis with Latent Diffusion Models." arXiv:2112.10752.](https://arxiv.org/abs/2112.10752) 2022.
- [OpenAI. "Addendum to GPT-4o System Card: 4o image generation."](https://cdn.openai.com/11998be9-5319-4302-bfbf-1167e093f1fb/Native_Image_Generation_System_Card.pdf) 2025.
- [Whitney Museum of American Art. "Harold Cohen: AARON."](https://whitney.org/exhibitions/harold-cohen-aaron) 2024.
- [Greenberger, A.「『絵を描くコンピュータ』から『ディープフェイク作品』まで、AIアートの歴史を知るための25作品」ARTnews JAPAN.](https://artnewsjapan.com/article/2695) 2024.
- [白井暁彦「画像生成AIの誕生と変遷(2)画像生成技術の歴史年表」note.](https://note.com/o_ob/n/n971483495ef3) 2024.
