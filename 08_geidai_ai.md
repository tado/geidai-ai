---
marp: true
theme: tadokoro
paginate: true
---

# AIと音楽制作
東京藝術大学芸術情報センター
田所 淳

---

## 今日の内容

- AIと音楽の歩み
  - 規則から生まれる音楽: ブライアン・イーノ
  - AIとの共演: AI DJ Project
  - 声と合唱の学習: Holly Herndon & Mat Dryhurst
  - 古い録音の修復: The Beatles「Now And Then」
  - 音色の生成と変換: NSynth Super、Neutone Morpho
  - リアルタイムの生成: MusicFX DJ
  - 言葉から曲をまるごと生成: Suno と Udio、ストリーミングにあふれるAIの曲
- 現在の主な音楽生成AIサービス

---

## 音楽とAI

- 第4回: 「人間はAIに何を渡して描かせてきたか」
- 音楽でも、渡すものは移り変わってきた: 作曲の規則 → 声 → 古い録音 → 音色 → 言葉
- 音楽には絵と違う面もある: 時間とともに流れる、演奏する、歌声がその人自身と結びつく

![height:250](https://images.ctfassets.net/jhi4pj6pvhnp/3eG75oywwM54TqW8xABVqI/c6b56fcb9f9d0d5a61ff8af648ab5b52/IMG_0043.JPG?w=1280)

<!-- _footer: '画像出典: 徳井直生 / Qosmo「AI DJ Project」(2016-), [Qosmo](https://qosmo.jp/art/ai-dj-human-dj-b2b)' -->

---

<!-- _class: bigtxt -->

# AIと音楽の歩み

---

## 規則から生まれる音楽: ブライアン・イーノ

- アンビエント・ミュージックの創始者として知られる音楽家
- 長く **生成音楽 (Generative Music)** に取り組む
  - 一つひとつの音ではなく、音の素材と規則を用意し、しくみに音楽を生み出させる
  - 1975年『Discreet Music』: シンセサイザーとテープによる生成のしくみ
  - 1996年「Generative Music 1」: 再生するたびに異なる音楽が流れるソフトウェア
  - 2017年『Reflection』: 終わりなく変化し続けるアプリ

[![height:200](https://img.youtube.com/vi/fSofXKGpenQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=fSofXKGpenQ)

<!-- _footer: '[Brian Eno - Reflection (Excerpt) [Official Visual] (YouTube)](https://youtu.be/fSofXKGpenQ) (Warp Records)' -->

---

## コンピュータ以前の生成音楽: 『Discreet Music』(1975)

- 音楽づくりにパソコンが使われていなかった時代の、**自動的に音楽が生まれ続けるしくみ**
  - シンセサイザー (EMS Synthi AKS) のシーケンサーが、長さの違う2つの短いフレーズをくり返す
  - イコライザーとエコーを通して、2台のテープレコーダーへ
  - 1台目で録音したテープを2台目で再生し、1台目に戻して重ねて録音する
  - フレーズは少し遅れて何度も重なり、少しずつ薄れていく
  - 2つのフレーズの長さが違うので、同じ重なり方をくり返さない
- イーノは、しくみを組み立てて動かすだけ
  - 約30分の曲は、来客の相手をしているあいだにもできあがっていった
  - 「まさに自動の音楽 (automatic music)」

<!-- _footer: '[Brian Eno『Discreet Music』(Spotify)](https://open.spotify.com/album/7b67MKOwyj7mIcEVnoJSOG) / [Wikipedia「Discreet Music」](https://en.wikipedia.org/wiki/Discreet_Music)' -->

---

## 楽譜は装置の図

- ライナーノーツの「Operational diagram」: シンセサイザー → イコライザー → エコー → 録音 (record) → 再生 (playback) → 「delay return」で録音に戻る
- 2台のあいだのテープの長さが、遅れの長さ (delay line)
- 「この曲に楽譜があるとすれば、それはこの装置の図」(イーノ)

![height:300](https://lloydcontextualstudies.wordpress.com/wp-content/uploads/2014/05/eno-discreet-music.jpg)

<!-- _footer: 'Brian Eno『Discreet Music』(Obscure, 1975) のライナーノーツ ([lloydcontextualstudies](https://lloydcontextualstudies.wordpress.com/wp-content/uploads/2014/05/eno-discreet-music.jpg) 掲載のスキャン)' -->

---

## B面: パッヘルベルのカノンによる3つの変奏曲

- 演奏: The Cockpit Ensemble (指揮: ギャヴィン・ブライアーズ)
- 「システム」は **指示を与えられた演奏者のグループ**、「入力」はカノンの断片
  - A面のテープの装置の役割を、人間の演奏者と規則が担う
  - 楽譜の2小節か4小節を出発点に、各パートを入れ替えて、楽譜にない重なりを生む
- 3曲それぞれの規則
  - 「Fullness of Wind」: テンポがだんだん遅くなる。遅くなる割合は音の高さで決まる (低いほど遅い)
  - 「French Catalogues」: 楽譜のほかの部分から集めた音やメロディを、テンポの指示とともにまとめる
  - 「Brutal Ardour」: 長さの違う音の並びが重なり、もとの関係がすぐに崩れる
- 題名は、パイヤール室内管弦楽団のレコードのフランス語の解説を、不正確に英訳した言葉から

<!-- _footer: 'Brian Eno『Discreet Music』(Obscure, 1975) のライナーノーツ / [Wikipedia「Discreet Music」](https://en.wikipedia.org/wiki/Discreet_Music)' -->

---

## 環境の一部として聴く音楽へ

- ライナーノーツのエピソード
  - 事故でベッドから動けなかったイーノは、18世紀のハープ音楽のレコードを、聴こえるか聴こえないかの小さな音で流すことになった
  - 音楽を部屋の環境の一部として聴く、新しい聴き方に気づく (友人本人による異論もある)
  - 1978年『Ambient 1: Music for Airports』で「アンビエント」と名づけられる
- 1996年「Generative Music 1」
  - テープとシンセサイザーで組み立てていたしくみを、コンピュータのプログラムに置き換えた

<!-- _footer: '[Wikipedia「Discreet Music」](https://en.wikipedia.org/wiki/Discreet_Music)' -->

---

## 作曲家は庭師

- 『Reflection』(2017年1月1日)
  - アルバムとしては約54分の1曲
  - Peter Chilvers と開発したアプリ版も公開
  - 用意した音やフレーズと、組み合わせ方の規則にしたがって、終わりなく変化し続ける
  - 時間帯によっても、曲の雰囲気が変わる
- イーノは、こうした音楽をつくる作曲家を **庭師** にたとえる
  - すべてを設計する建築家ではなく、種をまき、育つのを見守る
- 『Discreet Music』のテープの装置も、『Reflection』のアプリも、データから学習するAIではなく、**規則で生成するしくみ**
  - 第4回の AARON、第5回の生成芸術のタイムラインと同じ流れ

<!-- _footer: '[Generative Music「Brian Eno: Reflection」](https://generativemusic.com/reflection.html) / [Mikiki](https://mikiki.tokyo.jp/articles/-/12953)' -->

---

## 上映のたびに変わる映画『Eno』(2024)

- イーノを描いたドキュメンタリー映画 (監督: Gary Hustwit)
- Brendan Dawes と開発したソフトウェア「Brain One」(Brian Eno のアナグラム)
  - インタビューや記録映像の場面を、上映のたびに並べ直す
  - **上映ごとに内容が変わる**
- 生成のしくみが、音楽から映画へと広がった例

<!-- _footer: '[Gary Hustwit「Eno」](https://www.hustwit.com/eno)' -->

---

## AIと人間が交互に選曲する: 徳井直生「AI DJ Project」(2016-)

- 徳井直生 (株式会社 Qosmo) が2016年に始めたプロジェクト
- 人間のDJとAIのDJが1曲ずつ交互にかけ合う「バック・トゥ・バック」

![height:280](https://images.ctfassets.net/jhi4pj6pvhnp/3eG75oywwM54TqW8xABVqI/c6b56fcb9f9d0d5a61ff8af648ab5b52/IMG_0043.JPG?w=1280)

<!-- _footer: '画像出典: [Qosmo「AI DJ Project - A dialogue between AI and a human」](https://qosmo.jp/art/ai-dj-human-dj-b2b)' -->

---

## 自動化ではなく、対話

- AIのしくみ
  - 3つのニューラルネットワークで、曲のジャンル、楽器、ドラムマシンを推定し、次の曲を選ぶ
  - ターンテーブルを操作して、ビートを合わせる
  - カメラで観客の動きをとらえ、選曲に反映する
- 目的は、DJの作業を自動化することではない
  - 人間とは違う基準で曲を選ぶAIを相手に、**人間とAIのあいだにどんな対話が生まれるか** を探る
  - 人間のDJはAIの意外な選曲に応え、AIは人間のDJの選曲を分析して次の曲を選ぶ
- 2016年の京都での初演以来、YCAM、MUTEK.JP、Google I/O 2019 などで公演

<!-- _footer: '[Qosmo「AI DJ Project - A dialogue between AI and a human」](https://qosmo.jp/art/ai-dj-human-dj-b2b)' -->

---

## 声を学習させる: Holly Herndon & Jlin「Godmother」(2018)

- Herndon と Dryhurst (第4回「xhairymutantx」) は、音楽の分野で早くからAIに取り組む
- 聴いた音から学び、自分で音を出すAI「Spawn」を開発
  - 家族や、家を訪れた人々、公演の観客の声を聴かせて「育てた」

[![height:240](https://img.youtube.com/vi/sc9OjL6Mjqo/maxresdefault.jpg)](https://www.youtube.com/watch?v=sc9OjL6Mjqo)

<!-- _footer: '[Holly Herndon & Jlin (feat. Spawn) - Godmother (Official Video) (YouTube)](https://youtu.be/sc9OjL6Mjqo) (Holly Herndon)' -->

---

## 「まだ赤ちゃん」

- 「Godmother」: Spawn が Jlin の曲を聴き、Herndon の声で再現しようとした
  - サンプリングや編集、重ね録りは使わず、無音の状態から生成
- ざらざらとした、打楽器のような音
  - Herndon: AIは「まだ赤ちゃん」であり、その荒さは技術の正直な姿
  - 同時に「怪物を育てていないか、注意しなければならない」
- アルバム『PROTO』(2019)
- 2021年「**Holly+**」: Herndon の声のモデル
  - 誰でも、アップロードした音声を Herndon の声で歌わせることができる
  - 自分の声を開放し、その使われ方を自分たちで決める

<!-- _footer: '[The FADER](https://www.thefader.com/2018/12/04/holly-herndon-jlin-godmother-spawn-ai-music-video) / [Holly+](https://holly.plus/)' -->

---

## 合唱を学習させる: 「The Call」(2024-2025)

- Herndon と Dryhurst の展覧会 (ロンドン、サーペンタイン・ギャラリー)
- 賛美歌や発声練習の「歌集」で、イギリス各地の **15の地域の合唱団** を録音
- 録音から合唱のAIモデルを作り、立体音響のなかで来場者の声にAIの合唱が応える

![height:250](https://d37zoqglehb9o7.cloudfront.net/uploads/2024/08/SerpentineGallery_HHMD03119_B2-2-1200x627.jpg)

<!-- _footer: '画像出典: [Serpentine「Holly Herndon & Mat Dryhurst: The Call」](https://www.serpentinegalleries.org/whats-on/holly-herndon-mat-dryhurst-the-call/)' -->

---

## 学習データの扱い方

- 「The Call」でとくに重視されたのは、**学習データの扱い方**
- 録音したデータは、参加した合唱団が決めた条件にしたがってのみ、ほかの人に利用を許諾できる
- AIの学習に使われる人々が、自分たちの声の使われ方に関わることのできるモデルを、作品として示した

<!-- _footer: '[Serpentine「Holly Herndon & Mat Dryhurst: The Call」](https://www.serpentinegalleries.org/whats-on/holly-herndon-mat-dryhurst-the-call/)' -->

---

## 古い録音から声を取り出す: The Beatles「Now And Then」(2023)

- ジョン・レノンが1970年代後半に自宅で録音したデモがもと
  - 歌とピアノが一つの音として録音されていた
- 1995年にも残りのメンバーが完成を試みたが、雑音が多く断念

[![height:240](https://img.youtube.com/vi/APJAQoSCwuA/maxresdefault.jpg)](https://www.youtube.com/watch?v=APJAQoSCwuA)

<!-- _footer: '[The Beatles - Now And Then - The Last Beatles Song (Short Film) (YouTube)](https://youtu.be/APJAQoSCwuA) (TheBeatlesVEVO)' -->

---

## 音源分離で、本人の声を取り出す

- ピーター・ジャクソン監督のチームが『ザ・ビートルズ: Get Back』(2021) のために開発した **音源分離** の技術
  - 機械学習で、混ざった録音からレノンの声だけを取り出した
- ポール・マッカートニーとリンゴ・スターが演奏を加え、1995年のジョージ・ハリスンのギターも使って完成
- AIはレノンの声を **新しく作ったのではない**
  - 埋もれていた本人の声を取り出しただけ
- 2025年2月、グラミー賞の最優秀ロック・パフォーマンス賞
  - AIの助けを借りた曲として、初めてグラミー賞を受けた

<!-- _footer: '[GIZMODO](https://www.gizmodo.jp/2023/11/listen-to-ai-john-lennon-in-the-beatles-final-new-son.html) / [Guinness World Records](https://www.guinnessworldrecords.com/world-records/775447-first-ai-assisted-song-to-win-a-grammy-award)' -->

---

## 新しい音色をつくる: Google Magenta「NSynth」(2017)

- **NSynth** (Neural Synthesizer)
  - Google の研究チーム Magenta が DeepMind とともに発表
  - 新しい音色を作るための機械学習のアルゴリズム
- 約1,000種類の楽器の、約30万の音を学習
- 2つの楽器の音の「あいだ」にある、これまでにない音色を合成
  - 例: フルートとスネアドラムの中間の音

<!-- _footer: '[Magenta「NSynth」](https://magenta.tensorflow.org/nsynth)' -->

---

## NSynth Super (2018)

- NSynth を演奏するための実験的な楽器 (Magenta と Google Creative Lab)
- 4つの音のあいだを、タッチスクリーンの上で行き来して、音色を混ぜ合わせる
- 基板やケースの図面、ソフトウェア (openFrameworks) までオープンソース
- 画像生成AIでいえば、**絵の具そのものを新しく作る** ような使い方

![height:230](https://magenta.withgoogle.com/assets/nsynth_super/nss.jpeg)

<!-- _footer: '画像出典: [Magenta「Hands on, with NSynth Super」](https://magenta.tensorflow.org/nsynth-super) / [NSynth Super](https://nsynthsuper.withgoogle.com/)' -->

---

## 音を別の音に変える: Neutone「Morpho」(2024)

- 徳井直生が率いる Qosmo から生まれた会社 Neutone が開発
- 音楽制作ソフトウェア (DAW) のためのプラグイン

[![height:280](https://img.youtube.com/vi/CI79qnstFN0/maxresdefault.jpg)](https://www.youtube.com/watch?v=CI79qnstFN0)

<!-- _footer: '[Neutone Morpho, real-time Tone Morphing plugin, has arrived! (YouTube)](https://youtu.be/CI79qnstFN0) (Neutone)' -->

---

## 演奏するのは人間

- 入力された音の大まかな形 (抑揚やリズム) を保ったまま、学習した別の音色で鳴らし直す
  - 歌った声 → バイオリンの音
  - 机をたたく音 → ドラムの音
  - **リアルタイムで** 変換できる
- 自分で用意した音を学習させて、自分だけのモデルを作ることもできる
- 言葉から曲をまるごと作るのではなく
  - **人間が演奏した音をAIに渡し、AIは音色を変える** という役割分担

<!-- _footer: '[Neutone Morpho](https://neutone.jp/morpho)' -->

---

## AIをリアルタイムに操る: 「MusicFX DJ」(2024)

- 2024年10月、Google が「MusicFX DJ」を大きく刷新 (ジェイコブ・コリアーが約1年協力)
- 楽器、ジャンル、雰囲気のプロンプトを組み合わせ、それぞれの強さをつまみで調整
- **途切れずに流れ続ける音楽** をリアルタイムに操る: 利用者はAIとのジャムセッションの指揮者

![height:230](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/Jacob_Collier_2096x1182_02_1.width-1300.jpg)

<!-- _footer: '画像出典: [Google「Jacob Collier and Google Labs」](https://blog.google/technology/ai/jacob-collier-labs-sessions/)' -->

---

## MusicFX DJ のその後

- 1曲を生成して終わりではなく、DJのように、流れている音楽を変え続けられるのが特徴だった
- MusicFX DJ のアドレスは、2026年に Google が公開した「Google Flow Music」へ転送されるようになった
  - MusicFX DJ はいまは使えない
- MusicFX DJ を支えていたリアルタイム生成のモデル **Lyria RealTime**
  - 開発者向けに、Gemini API から利用できる

<!-- _footer: '[Google DeepMind「Lyria RealTime」](https://deepmind.google/models/lyria/realtime/)' -->

---

## 言葉から曲をまるごと生成する: Suno と Udio (2024-)

- 2024年、言葉だけで、歌も伴奏も入った曲を生成するサービスが広まる
  - **Suno** (3月に新しいモデル)、**Udio** (4月に公開)
  - 日本語の歌詞でも、数十秒で、それらしい曲が返ってくる
- しくみは画像と似ている
  - 音声を短い音の断片を表す記号 (トークン) に変換し、言語モデルと同じように「次の音」を予測する方式
  - 第2回で見た拡散モデルを使って、ノイズから音を作る方式
  - Suno は詳しいしくみを公開していない

---

## 学習データをめぐる訴訟と和解

- どんな曲を学習したのかも、公開されていなかった
- 2024年6月、大手レコード会社3社 (ユニバーサル、ソニー、ワーナー) が Suno と Udio を提訴
  - 許可なく録音物を学習に使ったとして
- 2025年10〜11月、ユニバーサルと Udio、ワーナーと Udio、ワーナーと Suno が和解
  - レコード会社の許諾を得たモデルを作る方向へ
- 利用者への影響
  - Udio: ダウンロードを停止し、曲をサービスの外に持ち出せない形へ
  - Suno: 2026年9月に新モデル **v6**。無料プランではダウンロード不可に
- ソニーなどとの訴訟は、2026年11月の時点でも続いていると報じられている

<!-- _footer: '[Music Ally](https://musically.com/2025/11/25/ai-music-firm-suno-strikes-first-licensing-deal-with-warner-music-group/) / [Music Business Worldwide](https://www.musicbusinessworldwide.com/universal-music-settles-udio-lawsuit-strikes-deal-for-licensed-ai-music-platform)' -->

---

## ストリーミングにあふれるAIの曲 (2025-)

- 2025年夏「The Velvet Sundown」
  - Spotify で月に100万人以上に聴かれていたバンドが、実はAIで作られていた
  - メンバーの写真も、インタビューの記録もないことを不審に思った人々が調べる
  - バンド側は、人間が方向を決め、AIで作曲し、歌い、映像を作った「合成された音楽プロジェクト」だと認めた

<!-- _footer: '[TechRadar](https://www.techradar.com/computing/artificial-intelligence/spotifys-latest-breakout-band-the-velvet-sundown-appears-to-be-ai-generated-and-fans-arent-happy)' -->

---

## 聴かれない「ありそうな曲」

- Deezer (2026年6月): **1日に新しくアップロードされる曲の半数以上** (約9万曲) が、すべてAIで生成された曲
  - 実際に聴かれた回数は全体の1〜3%
  - その再生の約85%は、再生回数を水増しする不正なもの
- Spotify (2026年8月): AIで作られた架空のアーティストに「AI Persona」の表示を付け、おすすめの対象から外す
- 聴かれることのない、ありそうな曲が、大量に作られている
  - 第2回の **平均への引力** が、作品の数として現れている?

<!-- _footer: '[Deezer Newsroom](https://newsroom-deezer.com/2026/07/ai-music-exceeds-50-percent-daily-uploads-deezer/) / [NPR](https://www.npr.org/2026/08/13/nx-s1-5929744/spotify-labeling-ai-personas)' -->

---

## 年表 (1957-2021)

| 年 | 出来事 |
| :--- | :--- |
| 1957 | 最初期のコンピュータ作曲「イリアック組曲」、Max Mathews の MUSIC I (第5回) |
| 1975 | ブライアン・イーノ『Discreet Music』、シンセサイザーとテープによる生成のしくみ |
| 1996 | ブライアン・イーノ「Generative Music 1」 |
| 2016 | 「AI DJ Project」、Sony CSL の Flow Machines による「Daddy's Car」 |
| 2017 | イーノ『Reflection』(1月)、Magenta の NSynth (4月) |
| 2018 | NSynth Super (3月)、Holly Herndon & Jlin「Godmother」 |
| 2020 | OpenAI が、歌声を含む音楽を生成する Jukebox を発表 |
| 2021 | Holly Herndon の声のモデル「Holly+」 |

---

## 年表 (2023-2026)

| 年 | 出来事 |
| :--- | :--- |
| 2023 | Google の MusicLM (1月)、ビートルズ「Now And Then」(11月) |
| 2024 | Suno の新モデル (3月)、Udio (4月)、大手レコード会社が両社を提訴 (6月)、MusicFX DJ の刷新 (10月)、Neutone Morpho、「The Call」(10月) |
| 2025 | 「Now And Then」がグラミー賞 (2月)、The Velvet Sundown (6-7月)、レコード会社と Suno・Udio の和解 (10-11月) |
| 2026 | Gemini で Lyria 3 (2月)、Google Flow Music (4月)、Lyria 3.5 (7月)、Spotify「AI Persona」(8月)、Suno v6 (9月) |

---

## 参考

- [Google Arts & Culture「12 songs created by AI」](https://artsandculture.google.com/story/12-songs-created-by-ai-barbican-centre/VwVhbAD7QslgLA?hl=en) (Barbican Centre)
  - AIで作られた12曲を紹介
- [Ableton「AIと音楽制作：現段階の状況」](https://www.ableton.com/ja/blog/ai-and-music-making-the-state-of-play/) (2023年)
  - 音楽制作のなかでのAIの使われ方を整理

---

<!-- _class: bigtxt -->

# 現在の主な<br>音楽生成AIサービス

---

## 主なサービス (2026年11月時点)

| サービス | 主なモデル | 無料での利用 | 特徴 |
| :--- | :--- | :--- | :--- |
| [Suno](https://suno.com/) | v6、v6-wild (有料)、v6-mini (無料) | 可 (ダウンロードと商用利用は不可) | 歌詞から歌入りの曲、Suno Studio |
| [Gemini](https://gemini.google.com/music) | Lyria 3 / 3.5 | 可 (18歳以上) | 言葉や写真から曲、カバーアートつき |
| [Google Flow Music](https://www.flowmusic.app/) | Lyria 3.5 | 可 (毎日クレジットを補充) | 対話で作曲、ステムの書き出し、MV |
| [Neutone Morpho](https://neutone.jp/morpho) | 30以上の音色モデル | 可 (5つのモデル) | DAW のプラグイン、音をリアルタイムに変換 |

- そのほか: ElevenLabs の [Eleven Music](https://elevenlabs.io/music)、Stability AI の [Stable Audio](https://stableaudio.com/) など
- 料金や無料で使える範囲は頻繁に変わる → 利用前に公式情報を確認

---

## Suno

- 言葉から、歌と伴奏を含む曲を生成する
  - 曲のイメージを短い文章で伝えるだけの方法
  - **歌詞** と **スタイル** (ジャンル、楽器、声の特徴など) を書き分けるカスタムの方法
  - 日本語の歌詞にも対応、歌なしのインストゥルメンタルも作れる
- 2026年9月公開の **v6** は Pro (月額10ドル) 以上、無料プランは **v6-mini**
- 無料プラン: 1日50クレジット (約10曲)
  - サービス上で再生、共有できるだけで、**ダウンロードはできない**
  - 商用利用は不可 (あとから有料プランにしても、さかのぼって認められない)

<!-- _footer: '[Suno「Pricing」](https://suno.com/pricing)' -->

---

## Gemini (Google)

- Gemini のアプリでも、音楽を生成できる
  - 2026年2月に **Lyria 3** を追加 (当初は30秒まで)
  - 現在は **Lyria 3.5** で、最長3分
- 言葉のほか、写真をアップロードして、雰囲気に合う曲を作れる
- 歌詞は自分で書くことも、Gemini に任せることもできる
- Nano Banana (第4回) で作ったカバーアートが付く
- 利用できるのは **18歳以上**、有料プランでは上限が増える
- AIで作られたことを示す透かし **SynthID** が埋め込まれる
- 実在のアーティスト名を挙げても、まねるのではなく、似た雰囲気を参考にする程度

<!-- _footer: '[Gemini「Lyria 3.5」](https://gemini.google/overview/music-generation/) / [Google「Use Lyria 3 to create music tracks in the Gemini app」](https://blog.google/innovation-and-ai/products/gemini-app/lyria-3/)' -->

---

## Google Flow Music (Google)

- 2026年4月に公開。ProducerAI が前身で、2026年7月から Lyria 3.5
- MusicFX と MusicFX DJ のアドレスも、ここに転送される
- 「Producer」と相談しながら作曲、曲の構成も指定できる

![height:230](https://www.flowmusic.app/og-image.png)

<!-- _footer: '画像出典: [Google Flow Music](https://www.flowmusic.app/)' -->

---

## Google Flow Music の無料プランと特典

- 無料プランでも
  - 毎日クレジットが補充される
  - ダウンロード (mp3、wav、m4a) と、パートごとの音 (ステム) の書き出しができる
- **Google AI Plus** (第1回の Gemini 学割プラン) に Starter プランの特典
  - 月3,000クレジット (約600曲)
  - 商用利用可

<!-- _footer: '[Google Flow Music「Pricing」](https://www.flowmusic.app/pricing) / [Google AI Plus の特典](https://support.google.com/googleone/answer/16882689?hl=ja)' -->

---

## Neutone Morpho

- Ableton Live や Logic Pro などの DAW に組み込んで使うプラグイン
  - macOS 12 以降、Windows 10 / 11
- 無料版: 5つのモデル、7日間は全モデルを試せる
- フルバンドル: 全モデル (30以上)、99ドル (買い切り)

<!-- _footer: '[Neutone Morpho](https://neutone.jp/morpho)' -->

---

## 参考文献

<style scoped>ul { font-size: 0.82em; }</style>

- [The FADER. "Holly Herndon and Jlin's "Godmother" features an A.I. named Spawn."](https://www.thefader.com/2018/12/04/holly-herndon-jlin-godmother-spawn-ai-music-video) 2018.
- [Serpentine. "Holly Herndon & Mat Dryhurst: The Call."](https://www.serpentinegalleries.org/whats-on/holly-herndon-mat-dryhurst-the-call/) 2024.
- [Qosmo「AI DJ Project - A dialogue between AI and a human」](https://qosmo.jp/art/ai-dj-human-dj-b2b)
- [Magenta. "Hands on, with NSynth Super."](https://magenta.tensorflow.org/nsynth-super) 2018.
- [Google. "Jacob Collier and Google Labs."](https://blog.google/technology/ai/jacob-collier-labs-sessions/) 2024.
- [Guinness World Records. "First AI-assisted song to win a Grammy award."](https://www.guinnessworldrecords.com/world-records/775447-first-ai-assisted-song-to-win-a-grammy-award) 2025.
- [Music Ally. "AI-music firm Suno strikes first licensing deal… with Warner Music Group."](https://musically.com/2025/11/25/ai-music-firm-suno-strikes-first-licensing-deal-with-warner-music-group/) 2025.
- [Deezer Newsroom. "AI Music Tops 50% of Daily Uploads on Deezer."](https://newsroom-deezer.com/2026/07/ai-music-exceeds-50-percent-daily-uploads-deezer/) 2026.
- [NPR. "Spotify will now label AI creators posing as human artists."](https://www.npr.org/2026/08/13/nx-s1-5929744/spotify-labeling-ai-personas) 2026.
- [Google. "Use Lyria 3 to create music tracks in the Gemini app."](https://blog.google/innovation-and-ai/products/gemini-app/lyria-3/) 2026.
- [Ableton「AIと音楽制作：現段階の状況」](https://www.ableton.com/ja/blog/ai-and-music-making-the-state-of-play/) 2023.
