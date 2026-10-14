![](https://botnik.org/content/hp01.jpg)

<small>画像出典: Botnik Studios「Harry Potter and the Portrait of What Looked Like a Large Pile of Ash」(2017), [botnik.org](https://botnik.org/content/harry-potter.html)</small>

今回は「AIと書く - 次の言葉を選ぶのは誰か」というテーマで、AIによるテキストの補完を使いながら文章を書く実習を行います。

前回は、生成AIが「次の言葉」を確率で予測していること、そしてその性質によって、AIの出力が「平均」へと引き寄せられることを確認しました。今回は、その予測をエディタのなかで実際に受け取りながら書いてみます。エディタには Visual Studio Code (VS Code) を、AIには GitHub Copilot の補完機能を使います。

まず前回の内容を振り返り、スマホの予測変換を使ったウォームアップを行います。続いて VS Code と GitHub Copilot をセットアップし、補完の基本操作を覚えたら、同じテーマで「AI補完なしで書いた文章」と「AI補完だけで書いた文章」を作り、どちらがAIの文章かを互いに当て合います。最後に、次週までの課題について説明して終了です。

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

第1回の Mentimeter では、「AIを使いこなせるようになりたいけれど、使いこなせるとはどういう状態なのかも分からない」という趣旨の声がありました。ここでは、ひとつの答えとして、**AIの提案を受け入れるか、書き換えるか、断るかを、自分で選べること** を「使いこなす」と考えてみます。今日の実習では、まずその両極端を体験します。AIをまったく使わずに書くことと、AIの提案をすべて受け入れるだけで書くことです。そのあいだ、つまり提案を選びながら書くことには、次週までの課題で取り組みます。

## ウォームアップ: 予測変換で書く

### スマホの予測変換だけで書いてみよう

まずは、PCを使わずに始めます。スマホのメモアプリを開いて「生成AIによる創作とは」と入力し、そのあとはキーボードに表示される **予測変換の候補だけ** をタップして、文章を続けてみてください。できあがった文章を、隣の人と見せ合ってみましょう。

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

詳しい手順は、[GitHub Docs「GitHubでのアカウントの作成」](https://docs.github.com/ja/account-and-profile/how-tos/account-management/creating-an-account-on-github) を参照してください。

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

右下ステータスバーの Copilot アイコンをクリックすると、今月の利用枠を何%消費したかが表示されます (図は有料プランの例です。Free では補完の使用量も表示されます)。Copilot Free の月間上限は以下のとおりです。実習に入る前に、残り枠を確認しておきましょう。

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

## 実習: 人間の文章とAIの文章

補完の操作に慣れたら、実習に入ります。同じテーマで2つの文章を書き、どちらがAIの文章かを互いに当て合います。

| | 書き方 | 人間がすること |
| :--- | :--- | :--- |
| **文章1** | AI補完なしで書く | すべて |
| **文章2** | AI補完だけで書く | 書き出しを入力するだけ |

テーマはどちらも「**生成AIによる創作**」で、書き出しを「**生成AIによる創作とは**」に揃えます。分量は **400字程度** です。書き終えたら2つの文章を Google Classroom に提出し、提出された文章のどちらがAIかを、全員で予想して投票します。

### 文章1: AI補完なしで書く

まず、AIの補完を使わずに、テーマ「生成AIによる創作」について400字程度の文章を書きます。

1. 右下ステータスバーの Copilot アイコンをクリックし、手順5と同じメニューで Markdown の補完を **オフ** にする
2. 新しいファイルを作り、A.md か B.md のどちらかの名前で保存する (どちらにするかは自由)
3. 次の書き出しを入力して、その続きを書く

```markdown
# 生成AIによる創作

生成AIによる創作とは
```

ChatGPT など、ほかのAIも使いません。AIに似せたり、わざと崩したりせず、ふだんの自分の言葉で書いてください。文字数は、本文を選択すると右下のステータスバーに「(120 selected)」のように表示されるので、それで確認できます。

### 文章2: AI補完だけで書く

次に、同じテーマの文章を、AIの補完だけで書きます。

1. Copilot アイコンのメニューから、Markdown の補完を **オン** に戻す
2. もう一方の名前 (B.md か A.md) で新しいファイルを作る
3. 文章1と同じ書き出しだけを入力して、提案を待つ
4. グレーの提案が出たら、<kbd>Tab</kbd> で確定する。これを繰り返す
5. 提案が出ないときは、<kbd>Enter</kbd> で改行だけを入れて待つ
6. 400字程度になったら止める

自分で入力してよいのは、書き出しと改行だけです。文字を打つ、消す、書き換えるといった編集は **一切しません**。別の候補を見る (<kbd>Alt</kbd> + <kbd>]</kbd>) や、単語ごとの確定 (<kbd>Ctrl</kbd> + <kbd>→</kbd>) も使わず、最初に出てきた提案をそのまま受け入れます。同じ文が繰り返されたり、話が途中で変わったりしても、そのまま残してください。

### Google Classroom に提出する

1. Google Classroom の課題に、A.md と B.md の2つのファイルを提出する
2. どちらがAIの文章かは、課題の「限定公開のコメント」で教員にだけ伝える

ファイル名やクラスのコメントなど、ほかの人に見える場所には、どちらがAIかを書かないでください。

### どちらがAIかを当てる

提出された文章を、名前を伏せてスクリーンに映します。組ごとに、A と B のどちらがAIの文章かを予想して、Mentimeter で投票しましょう。投票が終わったら答え合わせをします。

当たった人は、何を手がかりにしたでしょうか。外れた人は、どこにだまされたのでしょうか。たとえば、よく見かける言い回し、なめらかすぎる文、具体的な体験の有無、同じ表現の繰り返しなどに注目してみましょう。前回考えた「平均への引力」は、文章のどこに表れていたでしょうか。

## まとめ: ボタンの奥だけで書かれた文章

今日は、AI補完を使わずに書いた文章と、AI補完だけで書いた文章を並べて、どちらがAIの文章かを当て合いました。

前回の「ボタンの手前・奥・向こう」で考えてみましょう。文章1は、構想から言葉選び、推敲まで、すべてを人間が担っています。一方、文章2で人間が入力したのは、書き出しの言葉だけです。手前の仕事はほとんどなく、返ってきたものを吟味し、選び、手を加える「向こう」の仕事はまったくありません。いわば、**ボタンの奥だけで書かれた文章** です。Botnik Studios のメンバーは、予測された言葉のなかから候補を選んでいましたが、文章2では選ぶことさえしていません。

![](https://raw.githubusercontent.com/tado/geidai-ai/main/img/fig00-1_prompt_cycle.svg)

上の図の (b) は、生成し、見きわめ、手を加えるという実践のサイクルです。今日の文章2は、このサイクルの「生成する」だけでできています。次週までの課題では、この文章を出発点に、「見きわめる」と「手を加える」を自分で回してみます。(a) のように、AIが返してきたものに「こういう方向もありえたのか」と気づかされながら往復を重ねることで、当初は想像もしなかった場所にたどり着けるかもしれません。

提案を受け入れる、書き換える、断る。その判断を自分で選べることが、今日の最初に考えた「使いこなす」ということです。

## 次週までの課題

### AIの文章を仕上げる

実習で AI補完だけで書いた文章 (文章2) を出発点に、修正を加えて、自分の作品として仕上げてください。修正の方法は自由で、次の2つを組み合わせてもかまいません。

* **自分の手で直す**: 言葉を足す、削る、書き換える、順番を入れ替える
* **AIに修正を頼む**: 直したい部分と、どう直したいか (修正ポイント) をプロンプトで指摘し、AIに書き直してもらう

仕上がりの分量は、400字程度を目安にします。仕上げた文章には、制作をふりかえる考察を添えてください。

### AIに修正を頼むには

補完は「続き」を書く機能なので、すでに書かれた文章を直してもらうには、チャットを使います。VS Code では、直したい部分を選択して <kbd>Ctrl</kbd> + <kbd>I</kbd> (macOS は <kbd>⌘ Command</kbd> + <kbd>I</kbd>) を押すと、その場でAIに指示を出せます (インラインチャット)。ChatGPT や Gemini など、ふだん使っているチャットAIに文章を貼り付けて頼んでもかまいません。

修正ポイントは、具体的に指摘するほど効果があります。たとえば、次のような指摘です。

* 「『可能性』や『便利』のような、よく見かける言葉を使わずに言い換えて」
* 「3文目の主張に、反対の立場からの意見も加えて」
* 「最後の一文を、読み手への問いかけで終わるように書き直して」

なお、Copilot Free のチャットには、利用回数の上限があります (月50回程度が目安)。

### 考察

仕上げた文章のあとに、400字程度の考察を書いてください。たとえば、次のようなことを書きます。

* AIだけで書いた文章の、どこを、なぜ直したのか
* 自分の手で直したところと、AIに頼んだところの違い
* 実習の投票で、AIの文章は見破られたか。その決め手は何だったか
* 人間が書いた文章とAIが書いた文章の違いについて、気づいたこと
* 生成AIによる創作について、書く前と書いた後で考えが変わったところ

### 提出方法

次のような構成で、1つのファイルにまとめてください。

```markdown
## もとの文章 (AI補完のみ)

(実習で書いた文章2を、そのまま貼る)

## 仕上げた文章

(修正して仕上げた文章)

## 考察

(400字程度)
```

* **提出物**: テキストファイル (.md)
  * ファイル名は 学籍番号_氏名.md に変更して提出
* **提出先**: Google Classroom の課題
* **締切**: 次回の授業の前日まで

個人情報や、他人に見せたくない内容は入力しないように注意してください。

## 関連リンク

* [Visual Studio Code](https://code.visualstudio.com/)
* [GitHub](https://github.com/)
* [GitHub Copilot](https://github.com/features/copilot)
* [VS Code Docs「Inline suggestions from GitHub Copilot in VS Code」](https://code.visualstudio.com/docs/editing/ai-powered-suggestions)
* [VS Code Docs「Inline chat and Quick Chat」](https://code.visualstudio.com/docs/chat/inline-chat)
* [GitHub Docs「Copilot Student の設定」](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students)
* [Botnik Studios「Harry Potter」](https://botnik.org/content/harry-potter.html)

## 参考文献

* [Botnik Studios. "Harry Potter and the Portrait of What Looked Like a Large Pile of Ash."](https://botnik.org/content/harry-potter.html) 2017.
* [Visual Studio Code Docs. "Inline suggestions from GitHub Copilot in VS Code."](https://code.visualstudio.com/docs/editing/ai-powered-suggestions)
* [Visual Studio Code Docs. "Inline chat and Quick Chat."](https://code.visualstudio.com/docs/chat/inline-chat)

## アンケート

本日の講義に参加した方は以下のアンケートに答えてください。

* [アンケートフォーム]()
