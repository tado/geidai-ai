![](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg/1280px-Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg)

<small>画像出典: Jason M. Allen「Théâtre D'opéra Spatial」(2022), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg) (Public domain)</small>

今回は「生成AI - 熱狂と拒絶のあいだで」というテーマで、生成AIと創作をめぐる現在の状況について考えます。

まず、AIを使った作品をめぐって起きた3つの出来事を手がかりに、「AIが作った」というラベルが何を見えなくしてしまうのかを考えます。続いて、生成AIが実際に何をしているのか、学習と生成のしくみ、そしてAIが「平均」へと引き寄せられる性質について、制作者の立場から最小限知っておきたいことを確認します。

後半は実習として、VS Code と GitHub Copilot をセットアップし、AIによるテキストの自動補完を使いながら文章を書く体験をします。最後に次週までの課題について説明して本日は終了です。

## スライド資料

* [スライド資料 (PDF)](https://drive.google.com/file/d/1UMHqm5N-9pCI9dJm7xwG1CMVYwUdMg2K/view?usp=sharing)

## 「AIが作った」というラベル

生成AIに熱狂する人も拒絶する人も、AIを **「ボタンを押せば作品が出てくる装置」** と見なしている点では、実は同じ前提を共有しています。この「ボタン」のイメージは、生成AIをめぐる議論のいたるところに顔を出します。今日は、このボタンを手がかりに、生成AIと創作をめぐる現在の状況を見ていきます。まずは、ひとつの絵をめぐる騒動から始めます。

### Jason Allen「Théâtre D'opéra Spatial」(2022)

![](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg/1280px-Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg)

<small>画像出典: Jason M. Allen「Théâtre D'opéra Spatial」(2022), [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg) (Public domain)</small>

2022年8月、アメリカ・コロラド州の品評会「コロラド・ステート・フェア」の美術コンテストで、Jason Allen の「Théâtre D'opéra Spatial」がデジタルアート部門の最優秀賞 (賞金$300) に選ばれました。この作品は画像生成AIの **Midjourney** で制作されたものです。Allen は作者名を「Jason M. Allen via Midjourney」と記載しており、AIの使用を隠してはいませんでした。しかし受賞の話題はSNSで拡散し、「不公平だ」「芸術の死だ」と数千件の非難が寄せられました。

* [スペース・オペラ・シアター (Wikipedia)](https://ja.wikipedia.org/wiki/%E3%82%B9%E3%83%9A%E3%83%BC%E3%82%B9%E3%83%BB%E3%82%AA%E3%83%9A%E3%83%A9%E3%83%BB%E3%82%B7%E3%82%A2%E3%82%BF%E3%83%BC)
* [The Washington Post: He used AI art from Midjourney to win a fine-arts prize. Did he cheat?](https://www.washingtonpost.com/technology/2022/09/02/midjourney-artificial-intelligence-state-fair-colorado/)

批判する側も Allen も、実は同じ問いをめぐって争っていました。**この絵を作ったのは、AIなのか、人間なのか?** 実際の制作過程を見てみると、Allen は少なくとも **624回** プロンプトを入力しては書き直し、生成された **900枚以上** の画像から候補を選び、Photoshop で細部を修正し、別のAIツールで高解像度化して作品を仕上げていました。費やした時間は **約80時間** に及びます。これはまさに「反復と選択」そのものですが、この地道な過程は、熱狂する側からも拒絶する側からも顧みられませんでした。

審査員の一人は、審査の時点ではMidjourneyがAIだとは知らなかったものの、知っていても評価は変わらなかったと語っています。作品は、作品として評価されたのです。しかしアメリカ著作権局は2023年9月、この作品の **著作権登録を拒否** しました。624回のプロンプト入力は、「作者」であることの根拠とは認められませんでした。Allen は2024年に著作権局を提訴し、現在も係争が続いています。

* [米国著作権局の決定 (PDF)](https://www.copyright.gov/rulings-filings/review-board/docs/Theatre-Dopera-Spatial.pdf)

### Boris Eldagsen「PSEUDOMNESIA: The Electrician」(2023)

![](https://www.eldagsen.com/wp-content/uploads/2022/12/eldagsen_THEELECTRICIAN-703x700.jpg)

<small>画像出典: Boris Eldagsen「PSEUDOMNESIA: The Electrician」, [eldagsen.com](https://www.eldagsen.com/sony-world-photography-awards-2023/)</small>

2023年4月、ソニー・ワールド・フォトグラフィー・アワードのクリエイティブ部門で最優秀に選ばれたドイツのアーティスト Boris Eldagsen は、**受賞を辞退** しました。受賞作は古いモノクロ写真のような肖像ですが、実際には画像生成AIの **DALL·E 2** で生成した画像でした。シリーズ名の「PSEUDOMNESIA」は「偽の記憶」を意味します。

Eldagsen は、写真コンテストがAI画像を受け入れる準備ができているかを試すために、あえて応募したのだと明かしました。AI画像は写真とは別物であり、**「プロンプトグラフィー」** と呼んで区別することを提案しています。

* [Boris Eldagsen によるステートメント](https://www.eldagsen.com/sony-world-photography-awards-2023/)

### Allen と Eldagsen

二人には共通点があります。どちらもAIを使って時間をかけて作品を作り、それが「ボタンを押すだけ」の産物ではないと考えていました。プロンプトの工夫と、画像の一部の描き直しや描き足しを組み合わせて制作している点も同じです。

一方で、作品を世界のどこに位置づけるかについて、二人の態度は正反対でした。

* **Allen**: AIと作った作品を、既存の芸術の枠組みのなかで「自分の作品」として認めさせようとした
* **Eldagsen**: 作品が自分のものであることは手放さずに、「写真」という枠組みから切り離そうとした

Eldagsen の場合、受賞を辞退するという行為そのものが、**作品の一部** になっていたとも言えます。

### 九段理江『東京都同情塔』(2024)

![](https://www.shinchosha.co.jp/images_v2/book/cover/355511/355511_xl.jpg)

<small>画像出典: 九段理江『東京都同情塔』書影, [新潮社](https://www.shinchosha.co.jp/book/355511/)</small>

2024年1月、九段理江の『東京都同情塔』が第170回 **芥川賞** を受賞しました。受賞会見で九段は「全体の5%ほどは生成AIの文章をそのまま使っている」と発言し、あたかも「AIで書いた小説」が芥川賞を獲ったかのように報じられました。しかし実際に使われたのは、作中に登場する生成AI「AI-built」の返答の一部で、分量は単行本の1ページにも満たず、地の文はすべて自分で書いたものだと九段は補足しています。

『東京都同情塔』は、新宿御苑に建てられる高層の刑務所「シンパシータワートーキョー」をめぐる近未来の物語です。差別的な響きを避けるために言葉が当たり障りのない表現へと言い換えられ、本来の意味がぼやけていく社会を描いています。AIの **なめらかで無難な言葉** は、その主題を体現する素材として、作家によって作品に取り込まれていたのです。

* [新潮社 書籍ページ](https://www.shinchosha.co.jp/book/355511/)
* [東京新聞のインタビュー](https://www.tokyo-np.co.jp/article/310036)
* [九段理江 (Wikipedia)](https://ja.wikipedia.org/wiki/%E4%B9%9D%E6%AE%B5%E7%90%86%E6%B1%9F)

### 九段理江「影の雨」(2025)

![](https://files.hakuhodo.co.jp/v=1769567244/files/user/2025/06/10d3c77562d74c9996616450d4b4dd27.jpg)

<small>画像出典: [博報堂「雑誌『広告』Vol.418 … プロンプト全文公開」](https://www.hakuhodo.co.jp/news/newsrelease/117760/)</small>

その後九段は、雑誌『広告』の依頼で「小説の95%をAIで書く」という実験に取り組みました。完成した短編「影の雨」は約4,000字ですが、そのために書かれたプロンプトは **20万字** (本文の50倍) に及びます。九段は「AIが人間の意向を汲みすぎて、指示を超えたところへ行ってくれない」というもどかしさも語っています。5日間にわたるAIとのやりとりは、全文が公開されています。

* [プロンプト全文公開のお知らせ (博報堂)](https://www.hakuhodo.co.jp/news/newsrelease/117760/)
* [インタビュー「4,000字の小説に20万字のプロンプト」(博報堂)](https://www.hakuhodo.co.jp/magazine/116524/)

### 人々は何に反応したのか

これらの出来事を並べてみると、人々が激しく反応したのは、必ずしも作品そのものに対してではなかったことに気づきます。

* Allen の作品: AIだと知らない審査員が高く評価した
* Eldagsen の作品: 写真の専門家たちの審査を経て最優秀に選ばれた
* 『東京都同情塔』: AIの文章によって評価されたわけではない

反応を引き起こしたのは、**「AIが作った」というラベル** でした。そのラベルが貼られた瞬間、80時間に及ぶ試行錯誤も、プロンプトと描き直しの積み重ねも、言葉をめぐる作家の問題意識も見えなくなってしまいました。熱狂する側も拒絶する側も、**制作者が実際に何をしていたのか** には目を向けていなかったのです。

### ボタンの手前・奥・向こう

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-1_button_zones.svg)

AIを使った制作には、三つの段階があります。

* **手前**: 何を作りたいのかを構想し、それを言葉にし、参照する素材を選び、設定を決める
* **奥**: 人間が押したボタンを受けて、AIが像や言葉を生成する
* **向こう**: 返ってきたものを吟味し、選び、手を加え、作品として世界に差し出す

熱狂する人々も拒絶する人々も、もっぱら **ボタンの奥** だけを見ていました。しかし、制作者の仕事の大半は、その **手前と向こう** にありました。そして、向こうで受け取ったものは、次の手前を変えていきます。

人々が本当に反応していたのは、作品の質だったのでしょうか、制作の手続きだったのでしょうか。それとも「芸術家」という存在の輪郭が揺らぐことへの不安だったのでしょうか。

## 生成AIは何をしているのか

「AIが描いた」「AIが書いた」という言い方は、機械のなかに **小さな画家や作家** が住んでいるかのような像を呼び起こします。反対に「AIは既存の作品を切り貼りしているだけだ」という批判は、機械のなかに **膨大な作品の倉庫** があり、断片をつなぎ合わせているかのような像を前提にしています。けれども、実際の仕組みはそのどちらとも異なります。ここでは、AIと共に作品を作るうえで知っておきたい最小限の仕組みを確認します。

### 学習 - 膨大なデータから傾向を学ぶ

生成AIの出発点は、膨大なデータからの学習です。画像生成AIの研究で広く使われた [LAION-5B](https://arxiv.org/abs/2210.08402) というデータセットには、約 **58億組** の画像と説明文が含まれています。言語モデルの場合はさらに規模が大きく、2024年に公開された [Meta Llama 3](https://ai.meta.com/blog/meta-llama-3/) は **15兆** を超えるトークンで学習されました。

ここで押さえておきたいのは、**学習はデータの保存とは違う** という点です。学習とは、「この言葉の後にはどんな言葉が来やすいか」「『夕日』という言葉には、どんな色や形が結びつきやすいか」といった傾向を、モデル内部の膨大な数値の組み合わせとして少しずつ調整していく過程です。

#### 補足: 巨大化する言語モデル

[![](https://infobeautiful4.s3.amazonaws.com/2023/05/IIB-LLMs2-decorative-1030x520-1-960x485.png)](https://informationisbeautiful.net/visualizations/the-rise-of-generative-ai-large-language-models-llms-like-chatgpt/)

<small>画像出典: [Information is Beautiful「The Rise of Generative AI Large Language Models (LLMs) like ChatGPT」](https://informationisbeautiful.net/visualizations/the-rise-of-generative-ai-large-language-models-llms-like-chatgpt/)</small>

言語モデルがどれほど急速に巨大化してきたかは、Information is Beautiful の「[Major Large Language Models (LLMs)](https://informationisbeautiful.net/visualizations/the-rise-of-generative-ai-large-language-models-llms-like-chatgpt/)」というグラフで見ることができます。主要なLLMを性能 (MMLU というベンチマークのスコア) で並べ、**円の大きさでモデルの規模 (パラメータ数)** を表したもので、モデルの規模が桁違いに広がっていることが一目で分かります。元のページは操作できるインタラクティブなグラフになっていて、各モデルの詳細を確認できるので、実際に操作してみてください。

なお、このグラフが示しているのはモデル自体の大きさ (パラメータ数) で、学習に使われたデータの量とは別の指標です。学習データ量の推移は、Our World in Data の「[Data points used to train notable artificial intelligence systems](https://ourworldindata.org/grapher/artificial-intelligence-number-training-datapoints)」で確認できます。

#### 補足: 人間とLLM、触れる言葉の量を比べる

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-3_data_scale.svg)

では、LLMが学習する言葉の量は、一人の人間が触れる言葉の量と比べてどれくらいなのでしょうか。上の図は、それぞれの量を円の面積で表したものです。

一人の人間が一生のあいだに触れる言葉の量は、多めに見積もっても **約10億語** 程度です。子どもの言語環境を録音して調べた研究によると、子どもが1年間に耳にする言葉は200万〜700万語程度とされています ([Gilkerson et al. 2017](https://doi.org/10.1044/2016_AJSLP-15-0169))。これを80年分に延ばすと約1.6億〜5.6億語になり、読書などで触れる言葉を加えても10億語には届きません。一方、AIモデルの学習量を調べている研究機関 [Epoch AI](https://epoch.ai/data/ai-models) の推定によると、2026年10月時点で学習データ量が最大のモデルは、DeepSeek V4.1 Flash (2026年9月公開) などの **45兆トークン** です。また、2025年に公開された Qwen3 は **36兆トークン** ([Qwen3 Technical Report](https://arxiv.org/abs/2505.09388))、2024年の Llama 3 は **15兆トークン** で学習されています。最大のモデルの学習データは、人間の一生分を多めに見積もった量のさらに **約4.5万倍** にあたり、同じ縮尺で描くと、人間の円は直径わずか1.6ピクセルの「点」にしかなりません。一生のあいだに触れる言葉を約4.5万人分集めて、ようやく最大のモデルの学習データ量に届くことになります。

それでも人間は、このわずかな量の言葉から言語を身につけ、自分の言葉で考え、表現します。AIの「学習」と人間の「学び」が、量の面でもまったく異なるものであることを、この図から感じ取ってみてください。

<small>※ 円の面積をデータ量に比例させています。人間の値は上記の研究をもとにした概算です。Thinking Machines の Inkling も、Epoch AI の推定では同じ45兆トークンです。トークンと語は厳密には異なる単位です (英語では1トークン ≒ 0.75語)。</small>

### 学習 - 圧縮された文化的記憶

![](https://upload.wikimedia.org/wikipedia/commons/8/82/Astronaut_Riding_a_Horse_%28SD3.5%29.webp)

<small>画像出典: Stable Diffusion 3.5 による生成画像の例, [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Astronaut_Riding_a_Horse_%28SD3.5%29.webp) (Public domain)</small>

Stable Diffusion の初期モデルは、約 **23億組** の画像と説明文で学習されましたが、完成したモデルは **数ギガバイト** ほどにすぎません。画像1枚あたりに換算すれば **数バイトにも満たない** 量です。これでは個々の画像をそのまま保存しておくことはできません。モデルが保持しているのは、膨大な作品群から抽出された **傾向を極度に圧縮したもの**、つまり膨大な文化的記憶を内包した「物質」です。

* [Stable Diffusion (Wikipedia)](https://ja.wikipedia.org/wiki/Stable_Diffusion)
* [Stable Diffusion v1-4 モデルカード](https://huggingface.co/CompVis/stable-diffusion-v1-4)

### 学習 - 記憶と再現のあいだ

ただし、話はそれほど単純ではありません。学習データのなかで何度も重複して現れる画像、たとえば有名な絵画や広く出回った写真は、ほぼそのまま再現されてしまうことがあります。重複の多い35万件を調べた研究では、元の画像とほとんど見分けのつかない画像が **約100件** 生成されました ([Carlini et al. 2023](https://arxiv.org/abs/2301.13188))。AIの記憶は、**「何も覚えていない」と「すべてを覚えている」の中間** のどこかにあります。この曖昧さが、著作権をめぐる議論を複雑にしています。

### 生成のしくみ (1) - 言語モデル

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-2_next_word_probability.svg)

ChatGPT のような言語モデルは、与えられた文章に続く **「次の言葉」を確率で予測** します。そのなかから一つを選んで文章に加え、また次の言葉を予測します。この単純な手順を何千回と繰り返すことで、長い文章が紡がれていきます。

### 体験してみよう: Transformer Explainer

[![](https://img.youtube.com/vi/TFUc41G2ikY/maxresdefault.jpg)](https://poloclub.github.io/transformer-explainer/)

<small>画像出典: [Transformer Explainer デモ動画 (YouTube)](https://youtu.be/TFUc41G2ikY) (Georgia Institute of Technology)</small>

[Transformer Explainer](https://poloclub.github.io/transformer-explainer/) は、ジョージア工科大学のチームが開発した、言語モデルのしくみを可視化するツールです。ブラウザ上で実際の言語モデル (**GPT-2**) が動いていて、好きな文章を入力すると、内部でどのような計算が行われ、**次に来る言葉の候補とその確率** がどのように決まるのかを、リアルタイムに見ることができます。

画面は、大きく次のような流れで構成されています。

* **Embedding**: 入力した文章を単語 (トークン) に分け、数値のベクトルに変換する
* **Self-Attention**: 各単語が、文中の他のどの単語に注目しているかを計算する。文脈に応じて、同じ単語でも意味の重みが変わる
* **Probabilities**: 最後に、次に来る言葉の候補それぞれに確率を割り当てる

画面上部の **Temperature** (温度) や **Top-k / Top-p** の設定を変えると、選ばれる言葉の傾向が変わります。Temperature を下げると、最も確率の高い、ありふれた言葉ばかりが選ばれるようになります。反対に Temperature を上げると、確率の低い「裾野」の言葉も選ばれるようになり、意外な展開や文章の破綻が増えていきます。このあと説明する **「平均への引力」** を、自分の手で確かめてみましょう。

* [Transformer Explainer](https://poloclub.github.io/transformer-explainer/)
* [デモ動画 (YouTube)](https://youtu.be/TFUc41G2ikY)
* [GitHub リポジトリ](https://github.com/poloclub/transformer-explainer)
* [論文: Transformer Explainer (arXiv)](https://arxiv.org/abs/2408.04619)

### 参考: マンガでわかるAIの仕組み 第1話

[![](https://cz-cdn.shoeisha.jp/static/images/article/24575/ogp1200x630_manga_ai.png)](https://codezine.jp/article/detail/24575)

<small>画像出典: [CodeZine「ChatGPTの心臓部『Transformer』って何がすごいの? #マンガでわかるAIの仕組み 第1話」](https://codezine.jp/article/detail/24575)</small>

Transformer のしくみをもう少し知りたい人には、CodeZine の Web 連載「マンガでわかるAIの仕組み」の第1話「[ChatGPTの心臓部『Transformer』って何がすごいの?](https://codezine.jp/article/detail/24575)」(2026年6月公開、漫画と解説: 湊川あい、監修: 西見公宏) がおすすめです。

私たちが普段何気なくやっている「文脈を読む」ことのすごさを入り口に、AI界に革命を起こした Transformer の秘密をマンガで分かりやすく解説しています。文中のすべての単語を同時に見渡し、どの単語に注目すべきかを計算する **Attention (注意機構)** や、言葉を数値に変える **エンコーダ** と、次に来る言葉を予測する **デコーダ** の役割分担など、Transformer Explainer の画面で見た仕組みを、言葉とマンガで確認することができます。

* [ChatGPTの心臓部『Transformer』って何がすごいの? #マンガでわかるAIの仕組み 第1話 (CodeZine)](https://codezine.jp/article/detail/24575)

### 生成のしくみ (2) - 拡散モデル

画像生成AIで広く使われているのが、拡散モデルの方式です ([Rombach et al. 2022](https://arxiv.org/abs/2112.10752))。拡散モデルは学習の際、画像に少しずつノイズを加えて砂嵐のような状態にし、**その逆 (ノイズを取り除いて元に戻す) 方法を学びます**。生成するときには、まったくのノイズから出発し、プロンプトを手がかりにノイズを少しずつ取り除いていきます。すると、砂嵐のなかから徐々に像が浮かび上がってきます。

**シード値** とは、この出発点となるノイズの模様を決める数値のことです。同じプロンプトでもシード値が違えば、まったく別の画像が現れます。ボタンを押すことは、**シード値というサイコロを振る** ことに近いと言えます。音楽や動画の生成も、基本的にはこれらの考え方の延長にあります。

* [拡散モデル (Wikipedia)](https://ja.wikipedia.org/wiki/%E6%8B%A1%E6%95%A3%E3%83%A2%E3%83%87%E3%83%AB)

### 体験してみよう: Diffusion Explainer

[![](https://img.youtube.com/vi/Zg4gxdIWDds/maxresdefault.jpg)](https://poloclub.github.io/diffusion-explainer/)

<small>画像出典: [Diffusion Explainer デモ動画 (YouTube)](https://youtu.be/Zg4gxdIWDds) (Georgia Institute of Technology)</small>

[Diffusion Explainer](https://poloclub.github.io/diffusion-explainer/) は、Transformer Explainer と同じジョージア工科大学のチームが開発した、**Stable Diffusion** がプロンプトから画像を生成する過程を可視化するツールです。ブラウザで開くだけで、インストールやプログラミングの知識、GPU がなくても、用意されたプロンプトから選んで試すことができます。

画面は、大きく次のような流れで構成されています。

* **Text Representation Generator**: プロンプトの文章を、画像生成の手がかりとなる数値に変換する
* **Image Representation Refiner**: ランダムなノイズから出発し、手がかりをもとにノイズを少しずつ取り除いていく。**Timestep** のスライダーを動かすと、砂嵐のなかから像が浮かび上がる過程を1ステップずつ見ることができる

**Random Seed** (シード値) を変えると、同じプロンプトでもまったく別の画像が生成されます。上で説明した「ボタンを押すことは、シード値というサイコロを振ることに近い」ということを、実際に確かめてみましょう。また **Guidance Scale** を変えると、生成される画像がプロンプトにどれだけ忠実に従うかが変わります。プロンプトの言葉を少しだけ変えて、生成される2つの画像を比べることもできます。

* [Diffusion Explainer](https://poloclub.github.io/diffusion-explainer/)
* [デモ動画 (YouTube)](https://youtu.be/Zg4gxdIWDds)
* [GitHub リポジトリ](https://github.com/poloclub/diffusion-explainer)
* [論文: Diffusion Explainer (arXiv)](https://arxiv.org/abs/2305.03509)

### 平均への引力 (1) - 確率の高い方へ

言語モデルも拡散モデルも、**確率の高い方へ** と進むことで生成を行います。確率が高いとは、学習データのなかで頻繁に見かけた、ということです。「夕日」と打ち込めば、水平線に沈む太陽と橙色の空という **典型的な夕日** が現れます。最もありそうな言葉を選び続ければ、最もありふれた表現に行き着きます。偶然性を高める設定もありますが、強めすぎると文章や画像が破綻してしまいます。めずらしいもの、変わったものは **確率の低い裾野** にあり、そこはAIが最も苦手とする領域です。

### 平均への引力 (2) - 人間の好みに合わせる調整

多くのサービスでは、学習を終えたモデルに対して、もう一段階の調整が加えられています ([Ouyang et al. 2022](https://arxiv.org/abs/2203.02155))。人間がAIの出力を評価し、高く評価された出力を出しやすいようにモデルを調整することで、AIは指示に従い、礼儀正しく、安全な応答を返すようになりました。しかしその代償として、**出力の多様性が大きく失われる** ことが報告されています ([Kirk et al. 2024](https://arxiv.org/abs/2310.06452))。

画像生成AIにも、多くの人が美しいと感じる方向への調整が施されています。Midjourney には、この自動的な「美化」を弱める [「Raw」モード](https://docs.midjourney.com/docs/style) が用意されています。いわゆる **「AI臭さ」**、つまりつややかな質感、劇的な光、隙のない構図は、「多くの人が好むものの平均」でもあるのです。

### AIの誤り

AIは奇妙な誤りも犯します。初期の画像生成AIが描く人間の手には、しばしば6本や7本の指が生えていました。言語モデルは、存在しない論文や判例を、もっともらしい体裁で引用してみせます。

こうした誤りは、AIが **意味ではなく統計的な近さ** によって要素を結びつけていることから生じます。AIの内部では、言葉や画像の特徴が巨大な空間のなかの位置として表され、似たものは近くに、異なるものは遠くに置かれています。AIは手に指が5本あることを「知っている」わけではありません。

人間から見れば誤りでも、AIから見れば学習データの統計的な近さを忠実に反映した結果です。そこには、人類が残したデータに潜む、**普段は意識されない結びつきが露出** しています。

### 制作者の立場から整理すると

1. 生成AIは、機械のなかの小さな芸術家でも、作品の切り貼り装置でもない。膨大な文化的記憶から抽出された傾向の、**圧縮された塊** である
2. 平均へと引き寄せられる性質は、確率にもとづく生成と、人間の好みに合わせる調整の両方によって、**AIの構造そのものに組み込まれている**。平均から抜け出すには、人間の側の粘り強い働きかけが必要になる (Allen の624回のプロンプト、九段の20万字のプロンプト)
3. AIの誤りは、学習データに含まれる思いがけない結びつきを表に出す。それを手がかりとして生かせるかどうかは、**使い手しだい** である

## 実習: AIと共創しながら文章を作成する

### AIとの共創の準備: VS Code と GitHub Copilot のセットアップ

後半の実習では、文章を書きながら、その続きをAIがリアルタイムに提案する環境をつくります。エディタには **Visual Studio Code** (VS Code) を、AIには **GitHub Copilot** の **補完機能** (書きかけの文章の続きを提案する機能) を使います。VS Code 1.116 以降は本体に Copilot が標準搭載されているので、拡張機能のインストールは不要です。

準備の流れは以下のとおりです。

1. VS Code をインストール
2. GitHub アカウントを作成
3. VS Code で AI 機能を有効化
4. GitHub でサインインして認可 (Copilot Free に自動登録)
5. Markdown で補完を有効にする
6. テキスト補完を試す

### 1. VS Code をインストール

公式サイト [https://code.visualstudio.com/](https://code.visualstudio.com/) からダウンロードします。

| OS | インストール手順 |
| :--- | :--- |
| **Windows** | ダウンロードしたインストーラを実行（設定はデフォルトのままで OK） |
| **macOS** | zip を展開し、Visual Studio Code.app を「アプリケーション」フォルダへ移動 |

メニューは最初は英語で表示されます。ここでも英語のUI名 (Settings, Accounts など) で説明します。

### 2. GitHub アカウントを作成

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/github-email-verify.png)

<small>画像出典: [GitHub Docs](https://docs.github.com/) (© GitHub, CC BY 4.0)</small>

[https://github.com/](https://github.com/) を開いて **Sign up** から登録します (Google アカウントでも登録可能)。メールアドレス・パスワード・ユーザー名・国/地域を入力し、パズルを解いたら、メールに届く確認コードを入力して **メール認証を完了** させます。認証状態は Settings > Emails で確認でき、Unverified になっている場合は確認メールを再送できます。

### 3. VS Code で AI 機能を有効にする

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/vscode-enable-ai-features.png)

<small>画像出典: [Visual Studio Code Docs](https://code.visualstudio.com/docs) (© Microsoft, CC BY 3.0 US)</small>

VS Code を起動し、次のどちらかをクリックします (図の赤枠を参照)。

* **方法 A (推奨)**: タイトルバー右上の **Sign In**
* **方法 B**: 右下ステータスバーの Copilot アイコン → **Use AI Features**

### 4. GitHub でサインインして認可する

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/copilot-sign-in.png)

<small>画像出典: [Visual Studio Code Docs](https://code.visualstudio.com/docs) (© Microsoft, CC BY 3.0 US)</small>

サインイン方法として **Continue with GitHub** を選びます。自動でブラウザが開くので、手順2で作ったアカウントでログインします。Copilot の契約がないアカウントは、自動的に **Copilot Free** (無料プラン) に登録されます。クレジットカードの登録などは一切不要です。

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/github-authorize-app.png)

<small>画像出典: [GitHub Docs](https://docs.github.com/) (© GitHub, CC BY 4.0)</small>

VS Code からのアクセス許可画面が出たら、緑の **Authorize** ボタンを押します (図は画面の例です。実際はアプリ名が Visual Studio Code と表示されます)。「Visual Studio Code を開きますか?」と聞かれたら許可してエディタに戻ります。右下の Copilot アイコンを開き、プラン名 (Copilot Free など) が表示されていれば完了です。

### 5. Markdown で補完を有効にする

今回はプログラムではなく **文章** を書くので、Markdown ファイル (.md) を使います。Copilot の補完は、初期設定では **Markdown やプレーンテキストでは無効** になっている場合があります。.md ファイルを開いた状態で右下ステータスバーの Copilot アイコンをクリックし、メニューから **Markdown** での補完を有効にしてください。

設定ファイル (settings.json) で指定する場合は、以下のように記述します。

```json
"github.copilot.enable": {
  "*": true,
  "markdown": true,
  "plaintext": true
}
```

### 6. テキスト補完を試す

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/inline-suggestion.png)

<small>画像出典: [Visual Studio Code Docs](https://code.visualstudio.com/docs) (© Microsoft, CC BY 3.0 US)</small>

File > New Text File で新規ファイルを作り、story.md などの名前で保存します。文章を書き始めると、続きの文章が **薄いグレー (ゴーストテキスト)** で提案されます (図はプログラムの例ですが、文章でも同じようにグレーの文字で続きが提案されます)。

* <kbd>Tab</kbd>: **提案を確定**
* <kbd>Esc</kbd>: **提案を破棄**

試しに # 雨の日の図書館 と見出しを書き、1行目を書き始めて少し待ってみましょう。

### 補完をコントロールする

提案を **全部は受け入れない** ことも、共創の大切な判断です。以下の操作を使うと、AIの提案を細かくコントロールできます。

* **単語ごとに確定**: Windows <kbd>Ctrl</kbd> + <kbd>→</kbd> / macOS <kbd>⌘ Command</kbd> + <kbd>→</kbd>
  * 気に入った部分までだけ受け入れ、その先は自分で書く
* **別の候補を見る**: Windows <kbd>Alt</kbd> + <kbd>]</kbd> / macOS <kbd>⌥ Option</kbd> + <kbd>]</kbd>
  * 提案にマウスを重ねると、候補を切り替えるツールバーも表示される

提案は、直前までの文章 (= プロンプト) によって変わります。書き出しの言葉、文体、見出しを変えると、続きの方向も変わります。

### 使用量を確認する

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/copilot-status-dashboard.png)

<small>画像出典: [Visual Studio Code Docs](https://code.visualstudio.com/docs) (© Microsoft, CC BY 3.0 US)</small>

右下ステータスバーの Copilot アイコンをクリックすると、今月の利用枠を何%消費したかが表示されます (図は有料プランの例です。Free では補完の使用量も表示されます)。Copilot Free の月間上限は以下のとおりです。実習に入る前に、残り枠を確認しておきましょう。

* **補完**: 2,000回まで (確定ベース)
* **チャット**: AIクレジットの範囲内 (月50回程度が目安)

### 上限を気にせず使うには?

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/education-upload-proof.png)

<small>画像出典: [GitHub Docs](https://docs.github.com/) (© GitHub, CC BY 4.0)</small>

**GitHub Student Developer Pack** で学生認証を行うと、有料相当の **Copilot Student** を **無料** で利用できます。

1. [https://github.com/settings/education/benefits](https://github.com/settings/education/benefits) にアクセス
2. 大学のメールアカウント (ac.jp) を登録し、学生証の写真等を提出して申請
3. 認証完了後、同ページで Copilot Student を有効化

認証の反映には数日かかる場合があります。詳しくは [GitHub Docs「Copilot Student の設定」](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students) を参照してください。

### データの扱いとプライバシー設定

自分の文章を安心して書くために、初期設定と変更方法を把握しておきましょう。Copilot Free の初期設定では、テレメトリ (製品改善のためのデータ送信) が **有効**、公開コードと一致する提案 (Public code suggestions) が **許可** になっています。より厳格に変更したい場合は、以下のように設定します。

* **VS Code 設定**: telemetry.telemetryLevel を検索して off に設定
* **GitHub 設定**: [https://github.com/settings/copilot](https://github.com/settings/copilot) を開き、
  * 「Suggestions matching public code」を **Block** に変更
  * 「Allow GitHub to use my data for AI model training」を **Disabled** に変更

個人情報や、未発表の大切な原稿は入力しないように注意してください。

### うまくいかないとき

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/vscode-accounts-menu.png)

<small>画像出典: [Visual Studio Code Docs](https://code.visualstudio.com/docs) (© Microsoft, CC BY 3.0 US)</small>

* **Sign In ボタンや Copilot アイコンが見当たらない**
  * 左下の人型アイコン (Accounts) → **Sign in with GitHub to use GitHub Copilot**
  * VS Code のバージョンを確認 (1.116 以降が必要。古ければアップデート)
* **別のアカウントでサインインしてしまった**
  * Accounts メニューから **Sign out** して正しいアカウントで入り直す
* **文章の補完が出ない**
  * ファイルを .md 付きで保存しているか確認
  * Markdown での補完が有効になっているか確認 (手順5)

## 関連リンク

* [Visual Studio Code](https://code.visualstudio.com/)
* [GitHub](https://github.com/)
* [GitHub Copilot](https://github.com/features/copilot)
* [GitHub Docs「Copilot Student の設定」](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students)
* [米国著作権局「Théâtre D'opéra Spatial」の決定 (PDF)](https://www.copyright.gov/rulings-filings/review-board/docs/Theatre-Dopera-Spatial.pdf)
* [Boris Eldagsen「Sony World Photography Awards 2023」](https://www.eldagsen.com/sony-world-photography-awards-2023/)
* [博報堂『影の雨』プロンプト全文公開](https://www.hakuhodo.co.jp/news/newsrelease/117760/)

## 次週までの課題

### AIと共創するレポート「創作において人工知能とは...」

VS Code と GitHub Copilot の **テキスト補完** を使って、レポートを書いてください。書き出しは、必ず次の一文から始めます。

```markdown
# 創作において人工知能とは

創作において人工知能とは、
```

この続きを、AIの補完と自分の言葉を往復させながら書き進めます。分量の目安は **1,200〜2,000字程度** です。AIの提案をそのまま並べるのではなく、**採用・修正・拒否の判断** を重ねて、自分のレポートに仕上げてください。

### 進め方

1. report.md という名前で新しいファイルを作り、書き出しの一文を入力する
2. 少し待って、グレーの文字で提案される続きを読む
3. 提案を **全部確定する / 単語ごとに確定する / 破棄して自分で書く** を選ぶ
   * <kbd>Tab</kbd>: 確定 / <kbd>Ctrl</kbd>(<kbd>⌘</kbd>) + <kbd>→</kbd>: 単語ごとに確定 / <kbd>Esc</kbd>: 破棄
4. 方向を変えたいときは、自分で数語を書き足してから、再び提案を待つ
   * 書き出しの言葉や文体を変えると、続きの方向も変わる
5. 今日の講義の内容 (ボタンの手前・奥・向こう、平均への引力など) も手がかりにする

### 提出方法

* **提出物**: テキストファイル (report.md)
  * ファイル名は 学籍番号_氏名.md に変更して提出
* **提出先**: (提出先を記入)
* **締切**: 次回の授業の前日まで

以下の点に注意してください。

* 書き出しの一文「創作において人工知能とは、」から始めること
* 個人情報や、他人に見せたくない内容は入力しないこと

## 参考文献

* Roose, Kevin. "An A.I.-Generated Picture Won an Art Prize. Artists Aren't Happy." The New York Times, 2022.
* [CBS Colorado. "Artificial intelligence artwork wins 1st place at Colorado State Fair..."](https://www.cbsnews.com/colorado/news/ai-created-art-exhibit-first-place-colorado-state-fair-causing-controversy-jason-allen/) 2022.
* [Harwell, Drew. "He used AI art from Midjourney to win a fine-arts prize. Did he cheat?"](https://www.washingtonpost.com/technology/2022/09/02/midjourney-artificial-intelligence-state-fair-colorado/) The Washington Post, 2022.
* [U.S. Copyright Office Review Board. "Théâtre D'opéra Spatial."](https://www.copyright.gov/rulings-filings/review-board/docs/Theatre-Dopera-Spatial.pdf) 2023.
* [Eldagsen, Boris. "Sony World Photography Awards 2023."](https://www.eldagsen.com/sony-world-photography-awards-2023/)
* 九段理江 著. 東京都同情塔, 新潮社, 2024.
* [東京新聞. 芥川賞作家・九段理江さん「受賞作の5％は生成AIの文章」発言の誤解と真意](https://www.tokyo-np.co.jp/article/310036), 2024.
* [博報堂. 4,000字の小説に20万字のプロンプト](https://www.hakuhodo.co.jp/magazine/116524/), 2025.
* [博報堂. 『影の雨』プロンプト全文公開](https://www.hakuhodo.co.jp/news/newsrelease/117760/), 2025.
* [Schuhmann, Christoph, et al. "LAION-5B."](https://arxiv.org/abs/2210.08402) NeurIPS 2022.
* [Meta. "Introducing Meta Llama 3."](https://ai.meta.com/blog/meta-llama-3/) 2024.
* [CompVis. "Stable Diffusion v1-4 Model Card."](https://huggingface.co/CompVis/stable-diffusion-v1-4)
* [Carlini, Nicholas, et al. "Extracting Training Data from Diffusion Models."](https://arxiv.org/abs/2301.13188) 2023.
* [Rombach, Robin, et al. "High-Resolution Image Synthesis with Latent Diffusion Models."](https://arxiv.org/abs/2112.10752) CVPR 2022.
* [Ouyang, Long, et al. "Training Language Models to Follow Instructions with Human Feedback."](https://arxiv.org/abs/2203.02155) NeurIPS 2022.
* [Kirk, Robert, et al. "Understanding the Effects of RLHF on LLM Generalisation and Diversity."](https://arxiv.org/abs/2310.06452) ICLR 2024.
* [Midjourney. "Raw."](https://docs.midjourney.com/docs/style)
* [Cho, Aeree, et al. "Transformer Explainer: Learning LLM Transformers with Interactive Visual Explanation and Experimentation."](https://arxiv.org/abs/2408.04619) CHI 2026.
* [Lee, Seongmin, et al. "Diffusion Explainer: Visual Explanation for Text-to-image Stable Diffusion."](https://arxiv.org/abs/2305.03509) 2023.
