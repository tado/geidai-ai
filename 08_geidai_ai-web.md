---
title: "AIと音楽制作"
date: 2026-11-18T16:50:54+09:00
categories: ["geidai-ai26"]
---

![](https://images.ctfassets.net/jhi4pj6pvhnp/3eG75oywwM54TqW8xABVqI/c6b56fcb9f9d0d5a61ff8af648ab5b52/IMG_0043.JPG?w=1280)

<small>画像出典: 徳井直生 / Qosmo「AI DJ Project - A dialogue between AI and a human」(2016-), [Qosmo](https://qosmo.jp/art/ai-dj-human-dj-b2b)</small>

今回は「AIと音楽制作」というテーマで、AIを使った音楽の制作を取り上げます。

第4回では、画像生成AIの50年をたどりながら、「人間はAIに何を渡して描かせてきたか」を考えました。音楽でも、AIに渡すものは、作曲の規則、声、古い録音、音色、そして言葉へと移り変わってきました。ただし、音楽には絵とは違う面もあります。時間とともに流れること、演奏すること、そして歌声が、その人自身と強く結びついていることです。

まず、ブライアン・イーノの生成音楽から、AIとの共演、声の学習、古い録音の修復、音色の生成、リアルタイムの生成、そして言葉から曲をまるごと作るサービスまで、AIと音楽の関わりの歴史を事例とともにたどります。続いて、現在の主な音楽生成AIサービスを紹介します。

## スライド資料

* [スライド資料 (PDF)](https://drive.google.com/file/d/1m8PwCbGjEXTnrwsOV2rssa6qYehLjgkr/view?usp=sharing)

## AIと音楽の歩み

### 規則から生まれる音楽: ブライアン・イーノ「Reflection」(2017)

[![](https://img.youtube.com/vi/fSofXKGpenQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=fSofXKGpenQ)

<small>画像出典: [Brian Eno - Reflection (Excerpt) [Official Visual] (YouTube)](https://youtu.be/fSofXKGpenQ) (Warp Records)</small>

ブライアン・イーノ (Brian Eno) は、アンビエント・ミュージックの創始者として知られる音楽家です。イーノは、作曲家が一つひとつの音を決めるのではなく、音の素材と規則を用意し、そのしくみに音楽を生み出させる **生成音楽 (Generative Music)** に、長く取り組んできました。

その出発点の一つが、1975年に発表されたアルバム『[**Discreet Music**](https://open.spotify.com/album/7b67MKOwyj7mIcEVnoJSOG)』です。まだ音楽づくりにパソコンが使われていなかった時代に、イーノは、シンセサイザーとテープレコーダーを組み合わせて、**自動的に音楽が生まれ続けるしくみ** を作りました。シンセサイザー (EMS Synthi AKS) に内蔵されたシーケンサーが、長さの違う2つの短いフレーズをくり返し演奏します。その音は、イコライザーとエコーを通して、2台のテープレコーダーに送られます。1台目で録音したテープを2台目で再生し、その音を1台目に戻して重ねて録音するため、フレーズは少し遅れて何度も重なり合い、少しずつ薄れていきます。2つのフレーズは長さが違うので、その重なり方は、同じ形をくり返すことがありません。

イーノがしたのは、このしくみを組み立てて動かすことでした。約30分のタイトル曲は、イーノが訪ねてきた人の相手をしているあいだにも、鳴り続けてできあがっていきました。イーノは、これを「まさに自動の音楽 (automatic music)」だったと振り返っています。アルバムのライナーノーツには、この装置の **図** が載っていて、音だけでなく、音を生み出すしくみそのものが作品の一部として示されています。

![](https://lloydcontextualstudies.wordpress.com/wp-content/uploads/2014/05/eno-discreet-music.jpg)

<small>画像出典: Brian Eno『Discreet Music』(Obscure, 1975) のライナーノーツ。下部が「Operational diagram for "Discreet Music"」。[lloydcontextualstudies](https://lloydcontextualstudies.wordpress.com/wp-content/uploads/2014/05/eno-discreet-music.jpg) 掲載のスキャン</small>

図では、左のシンセサイザー (digital recall system) から出た音が、グラフィック・イコライザー (graphic equalizer)、エコー (echo unit) を通って、右の2台のテープレコーダーに入ります。左のテープレコーダーで録音 (record) したテープは、そのまま右のテープレコーダーで再生 (playback) され、その音が「delay return」の線で左に戻って、新しい音と重ねて録音されます。2台のあいだのテープの長さが、遅れの長さ (delay line) になります。イーノはライナーノーツで、この曲に楽譜があるとすれば、それはこの装置の図だと書いています。

アルバムのB面には、もう一つの生成の試みとして「**パッヘルベルのカノンによる3つの変奏曲** (Three Variations on the Canon in D Major by Johann Pachelbel)」が収められています。演奏は、作曲家ギャヴィン・ブライアーズ (Gavin Bryars) が指揮する The Cockpit Ensemble です。イーノはライナーノーツで、ここでの「システム」は **指示を与えられた演奏者のグループ** で、「入力」はパッヘルベルのカノンの断片だと説明しています。A面ではテープの装置が担っていた役割を、B面では人間の演奏者と規則が担っているのです。

どの変奏も、楽譜の短い部分 (2小節か4小節) を出発点に、各パートを入れ替えて、もとの楽譜にはない重なり方を生み出します。3曲には、それぞれ別の規則が与えられています。

* 「Fullness of Wind」: 各奏者のテンポがだんだん遅くなり、その遅くなる割合は楽器の音の高さで決まります (低い楽器ほど遅くなる)。
* 「French Catalogues」: 楽譜のほかの部分から集めた音やメロディを、テンポの指示とともにまとめて組み合わせます。
* 「Brutal Ardour」: 各奏者は、互いに関係のある音の並びを演奏しますが、その長さがそれぞれ違うため、もとの関係はすぐに崩れていきます。

「Brutal Ardour」の、長さの違うくり返しがずれていくしくみは、A面の2つのフレーズと同じ考え方です。なお、3曲の題名は、パイヤール室内管弦楽団によるカノンのレコードの、フランス語の解説を不正確に英訳した言葉からとられています。

ライナーノーツには、もう一つのエピソードも書かれています。交通事故でベッドから動けなかったイーノは、友人が持ってきた18世紀のハープ音楽のレコードを、聴こえるか聴こえないかの小さな音で流すことになりました。それが、音楽を部屋の環境の一部として聴く、新しい聴き方に気づくきっかけになったといいます (この話には、友人本人による異論もあります)。この考えは、1978年の『Ambient 1: Music for Airports』で「アンビエント」と名づけられます。

その後、イーノは1996年に、パソコン用のソフトウェアで再生するたびに異なる音楽が流れる「Generative Music 1」を発表しました。テープとシンセサイザーで組み立てていたしくみを、コンピュータのプログラムに置き換えたものといえます。

2017年1月1日に発表された『Reflection』は、その延長にある作品です。アルバムとしては約54分の1曲ですが、同時に、長年の協力者 Peter Chilvers と開発したアプリ版も公開されました。アプリ版では、イーノが用意した音やフレーズと、その組み合わせ方の規則にしたがって、終わりなく変化し続ける音楽が流れます。時間帯によっても、曲の雰囲気が変わります。イーノは、こうした音楽をつくる作曲家を、すべてを設計する建築家ではなく、種をまき、育つのを見守る **庭師** にたとえています。

『Discreet Music』のテープの装置も、『Reflection』のアプリも、第4回の AARON と同じく、データから学習するAIではなく、**規則で生成するしくみ** です。第5回の生成芸術のタイムラインで見た流れが、音楽にもあることが分かります。

2024年には、イーノを描いたドキュメンタリー映画『Eno』(監督: Gary Hustwit) が公開されました。この映画は、Brendan Dawes と開発したソフトウェア「Brain One」(Brian Eno のアナグラム) が、インタビューや記録映像の場面を上映のたびに並べ直すため、**上映ごとに内容が変わります**。生成のしくみが、音楽から映画へと広がった例です。

* [Wikipedia「Discreet Music」](https://en.wikipedia.org/wiki/Discreet_Music)
* [Generative Music「Brian Eno: Reflection」](https://generativemusic.com/reflection.html)
* [Mikiki「ブライアン・イーノ (Brian Eno) が『Reflection』で行う自己省察」](https://mikiki.tokyo.jp/articles/-/12953)
* [Gary Hustwit「Eno」](https://www.hustwit.com/eno)

### AIと人間が交互に選曲する: 徳井直生「AI DJ Project」(2016-)

![](https://images.ctfassets.net/jhi4pj6pvhnp/3eG75oywwM54TqW8xABVqI/c6b56fcb9f9d0d5a61ff8af648ab5b52/IMG_0043.JPG?w=1280)

<small>画像出典: [Qosmo「AI DJ Project - A dialogue between AI and a human」](https://qosmo.jp/art/ai-dj-human-dj-b2b)</small>

「AI DJ Project」は、徳井直生 (株式会社 Qosmo) が2016年に始めたプロジェクトです。人間のDJとAIのDJが、1曲ずつ交互に曲をかけ合う「バック・トゥ・バック (Back to Back)」の形式でライブを行います。

AIは、人間のDJがかけた曲を聴き、3つのニューラルネットワークで曲のジャンルや楽器、使われているドラムマシンを推定して、次にかける曲を選びます。そして、ターンテーブルを操作して、前の曲とビートを合わせます。さらに、カメラで観客の動きをとらえ、盛り上がり具合を次の選曲に反映します。

プロジェクトの目的は、DJの作業を自動化することではありません。人間とは違う基準で曲を選ぶAIを相手に、**人間とAIのあいだにどんな対話が生まれるか** を探ることです。人間のDJはAIの意外な選曲に応え、AIは人間のDJの選曲を分析して次の曲を選びます。2016年の京都での初演以来、山口情報芸術センター (YCAM)、MUTEK.JP、Google I/O 2019 などで公演が行われました。

* [Qosmo「AI DJ Project - A dialogue between AI and a human」](https://qosmo.jp/art/ai-dj-human-dj-b2b)

### 声を学習させる: Holly Herndon & Jlin「Godmother」(2018)

[![](https://img.youtube.com/vi/sc9OjL6Mjqo/maxresdefault.jpg)](https://www.youtube.com/watch?v=sc9OjL6Mjqo)

<small>画像出典: [Holly Herndon & Jlin (feat. Spawn) - Godmother (Official Video) (YouTube)](https://youtu.be/sc9OjL6Mjqo) (Holly Herndon)</small>

第4回で「xhairymutantx」を紹介した Holly Herndon と Mat Dryhurst は、音楽の分野で早くからAIに取り組んできました。二人は、聴いた音から学び、自分で音を出すAI「Spawn」を開発し、自分たちの子どものように、家族や、家を訪れた人々、公演の観客の声を聴かせて「育て」ました。

2018年に発表された「Godmother」では、Spawn が、アメリカのプロデューサー Jlin の曲を聴き、それを Herndon の声で再現しようとしています。サンプリングや編集、重ね録りは使わず、Spawn が無音の状態から生成した音です。ざらざらとした、打楽器のようなその音について、Herndon は、AIは「まだ赤ちゃん」であり、その荒さは技術の正直な姿だと語っています。そして同時に、「怪物を育てていないか、注意しなければならない」とも述べています。この曲を含むアルバム『PROTO』は、2019年に発表されました。

2021年には、Herndon の声をモデルにした「**Holly+**」を公開しました。誰でも音声をアップロードすると、それを Herndon の声で歌わせることができます。自分の声をAIのモデルとして開放し、その使われ方を自分たちで決めるという試みです。

* [The FADER「Holly Herndon and Jlin's "Godmother" features an A.I. named Spawn」](https://www.thefader.com/2018/12/04/holly-herndon-jlin-godmother-spawn-ai-music-video)
* [Holly+](https://holly.plus/)

### 合唱を学習させる: Holly Herndon & Mat Dryhurst「The Call」(2024-2025)

![](https://d37zoqglehb9o7.cloudfront.net/uploads/2024/08/SerpentineGallery_HHMD03119_B2-2-1200x627.jpg)

<small>画像出典: [Serpentine「Holly Herndon & Mat Dryhurst: The Call」](https://www.serpentinegalleries.org/whats-on/holly-herndon-mat-dryhurst-the-call/)</small>

2024年10月から2025年2月まで、ロンドンのサーペンタイン・ギャラリーで、Herndon と Dryhurst の展覧会「The Call」が開かれました。二人は、賛美歌や発声練習からなる「歌集」を作り、イギリス各地の **15の地域の合唱団** を訪ねて、その歌声を録音しました。そして、その録音から合唱のAIモデルを作り、展示室では、立体音響のなかで、来場者の声にAIの合唱が応える作品を発表しました。

[![](https://img.youtube.com/vi/DNlr7olF6rE/maxresdefault.jpg)](https://www.youtube.com/watch?v=DNlr7olF6rE)

<small>画像出典: [Holly Herndon and Mat Dryhurst: The Call | Serpentine (YouTube)](https://youtu.be/DNlr7olF6rE) (Serpentine)</small>

この展覧会でとくに重視されたのは、**学習データの扱い方** です。録音したデータは、参加した合唱団が決めた条件にしたがってのみ、ほかの人に利用を許諾できる、というしくみが作られました。AIの学習に使われる人々が、自分たちの声の使われ方に関わることのできるモデルを、作品として示したのです。

* [Serpentine「Holly Herndon & Mat Dryhurst: The Call」](https://www.serpentinegalleries.org/whats-on/holly-herndon-mat-dryhurst-the-call/)

### 古い録音から声を取り出す: The Beatles「Now And Then」(2023)

[![](https://img.youtube.com/vi/APJAQoSCwuA/maxresdefault.jpg)](https://www.youtube.com/watch?v=APJAQoSCwuA)

<small>画像出典: [The Beatles - Now And Then - The Last Beatles Song (Short Film) (YouTube)](https://youtu.be/APJAQoSCwuA) (TheBeatlesVEVO)</small>

「Now And Then」は、ジョン・レノンが1970年代後半に自宅でカセットテープに録音したデモをもとに、2023年11月に発表された「ビートルズ最後の新曲」です。デモでは、レノンの歌とピアノが一つの音として録音されていました。1995年にも残りのメンバーが完成を試みましたが、雑音が多く、歌声をきれいに取り出せないために断念していました。

これを可能にしたのが、ピーター・ジャクソン監督のチームが、ドキュメンタリー『ザ・ビートルズ: Get Back』(2021) のために開発した **音源分離** の技術です。機械学習によって、混ざった録音のなかからレノンの声だけを取り出すことができました。そこに、ポール・マッカートニーとリンゴ・スターが新たに演奏を加え、1995年に録音されていたジョージ・ハリスンのギターも使って、曲が完成しました。

ここで、AIはレノンの声を **新しく作ったのではありません**。埋もれていた本人の声を取り出しただけです。2025年2月、この曲はグラミー賞の最優秀ロック・パフォーマンス賞を受賞し、AIの助けを借りた曲として初めてグラミー賞を受けた曲になりました。

* [The Beatles - Now And Then (Official Music Video)](https://www.youtube.com/watch?v=Opxhh9Oh3rg)
* [GIZMODO「ビートルズ最後の新曲｢Now and Then｣はどうやって作られたのか」](https://www.gizmodo.jp/2023/11/listen-to-ai-john-lennon-in-the-beatles-final-new-son.html)
* [Guinness World Records「First AI-assisted song to win a Grammy award」](https://www.guinnessworldrecords.com/world-records/775447-first-ai-assisted-song-to-win-a-grammy-award)

### 新しい音色をつくる: Google Magenta「NSynth Super」(2018)

![](https://magenta.withgoogle.com/assets/nsynth_super/nss.jpeg)

<small>画像出典: [Magenta「Hands on, with NSynth Super」](https://magenta.tensorflow.org/nsynth-super)</small>

**NSynth** (Neural Synthesizer) は、Google の研究チーム Magenta が DeepMind とともに2017年に発表した、新しい音色を作るための機械学習のアルゴリズムです。約1,000種類の楽器の、約30万の音を学習し、2つの楽器の音の「あいだ」にある、これまでにない音色を合成します。たとえば、フルートとスネアドラムの中間の音を作ることができます。

**NSynth Super** は、この NSynth を演奏するために、Magenta と Google Creative Lab が2018年に公開した実験的な楽器です。四隅に割り当てた4つの音のあいだを、タッチスクリーンの上で指を動かして行き来しながら、音色を混ぜ合わせて演奏します。基板の設計図やケースの図面、ソフトウェアまでがオープンソースで公開されていて、誰でも自作できます。ソフトウェアは、メディアアートでもよく使われる openFrameworks で作られています。

画像生成AIでいえば、言葉で絵を描かせるのではなく、**絵の具そのものを新しく作る** ような使い方です。

* [NSynth Super](https://nsynthsuper.withgoogle.com/)
* [Magenta「NSynth」](https://magenta.tensorflow.org/nsynth)

### 音を別の音に変える: Neutone「Morpho」(2024)

[![](https://img.youtube.com/vi/CI79qnstFN0/maxresdefault.jpg)](https://www.youtube.com/watch?v=CI79qnstFN0)

<small>画像出典: [Neutone Morpho, real-time Tone Morphing plugin, has arrived! (YouTube)](https://youtu.be/CI79qnstFN0) (Neutone)</small>

**Neutone Morpho** は、AI DJ Project の徳井直生が率いる Qosmo から生まれた会社 Neutone が開発した、音楽制作ソフトウェア (DAW) のためのプラグインです。入力された音の大まかな形 (抑揚やリズム) を保ったまま、学習した別の音色で鳴らし直します。たとえば、マイクに向かって歌った声をバイオリンの音に、机をたたく音をドラムの音に、**リアルタイムで** 変えることができます。

あらかじめ学習されたモデルを選んで使うほか、自分で用意した音を学習させて、自分だけのモデルを作ることもできます。Suno のように言葉から曲をまるごと作るのではなく、**人間が演奏した音をAIに渡し、AIは音色を変える** という役割分担です。演奏するのは、あくまで人間です。

* [Neutone Morpho](https://neutone.jp/morpho)

### AIをリアルタイムに操る: Jacob Collier と「MusicFX DJ」(2024)

![](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/Jacob_Collier_2096x1182_02_1.width-1300.jpg)

<small>画像出典: [Google「Jacob Collier and Google Labs」](https://blog.google/technology/ai/jacob-collier-labs-sessions/)</small>

2024年10月、Google は音楽生成ツール「MusicFX DJ」を大きく刷新しました。この刷新には、グラミー賞を受賞したミュージシャンのジェイコブ・コリアー (Jacob Collier) が、約1年にわたって協力しています。

MusicFX DJ では、楽器やジャンル、雰囲気を表す複数のプロンプトを組み合わせ、それぞれの強さをつまみで調整しながら、**途切れずに流れ続ける音楽** をリアルタイムに操ります。利用者は、AIとのジャムセッションの指揮者のような立場になります。1曲を生成して終わりではなく、DJのように、流れている音楽を変え続けることができるのが特徴でした。

その後、MusicFX DJ のアドレスは、2026年に Google が公開した音楽制作サービス「Google Flow Music」(後述) へ転送されるようになりました。MusicFX DJ を支えていたリアルタイム生成のモデル **Lyria RealTime** は、開発者向けに Gemini API から利用できます。

* [Google「Jacob Collier and Google Labs」](https://blog.google/technology/ai/jacob-collier-labs-sessions/)
* [Google DeepMind「Lyria RealTime」](https://deepmind.google/models/lyria/realtime/)

### 言葉から曲をまるごと生成する: Suno と Udio (2024-)

2024年、言葉を入力するだけで、歌も伴奏も入った曲を生成するサービスが一般に広まりました。3月に新しいモデルを公開した **Suno** と、4月に公開された **Udio** です。日本語の歌詞でも、数十秒で、それらしい曲が返ってきます。

言葉から曲を作るAIのしくみは、画像と似ています。音声を、短い音の断片を表す記号 (トークン) に変換して、言語モデルと同じように「次の音」を予測する方式や、第2回で見た拡散モデルを使って、ノイズから音を作り出す方式があります。Suno は、詳しいしくみを公開していません。

また、これらのサービスが、どんな曲を学習したのかも公開されていませんでした。2024年6月、ユニバーサル、ソニー、ワーナーの大手レコード会社3社は、許可なく録音物を学習に使ったとして、Suno と Udio を訴えました。その後、2025年10月から11月にかけて、ユニバーサルと Udio、ワーナーと Udio、ワーナーと Suno が和解し、レコード会社の許諾を得たモデルを作る方向に進んでいます。

和解は、利用者にも影響を与えました。Udio は、生成した曲のダウンロードを停止し、作った曲をサービスの外に持ち出せない形へと移行しました。Suno は、2026年9月に、レコード会社と協力して作った新しいモデル **v6** を公開し、無料プランでは曲をダウンロードできなくなりました。ソニーなどとの訴訟は、2026年11月の時点でも続いていると報じられています。

* [Music Ally「AI-music firm Suno strikes first licensing deal… with Warner Music Group」](https://musically.com/2025/11/25/ai-music-firm-suno-strikes-first-licensing-deal-with-warner-music-group/)
* [Music Business Worldwide「Universal Music settles Udio lawsuit, strikes deal for licensed AI music platform」](https://www.musicbusinessworldwide.com/universal-music-settles-udio-lawsuit-strikes-deal-for-licensed-ai-music-platform)

### ストリーミングにあふれるAIの曲 (2025-)

2025年の夏、Spotify で月に100万人以上に聴かれていたバンド「The Velvet Sundown」が、実はAIで作られていたことが話題になりました。メンバーの写真も、インタビューの記録もないことを不審に思った人々が調べ、最終的にバンド側は、人間が方向を決め、AIで作曲し、歌い、映像を作った「合成された音楽プロジェクト」だと認めました。

音楽配信サービスの Deezer は、2026年6月には、**1日に新しくアップロードされる曲の半数以上** (約9万曲) が、すべてAIで生成された曲だと発表しています。一方で、それらの曲が実際に聴かれた回数は全体の1〜3%にすぎず、さらにその再生の約85%は、再生回数を水増しする不正なものだったといいます。Spotify も、2026年8月、AIで作られた架空のアーティストのプロフィールに「AI Persona」の表示を付け、その曲をおすすめの対象から外すと発表しました。

言葉だけで曲が作れるようになった結果、聴かれることのない、ありそうな曲が、大量に作られています。第2回で見た **平均への引力** が、作品の数として現れているといえるかもしれません。

* [TechRadar「Spotify's latest breakout band The Velvet Sundown appears to be AI-generated」](https://www.techradar.com/computing/artificial-intelligence/spotifys-latest-breakout-band-the-velvet-sundown-appears-to-be-ai-generated-and-fans-arent-happy)
* [Deezer Newsroom「AI Music Tops 50% of Daily Uploads on Deezer」](https://newsroom-deezer.com/2026/07/ai-music-exceeds-50-percent-daily-uploads-deezer/)
* [NPR「Spotify will now label AI creators posing as human artists」](https://www.npr.org/2026/08/13/nx-s1-5929744/spotify-labeling-ai-personas)

### 年表

| 年 | 出来事 |
| :--- | :--- |
| 1957 | コンピュータで作曲した最初期の作品「イリアック組曲」、Max Mathews の MUSIC I (第5回) |
| 1975 | ブライアン・イーノ『Discreet Music』、シンセサイザーとテープによる生成のしくみ |
| 1996 | ブライアン・イーノが「Generative Music 1」を発表 |
| 2016 | 「AI DJ Project」、Sony CSL の Flow Machines による「Daddy's Car」 |
| 2017 | イーノ『Reflection』(1月)、Magenta が NSynth を発表 (4月) |
| 2018 | NSynth Super (3月)、Holly Herndon & Jlin「Godmother」 |
| 2020 | OpenAI が、歌声を含む音楽を生成する Jukebox を発表 |
| 2021 | Holly Herndon の声のモデル「Holly+」 |
| 2023 | Google の MusicLM (1月)、ビートルズ「Now And Then」(11月) |
| 2024 | Suno の新モデル (3月)、Udio (4月)、大手レコード会社が両社を提訴 (6月)、MusicFX DJ の刷新 (10月)、Neutone Morpho、「The Call」(10月) |
| 2025 | 「Now And Then」がグラミー賞 (2月)、The Velvet Sundown (6-7月)、レコード会社と Suno・Udio の和解 (10-11月) |
| 2026 | Gemini アプリで Lyria 3 (2月)、Google Flow Music (4月)、Lyria 3.5 (7月)、Spotify が「AI Persona」の表示を発表 (8月)、Suno v6 (9月) |

### 参考

* [Google Arts & Culture「12 songs created by AI」](https://artsandculture.google.com/story/12-songs-created-by-ai-barbican-centre/VwVhbAD7QslgLA?hl=en) (Barbican Centre)
* [Ableton「AIと音楽制作：現段階の状況」](https://www.ableton.com/ja/blog/ai-and-music-making-the-state-of-play/) (2023年)

## 現在の主な音楽生成AIサービス

ここでは、2026年11月時点の主なサービスを紹介します。モデルの名前や料金、無料で使える範囲は頻繁に変わるので、利用する前に各サービスの公式情報を確認してください。

| サービス | 開発 | 主なモデル | 無料での利用 | 特徴 |
| :--- | :--- | :--- | :--- | :--- |
| [Suno](https://suno.com/) | Suno | v6、v6-wild (有料)、v6-mini (無料) | 可 (ダウンロードと商用利用は不可) | 歌詞から歌入りの曲、Suno Studio で編集 |
| [Gemini](https://gemini.google.com/music) | Google | Lyria 3 / 3.5 | 可 (18歳以上) | 言葉や写真から曲を生成、カバーアートつき |
| [Google Flow Music](https://www.flowmusic.app/) | Google | Lyria 3.5 | 可 (毎日クレジットを補充) | 対話で作曲、ステム (パートごとの音) の書き出し、ミュージックビデオの生成 |
| [Neutone Morpho](https://neutone.jp/morpho) | Neutone | 30以上の音色モデル | 可 (5つのモデル) | DAW のプラグイン、入力した音をリアルタイムに変換 |

そのほかにも、ElevenLabs の [Eleven Music](https://elevenlabs.io/music)、Stability AI の [Stable Audio](https://stableaudio.com/) など、多くのサービスがあります。

### Suno

[Suno](https://suno.com/) は、言葉から、歌と伴奏を含む曲を生成するサービスです。曲のイメージを短い文章で伝えるだけの方法と、**歌詞** と **スタイル** (ジャンル、楽器、声の特徴など) を自分で書き分けるカスタムの方法があります。日本語の歌詞にも対応していて、歌なしのインストゥルメンタルも作れます。

2026年9月に公開された **v6** は、Pro (月額10ドル) 以上の有料プランで使え、無料プランでは軽量版の **v6-mini** を使います。無料プランでは、1日50クレジット (約10曲) まで生成できますが、曲はサービス上で再生、共有できるだけで、**ダウンロードはできません**。また、無料プランで作った曲は商用に利用できず、あとから有料プランに切り替えても、さかのぼって商用利用が認められるわけではありません。

* [Suno「Pricing」](https://suno.com/pricing)

### Gemini (Google)

[Gemini](https://gemini.google.com/music) のアプリでも、音楽を生成できます。2026年2月に、Google DeepMind の音楽生成モデル **Lyria 3** が追加されました (当初は30秒まで)。現在は **Lyria 3.5** になり、最長3分の曲を作れます。言葉のほか、写真をアップロードして、その雰囲気に合う曲を作ることもできます。歌詞は自分で書くことも、Gemini に任せることもでき、生成した曲には、第4回で紹介した Nano Banana で作ったカバーアートが付きます。

利用できるのは **18歳以上** で、Google AI の有料プランでは利用の上限が増えます。生成した曲には、AIで作られたことを示す透かし **SynthID** が埋め込まれます。また、プロンプトで実在のアーティストの名前を挙げても、そのアーティストをまねるのではなく、似た雰囲気を参考にする程度にとどめるよう設計されています。

* [Gemini「Lyria 3.5」](https://gemini.google/overview/music-generation/)
* [Google「Use Lyria 3 to create music tracks in the Gemini app」](https://blog.google/innovation-and-ai/products/gemini-app/lyria-3/)

### Google Flow Music (Google)

![](https://www.flowmusic.app/og-image.png)

<small>画像出典: [Google Flow Music](https://www.flowmusic.app/)</small>

[Google Flow Music](https://www.flowmusic.app/) は、Google が2026年4月に公開した音楽制作のサービスです。音楽AIのサービス ProducerAI を前身とし、MusicFX と MusicFX DJ のアドレスも、現在はこのサービスに転送されます。2026年7月から、Lyria 3.5 が使われています。

曲のイメージを入力して生成するほか、「Producer」とチャットするように相談しながら曲を作り込んだり、イントロやサビなど曲の構成を指定したりできます。無料プランでも、毎日クレジットが補充され、曲のダウンロード (mp3、wav、m4a) や、パートごとの音 (ステム) の書き出しができます。第1回で紹介した Gemini の学割プランで使える **Google AI Plus** には、Flow Music の Starter プラン (月3,000クレジット、約600曲、商用利用可) の特典が含まれています。

* [Google Flow Music「Pricing」](https://www.flowmusic.app/pricing)
* [Google One ヘルプ「Google AI Plus の特典を利用する」](https://support.google.com/googleone/answer/16882689?hl=ja)

### Neutone Morpho

[Neutone Morpho](https://neutone.jp/morpho) は、Ableton Live や Logic Pro などの DAW に組み込んで使うプラグインです (macOS 12 以降、Windows 10 / 11)。無料版では5つのモデルが使え、7日間は全モデルを試せます。全モデル (30以上) を使えるフルバンドルは99ドル (買い切り) です。

* [Neutone Morpho](https://neutone.jp/morpho)

## 関連リンク

* [Suno](https://suno.com/)
* [Gemini (音楽の生成)](https://gemini.google.com/music)
* [Google Flow Music](https://www.flowmusic.app/)
* [Neutone Morpho](https://neutone.jp/morpho)
* [Google DeepMind「Lyria」](https://deepmind.google/models/lyria/)
* [NSynth Super](https://nsynthsuper.withgoogle.com/)
* [Qosmo「AI DJ Project」](https://qosmo.jp/art/ai-dj-human-dj-b2b)
* [Holly+](https://holly.plus/)
* [Serpentine「Holly Herndon & Mat Dryhurst: The Call」](https://www.serpentinegalleries.org/whats-on/holly-herndon-mat-dryhurst-the-call/)
* [Generative Music「Brian Eno: Reflection」](https://generativemusic.com/reflection.html)
* [人工知能と創作 2025「生成動画『幻覚 - バッド・トリップ』講評 / AIと音楽制作」](https://yoppa.org/geidai-ai25/18618.html)

## 参考文献

* [The FADER. "Holly Herndon and Jlin's "Godmother" features an A.I. named Spawn."](https://www.thefader.com/2018/12/04/holly-herndon-jlin-godmother-spawn-ai-music-video) 2018.
* [Serpentine. "Holly Herndon & Mat Dryhurst: The Call."](https://www.serpentinegalleries.org/whats-on/holly-herndon-mat-dryhurst-the-call/) 2024.
* [Qosmo「AI DJ Project - A dialogue between AI and a human」](https://qosmo.jp/art/ai-dj-human-dj-b2b)
* [Magenta. "Hands on, with NSynth Super."](https://magenta.tensorflow.org/nsynth-super) 2018.
* [Google. "Jacob Collier and Google Labs."](https://blog.google/technology/ai/jacob-collier-labs-sessions/) 2024.
* [Guinness World Records. "First AI-assisted song to win a Grammy award."](https://www.guinnessworldrecords.com/world-records/775447-first-ai-assisted-song-to-win-a-grammy-award) 2025.
* [Music Ally. "AI-music firm Suno strikes first licensing deal… with Warner Music Group."](https://musically.com/2025/11/25/ai-music-firm-suno-strikes-first-licensing-deal-with-warner-music-group/) 2025.
* [Deezer Newsroom. "AI Music Tops 50% of Daily Uploads on Deezer."](https://newsroom-deezer.com/2026/07/ai-music-exceeds-50-percent-daily-uploads-deezer/) 2026.
* [NPR. "Spotify will now label AI creators posing as human artists."](https://www.npr.org/2026/08/13/nx-s1-5929744/spotify-labeling-ai-personas) 2026.
* [Google. "Use Lyria 3 to create music tracks in the Gemini app."](https://blog.google/innovation-and-ai/products/gemini-app/lyria-3/) 2026.
* [Ableton「AIと音楽制作：現段階の状況」](https://www.ableton.com/ja/blog/ai-and-music-making-the-state-of-play/) 2023.
