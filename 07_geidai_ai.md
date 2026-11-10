---
marp: true
theme: tadokoro
paginate: true
---

# AIを活用した<br>プログラミング入門
東京藝術大学芸術情報センター
田所 淳

---

## 今日の内容

- コーディングの題材: p5.js の簡単な紹介
- AIによるコーディング 1: 対話型AIに質問する
  - ChatGPT などに質問して、コードを生成する
- AIによるコーディング 2: AI機能を搭載したエディターを使う
  - p5.CodingWithAI
- AIによるコーディング 3: さらに高度なAIとの連携
  - VS Code と GitHub Copilot (第3回で準備した環境)
- まとめ: AIにどこまで任せるか

---

## 構想した作品を形にする

![bg right:42% contain](https://yoppa.org/wp-content/uploads/2025/11/Image_fx-1.jpg)

- 前回: 制約を外して、最終制作の作品を構想した
- 構想した作品を形にする方法のひとつが、プログラミング
- いまは、プログラミングの経験がなくても、AIの力を借りて、動くプログラムを作れる
- 今日は、AIと一緒にプログラムを書く方法を、3つの段階で体験する

<!-- _footer: '画像: 画像生成AI (Google ImageFX) で生成' -->

---

<!-- _class: bigtxt -->

# コーディングの題材<br>p5.js の簡単な紹介

---

## p5.js とは

[![height:330](https://img.youtube.com/vi/HerCR8bw_GE/maxresdefault.jpg)](https://www.youtube.com/watch?v=HerCR8bw_GE)

- 絵やアニメーション、インタラクティブな作品をプログラムで作るための JavaScript のライブラリ
- 「Processing」(第5回のタイムラインにも登場) の考え方を、JavaScript で実現したもの

<!-- _footer: '[Code! Programming with p5.js for Beginners Trailer (YouTube)](https://youtu.be/HerCR8bw_GE) (The Coding Train) / [p5js.org](https://p5js.org/)' -->

---

## p5.js の特徴

- Web ブラウザでそのまま実行できる
- アートやデザイン、インタラクティブなメディア作品の制作に適している
- シンプルな書き方で、初心者でも直感的に使える
  - プログラミングの学習にも向いている
- 公式サイトに、多くのチュートリアルやリファレンスがある
- 活発なコミュニティによるサポートがある
- インストールは不要
  - [p5.js Web Editor](https://editor.p5js.org/) を開けば、すぐに書いて実行できる

---

## p5.js でどんなことができるのか - OpenProcessing

![bg right:50% contain](https://yoppa.org/wp-content/uploads/2024/11/image-5-1024x527.png)

- [OpenProcessing](https://openprocessing.org/)
- p5.js を使ったプログラムを、オンラインで作成し、共有できるサービス
- 世界中のクリエイティブコーダーの作品を、ソースコードも含めて見ることができる

<!-- _footer: '画像出典: [OpenProcessing](https://openprocessing.org/)' -->

---

## 簡単なプログラム例

![bg right:38% contain](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-103359-1.png)

```js
function setup() {
  // 画面全体にキャンバスを作成
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  // 背景をグレーに
  background(220);
  // 円を描く
  circle(width / 2, height / 2, 400);
}
```

- いまの段階では、意味がまったく分からなくてOK
- このようなプログラムを、AIの力を借りて生成してみよう

---

## p5.js のバージョンについて

- 2026年8月から、p5.js Web Editor の最初のバージョンが p5.js 2.x に (現在は 2.3.4)
  - 基本的なプログラムは、1.x でも 2.x でも同じように動く
  - 画像や音声などのファイルを読み込む方法 (preload) など、いくつかの書き方が変わった
- AIは、1.x の書き方でコードを生成することがある → そのままでは動かない場合も
- うまく動かないときは
  - 依頼に「p5.js 2.x で」と書き添える
  - エラーメッセージを、そのままAIに伝えて修正してもらう
  - エディタ右上のバージョンの表示をクリック → 互換アドオン (Preload など) をオンにするか、p5.js Version を 1.x に切り替える

<!-- _footer: '[p5.js v2 Transition Guide](https://p5js.org/tutorials/v2_transition/) / [p5.js-compatibility](https://github.com/processing/p5.js-compatibility)' -->

---

<!-- _class: bigtxt -->

# AIによるコーディング 1<br>対話型AIに質問する

---

## ChatGPT に質問する

- もっとも手軽に始められる方法
- ChatGPT などの対話型AIに、作りたいプログラムを言葉で伝えるだけ

```text
ブラウザの画面中央に円を描くプログラムを作りたいです。どのようにすればよいでしょうか?
表示領域はフルスクリーンにしてください。使用する開発環境は、p5.jsを使用してください。
```

- ChatGPT に質問してみると…

---

## ChatGPT の回答: コード

<style scoped>pre { font-size: 0.68em; }</style>

```js
function setup() {
  // ウィンドウサイズに合わせてフルスクリーンキャンバスを作成
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  background(220); // 背景色（薄いグレー）

  // 円の色を設定
  fill(100, 150, 255); // 青系の塗り色
  noStroke(); // 円の境界線をなしに

  // 画面中央に円を描く
  let centerX = width / 2;
  let centerY = height / 2;
  let diameter = 100; // 円の直径

  ellipse(centerX, centerY, diameter, diameter);
}

function windowResized() {
  // ウィンドウサイズが変更されたとき、キャンバスを再調整
  resizeCanvas(windowWidth, windowHeight);
}
```

---

## ChatGPT の回答: 説明と手順

- コードといっしょに、その説明と、実行するための手順も示される
  - **setup 関数**: ブラウザのウィンドウ全体をキャンバスにする
  - **draw 関数**: 背景を塗りつぶし、画面の中心に直径100の円を描く
  - **windowResized 関数**: ウィンドウの大きさが変わったら、キャンバスの大きさを合わせる
  - **実行の手順**: p5.js Web Editor を開き、コードをコピー&ペーストして、再生ボタンを押す
- これは2024年11月、当時の ChatGPT (GPT-4o) の回答
  - GPT-4o は2026年2月に ChatGPT での提供を終了。モデルは入れ替わったが、同じように質問できる
  - 同じ質問をしても、返ってくるコードや説明は毎回少しずつ変わる

---

## 実行結果

![height:400](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-110352-1.png)

- [p5.js Web Editor](https://editor.p5js.org/) にコピー&ペーストして実行
- 依頼したとおり、画面の中央に円が描かれた!

---

## 対話型AIを使うときのヒント

- 最初に「p5.js で」と、制作に使う環境を伝える
- ChatGPT だけでなく、Gemini や Claude でも同じように質問できる
- コードの意味が分からないときは、「このコードを1行ずつ説明して」と頼む
- 思ったとおりにならないときは、何が違うのかを言葉にして、修正を頼む
- 生成したコードを、チャットの画面のなかで動かして確かめられる機能もある
  - ChatGPT や Gemini の Canvas、Claude のアーティファクトなど
  - サービスやプランによって使える範囲が異なる

---

## 実習: 対話型AIによるコード生成を試してみる

1. ChatGPT などの対話型AIに、p5.js で作りたいものをリクエストする
2. 生成されたコードを [p5.js Web Editor](https://editor.p5js.org/) にコピー&ペーストする
3. 再生ボタンを押して、コードを実行する
4. 結果を見て、修正や追加を頼む

---

<!-- _class: bigtxt -->

# AIによるコーディング 2<br>AI機能を搭載したエディターを使う

---

## もっと高度な機能を利用したい

- 対話型AIに質問する方法では、コードをコピー&ペーストして行き来する手間がかかる
- 次のようなことができると、もっと便利
  - 生成された結果を見ながら、対話を重ねてAIのサポートを受けたい
  - エラーが出たときにも、AIに助けてほしい
  - すでにあるコードを、AIに改良してほしい

---

## p5.CodingWithAI を使ってみる

![bg right:40% contain](https://kyabe.net/static/fdec8457230ed05b1fea8500a5215ef2/thumbnail.png)

- https://app.kyabe.net/p5-coding-with-ai/
- [きゃべ / Masaya Kurahashi](https://kyabe.net/) さんが開発した、ChatGPT との連携機能を備えた p5.js の Web エディタ
- チャットに言葉でリクエストを送ると、AIが解説とともに、コードの変更を提案する
- 提案を受け入れるかどうかは、そのつど自分で選ぶ
- 人間とAIの共創の可能性を探るプロジェクト
- 無料で公開 (最初の読み込みには少し時間がかかる)
  - 試験的なプロジェクトのため、予告なく提供を終了する可能性がある

<!-- _footer: '画像出典: [きゃべ / Masaya Kurahashi「p5.CodingWithAI」](https://kyabe.net/works/p5-coding-with-ai/)' -->

---

## 同じ質問を p5.CodingWithAI に送ってみる

![height:400](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-115424-1.png)

- エディタにコードが入力され、そのまま右側に実行結果が表示される
- 使えない場合は、第1回で紹介した [Text-GPT-p5](https://text-gpt-p5.vercel.app/) でも同じように試せる

---

## 実習: p5.CodingWithAI でコード生成

1. 最初に、プロンプトから基本になるコードを生成する
   - または、[OpenProcessing](https://openprocessing.org/) などから気になるコードを選んで、コピー&ペーストする
2. リクエストをくりかえして、少しずつ自分の好みの結果に近づけていく
3. 提案されたコードを受け入れるかどうかは、そのつど吟味する

- 最終的にどのようなコードができあがるのか!?

---

<!-- _class: bigtxt -->

# AIによるコーディング 3<br>さらに高度なAIとの連携

---

## GitHub Copilot を使用してみる

- [GitHub Copilot](https://github.com/features/copilot): GitHub が提供する、プログラミングを支援するAI
- 2021年に、書きかけのコードの続きを提案する「AIペアプログラマー」として登場
  - 当初は OpenAI のモデル Codex をもとにしていた
- 現在は「コーディングエージェント」へと発展
  - OpenAI、Anthropic、Google など複数の企業のAIモデルを使う
  - ファイルの作成からプログラムの実行、エラーの修正までを自律的に進める
- VS Code をはじめ、Visual Studio、JetBrains、Xcode など多くのエディタで使える
- 第3回では補完機能で文章を書いた → 今回は、本来の用途であるプログラミングに使う

---

## GitHub Copilot の主な機能

- **コード補完**: 入力中のコードの続きを予測して提案する
- **チャット**: 言葉で質問や指示をすると、コードの説明や修正案を返す
- **インラインチャット**: エディタのなかで、選択した部分について直接指示する
- **エージェント**: ファイルの作成や編集、プログラムの実行、エラーの修正までを自分で進める
- **クラウドエージェント**: GitHub 上で作業を任せ、結果を変更の提案 (プルリクエスト) として受け取る
- **コードレビュー**: 書いたコードの問題点や改善点を指摘する
- **モデルの選択**: 複数のAIモデルから選んで使う
- **多言語への対応**: JavaScript、Python、TypeScript など、多くの言語で使える

---

## プランによる違い

- 使える機能や回数は、プランによって異なる (2026年11月現在)
- 無料の Copilot Free
  - 補完: 月2,000回まで
  - チャットとエージェント: 決められた利用枠の範囲
  - モデル: 自動選択のみ (Copilot Student も同じ)
  - クラウドエージェントは含まれない。コードレビューは一部の機能のみ
- 利用枠を使い切った場合は、第1段階や第2段階の方法に切り替える

<!-- _footer: '[GitHub Docs「GitHub Copilot のプラン」](https://docs.github.com/ja/copilot/get-started/plans)' -->

---

## GitHub Copilot を使用するための準備

- 第3回で済ませていること
  - VS Code のインストール
  - GitHub アカウントの作成
  - Copilot へのサインイン
  - まだの人は、[第3回の資料](https://yoppa.org/geidai-ai26/19817.html) の手順1から4を行う
- 今回追加すること: p5.js のプログラムをブラウザで表示するための拡張機能
  1. VS Code の左側にある拡張機能 (Extensions) のアイコンをクリック
  2. 「Live Server」を検索して、インストール

---

## GitHub Copilot を使用したコード生成

1. 作業用のフォルダ (例: p5-copilot) を作り、File > Open Folder で開く
2. チャットを開く (タイトルバーの Copilot アイコンをクリック)
   - Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>I</kbd> / macOS: <kbd>Ctrl</kbd> + <kbd>⌘ Command</kbd> + <kbd>I</kbd>
3. チャットの入力欄で、エージェントを **Agent** に切り替える
4. 作りたいものを言葉で依頼する
5. 作成されたファイルの内容を確認し、変更を採用する
6. index.html を開いた状態で、右下の **Go Live** をクリック
   - ブラウザに結果が表示される
7. 結果を見ながら、修正や追加を依頼する

---

## 依頼の例

```text
p5.jsを使用して、かわいいキャラクターを描いてください。
画面はフルスクリーンで、カラフルで愛らしいキャラクターにしてください。
index.html と sketch.js を作成し、p5.js は CDN から読み込んでください。
```

- エージェントが、2つのファイルを作成する
  - **index.html**: p5.js を読み込む
  - **sketch.js**: プログラムの本体

---

## index.html の例

<style scoped>pre { font-size: 0.8em; }</style>

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8" />
    <style>
      body { margin: 0; overflow: hidden; }
    </style>
    <script src="https://cdn.jsdelivr.net/npm/p5@2.3.4/lib/p5.min.js"></script>
  </head>
  <body>
    <script src="sketch.js"></script>
  </body>
</html>
```

---

## VS Code と GitHub Copilot の画面

![bg right:55% contain](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-121622-1.png)

- 左側のエディタにコードが書き込まれる
- 右側のチャットで Copilot とやりとりをする
- 2024年11月時点の画面
  - 現在の VS Code では、画面の構成や選べるモデルが変わっている

---

## 生成された「かわいいキャラクター」

![bg right:50% contain](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-121932-1-1.png)

- 思ったとおりにならないときは、言葉で修正を重ねていく
  - 「もっとカラフルに」
  - 「マウスの位置に合わせて目が動くように」
- エラーが出たときは、エラーの内容をそのまま伝えて、修正を頼む

---

## 参考: YCAM ワークショップ「AIを使ったコード生成」

![bg right:45% contain](https://yoppa.org/wp-content/uploads/2024/11/image.jpg)

- 2024年に山口情報芸術センター (YCAM) で行ったワークショップ
- [ハンズオン: AIを使ったコード生成 (YCAMワークショップ 2024)](https://yoppa.org/ycam24/16647.html)
- Copilot の登録方法や画面は当時のもの
  - 準備の手順は、第3回の資料を参照

<!-- _footer: '画像出典: [YCAM InterLab Camp vol.5「ホモ・コーデンス—AI時代、人類はどう描くのか」](https://www.ycam.jp/events/2024/interlab-camp-vol5/)' -->

---

## 参考: そのほかのコーディングエージェント

- AIにプログラミングを任せるツールは、GitHub Copilot のほかにも数多くある
  - [Claude Code](https://claude.com/product/claude-code) (Anthropic)
  - [Codex](https://openai.com/codex/) (OpenAI)
  - [Antigravity](https://antigravity.google/) (Google)
  - [Cursor](https://cursor.com/)
- どのツールにも共通する流れ
  - 言葉で依頼し、AIが作業を進め、人間がその結果を確認する

---

<!-- _class: bigtxt -->

# まとめ<br>AIにどこまで任せるか

---

## 3つの段階

- **対話型AIに質問する**
  - AIが書いたコードを、人間がコピー&ペーストで運び、実行する
- **AI機能を搭載したエディターを使う**
  - エディタがコードをAIに渡し、人間はAIの提案を受け入れるかどうかを選ぶ
- **エージェントに任せる**
  - AIがファイルを作り、コードを書き、エラーの修正まで進める
- 段階が進むほど、AIに任せる範囲は広がり、人間が手を動かす部分は減っていく

---

## 人間の側に残ること

- 何を作りたいのかを言葉にすること、返ってきた結果を見て判断すること
  - 「AIの提案を受け入れるか、書き換えるか、断るかを、自分で選べること」(第3回) は、コードでも同じ
- プログラミングの経験がなくても、言葉で依頼すれば、動くものを作れる
  - 前回構想した作品の一部を、まず小さなプログラムとして試してみることもできる
- 動いたところで終わりにせず、コードが何をしているのかをAIに説明してもらう
  - しくみが分かるほど、次に頼めることが具体的になっていく

---

## 参考文献

- [p5.js. "p5.js v2 Transition Guide for Middle School and High School Educators."](https://p5js.org/tutorials/v2_transition/)
- [Processing Foundation. "p5.js-compatibility."](https://github.com/processing/p5.js-compatibility)
- [GitHub Docs「GitHub Copilot のプラン」](https://docs.github.com/ja/copilot/get-started/plans)
- [Visual Studio Code Docs. "GitHub Copilot in VS Code."](https://code.visualstudio.com/docs/copilot/overview)
- [OpenAI Help Center. "Retiring GPT-4o and other ChatGPT models."](https://help.openai.com/en/articles/20001051-retiring-gpt-4o-and-other-chatgpt-models) 2026.
- [きゃべ / Masaya Kurahashi「p5.CodingWithAIのこれまでを振り返る 2024」](https://kyabe.net/blog/2024-p5-coding-with-ai/)
