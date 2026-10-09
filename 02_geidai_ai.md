---
marp: true
theme: tadokoro
paginate: true
---

# 人工知能と創作<br>熱狂と拒絶のあいだで
東京藝術大学芸術情報センター
田所 淳

---

## 今日の内容

- 「AIが作った」というラベル
  - Allen / Eldagsen / 九段理江、3つの出来事から考える
  - ボタンの手前・奥・向こう
- 生成AIは何をしているのか
  - 学習、生成のしくみ、平均への引力、誤り
- 実習: AIと共創しながら文章を作成する
  - VS Code と GitHub Copilot のセットアップ
  - テキスト補完を試す
- 次週までの課題
  - AIと共創するレポート「創作において人工知能とは...」

---

<!-- _class: bigtxt -->

# 「AIが作った」というラベル

---

## 「ボタン」のイメージ

- 生成AIに熱狂する人も拒絶する人も、AIを **「ボタンを押せば作品が出てくる装置」** と見なしている
- この「ボタン」のイメージは、生成AIをめぐる議論のいたるところに顔を出す
- 今日は、このボタンを手がかりに、生成AIと創作をめぐる現在の状況を見ていく
- まずは、ひとつの絵をめぐる騒動から

---

## Jason Allen「Théâtre D'opéra Spatial」(2022)

![bg right:45% contain](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg/1280px-Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg)

- 2022年8月、コロラド・ステート・フェアの美術コンテスト
- デジタルアート部門で**最優秀賞** (賞金$300)
- 画像生成AI **Midjourney** で制作
- 作者名は「Jason M. Allen via Midjourney」と記載、AIの使用は隠さず
- SNSで拡散し「不公平だ」「芸術の死だ」と数千件の非難

<!-- _footer: '[解説 (Wikipedia)](https://ja.wikipedia.org/wiki/%E3%82%B9%E3%83%9A%E3%83%BC%E3%82%B9%E3%83%BB%E3%82%AA%E3%83%9A%E3%83%A9%E3%83%BB%E3%82%B7%E3%82%A2%E3%82%BF%E3%83%BC) / [The Washington Post](https://www.washingtonpost.com/technology/2022/09/02/midjourney-artificial-intelligence-state-fair-colorado/) / [画像出典](https://commons.wikimedia.org/wiki/File:Th%C3%A9%C3%A2tre_D%E2%80%99op%C3%A9ra_Spatial.jpg)' -->

---

## 「ボタンを押しただけ」だったのか?

- 批判する側も Allen も、同じ問いをめぐって争っていた
- **この絵を作ったのは、AIなのか、人間なのか?**
- 実際の制作過程
  - 少なくとも **624回** プロンプトを入力し、書き直す
  - 生成された **900枚以上** の画像から候補を選ぶ
  - Photoshop で細部を修正、別のAIツールで高解像度化
  - 費やした時間は **約80時間**
- 「反復と選択」そのもの
- しかし、この地道な過程は熱狂する側からも拒絶する側からも顧みられなかった

---

## 作品の評価と著作権

- 審査員の一人: 審査時にMidjourneyがAIだとは知らなかったが、知っていても評価は変わらなかった → **作品は、作品として評価された**
- しかし、アメリカ著作権局は2023年9月に **著作権登録を拒否**
  - 624回のプロンプト入力は「作者」であることの根拠とは認められなかった
  - Allen は2024年に著作権局を提訴、係争中
- [著作権局の決定 (PDF)](https://www.copyright.gov/rulings-filings/review-board/docs/Theatre-Dopera-Spatial.pdf)

---

## Boris Eldagsen「PSEUDOMNESIA: The Electrician」(2023)

![bg right:40% contain](https://www.eldagsen.com/wp-content/uploads/2022/12/eldagsen_THEELECTRICIAN-703x700.jpg)

- 2023年4月、ソニー・ワールド・フォトグラフィー・アワード
- クリエイティブ部門で最優秀に選出、**受賞を辞退**
- 古いモノクロ写真のような肖像だが、**DALL·E 2** で生成した画像 (「PSEUDOMNESIA」= 偽の記憶)
- 写真コンテストがAI画像を受け入れる準備ができているかを試すために応募
  - AI画像は写真とは別物
  - **「プロンプトグラフィー」** と呼ぶことを提案

<!-- _footer: '[Boris Eldagsen によるステートメント](https://www.eldagsen.com/sony-world-photography-awards-2023/)' -->

---

## AllenとEldagsen

共通点：
- どちらもAIを使って時間をかけて作品を作り「ボタンを押すだけ」の産物ではない
- プロンプトの工夫と、画像の一部の描き直し・描き足しを組み合わせて制作

違い:
- **Allen**: AIと作った作品を、既存の芸術の枠組みのなかで「自分の作品」
として認めさせようとした
- **Eldagsen**: 作品が自分のものであることは手放さず「写真」という枠組みから切り離そうとした
  - 受賞を辞退するという行為そのものが、**作品の一部** になっていた

---

## 九段理江『東京都同情塔』(2024)

![bg right:30% contain](https://www.shinchosha.co.jp/images_v2/book/cover/355511/355511_xl.jpg)

- 2024年1月、第170回 **芥川賞** 受賞
- 受賞会見で「全体の5%ほどは生成AIの文章をそのまま使っている」と発言
- 「AIで書いた小説」が芥川賞を獲ったかのように報じられた
- 実際には…
  - 作中に登場する生成AI「AI-built」の返答の一部
  - 分量は単行本の1ページにも満たず、地の文はすべて自分で書いた

<!-- _footer: '[新潮社 書籍ページ](https://www.shinchosha.co.jp/book/355511/) / [東京新聞のインタビュー](https://www.tokyo-np.co.jp/article/310036) / [九段理江 (Wikipedia)](https://ja.wikipedia.org/wiki/%E4%B9%9D%E6%AE%B5%E7%90%86%E6%B1%9F)' -->

---

## 作品の主題としてのAIの言葉

- 『東京都同情塔』
  - 新宿御苑に建てられる高層の刑務所「シンパシータワートーキョー」をめぐる近未来の物語
  - 差別的な響きを避けるために言葉が当たり障りのない表現へと言い換えられ、本来の意味がぼやけていく社会を描く
- AIの **なめらかで無難な言葉** は、その主題を体現する素材として、作家によって作品に取り込まれていた

---

## 九段理江「影の雨」(2025)

![height:260](https://files.hakuhodo.co.jp/v=1769567244/files/user/2025/06/10d3c77562d74c9996616450d4b4dd27.jpg) ![height:260](https://files.hakuhodo.co.jp/v=1769566571/files/user/2025/04/H20250424_zassikoukoku_OGP.jpg)

- 雑誌『広告』の依頼で「小説の95%をAIで書く」実験
  - 約4,000字の短編のために、**20万字のプロンプト** (本文の50倍)
  - 「AIが人間の意向を汲みすぎて、指示を超えたところへ行ってくれない」
  - 5日間にわたるAIとのやりとりを全文公開

<!-- _footer: '[プロンプト全文公開のお知らせ](https://www.hakuhodo.co.jp/news/newsrelease/117760/) / [インタビュー「4,000字の小説に20万字のプロンプト」](https://www.hakuhodo.co.jp/magazine/116524/)' -->

---

## 人々は何に反応したのか

- 人々が激しく反応したのは、必ずしも作品そのものに対してではなかった
  - Allen の作品: AIだと知らない審査員が高く評価
  - Eldagsen の作品: 写真の専門家たちの審査を経て最優秀に
  - 『東京都同情塔』: AIの文章によって評価されたわけではない
- 反応を引き起こしたのは、**「AIが作った」というラベル**
- ラベルが貼られた瞬間、見えなくなったもの
  - 80時間に及ぶ試行錯誤、プロンプトと描き直しの積み重ね、言葉をめぐる作家の問題意識
- 熱狂する側も拒絶する側も、**制作者が実際に何をしていたのか** には目を向けていなかった

---

## ボタンの手前・奥・向こう

![height:330](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-1_button_zones.svg)

- **手前**: 構想し、言葉にし、素材を選び、設定を決める
- **奥**: AIが像や言葉を生成する
- **向こう**: 吟味し、選び、手を加え、作品として世界に差し出す

---

## 制作者の仕事はどこにあるのか

- 熱狂する人々も拒絶する人々も、もっぱら **ボタンの奥** だけを見ていた
- しかし、制作者の仕事の大半は、その **手前と向こう** にあった
- そして、向こうで受け取ったものは、次の手前を変えていく
- 人々が本当に反応していたのは…
  - 作品の質?
  - 制作の手続き?
  - それとも「芸術家」という存在の輪郭が揺らぐことへの不安?

---

<!-- _class: bigtxt -->

# 生成AIは何をしているのか

---

## AIのなかに何があるのか?

- 「AIが描いた」「AIが書いた」
  - → 機械のなかに **小さな画家や作家** が住んでいるかのような像
- 「AIは既存の作品を切り貼りしているだけだ」
  - → 機械のなかに **膨大な作品の倉庫** があり、断片をつなぎ合わせているかのような像
- 実際の仕組みは、そのどちらとも異なる
- AIと共に作品を作るうえで知っておきたい最小限の仕組みを確認する

---

## 学習 - 膨大なデータから傾向を学ぶ

- 画像生成AI: 画像と説明文の組を大量に学習
  - [LAION-5B](https://arxiv.org/abs/2210.08402): 約 **58億組** の画像と説明文
- 言語モデル: さらに大規模
  - [Meta Llama 3](https://ai.meta.com/blog/meta-llama-3/) (2024): **15兆** を超えるトークンで学習
- **学習はデータの保存とは違う**
  - 「この言葉の後にはどんな言葉が来やすいか」
  - 「『夕日』には、どんな色や形が結びつきやすいか」
  - といった傾向を、モデル内部の膨大な数値の組み合わせとして少しずつ調整していく

---

## 補足: 巨大化する言語モデル

[![height:300](https://infobeautiful4.s3.amazonaws.com/2023/05/IIB-LLMs2-decorative-1030x520-1-960x485.png)](https://informationisbeautiful.net/visualizations/the-rise-of-generative-ai-large-language-models-llms-like-chatgpt/)

- Information is Beautiful「Major Large Language Models (LLMs)」
  - 主要なLLMを性能 (MMLU ベンチマークのスコア) で並べ、**円の大きさでモデルの規模 (パラメータ数)** を表したグラフ
  - モデルの規模が桁違いに広がっていることが一目で分かる
  - 元のページは操作できるインタラクティブなグラフで、各モデルの詳細を確認できる

<!-- _footer: '画像出典: [Information is Beautiful「The Rise of Generative AI Large Language Models (LLMs) like ChatGPT」](https://informationisbeautiful.net/visualizations/the-rise-of-generative-ai-large-language-models-llms-like-chatgpt/)' -->

---

## 補足: 人間とLLM、触れる言葉の量を比べる

![height:430](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-3_data_scale.svg)

<!-- _footer: '出典: [Qwen3 Technical Report](https://arxiv.org/abs/2505.09388) / [Meta Llama 3](https://ai.meta.com/blog/meta-llama-3/) / 人間の値は [Gilkerson et al. 2017](https://doi.org/10.1044/2016_AJSLP-15-0169) をもとにした概算' -->

---

## 学習 - 圧縮された文化的記憶

![bg right:35% contain](https://upload.wikimedia.org/wikipedia/commons/8/82/Astronaut_Riding_a_Horse_%28SD3.5%29.webp)

- Stable Diffusion の初期モデル
  - 約 **23億組** の画像と説明文で学習
  - 完成したモデルは **数ギガバイト** ほど
  - 画像1枚あたり **数バイトにも満たない**
- 個々の画像をそのまま保存しておくことはできない
- モデルが保持しているのは、膨大な作品群から抽出された **傾向を極度に圧縮したもの**
  - = 膨大な文化的記憶を内包した「物質」

<!-- _footer: 'Stable Diffusion による生成画像の例 [解説](https://ja.wikipedia.org/wiki/Stable_Diffusion) / [モデルカード](https://huggingface.co/CompVis/stable-diffusion-v1-4)' -->

---

## 学習 - 記憶と再現のあいだ

- ただし、話はそれほど単純ではない
- 学習データのなかで何度も重複して現れる画像 (有名な絵画、広く出回った写真) は、ほぼそのまま再現されることがある
  - 重複の多い35万件を調べた研究で、元の画像とほとんど見分けのつかない画像が **約100件** 生成された ([Carlini et al. 2023](https://arxiv.org/abs/2301.13188))
- AIの記憶は、**「何も覚えていない」と「すべてを覚えている」の中間** のどこかにある
- この曖昧さが、著作権をめぐる議論を複雑にしている

---

## 生成のしくみ (1) - 言語モデル

![height:340](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-2_next_word_probability.svg)

- 与えられた文章に続く **「次の言葉」を確率で予測**
- ひとつ選んで文章に加え、また次の言葉を予測 → 何千回と繰り返して長い文章に

---

## 体験してみよう: Transformer Explainer

[![height:300](https://img.youtube.com/vi/TFUc41G2ikY/maxresdefault.jpg)](https://poloclub.github.io/transformer-explainer/)

- ブラウザ上で実際の言語モデル (**GPT-2**) を動かし、内部のしくみを可視化するツール
  - 好きな文章を入力すると、**次に来る言葉の候補と確率** がリアルタイムに表示される
  - **Temperature** (温度) や **Top-k / Top-p** を変えると、選ばれる言葉の「ありふれ具合」が変わる

<!-- _footer: '[Transformer Explainer](https://poloclub.github.io/transformer-explainer/) / [デモ動画 (YouTube)](https://youtu.be/TFUc41G2ikY) / [GitHub (MIT License)](https://github.com/poloclub/transformer-explainer) / Georgia Institute of Technology' -->

---

## Transformer Explainer で見えること

- **Embedding**: 入力した文章を単語 (トークン) に分け、数値のベクトルに変換する
- **Self-Attention**: 各単語が、文中の他のどの単語に注目しているかを計算する
  - 文脈に応じて、同じ単語でも意味の重みが変わる
- **Probabilities**: 最後に、次に来る言葉の候補それぞれに確率を割り当てる
- 👉 **試してみよう**
  - Temperature を下げる → 最も確率の高い、ありふれた言葉ばかりが選ばれる
  - Temperature を上げる → 確率の低い「裾野」の言葉も選ばれ、意外な展開や破綻が増える
  - = **「平均への引力」** を自分の手で確かめる

---

## 生成のしくみ (2) - 拡散モデル

- 画像生成AIで広く使われている方式 ([Rombach et al. 2022](https://arxiv.org/abs/2112.10752))
- 学習: 画像に少しずつノイズを加えて砂嵐のような状態にし、**その逆 (ノイズを取り除いて元に戻す) 方法を学ぶ**
- 生成: まったくのノイズから出発し、プロンプトを手がかりにノイズを少しずつ取り除く
  - 砂嵐のなかから徐々に像が浮かび上がる
- **シード値** = 出発点となるノイズの模様を決める数値
  - 同じプロンプトでもシード値が違えば、まったく別の画像に
  - ボタンを押すことは、**シード値というサイコロを振る** ことに近い
- 音楽や動画の生成も、これらの考え方の延長にある

<!-- _footer: '[拡散モデルの解説 (Wikipedia)](https://ja.wikipedia.org/wiki/%E6%8B%A1%E6%95%A3%E3%83%A2%E3%83%87%E3%83%AB)' -->

---

## 体験してみよう: Diffusion Explainer

[![height:300](https://img.youtube.com/vi/Zg4gxdIWDds/maxresdefault.jpg)](https://poloclub.github.io/diffusion-explainer/)

- **Stable Diffusion** がプロンプトから画像を生成する過程を、ブラウザ上で可視化するツール
  - インストール不要、用意されたプロンプトから選んで試せる
  - Transformer Explainer と同じ、ジョージア工科大学のチームが開発

<!-- _footer: '[Diffusion Explainer](https://poloclub.github.io/diffusion-explainer/) / [デモ動画 (YouTube)](https://youtu.be/Zg4gxdIWDds) / [GitHub (MIT License)](https://github.com/poloclub/diffusion-explainer) / Georgia Institute of Technology' -->

---

## Diffusion Explainer で見えること

- **Text Representation Generator**: プロンプトの文章を、画像生成の手がかりとなる数値に変換する
- **Image Representation Refiner**: ランダムなノイズから出発し、手がかりをもとにノイズを少しずつ取り除く
  - **Timestep** のスライダーを動かすと、砂嵐から像が浮かび上がる過程を1ステップずつ見られる
- 👉 **試してみよう**
  - **Random Seed** を変える → 同じプロンプトでも、まったく別の画像になる (= サイコロを振る)
  - **Guidance Scale** を変える → プロンプトにどれだけ忠実に従うかが変わる
  - プロンプトの言葉を少し変えて、2つの画像を比べる

---

## 平均への引力 (1) - 確率の高い方へ

- 言語モデルも拡散モデルも、**確率の高い方へ** と進むことで生成を行う
  - 確率が高い = 学習データのなかで頻繁に見かけた
- 「夕日」→ 水平線に沈む太陽と橙色の空という、**典型的な夕日**
- 最もありそうな言葉を選び続ければ、最もありふれた表現に行き着く
- 偶然性を高める設定もあるが、強めすぎると破綻する
- めずらしいもの、変わったものは、**確率の低い裾野** にある
  - そこは、AIが最も苦手とする領域

---

## 平均への引力 (2) - 人間の好みに合わせる調整

- 多くのサービスでは、学習後にもう一段階の調整 ([Ouyang et al. 2022](https://arxiv.org/abs/2203.02155))
  - 人間がAIの出力を評価し、高く評価された出力を出しやすいようにモデルを調整
  - → 指示に従い、礼儀正しく、安全な応答に
- 代償として、**出力の多様性が大きく失われる** ([Kirk et al. 2024](https://arxiv.org/abs/2310.06452))
- 画像生成AIにも、多くの人が美しいと感じる方向への調整
  - Midjourney の [「Raw」モード](https://docs.midjourney.com/docs/style) = 自動的な「美化」を弱める
- いわゆる **「AI臭さ」** (つややかな質感、劇的な光、隙のない構図) は、「多くの人が好むものの平均」

---

## AIの誤り

- 初期の画像生成AIが描く人間の手には、6本や7本の指
- 言語モデルは、存在しない論文や判例を、もっともらしい体裁で引用する
- AIは **意味ではなく統計的な近さ** によって要素を結びつけている
  - 言葉や画像の特徴が、巨大な空間のなかの位置として表される
  - 似たものは近くに、異なるものは遠くに
  - AIは手に指が5本あることを「知っている」わけではない
- 人間から見れば誤り、しかしAIから見れば学習データの統計的な近さを忠実に反映した結果
  - → 人類が残したデータに潜む、**普段は意識されない結びつきが露出** する瞬間

---

## 制作者の立場から整理すると

1. 生成AIは、機械のなかの小さな芸術家でも、作品の切り貼り装置でもない
   - 膨大な文化的記憶から抽出された傾向の、**圧縮された塊**
2. 平均へと引き寄せられる性質は、確率にもとづく生成と、人間の好みに合わせる調整の両方によって、**AIの構造そのものに組み込まれている**
   - 平均から抜け出すには、人間の側の粘り強い働きかけが必要
   - Allen の624回のプロンプト、九段の20万字のプロンプト
3. AIの誤りは、学習データに含まれる思いがけない結びつきを表に出す
   - それを手がかりとして生かせるかどうかは、**使い手しだい**

---

<!-- _class: bigtxt -->

# 実習: AIと共創しながら文章を作成する

---

## AIとの共創の準備: VS Code と GitHub Copilot のセットアップ

- 文章を書きながら、その続きを AI がリアルタイムに提案する環境をつくる
  - エディタ: **Visual Studio Code** (VS Code)
  - AI: **GitHub Copilot** の **補完機能** (書きかけの文章の続きを提案)
- 準備の流れ
  1. VS Code をインストール
  2. GitHub アカウントを作成
  3. VS Code で AI 機能を有効化
  4. GitHub でサインインして認可 (Copilot Free に自動登録)
  5. Markdown で補完を有効にする
  6. テキスト補完を試す

> 💡 **拡張機能のインストールは不要**（VS Code 1.116 以降は本体に Copilot が標準搭載）

---

## 1. VS Code をインストール

- 公式サイトからダウンロード: https://code.visualstudio.com/

| OS | インストール手順 |
| :--- | :--- |
| **Windows** | ダウンロードしたインストーラを実行（設定はデフォルトのままで OK） |
| **macOS** | zip を展開し、`Visual Studio Code.app` を「アプリケーション」フォルダへ移動 |

> > ⚠️ **メニューの言語について**: 最初は英語で表示されます。このスライドでも英語UI名（Settings, Accounts など）で説明します。

---

<!-- _footer: 画像出典:GitHub Docs(CC BY 4.0) -->

## 2. GitHub アカウントを作成

- https://github.com/ を開いて **Sign up**（Google アカウントでも登録可能）
- メールアドレス・パスワード・ユーザー名・国/地域を入力し、パズルを解く
- メールに届く確認コードを入力して **メール認証を完了**
  - 認証状態は `Settings > Emails` で確認可能（Unverified なら再送できる）

![height:220](https://raw.githubusercontent.com/tado/sfc-design/main/img/github-email-verify.png)

---

<!-- _footer: 画像出典:Visual Studio Code Docs(CC BY 3.0 US) -->

## 3. VS Code で AI 機能を有効にする

VS Code を起動し、次のどちらかをクリック（図の赤枠参照）:

- **方法 A（推奨）**: タイトルバー右上の **Sign In**
- **方法 B**: 右下ステータスバーの Copilot アイコン → **Use AI Features**

![height:380](https://raw.githubusercontent.com/tado/sfc-design/main/img/vscode-enable-ai-features.png)

---

<!-- _footer: 画像出典:Visual Studio Code Docs(CC BY 3.0 US) -->

## 4-1. サインイン方法を選ぶ

![bg right:38% contain](https://raw.githubusercontent.com/tado/sfc-design/main/img/copilot-sign-in.png)

- **Continue with GitHub** を選ぶ
- 自動でブラウザが開くので、手順2で作ったアカウントでログイン
- Copilot の契約がないアカウントは、自動的に **Copilot Free**（無料プラン）に登録される
  - クレジットカードの登録などは一切不要

---

<!-- _footer: 画像出典:GitHub Docs(CC BY 4.0) -->

## 4-2. ブラウザで認可する

![bg right:40% contain](https://raw.githubusercontent.com/tado/sfc-design/main/img/github-authorize-app.png)

- **認可を実行**:
  - VS Code からのアクセス許可画面が出たら、緑の **Authorize** ボタンを押す
  - （右は画面の例。実際はアプリ名が Visual Studio Code と表示されます）
- **エディタに戻る**:
  - 「Visual Studio Code を開きますか?」と聞かれたら許可して戻る
- **完了確認**:
  - 右下の Copilot アイコンを開き、プラン名（Copilot Free など）が表示されていれば完了！

---

## 5. Markdown で補完を有効にする

- 今回はプログラムではなく **文章** を書くので、Markdown ファイル (`.md`) を使う
- Copilot の補完は、初期設定では **Markdown やプレーンテキストでは無効** になっている場合がある
- **有効にする方法**:
  1. `.md` ファイルを開いた状態で、右下ステータスバーの Copilot アイコンをクリック
  2. メニューから **Markdown** での補完を有効にする
- **設定ファイルで指定する場合** (`settings.json`):

```json
"github.copilot.enable": {
  "*": true,
  "markdown": true,
  "plaintext": true
}
```

---

<!-- _footer: 画像出典:Visual Studio Code Docs(CC BY 3.0 US) -->

## 6. テキスト補完を試す

- `File > New Text File` で新規ファイルを作り、`story.md` などの名前で保存
- 文章を書き始めると、続きの文章が **薄いグレー（ゴーストテキスト）** で提案される

![width:760](https://raw.githubusercontent.com/tado/sfc-design/main/img/inline-suggestion.png)

- （図はプログラムの例。文章でも同じようにグレーの文字で続きが提案される）

- <kbd>Tab</kbd>: **提案を確定** / <kbd>Esc</kbd>: **提案を破棄**
- 👉 **試してみよう**: `# 雨の日の図書館` と見出しを書き、1行目を書き始めて少し待つ

---

## 補完をコントロールする

- 提案を **全部は受け入れない** ことも、共創の大切な判断
- 便利な操作
  - **単語ごとに確定**: Windows <kbd>Ctrl</kbd> + <kbd>→</kbd> / macOS <kbd>⌘ Command</kbd> + <kbd>→</kbd>
    - 気に入った部分までだけ受け入れ、その先は自分で書く
  - **別の候補を見る**: Windows <kbd>Alt</kbd> + <kbd>]</kbd> / macOS <kbd>⌥ Option</kbd> + <kbd>]</kbd>
    - 提案にマウスを重ねると、候補を切り替えるツールバーも表示される
- 提案は、直前までの文章 (= プロンプト) によって変わる
  - 書き出しの言葉、文体、見出しを変えると、続きの方向も変わる

---

<!-- _footer: 画像出典:Visual Studio Code Docs(CC BY 3.0 US) -->

## 使用量を確認する

![bg right:45% contain](https://raw.githubusercontent.com/tado/sfc-design/main/img/copilot-status-dashboard.png)

- 右下ステータスバーの Copilot アイコンをクリック
- 今月の利用枠を何%消費したかが表示される
  - （右は有料プランの例。Free ではコード補完の使用量も表示）
- **Copilot Free の月間上限**:
  - **補完**: 2,000回まで（確定ベース）
  - **チャット**: AIクレジットの範囲内（月50回程度が目安）
- 実習に入る前に、残り枠を確認しておきましょう

---

<!-- _footer: 画像出典:GitHub Docs(CC BY 4.0) -->

## 上限を気にせず使うには？

![bg right:40% contain](https://raw.githubusercontent.com/tado/sfc-design/main/img/education-upload-proof.png)

- **GitHub Student Developer Pack**:
  - 学生認証を行うと、有料相当の **Copilot Student** を **無料** で利用できます
- **申請・有効化の手順**:
  1. https://github.com/settings/education/benefits にアクセス
  2. 大学のメールアカウント (ac.jp) を登録し、学生証の写真等を提出して申請
  3. 認証完了後、同ページで Copilot Student を有効化
  - ※ 認証反映に数日かかる場合があります
- 詳細: [GitHub Docs「Copilot Student の設定」](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students)

---

## データの扱いとプライバシー設定

自分の文章を安心して書くために、初期設定と変更方法を把握しておきましょう。

- **Copilot Free の初期設定**:
  - テレメトリ（製品改善のためのデータ送信）: **有効**
  - 公開コードと一致する提案（Public code suggestions）: **許可**
- **より厳格に変更したい場合**:
  - **VS Code 設定**: `telemetry.telemetryLevel` を検索して `off` に設定
  - **GitHub 設定**: 🔗 https://github.com/settings/copilot を開き、
    - 「Suggestions matching public code」を **Block** に変更
    - 「Allow GitHub to use my data for AI model training」を **Disabled** に変更

> > ⚠️ 個人情報や、未発表の大切な原稿は入力しないように注意

---

<!-- _footer: 画像出典:Visual Studio Code Docs(CC BY 3.0 US) -->

## トラブルシューティング（うまくいかないとき）

![bg right:32% contain](https://raw.githubusercontent.com/tado/sfc-design/main/img/vscode-accounts-menu.png)

- **Sign In ボタンや Copilot アイコンが見当たらない**
  - 左下の人型アイコン（Accounts）→ **Sign in with GitHub to use GitHub Copilot**
  - VS Code のバージョンを確認（1.116 以降が必要。古ければアップデート）
- **別のアカウントでサインインしてしまった**
  - Accounts メニューから **Sign out** して正しいアカウントで入り直す
- **文章の補完が出ない**
  - ファイルを `.md` 付きで保存しているか確認
  - Markdown での補完が有効になっているか確認（手順5）

---

<!-- _class: bigtxt -->

# 次週までの課題<br>AIと共創するレポート<br>「創作において人工知能とは...」

---

## 課題: AIと共創するレポート

- VS Code と GitHub Copilot の **テキスト補完** を使って、レポートを書く
- 書き出しは必ず次の一文から始める

```markdown
# 創作において人工知能とは

創作において人工知能とは、
```

- この続きを、AIの補完と自分の言葉を往復させながら書き進める
- 分量の目安: **1,200〜2,000字程度**
- AIの提案をそのまま並べるのではなく、**採用・修正・拒否の判断** を重ねて、自分のレポートに仕上げる

---

## 進め方

1. `report.md` という名前で新しいファイルを作り、書き出しの一文を入力する
2. 少し待って、グレーの文字で提案される続きを読む
3. 提案を **全部確定する / 単語ごとに確定する / 破棄して自分で書く** を選ぶ
   - <kbd>Tab</kbd>: 確定 / <kbd>Ctrl</kbd>(<kbd>⌘</kbd>) + <kbd>→</kbd>: 単語ごとに確定 / <kbd>Esc</kbd>: 破棄
4. 方向を変えたいときは、自分で数語を書き足してから、再び提案を待つ
   - 書き出しの言葉や文体を変えると、続きの方向も変わる
5. 今日の講義の内容 (ボタンの手前・奥・向こう、平均への引力など) も手がかりにする

---

## 提出方法

- **提出物**: テキストファイル (`report.md`)
  - ファイル名は `学籍番号_氏名.md` に変更して提出
- **提出先**: (提出先を記入)
- **締切**: 次回の授業の前日まで
- 注意
  - 書き出しの一文「創作において人工知能とは、」から始めること
  - 個人情報や、他人に見せたくない内容は入力しないこと

---


## 参考文献 (1)

- Roose, Kevin. "An A.I.-Generated Picture Won an Art Prize. Artists Aren't Happy." The New York Times, 2022.
- [CBS Colorado. "Artificial intelligence artwork wins 1st place at Colorado State Fair..."](https://www.cbsnews.com/colorado/news/ai-created-art-exhibit-first-place-colorado-state-fair-causing-controversy-jason-allen/) 2022.
- [Harwell, Drew. "He used AI art from Midjourney to win a fine-arts prize. Did he cheat?"](https://www.washingtonpost.com/technology/2022/09/02/midjourney-artificial-intelligence-state-fair-colorado/) The Washington Post, 2022.
- [U.S. Copyright Office Review Board. "Théâtre D'opéra Spatial."](https://www.copyright.gov/rulings-filings/review-board/docs/Theatre-Dopera-Spatial.pdf) 2023.
- [Eldagsen, Boris. "Sony World Photography Awards 2023."](https://www.eldagsen.com/sony-world-photography-awards-2023/)
- 九段理江 著. 東京都同情塔, 新潮社, 2024.
- [東京新聞. 芥川賞作家・九段理江さん「受賞作の5％は生成AIの文章」発言の誤解と真意](https://www.tokyo-np.co.jp/article/310036), 2024.
- [博報堂. 4,000字の小説に20万字のプロンプト](https://www.hakuhodo.co.jp/magazine/116524/), 2025.
- [博報堂. 『影の雨』プロンプト全文公開](https://www.hakuhodo.co.jp/news/newsrelease/117760/), 2025.

---

## 参考文献 (2)

- [Schuhmann, Christoph, et al. "LAION-5B."](https://arxiv.org/abs/2210.08402) NeurIPS 2022.
- [Meta. "Introducing Meta Llama 3."](https://ai.meta.com/blog/meta-llama-3/) 2024.
- [CompVis. "Stable Diffusion v1-4 Model Card."](https://huggingface.co/CompVis/stable-diffusion-v1-4)
- [Carlini, Nicholas, et al. "Extracting Training Data from Diffusion Models."](https://arxiv.org/abs/2301.13188) 2023.
- [Rombach, Robin, et al. "High-Resolution Image Synthesis with Latent Diffusion Models."](https://arxiv.org/abs/2112.10752) CVPR 2022.
- [Ouyang, Long, et al. "Training Language Models to Follow Instructions with Human Feedback."](https://arxiv.org/abs/2203.02155) NeurIPS 2022.
- [Kirk, Robert, et al. "Understanding the Effects of RLHF on LLM Generalisation and Diversity."](https://arxiv.org/abs/2310.06452) ICLR 2024.
- [Midjourney. "Raw."](https://docs.midjourney.com/docs/style)
- [Cho, Aeree, et al. "Transformer Explainer: Learning LLM Transformers with Interactive Visual Explanation and Experimentation."](https://arxiv.org/abs/2408.04619) CHI 2026.
- [Lee, Seongmin, et al. "Diffusion Explainer: Visual Explanation for Text-to-image Stable Diffusion."](https://arxiv.org/abs/2305.03509) 2023.
