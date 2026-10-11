![](https://botnik.org/content/hp01.jpg)

<small>画像出典: Botnik Studios「Harry Potter and the Portrait of What Looked Like a Large Pile of Ash」(2017), [botnik.org](https://botnik.org/content/harry-potter.html)</small>

今回は「AIと書く - 予測と意図のあいだで」というテーマで、AIによるテキストの補完を使いながら文章を書く実習を行います。

前回は、生成AIが「次の言葉」を確率で予測していること、そしてその性質によって、AIの出力が「平均」へと引き寄せられることを確認しました。今回は、その予測をエディタのなかで実際に受け取りながら書いてみます。エディタには Visual Studio Code (VS Code) を、AIには GitHub Copilot の補完機能を使います。

まず前回の内容を振り返り、スマホの予測変換を使ったウォームアップを行います。続いて VS Code と GitHub Copilot をセットアップし、補完の基本操作を覚えたら、4つの小さな実験で「平均への引力」や「ボタンの手前・奥・向こう」を自分の手で確かめます。次週までの課題について説明したら、授業の時間内にレポートを書き始め、最後に今日の実習をふりかえって終了です。

## スライド資料

* [スライド資料 (PDF)]()

## 前回の振り返り

### 次の言葉を確率で予測する

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-2_next_word_probability.svg)

ChatGPT のような言語モデルは、与えられた文章に続く **「次の言葉」を確率で予測** します。そのなかから一つを選んで文章に加え、また次の言葉を予測します。この単純な手順を繰り返すことで、長い文章が紡がれていきます。確率が高いのは、学習データのなかで頻繁に見かけた表現です。今回使う GitHub Copilot の補完も、書きかけの文章に続く言葉を、このしくみで予測しています。

### ボタンの手前・奥・向こう

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig01-1_button_zones.svg)

AIを使った制作には、三つの段階があります。

* **手前**: 何を作りたいのかを構想し、それを言葉にし、参照する素材を選び、設定を決める
* **奥**: 人間が押したボタンを受けて、AIが像や言葉を生成する
* **向こう**: 返ってきたものを吟味し、選び、手を加え、作品として世界に差し出す

制作者の仕事の大半は、ボタンの **手前と向こう** にあります。そして、向こうで受け取ったものは、次の手前を変えていきます。補完を使って文章を書くとき、この循環は数秒ごとに回ることになります。

### 平均への引力

言語モデルも画像生成AIも、**確率の高い方へ** と進むことで生成を行います。「夕日」と打ち込めば、水平線に沈む太陽と橙色の空という **典型的な夕日** が現れます。めずらしいもの、変わったものは **確率の低い裾野** にあり、そこはAIが最も苦手とする領域です。さらに、人間の好みに合わせる調整によって、AIの出力はなめらかで無難な方向へと寄っていきます。平均から抜け出すには、Allen の624回のプロンプトや、九段理江の20万字のプロンプトのような、人間の側の粘り強い働きかけが必要です。

### 今日の目標: 「使いこなす」とはどういうことか

第1回の Mentimeter では、「AIを使いこなせるようになりたいけれど、使いこなせるとはどういう状態なのかも分からない」という趣旨の声がありました。今日の実習では、ひとつの答えとして、**AIの提案を受け入れるか、書き換えるか、断るかを、自分で選べること** を「使いこなす」と考えてみます。補完は、この判断を何度も繰り返す練習にぴったりの環境です。

## ウォームアップ: 予測変換で書く

### スマホの予測変換だけで書いてみよう

まずは、PCを使わずに始めます。スマホのメモアプリを開いて「創作において人工知能とは、」と入力し、そのあとはキーボードに表示される **予測変換の候補だけ** をタップして、1分ほど文章を続けてみてください。できあがった文章を、隣の人と見せ合ってみましょう。

スマホの予測変換も、「次の言葉」を予測するしくみです。予測変換はあなたの入力の履歴も学習しているので、できあがる文章には、自分の言葉の癖が映ります (見せたくない言葉が出てきたら、共有しなくてかまいません)。これに対して、今日使う GitHub Copilot は、膨大なテキストから学習した言語モデルで続きを予測します。そこに映るのは、**多くの人々の言葉の傾向** です。

### Botnik Studios「Harry Potter and the Portrait of What Looked Like a Large Pile of Ash」(2017)

![](https://botnik.org/content/hp02.jpg)

<small>画像出典: [Botnik Studios「Harry Potter」](https://botnik.org/content/harry-potter.html)</small>

予測変換で書くことは、すでに創作の手法として試みられています。2017年12月、作家やエンジニアが集まる創作集団 Botnik Studios は、『ハリー・ポッター』の架空の続編「Harry Potter and the Portrait of What Looked Like a Large Pile of Ash」の第13章「The Handsome One」を公開しました。シリーズ全7巻の文章を学習させた **予測キーボード** を使い、メンバーが候補の言葉を一語ずつ選んで文を作り、それを編集者が一つの章にまとめたものです。

できあがった章は、いかにも『ハリー・ポッター』らしい語彙で書かれていながら、筋の通らない奇妙な場面の連続で、インターネットで大きな話題になりました。言葉の候補を出したのは機械ですが、**どの候補を選び、どれを捨て、どう並べるかを決めたのは人間** です。予測された言葉のなかから、あえて奇妙なものを選ぶことで、作品が生まれていました。

* [Botnik Studios「Harry Potter」](https://botnik.org/content/harry-potter.html)

## AIとの共創の準備: VS Code と GitHub Copilot のセットアップ

文章を書きながら、その続きをAIがリアルタイムに提案する環境をつくります。エディタには **Visual Studio Code** (VS Code) を、AIには **GitHub Copilot** の **補完機能** (書きかけの文章の続きを提案する機能) を使います。VS Code 1.116 以降は本体に Copilot が標準搭載されているので、拡張機能のインストールは不要です。

準備の流れは以下のとおりです。前回の「次回までの準備」で手順1と2を済ませた人は、手順3から進めてください。

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

### データの扱いとプライバシー設定

文章を書き始める前に、データの扱いについての初期設定と変更方法を把握しておきましょう。Copilot Free の初期設定では、テレメトリ (製品改善のためのデータ送信) が **有効**、公開コードと一致する提案 (Public code suggestions) が **許可** になっています。より厳格に変更したい場合は、以下のように設定します。

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

### セットアップが早く終わったら

セットアップが早く終わった人は、次の2つを確認しておきましょう。まわりに困っている人がいたら、手伝ってあげてください。

#### 使用量を確認する

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/copilot-status-dashboard.png)

<small>画像出典: [Visual Studio Code Docs](https://code.visualstudio.com/docs) (© Microsoft, CC BY 3.0 US)</small>

右下ステータスバーの Copilot アイコンをクリックすると、今月の利用枠を何%消費したかが表示されます (図は有料プランの例です。Free では補完の使用量も表示されます)。Copilot Free の月間上限は以下のとおりです。実験に入る前に、残り枠を確認しておきましょう。

* **補完**: 2,000回まで (確定ベース)
* **チャット**: AIクレジットの範囲内 (月50回程度が目安)

#### 上限を気にせず使うには?

![](https://raw.githubusercontent.com/tado/sfc-design/main/img/education-upload-proof.png)

<small>画像出典: [GitHub Docs](https://docs.github.com/) (© GitHub, CC BY 4.0)</small>

**GitHub Student Developer Pack** で学生認証を行うと、有料相当の **Copilot Student** を **無料** で利用できます。

1. [https://github.com/settings/education/benefits](https://github.com/settings/education/benefits) にアクセス
2. 大学のメールアカウント (ac.jp) を登録し、学生証の写真等を提出して申請
3. 認証完了後、同ページで Copilot Student を有効化

認証の反映には数日かかる場合があります。詳しくは [GitHub Docs「Copilot Student の設定」](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students) を参照してください。

## 補完の基本操作

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

グレーで表示される提案は、Copilot が予測した「確率の高い続き」です。ただし、続きの候補は一つとは限りません。前回 Transformer Explainer で見たように、次に来る言葉の候補は、それぞれの確率とともに複数あります。提案は、直前までの文章 (= プロンプト) によって変わります。書き出しの言葉、文体、見出しを変えると、続きの方向も変わります。

## 実験: 補完で「平均への引力」を確かめる

補完の操作に慣れたら、4つの小さな実験で、前回の講義で考えたことを自分の手で確かめてみましょう。

| 実験 | やること | 確かめること |
| :--- | :--- | :--- |
| **1. 平均を観察する** | 全員が同じ書き出しで書き、提案を比べる | 平均への引力 |
| **2. 文脈を設計する** | 書き出しの上に設定メモを書き足す | ボタンの手前 |
| **3. 平均から外れる** | 別の候補を選ぶ、1語だけ自分で変える | 向こうから次の手前へ |
| **4. 疑う** | 参考文献を補完させ、実在を確かめる | AIの誤り |

### 実験1: 平均を観察する

全員が同じファイル名、同じ書き出しで、Copilot がどんな続きを提案するかを比べます。yuuhi.md という名前で新しいファイルを作り、次の2行を入力して、提案が表示されるまで少し待ちます。

```markdown
# 夕日

窓の外の夕日は
```

提案された続きの最初の一文を確定し (<kbd>Tab</kbd>、または <kbd>Ctrl</kbd>(<kbd>⌘</kbd>) + <kbd>→</kbd> で途中まで)、Mentimeter に投稿してください。全員の投稿を並べてみると、どれくらい似通っているでしょうか。前回、「夕日」と打ち込めば典型的な夕日が現れるという話をしました。これはその言語版です。もし提案がばらつくなら、それは前回の「シード値というサイコロ」と同じように、生成に偶然の要素が含まれているからです。

### 実験2: 文脈を設計する

次に、同じ書き出しの上に、語り手や文体についての「設定メモ」を書き足して、提案がどう変わるかを比べます。

```markdown
# 夕日

- 語り手: 100年後の火星で暮らす子ども
- 文体: 短い文、ひらがなを多めに

窓の外の夕日は
```

火星の夕日は、地球とは逆に **青く見える** ことが知られています ([NASA](https://science.nasa.gov/resource/sunset-at-mars-gale-crater-curiosity/))。AIの提案は、設定メモに引っぱられるでしょうか。それとも、やはり橙色の典型的な夕日に戻ってしまうでしょうか。語り手、時代、場所、文体、見出しなどを自由に変えて、何度か試してみましょう。

Copilot の補完は、チャットのように指示に従っているわけではありません。ファイルに書かれた文章を「文書の一部」として読み、その続きとしてありそうな言葉を予測しています。つまり、**ファイルに書かれている文章そのものがプロンプト** です。何をどこまで書いておくかを決めることが、補完における「ボタンの手前」の仕事になります。

### 実験3: 平均から外れる

AIの提案は、確率の高い方へと寄っていきます。そこから外れるための、2つの方法を試します。

* **別の候補から選ぶ**: <kbd>Alt</kbd>(<kbd>⌥</kbd>) + <kbd>]</kbd> で候補を切り替え、いちばん変だと思うものを選ぶ
* **1語だけ自分で変える**: <kbd>Ctrl</kbd>(<kbd>⌘</kbd>) + <kbd>→</kbd> で提案を途中まで受け入れ、続く1語だけを、自分で思いがけない言葉に書き換える

たとえば「窓の外の夕日は、」のあとに、自分で「冷蔵庫の」と書き足してから、提案を待ってみてください。AIは、その1語をなんとか筋の通る文章に組み込もうとします。1語の介入によって、その先の提案はすべて変わります。前回、「向こうで受け取ったものは、次の手前を変えていく」と説明しました。補完では、自分で選んだ言葉や書き足した言葉が、すぐに次のプロンプトになります。

Botnik Studios の『ハリー・ポッター』も、予測された言葉のなかから、あえて奇妙なものを選ぶことで書かれていました。

### 実験4: 疑う

最後に、AIの誤りを確かめます。ファイルの末尾に次のように書いて、提案を待ちます。

```markdown
## 参考文献

1. 
```

どのような文献が提案されるでしょうか。提案を2〜3件確定したら、それぞれが実在するかどうかを、[Google Scholar](https://scholar.google.com/)、[CiNii Research](https://cir.nii.ac.jp/)、[国立国会図書館サーチ](https://ndlsearch.ndl.go.jp/) などで確かめてみましょう。

前回説明したように、言語モデルは存在しない論文や判例を、もっともらしい体裁で引用することがあります。実在する文献が提案されることもありますが、確かめなければ見分けがつきません。第1回で紹介した京都産業大学のガイドラインでも、AIが挙げた参考文献を、実在するか確認せずに記載することは、不正行為につながる利用例として挙げられていました。次週までの課題のレポートでも、補完で参考文献を書くときは、必ず実在を確かめてください。

### 発展: 頼む (チャット) と続ける (補完) を比べる

時間が余った人は、ふだん使っている ChatGPT や Gemini などのチャットAIに「『窓の外の夕日は』に続く文章を書いてください」と頼み、補完の提案と比べてみましょう。チャットAIの答えには、前置きが付いていたり、整った文章に仕上がっていたりすることがあります。前回説明した「人間の好みに合わせる調整」が、文章の手触りにどう表れているかを観察してみてください。なお、Copilot Free のチャットは利用回数に上限があるので、ここではふだん使っているチャットAIを使ってかまいません。

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
5. 前回と今回の講義の内容 (ボタンの手前・奥・向こう、平均への引力、今日の実験など) も手がかりにする
6. 参考文献を書くときは、実在するかどうかを必ず確かめる

### 共創メモ

レポートの最後に「## 共創メモ」という見出しを付けて、AIとの共創をふりかえる短い文章を書き添えてください。分量は200〜400字程度で、レポートの字数には含めません。たとえば、次のようなことを書きます。

* 印象に残ったAIの提案と、それを受け入れた (または書き換えた) 理由
* 断った提案と、断った理由
* 方向を変えるために、自分で書き足したり工夫したりしたこと

### 提出方法

* **提出物**: テキストファイル (report.md)
  * レポート本文と共創メモを、1つのファイルにまとめる
  * ファイル名は 学籍番号_氏名.md に変更して提出
* **提出先**: (提出先を記入)
* **締切**: 次回の授業の前日まで

以下の点に注意してください。

* 書き出しの一文「創作において人工知能とは、」から始めること
* 個人情報や、他人に見せたくない内容は入力しないこと

### 授業の残りの時間で書き始める

授業の残りの時間で report.md を作り、書き出しの一文と最初の段落を書いてみましょう。補完がうまく表示されない場合は、この時間に質問してください。

## まとめ: 提案を選ぶ

今日は、AIの補完を使って文章を書きながら、前回の講義で考えたことを確かめました。

* 全員が同じ書き出しで書くと、AIの提案は似通いやすい (**平均への引力**)
* 書き出しの前に何を書いておくかで、提案の方向が変わる (**ボタンの手前**)
* 1語を選び直すだけで、その先のすべてが変わる (**向こうで受け取ったものが、次の手前を変える**)
* AIは、もっともらしい誤りを提案することがある (**確かめるのは人間の仕事**)

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig00-1_prompt_cycle.svg)

上の図の (a) は、漠然とした言葉から始めても、AIが返してきたものに「こういう方向もありえたのか」と気づかされることで、イメージが少しずつ鋭くなっていく往復を表しています。(b) は、生成し、見きわめ、手を加えるという実践のサイクルです。画像生成AIでは、言葉を足し引きし、シード値を変え、参考素材を加えながら、このサイクルを何十回、何百回と繰り返します。補完を使って書くとき、このサイクルは数秒ごとに回っています。

提案を受け入れる、書き換える、断る。その判断を自分で選べることが、今日考えた「使いこなす」ということです。授業の最後に、Mentimeter で「AIの提案を断った瞬間」をひとことで共有しましょう。

## 関連リンク

* [Visual Studio Code](https://code.visualstudio.com/)
* [GitHub](https://github.com/)
* [GitHub Copilot](https://github.com/features/copilot)
* [VS Code Docs「Inline suggestions from GitHub Copilot in VS Code」](https://code.visualstudio.com/docs/editing/ai-powered-suggestions)
* [GitHub Docs「Copilot Student の設定」](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students)
* [Botnik Studios「Harry Potter」](https://botnik.org/content/harry-potter.html)
* [Google Scholar](https://scholar.google.com/)
* [CiNii Research](https://cir.nii.ac.jp/)
* [国立国会図書館サーチ](https://ndlsearch.ndl.go.jp/)

## 参考文献

* [Botnik Studios. "Harry Potter and the Portrait of What Looked Like a Large Pile of Ash."](https://botnik.org/content/harry-potter.html) 2017.
* [NASA. "Sunset at Mars' Gale Crater (Curiosity)."](https://science.nasa.gov/resource/sunset-at-mars-gale-crater-curiosity/) 2015.
* [Visual Studio Code Docs. "Inline suggestions from GitHub Copilot in VS Code."](https://code.visualstudio.com/docs/editing/ai-powered-suggestions)
* [京都産業大学. 生成AI利用ガイドライン](https://www.kyoto-su.ac.jp/torikumi/ai-basic-stance/ai-guideline/), 2026.

## アンケート

本日の講義に参加した方は以下のアンケートに答えてください。

* [アンケートフォーム]()
