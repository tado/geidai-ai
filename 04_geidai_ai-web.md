![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Edmond_de_Belamy.png/1280px-Edmond_de_Belamy.png)

<small>画像出典: Obvious「Edmond de Belamy」(2018), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Edmond_de_Belamy.png) (Public domain)</small>

今回は「AIと描く - 描いたのは誰か」というテーマで、画像生成AIを取り上げます。

前回は、GitHub Copilot の補完を使い、AIが予測した言葉だけで文章を書きました。人間が入力したのは書き出しだけで、返ってきた言葉を選ぶことさえしない「ボタンの奥だけで書かれた文章」です。今回は、言葉から絵へと移ります。

まず、1973年に始まるハロルド・コーエンの「AARON」から現在の画像生成AIまで、「AIが描いた絵」の歴史を振り返ります。続いて、ルールで描く AARON から、画風変換、GAN、拡散モデルへと進んできた技術の変化を、「人間はボタンの手前で何を渡してきたか」という視点で整理します。現在の主要な画像生成AIのサービスを紹介したら、実習「生成AI自画像」で、AIを使って自分の自画像を描きます。最後に、次週までの課題について説明して終了です。

## スライド資料

* [スライド資料 (PDF)](https://drive.google.com/file/d/1wXzPnaetVx2XXyCwpacXOjv_vRCV1RGf/view)

## 前回の振り返り

### ボタンの奥だけで書かれた文章

前回の実習では、同じテーマで「AI補完なしで書いた文章」と「AI補完だけで書いた文章」を作り、どちらがAIの文章かを当て合いました。AI補完だけの文章で人間が入力したのは、書き出しの言葉だけです。構想する「手前」の仕事も、吟味して手を加える「向こう」の仕事もほとんどない、いわば **ボタンの奥だけで書かれた文章** でした。

そのうえで、AIの提案を **受け入れるか、書き換えるか、断るかを、自分で選べること** を「使いこなす」と考えました。次週までの課題では、AIの文章を出発点に、その選択を自分で行って作品に仕上げています。

### 今日の問い: 描いたのは誰か

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-1_button_zones.svg)

文章の場合、AIが選んだ言葉と人間が選んだ言葉は、ある程度まで見分けることができました。では、絵の場合はどうでしょうか。AIが生成した画像を前にして「この絵を描いたのは誰か」と問われたら、何と答えればよいでしょうか。

今日は、この問いを手がかりに、50年におよぶ「AIが描いた絵」の歴史をたどります。注目するのは、**人間がボタンの手前で何を渡してきたか** です。AIに描かせるために人間が用意するものは、描き方のルールから始まり、画像、学習データ、言葉、対話へと移ってきました。そのたびに、「描いたのは誰か」という問いへの答えも変わっています。

## 「AIが描いた絵」の歴史

### ハロルド・コーエン「AARON」(1973-)

ハロルド・コーエン (Harold Cohen, 1928-2016) は、1960年代のイギリスを代表する画家の一人でした。1966年には、ヴェネチア・ビエンナーレのイギリス館の代表作家にも選ばれています。しかし1968年にカリフォルニア大学サンディエゴ校に移ると、コーエンはコンピュータに絵を描かせる研究に取り組み始めました。1970年代前半には、このプログラムを **「AARON」** と名づけ、スタンフォード大学の人工知能研究所で開発を進めます。AARON は、絵を描くための最も初期のAIプログラムとされています。

AARON は、データから学習するAIではありません。線をどう引くか、形をどう閉じるか、人物や植物をどう配置するかといった、**コーエン自身の描くための知識を、ルールとしてプログラムに書き込んだ** ものです (具体的な中身は、後の「技術の進化」で紹介します)。初期の AARON は、プロッターや紙の上を動き回る描画ロボットを使って、抽象的な線画を描きました。やがて人物や植物を描くようになり、さらにコーエンは、筆で色を塗る機械も自作しています。コーエンは2016年に亡くなるまで、40年以上にわたって AARON の改良を続けました。

コーエンは、AARON との制作を **共同作業 (コラボレーション)** だと考えていました。2024年には、ニューヨークのホイットニー美術館で展覧会「Harold Cohen: AARON」が開かれ、再現されたプロッターが展示室で実際に絵を描く様子が公開されました。展覧会の解説は、DALL-E や Midjourney、Stable Diffusion が広まった今こそ、AARON が重要な歴史的視点を与えてくれると述べています。作品の画像は、下のリンクから見ることができます。

* [Whitney Museum of American Art「Harold Cohen: AARON」(2024)](https://whitney.org/exhibitions/harold-cohen-aaron)
* [AARON (Wikipedia)](https://en.wikipedia.org/wiki/AARON)

### Google「DeepDream」(2015)

![](https://upload.wikimedia.org/wikipedia/commons/d/d0/%22Mona_Lisa%22_with_DeepDream_effect_using_VGG16_network_trained_on_ImageNet.jpg)

<small>画像出典: P.J. Finlay「"Mona Lisa" with DeepDream effect」(2021), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:%22Mona_Lisa%22_with_DeepDream_effect_using_VGG16_network_trained_on_ImageNet.jpg) (CC0)</small>

2015年6月、Google の研究者たちは、画像認識のためのニューラルネットワークが画像のなかに「見ている」ものを、逆に強調して描き出す手法を発表しました。のちに **DeepDream** と呼ばれるこの手法で画像を加工すると、雲や風景のなかから、犬の顔や目、建物のような模様が次々と湧き出してきます。

DeepDream が描き出したのは、ネットワークが学習した大量の写真の **記憶** のようなものでした。学習に使われた写真には、さまざまな犬種の犬が数多く含まれていたため、どんな画像からも犬の姿が浮かび上がってきます。そのサイケデリックで不気味な画像はインターネットで大流行し、多くの人が初めて「AIが描いた絵」を目にするきっかけとなりました。

* [Google Research Blog「Inceptionism: Going Deeper into Neural Networks」(2015)](https://research.google/blog/inceptionism-going-deeper-into-neural-networks/)

### Obvious「Edmond de Belamy」(2018)

![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Edmond_de_Belamy.png/1280px-Edmond_de_Belamy.png)

<small>画像出典: Obvious「Edmond de Belamy」(2018), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Edmond_de_Belamy.png) (Public domain)</small>

2018年10月、ニューヨークのクリスティーズのオークションで、1枚の肖像画が **43万2500ドル** で落札されました。予想落札価格 (7000〜1万ドル) の40倍以上です。パリのアート集団 **Obvious** による「Edmond de Belamy」で、14世紀から20世紀までの肖像画 **1万5000点** を GAN (後述) に学習させて生成した作品です。AIによる作品が大手オークションハウスで競売にかけられたのは、これが初めてだと話題になりました。

画面の右下には、画家のサインの代わりに、GAN の学習に使われる **数式** が記されています。まるでAI自身が作者であるかのような演出です。しかし、Obvious が使ったプログラムは、当時19歳だった Robbie Barrat がインターネットで公開していたコードを土台にしたものでした。作品を生んだのは Obvious なのか、Barrat なのか、それとも GAN なのか。この高額での落札をきっかけに、**「描いたのは誰か」** という問いが広く議論されるようになりました。

* [Christie's の解説記事 (2018)](https://www.christies.com/features/A-collaboration-between-two-artists-one-human-one-a-machine-9332-1.aspx)

### Anna Ridler「Mosaic Virus」(2018-2019)

![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d1/Mosaic_Virus%2C_Anna_Ridler%2C_2019._%2849845627646%29.jpg/1280px-Mosaic_Virus%2C_Anna_Ridler%2C_2019._%2849845627646%29.jpg)

<small>画像出典: Anna Ridler「Mosaic Virus」の展示で並べられた、手書きのラベル付きのチューリップの写真 (2020年、モントリオール), 撮影: art_inthecity, [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Mosaic_Virus,_Anna_Ridler,_2019._%2849845627646%29.jpg) (CC BY 2.0)</small>

イギリスのアーティスト Anna Ridler は、GAN を使って、刻々と姿を変えるチューリップの映像作品「Mosaic Virus」を制作しました。花びらの縞模様は、ビットコインの価格に連動して変化します。作品名の「モザイク・ウイルス」は、17世紀のオランダでチューリップの花びらに縞模様を生み、その価値をつり上げたウイルスの名前です。チューリップの投機ブームと、現代の暗号資産の投機が重ね合わされています。

注目したいのは、その学習データです。Ridler は、チューリップの季節の約3か月をかけて、**約1万本のチューリップを自分で撮影し、1枚ずつ手作業でラベルを付けて**、学習用のデータセットを作りました。このデータセット自体も「Myriad (Tulips)」(2018) という作品として展示されています。AIが描く前の、データを作る段階そのものに、作家の膨大な手作業が費やされています。

* [Anna Ridler「Mosaic Virus」](https://annaridler.com/mosaic-virus)

### Refik Anadol「Unsupervised」(2022-2023)

![](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7f/Unsupervised_by_Refik_Anadol.jpg/1280px-Unsupervised_by_Refik_Anadol.jpg)

<small>画像出典: Refik Anadol「Unsupervised」(2022), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Unsupervised_by_Refik_Anadol.jpg) (CC BY-SA 4.0)</small>

2022年11月から2023年10月まで、ニューヨーク近代美術館 (MoMA) のロビーで、Refik Anadol の「Unsupervised」が展示されました。MoMA が公開している所蔵作品のデータを機械学習モデルに学習させ、200年以上にわたる近代美術の歴史を、絶えず変化し続ける巨大な映像として「夢見させる」作品です。展示室の光や人の動き、外の天気といった情報も、映像の変化に影響を与えます。

美術館の所蔵品そのものを学習データにした作品が、その美術館のロビーを占めたことは大きな話題となり、評価は賛否両論に分かれました。

* [MoMA「Refik Anadol: Unsupervised」](https://www.moma.org/calendar/exhibitions/5535)

### 誰でも言葉で描ける時代へ (2022-)

![](https://upload.wikimedia.org/wikipedia/commons/d/d3/A_depiction_of_an_astronaut_riding_a_horse_2022-08-28.png)

<small>画像出典: Stable Diffusion で生成 (プロンプト: a photograph of an astronaut riding a horse), Asanagi (2022), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:A_depiction_of_an_astronaut_riding_a_horse_2022-08-28.png) (Public domain)</small>

2022年は、画像生成AIが一気に広まった年です。4月に OpenAI の **DALL·E 2**、7月に **Midjourney** のオープンベータ版、8月に **Stable Diffusion** が公開されました。言葉 (プロンプト) を入力するだけで、誰でも数秒で画像を生成できるようになりました。とくに Stable Diffusion は、プログラムと学習済みのモデルが公開され、家庭のパソコンでも動かせたことから、世界中で急速に利用が広がりました。

上の「馬に乗る宇宙飛行士」は、この時期の画像生成AIのデモでよく使われたプロンプトです。現実にはありえない組み合わせを、もっともらしい写真として描けることが、言葉から画像を生成するAIの力を示していました。同じ2022年の8月には、Midjourney で制作された Jason Allen の作品がコロラド州の美術コンテストで最優秀賞に選ばれ、大きな論争を呼んでいます (第2回で紹介)。

### 対話で描く時代へ (2025-)

2025年3月、OpenAI は ChatGPT に新しい画像生成機能を組み込みました。それまでの DALL·E 3 とは違い、言語モデルの GPT-4o そのものが画像を生成するしくみです。写真をアップロードして「ジブリ風にして」と頼むだけで変換できることから、SNS にはジブリ風の画像があふれ、画風の模倣をめぐる議論も起こりました。同じ年の8月には、Google が **Gemini 2.5 Flash Image** (通称 **Nano Banana**) を公開しました。写真の人物の特徴を保ったまま、「髪を短くして」「背景を夜にして」と、言葉で何度でも修正できます。

2026年に入っても、OpenAI の ChatGPT Images 2.0 (4月) と 2.5 (9月)、Google の Nano Banana 2 (2月) と 2.1 (10月) と、新しいモデルが次々に公開されています。画像のなかに日本語の文字を正確に描く、ウェブで調べた情報をもとに図解するといったことも可能になりました。画像生成AIは、一度で絵を出力する道具から、**言葉で指示し、対話しながら直していく道具** へと変わりつつあります。

### 年表

| 年 | 出来事 |
| :--- | :--- |
| 1973 | ハロルド・コーエンが AARON の開発を本格化 |
| 2014 | Ian Goodfellow らが GAN を発表 |
| 2015 | Google の DeepDream (6月)、ニューラル画風変換の論文 (8月) |
| 2018 | 「Edmond de Belamy」がクリスティーズで落札 (10月)、NVIDIA が StyleGAN を発表 (12月) |
| 2019 | 実在しない人物の顔を生成する「This Person Does Not Exist」が公開 |
| 2020 | 拡散モデル (DDPM) の論文 |
| 2021 | OpenAI が DALL·E と CLIP を発表 (1月) |
| 2022 | DALL·E 2 (4月)、Midjourney (7月)、Stable Diffusion (8月)。MoMA で「Unsupervised」展示 (11月) |
| 2024 | ホイットニー美術館で「Harold Cohen: AARON」展 |
| 2025 | ChatGPT の GPT-4o 画像生成 (3月)、Google の Nano Banana (8月) |
| 2026 | ChatGPT Images 2.0 / 2.5、Nano Banana 2 / 2.1、Midjourney V8 |

## 技術の進化: ルールから学習へ

歴史を、今度は技術の面から見直してみましょう。それぞれの方式で、**人間はボタンの手前で何を渡し、AIは何を描いてきた** のでしょうか。

### ルールで描く: AARON (1973-)

AARON の中身は、コーエンが書いた **ルールの集まり** です。他人の絵を一枚も学習しておらず、描ける絵はコーエンの知識の範囲に限られます。その代わり、描かれるもののすべてに、コーエンが考えた描き方の筋道が通っています。

では、コーエンは AARON に具体的に何を書き込んだのでしょうか。1988年の論文で、コーエン自身が次のような例を挙げています ([Cohen 1988](https://cdn.aaai.org/AAAI/1988/AAAI88-150.pdf))。

* **線の引き方**: 線は最初から全体を計画せず、手で描くときのように、いまの線の状態と目標とを比べながら少しずつ修正して引く。閉じた形は、駐車場をぐるりと回るときに途中の目印を次々に思い浮かべ、その方へ進路を変えながら出発点に戻ってくるようにして描く
* **初期のルール** (1970年代): 外の世界についての知識は持たず、「図と地」「内と外」「類似・分割・反復」といった区別だけで描く。世界中の岩絵にならって、閉じた形どうしは重ねない
* **子どもの絵に学んだ方法** (1980年〜): まず「芯」となる骨組みを作り、子どもがなぐり描きを線で囲むように、その周りに輪郭を描く。動物の骨組みを囲ませてみると、アフリカの岩絵のような絵になった
* **ものについての知識** (1980年代〜): 「人には頭、胴体、2本の腕、2本の脚がある」「植物には幹、枝、葉の茂みがある」。関節がどこにあり、それぞれがどこまで動くか。「頭を大きく」「腕を長く」といった指定は、標準の寸法の表に当てはめて決める
* **構図**: 基本は「空いている場所に置く」。人物や木の数は「いくつか (たとえば0〜4)」とだけ決めておき、とくに理由がなければランダムに選ぶ。消しゴムを使わないので、手前のものから順に描く
* **描き分け**: 太ももは骨組みから離してゆるく、手は骨組みに近づけて細かく描く

一方で、調和やバランスといった「美的な原則」は、AARON には一切教えられていません。コーエンは、AARON の作風を、多くの処理が絡み合った結果として生まれるものであり、そこに自分自身の一貫した判断が映っていると考えていました。

そして何より、AARON には **一枚ごとの指示を受け取るしくみがありません**。コーエンが書いたのは、どんな絵にも通じる描き方の知識であって、「次はこういう絵を描いて」という注文ではありませんでした。AARON は、知っていることをもとに、毎回ちがう絵を自分で描きます (1988年の時点で、プログラムは C 言語で約1万4000行あり、1枚を描くのに約1時間かかっていました)。一枚ごとに言葉で注文する現在の画像生成AIとは、「指示」の性質がまったく違います。

* **人間が渡すもの**: 描き方の知識を書き込んだルール (プログラム)。一枚ごとの指示はない

### 画風を移す: ニューラル画風変換 (2015-)

![](https://upload.wikimedia.org/wikipedia/commons/7/75/Jimmy_Wales_in_France%2C_with_the_style_of_Munch%27s_%22The_Scream%22_applied_using_neural_style_transfer.jpg)

<small>画像出典: Kira Wales「Jimmy Wales in France, with the style of Munch's "The Scream" applied using neural style transfer」(2018), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Jimmy_Wales_in_France,_with_the_style_of_Munch%27s_%22The_Scream%22_applied_using_neural_style_transfer.jpg) (CC BY-SA 3.0)</small>

2015年8月、Leon Gatys らは、写真をゴッホやムンクのような画風で描き直す手法を発表しました ([Gatys et al. 2015](https://arxiv.org/abs/1508.06576))。画像認識のために学習したニューラルネットワークの内部では、**何が描かれているかという「内容」** と、**色や筆致のくせといった「画風」** を、ある程度分けて取り出すことができます。そこで、ある写真の内容を保ったまま、別の絵の画風を当てはめます。上の画像は、人物の写真にムンク「叫び」の画風を当てはめたものです。2016年には、この技術を使ったスマホアプリ Prisma が世界中で流行しました。

* **人間が渡すもの**: 2枚の画像 (内容となる写真と、画風となる絵)

### 競い合って描く: GAN (2014-)

![](https://upload.wikimedia.org/wikipedia/commons/1/1c/This_Person_Does_Not_Exist_example.jpg)

<small>画像出典: StyleGAN2 による生成画像 (This Person Does Not Exist), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:This_Person_Does_Not_Exist_example.jpg) (Public domain)</small>

**GAN (敵対的生成ネットワーク)** は、2014年に Ian Goodfellow らが提案した方式です ([Goodfellow et al. 2014](https://arxiv.org/abs/1406.2661))。GAN では、偽の画像を作る **生成器** と、本物の画像か偽物かを見破る **識別器** という、2つのネットワークを競わせます。偽札を作る人と、それを見破る鑑定士が腕を磨き合うように学習を繰り返すことで、生成器は本物と見分けのつかない画像を作れるようになります。

2018年に NVIDIA が発表した **StyleGAN** は、実在しない人物の顔写真を、本物と見分けがつかないほどの精度で生成しました ([Karras et al. 2018](https://arxiv.org/abs/1812.04948))。2019年に公開された「This Person Does Not Exist」では、ページを開くたびに新しい「存在しない人」の顔が現れます。

GAN は、学習したデータに似た画像を生み出すのが得意です。一方で、顔なら顔、チューリップならチューリップと、学習したジャンルの外にあるものは描けず、言葉で指示することもできません。そのため、Edmond de Belamy や Mosaic Virus のように、作家の仕事の中心は **何を集めて学習させるか** に移りました。

* **人間が渡すもの**: 学習させるデータセット

### 言葉とつなぐ: CLIP (2021-)

2021年1月、OpenAI は **CLIP** を発表しました ([Radford et al. 2021](https://arxiv.org/abs/2103.00020))。インターネット上の約4億組の画像と説明文から、画像と言葉の対応関係を学習したモデルです。CLIP を使うと、「この画像は、この言葉にどれくらい合っているか」を測ることができます。同時に発表された DALL·E とあわせて、**言葉で画像を指示する** 道が開かれました。2021年には、CLIP と GAN を組み合わせて言葉から画像を生成する試みが、アーティストや愛好家のあいだで一気に広がります。

* **人間が渡すもの**: 言葉 (プロンプト)

### ノイズから描く: 拡散モデル (2020-)

![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/X-Y_plot_of_algorithmically-generated_AI_art_of_European-style_castle_in_Japan_demonstrating_DDIM_diffusion_steps.png/1280px-X-Y_plot_of_algorithmically-generated_AI_art_of_European-style_castle_in_Japan_demonstrating_DDIM_diffusion_steps.png)

<small>画像出典: Stable Diffusion v1.5 でノイズが取り除かれていく過程, Benlisquare (2022), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:X-Y_plot_of_algorithmically-generated_AI_art_of_European-style_castle_in_Japan_demonstrating_DDIM_diffusion_steps.png) (CC BY-SA 4.0)</small>

第2回で見たように、**拡散モデル** は、画像に少しずつノイズを加えて砂嵐のような状態にし、その逆 (ノイズを取り除いて元に戻す) 方法を学習します。生成するときは、まったくのノイズから出発し、言葉を手がかりにノイズを少しずつ取り除いていきます。上の画像は、ノイズのなかから城の姿が浮かび上がっていく過程を、ステップごとに並べたものです。

2020年の論文 ([Ho et al. 2020](https://arxiv.org/abs/2006.11239)) で画質が大きく向上し、2021年末には、画像を小さく圧縮した空間で計算する **潜在拡散モデル** が発表されました ([Rombach et al. 2022](https://arxiv.org/abs/2112.10752))。これが Stable Diffusion のもとになり、家庭のパソコンでも画像を生成できるようになります。GAN とは違ってジャンルを問わず、言葉で指示したものなら何でも描こうとする点が、2022年の急速な普及につながりました。

* **人間が渡すもの**: 言葉 (プロンプト) と、シード値などの設定
* [Diffusion Explainer](https://poloclub.github.io/diffusion-explainer/) (第2回で紹介)

### 対話で描く: 言語モデルとの一体化 (2025-)

2025年に ChatGPT に組み込まれた GPT-4o の画像生成について、OpenAI は、拡散モデルである DALL·E とは違い、ChatGPT に組み込まれた **自己回帰モデル** だと説明しています ([OpenAI 2025](https://cdn.openai.com/11998be9-5319-4302-bfbf-1167e093f1fb/Native_Image_Generation_System_Card.pdf))。自己回帰とは、第2回・第3回で見た言語モデルと同じく、**それまでの並びから、次の要素を順番に予測していく** 方式です。画像を生成するしくみが、言葉を生成する言語モデルと一体になりました。

一体になったことで、画像生成AIは会話の流れを理解し、前の画像を覚えたまま「もう少し明るく」といった修正に応じ、画像のなかに文字を正確に描けるようになりました。言語モデルが持つ世界の知識を、画像づくりに生かせるようにもなっています。

* **人間が渡すもの**: 対話 (言葉、参考にする画像、修正の指示)

### 人間はボタンの手前で何を渡してきたか

| 時期 | 方式 | 人間が渡すもの | 主な例 |
| :--- | :--- | :--- | :--- |
| 1973- | ルール | 描き方の知識を書いたルール | AARON |
| 2015- | 画風変換 | 内容の写真と画風の絵 | Prisma |
| 2014- | GAN | 学習させるデータセット | Edmond de Belamy、Mosaic Virus |
| 2021- | CLIP + 拡散モデル | 言葉 (プロンプト) | DALL·E 2、Midjourney、Stable Diffusion |
| 2025- | 言語モデルとの一体化 | 対話 (言葉、画像、修正の指示) | ChatGPT、Gemini |

こうして並べると、人間が渡すものは、どんどん **軽く** なってきたことが分かります。コーエンは何十年もかけて描き方の知識をルールにし、Ridler は3か月かけて1万枚の写真を撮りました。いまは数秒で書いた言葉だけで、絵が返ってきます。

その一方で、AIの側が抱えるものは、どんどん **重く** なりました。AARON が知っていたのは、コーエン一人の知識だけです。現在の画像生成AIは、第2回で見た LAION-5B (約58億組) のような、**無数の他人が撮り、描いた画像** から学習しています。人間が渡すものが軽くなるほど、AIは足りない部分を、学習した膨大な画像の「平均」で埋めることになります。

## 現在の主要な画像生成AIサービス

ここでは、2026年10月時点の主要なサービスを紹介します。モデルの名前や料金、無料で使える範囲は頻繁に変わるので、利用する前に各サービスの公式情報を確認してください。

| サービス | 開発 | 主なモデル | 無料での利用 | 特徴 |
| :--- | :--- | :--- | :--- | :--- |
| [ChatGPT](https://chatgpt.com/) | OpenAI | ChatGPT Images 2.5 | 可 | 対話で生成・修正、文字の描画が得意 |
| [Gemini](https://gemini.google.com/) | Google | Nano Banana 2 / 2.1 | 可 (2.1 は有料プラン) | 対話で編集、写真の合成、高速 |
| [Google Flow](https://flow.google.com/) | Google | Nano Banana 2 Lite / 2.1 / Pro | 可 (Nano Banana 2 Lite は無料) | 画像と動画を一つのプロジェクトで制作、エージェント、編集の履歴 |
| [Midjourney](https://www.midjourney.com/) | Midjourney | V8.2 | 不可 (月額10ドルから) | 美的な質感、好みの学習 |
| [Adobe Firefly](https://firefly.adobe.com/) | Adobe | Firefly Image 5 ほか | 一部 (回数に制限) | 商用利用への配慮、他社のモデルも選べる |
| [Stable Diffusion](https://stability.ai/stable-image)、[FLUX](https://bfl.ai/) など | Stability AI、Black Forest Labs など | 公開されたモデル | 可 (自分のPCで動かす) | 自由にカスタマイズできる、高性能なGPUが必要 |

### ChatGPT (OpenAI)

[ChatGPT](https://chatgpt.com/) の会話のなかで「〜の画像を作って」と頼むか、メニューの「画像」から生成します。2026年9月に公開された **ChatGPT Images 2.5** では、細部の描写や部分的な修正の精度が向上しました。アップロードした写真の修正、範囲を選んでの部分的な描き直し、スマホアプリでの手描きスケッチからの生成もできます。無料プランでも利用できますが、生成前に考えを深める「思考 (thinking)」モードは有料プラン向けです。

* [OpenAI Help Center「Images in ChatGPT」](https://help.openai.com/en/articles/11084440-chatgpt-images)

### Gemini (Google)

[Gemini](https://gemini.google.com/) のツールメニューから画像の作成 (🍌) を選んで生成します。無料で使える **Nano Banana 2** と、Google AI の有料プランで使える最上位の **Nano Banana 2.1** (2026年10月公開) があります。第1回で紹介した学割プラン (Google AI Plus) で Nano Banana 2.1 を使えるかどうかは、Gemini の画面で確認してください。人物の特徴を保ったままの編集や、複数の写真の合成が得意です。画像生成の対象は18歳以上で、生成した画像には、Google のAIで作られたことを示す電子透かし (SynthID) が埋め込まれます。

* [Gemini「Nano Banana 2」](https://gemini.google/jp/overview/image-generation/)
* [Google Gemini 学割プラン](https://gemini.google/jp/students/?hl=ja)

### Google Flow (Google)

[Google Flow](https://flow.google.com/) は、Google の画像生成モデル Nano Banana と、動画生成モデル Veo などを、一つのプロジェクトのなかで使える制作スタジオです。画像の生成と編集には、標準では無料の **Nano Banana 2 Lite** が使われ、Nano Banana 2.1 や Nano Banana Pro に切り替えることもできます。Gemini をもとにした「エージェント」に、「この画像のバリエーションを、ライティングを変えて20枚作って」のように頼むこともできます。画像を編集しても元の画像は失われず、「履歴」パネルに以前のバージョンと、生成に使ったプロンプトが残るので、制作の記録にも役立ちます。生成した画像は、そのまま動画の素材としても使えます。

Google アカウントがあれば無料で使え、サブスクリプションがなくても1日50クレジットが付与されます (動画の生成などに使います)。利用の対象は18歳以上で、Google は英語のプロンプトを推奨しています。自分の見た目と声にそっくりな「アバター」を作り、プロンプトのなかで「@me」と呼び出す機能もあります。ただし、アバターの作成には自分の顔と声を記録することになるので、使う場合は、実習の「顔写真とプライバシー」の注意をよく読んでからにしてください。

* [Google Flow ヘルプ「Google Flow で画像を作成、編集する」](https://support.google.com/flow/answer/16729550?hl=ja)
* [Google Flow ヘルプ「Google Flow クレジットを管理する」](https://support.google.com/flow/answer/16526234?hl=ja)

### Midjourney

[Midjourney](https://www.midjourney.com/) は、絵画的で美しい質感に定評のあるサービスです。現在のデフォルトは、2026年7月に公開された **V8.2** です。生成した画像を評価していくと、自分の好みを学習した「パーソナライズ」が使えます。Web ブラウザか Discord で利用し、無料プランはなく、月額10ドルの Basic プランからです。また、生成した画像を非公開にする「Stealth Mode」は Pro プラン以上でしか使えず、それ以外のプランでは、生成した画像がほかの利用者からも見える状態になります。

* [Midjourney Docs「Version」](https://docs.midjourney.com/hc/en-us/articles/32199405667853-Version)

### Adobe Firefly

[Adobe Firefly](https://firefly.adobe.com/) は、Adobe 独自のモデル **Firefly Image 5** に加えて、OpenAI や Google、Black Forest Labs など他社のモデルも、一つの画面で切り替えて使えるサービスです。Adobe 独自のモデルは、Adobe Stock など利用の許諾を得た画像で学習しており、商用利用への配慮を打ち出しています。Photoshop の「生成塗りつぶし」など、Creative Cloud のアプリとも連携しています。無料プランでは、使えるモデルや生成回数が限られます。

### オープンなモデル: Stable Diffusion、FLUX など

モデルそのものが公開されていて、自分のパソコンで動かせる画像生成AIもあります。Stability AI の Stable Diffusion や、その開発者たちが設立した Black Forest Labs の **FLUX** などです。[ComfyUI](https://www.comfy.org/) のようなツールを使って生成の手順を部品のように組み合わせたり、追加学習したモデルで特定の画風を加えたりと、自由にカスタマイズできます。画像やプロンプトが外部に送られない点も特徴です。ただし、高性能なGPUを積んだパソコンと、ある程度の技術的な知識が必要です。

そのほかにも、ByteDance の Seedream、文字の描画に強い Ideogram など、多くのサービスがあります。

### サービスを選ぶときに確認したいこと

* **学習への利用**: 入力した文章や画像が、モデルの改善に使われるか。オフにできるか
* **公開範囲**: 生成した画像が、ほかの利用者に公開されないか
* **透かしと来歴**: 生成した画像に、AIで作られたことを示す情報 (SynthID や C2PA など) が埋め込まれるか
* **年齢制限と利用規約**: 利用できる年齢や、禁止されている使い方
* **商用利用の条件**: 作品として発表したり、販売したりできるか

## 実習: 生成AI自画像

多くの画家たちが、自画像を描くことで「自分とは何か」を探ってきました。今日は、画像生成AIを使って **自分の自画像** を描きます。

AIは、あなたの顔を知りません。AIに「わたし」を描いてもらうには、何を渡せばよいのでしょうか。顔の特徴でしょうか。それとも、いつも持ち歩いているもの、好きな色、よくいる場所、癖でしょうか。この実習では、まず言葉だけで描いてみて、そこから少しずつ自分に近づけていきます。

| | 描き方 | 人間が渡すもの |
| :--- | :--- | :--- |
| **1枚目** | 言葉だけで描く | 自分を説明する文章 (プロンプト) だけ |
| **完成作** | 自分に近づける | 言葉、参考にする画像、修正の指示など、自由に |

* **サービス**: 上で紹介したサービスから自由に選ぶ (ChatGPT か Gemini の無料プランで十分に取り組める)
* **スタイル**: 写実的、イラスト、油彩、版画など自由

### 準備: 顔写真とプライバシー

自分の顔は、大切な個人情報です。次のことに注意してください。

* 顔写真のアップロードは **必須ではありません**。言葉や、自分で描いた絵だけで進めてもかまいません
* 写真をアップロードする場合は、**自分だけが写った写真** を使う。友人や家族など、ほかの人が写った写真は使わない。ほかの人の顔を生成することもしない
* 入力した内容を学習に使わない設定にしておく
  * ChatGPT: 「設定 > データコントロール > すべての人のためにモデルを改善する」をオフ
  * そのほかのサービスも、同じような設定があるか確認する
* 生成した自画像を、どこまで公開するかは自分で決める

### ステップ1: 言葉だけで描く

1. 使うサービスを選び、新しいチャットを開く
2. 自分の姿を言葉で説明するプロンプトを書いて、画像を生成する。写真や画像は使わない

```text
次の人物の自画像を描いてください。
(ここに、自分の外見や雰囲気を言葉で書く)
```

3. **最初に生成された画像** を、そのまま「1枚目」として保存する (生成し直さない)

1枚目は、自分に似ているでしょうか。言葉で指定しなかった部分、たとえば顔立ちや服装、背景、画風を、AIはどのように埋めたでしょうか。第2回で考えた「平均への引力」は、どこに表れているでしょうか。

### ステップ2: 自分に近づける

1枚目から出発して、自由な方法で自分に近づけていきます。

* プロンプトを書き直す、書き足す
* 「目をもう少し細く」「背景を自分の部屋に」のように、対話で修正を指示する
* 自分で描いた絵や写真を、参考の画像として渡す
* 別のサービスに切り替える

顔立ちだけにこだわる必要はありません。実習の最初に考えた手がかりも試しながら、何があれば「わたし」らしくなるのかを探ってください。第2回で紹介した Allen は、624回もプロンプトを書き直しました。どんな指示をしたか、何回くらい生成したかを、メモに残しておきましょう。

### ステップ3: 1枚を選んで仕上げる

生成した画像のなかから、自画像として **1枚を選びます**。必要なら、画像編集ソフトで手を加えてもかまいません。最後に、作品のタイトルを付けます。

授業の終わりに、1枚目と、その時点での自画像を隣の人と見せ合ってみましょう (見せたくないものは見せなくてかまいません)。仕上げと提出は、次週までの課題で行います。

## まとめ: 描いたのは誰か

今日は、「AIが描いた絵」の50年の歴史をたどりました。AIに描かせるために人間が用意するものは、時代とともに手軽になってきました。反対に、AIの側は、無数の他人が撮り、描いた膨大な画像を抱え込むようになっています。

それでも、コーエンのルール作りや Ridler の撮影、Allen のプロンプトの書き直しが示すように、「描いたのは誰か」という問いへの答えは、ボタンを押す前と後で人間が何をしたかにかかっています。

自画像の1枚目は、言葉だけを渡して生成したものです。AIは、言葉で伝えきれなかった部分を学習した画像の平均で埋めるので、そこに描かれるのは「わたし」というより、ありそうな **「誰か」** です。それを「わたし」に近づけていくのは、何を渡し、何を選び、どこに手を加えるかという、ボタンの手前と向こうの仕事です。前回考えた「使いこなす」ことは、絵の場合にも当てはまります。

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig00-1_prompt_cycle.svg)

## 次週までの課題

### 生成AI自画像を仕上げる

実習の続きとして、生成AI自画像を完成させてください。完成作には、タイトルを付けます。仕上げた自画像には、制作の記録と、制作をふりかえる考察を添えてください。

### 考察

400字程度の考察を書いてください。たとえば、次のようなことを書きます。

* 1枚目は自分に似ていたか。AIは、言葉で伝えなかった部分をどのように埋めたか
* 自分に近づけるために、何を渡し、どんな指示をしたか。うまくいったこと、いかなかったこと
* 「似ている」と感じたのは、顔か、それ以外の何か
* この自画像を描いたのは誰だと思うか (自分、AI、AIが学習した画像の向こうにいる無数の人々…)

### 提出方法

次のような構成のテキストファイルを作ってください。

```text
【タイトル】
(完成作のタイトル)

【使ったサービス】
(例: Gemini (Nano Banana 2))

【1枚目のプロンプト】
(ステップ1で入力したプロンプトを、そのまま貼る)

【制作の記録】
(主な修正の指示、参考にした画像の有無、生成したおおよその回数)

【考察】
(400字程度)
```

* **提出物**: 次の3つのファイル
  * 1枚目の画像
  * 完成作の画像
  * 上のテキストファイル (.txt)。ファイル名は 学籍番号_氏名.txt に変更
* **提出先**: Google Classroom の課題
* **締切**: 次回の授業の前日まで

次回の講評では、名前を伏せて完成作をスクリーンに映し、誰の自画像かを当て合います。映されたくない場合は、課題の「限定公開のコメント」で教員に伝えてください。

## 関連リンク

* [Whitney Museum of American Art「Harold Cohen: AARON」](https://whitney.org/exhibitions/harold-cohen-aaron)
* [MoMA「Refik Anadol: Unsupervised」](https://www.moma.org/calendar/exhibitions/5535)
* [Anna Ridler「Mosaic Virus」](https://annaridler.com/mosaic-virus)
* [This Person Does Not Exist](https://thispersondoesnotexist.com/)
* [Generative Art Timeline](https://timeline.lerandom.art/)
* [Diffusion Explainer](https://poloclub.github.io/diffusion-explainer/)
* [ChatGPT](https://chatgpt.com/)
* [Gemini](https://gemini.google.com/)
* [Google Flow](https://flow.google.com/)
* [Midjourney](https://www.midjourney.com/)
* [Adobe Firefly](https://firefly.adobe.com/)
* [Black Forest Labs (FLUX)](https://bfl.ai/)
* [ComfyUI](https://www.comfy.org/)
* [ARTnews JAPAN「『絵を描くコンピュータ』から『ディープフェイク作品』まで、AIアートの歴史を知るための25作品」](https://artnewsjapan.com/article/2695)
* [白井暁彦「画像生成AIの誕生と変遷(2)画像生成技術の歴史年表」(note)](https://note.com/o_ob/n/n971483495ef3)
* [人工知能と創作 2025「Transformer - ChatGPTへ至る30年の歴史 / 画像生成AI導入」](https://yoppa.org/geidai-ai25/18478.html)
* [人工知能と創作 2025「『AI生成自画像』講評 / 生成芸術の歴史と未来」](https://yoppa.org/geidai-ai25/18524.html)

## 参考文献

* [Mordvintsev, A., Olah, C., and Tyka, M. "Inceptionism: Going Deeper into Neural Networks." Google Research Blog.](https://research.google/blog/inceptionism-going-deeper-into-neural-networks/) 2015.
* [Gatys, L. A., Ecker, A. S., and Bethge, M. "A Neural Algorithm of Artistic Style." arXiv:1508.06576.](https://arxiv.org/abs/1508.06576) 2015.
* [Goodfellow, I. et al. "Generative Adversarial Networks." arXiv:1406.2661.](https://arxiv.org/abs/1406.2661) 2014.
* [Karras, T., Laine, S., and Aila, T. "A Style-Based Generator Architecture for Generative Adversarial Networks." arXiv:1812.04948.](https://arxiv.org/abs/1812.04948) 2018.
* [Ho, J., Jain, A., and Abbeel, P. "Denoising Diffusion Probabilistic Models." arXiv:2006.11239.](https://arxiv.org/abs/2006.11239) 2020.
* [Radford, A. et al. "Learning Transferable Visual Models From Natural Language Supervision." arXiv:2103.00020.](https://arxiv.org/abs/2103.00020) 2021.
* [Cohen, H. "How to Draw Three People in a Botanical Garden." Proceedings of AAAI-88.](https://cdn.aaai.org/AAAI/1988/AAAI88-150.pdf) 1988.
* [Rombach, R. et al. "High-Resolution Image Synthesis with Latent Diffusion Models." arXiv:2112.10752.](https://arxiv.org/abs/2112.10752) 2022.
* [OpenAI. "Addendum to GPT-4o System Card: 4o image generation."](https://cdn.openai.com/11998be9-5319-4302-bfbf-1167e093f1fb/Native_Image_Generation_System_Card.pdf) 2025.
* [Whitney Museum of American Art. "Harold Cohen: AARON."](https://whitney.org/exhibitions/harold-cohen-aaron) 2024.
* [Greenberger, A.「『絵を描くコンピュータ』から『ディープフェイク作品』まで、AIアートの歴史を知るための25作品」ARTnews JAPAN.](https://artnewsjapan.com/article/2695) 2024.
* [白井暁彦「画像生成AIの誕生と変遷(2)画像生成技術の歴史年表」note.](https://note.com/o_ob/n/n971483495ef3) 2024.

