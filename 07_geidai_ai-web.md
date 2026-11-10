---
title: "AIを活用したプログラミング入門"
date: 2026-11-10T12:00:17+09:00
categories: ["geidai-ai26"]
---

![](https://yoppa.org/wp-content/uploads/2025/11/Image_fx-1.jpg)

<small>画像: 画像生成AI (Google ImageFX) で生成</small>

今回は「AIを活用したプログラミング入門」というテーマで、AIと一緒にプログラムを書く方法を実践的に学びます。

前回は、最終制作に向けて、制約を外して作品を構想する課題に取り組みました。構想した作品を形にする方法のひとつが、プログラミングです。いまは、プログラミングの経験がなくても、AIの力を借りて、動くプログラムを作れるようになりました。

まず、題材として使う p5.js を簡単に紹介します。続いて、AIを活用したコーディングを3つの段階で体験します。第1段階では ChatGPT などの対話型AIに質問してコードを生成し、第2段階ではAI機能を搭載したエディターを使います。第3段階では、第3回で準備した VS Code と GitHub Copilot を使い、AIにより多くの作業を任せる方法を試します。

* コーディングの題材: p5.js の簡単な紹介
* AIによるコーディング 1: 対話型AIに質問する
* AIによるコーディング 2: AI機能を搭載したエディターを使う
* AIによるコーディング 3: さらに高度なAIとの連携

## スライド資料

* [スライド資料 (PDF)](https://drive.google.com/file/d/1gJPOPQuPLfpfYBew_JmPzMmsp9VaeEG7/view?usp=sharing)

## コーディングの題材: p5.js の簡単な紹介

### p5.js とは

[![](https://img.youtube.com/vi/HerCR8bw_GE/maxresdefault.jpg)](https://www.youtube.com/watch?v=HerCR8bw_GE)

<small>画像出典: [Code! Programming with p5.js for Beginners Trailer (YouTube)](https://youtu.be/HerCR8bw_GE) (The Coding Train)</small>

[p5.js](https://p5js.org/) は、絵やアニメーション、インタラクティブな作品をプログラムで作るための JavaScript のライブラリです。

* 第5回のタイムラインにも登場した、ビジュアルアートのためのプログラミング環境「Processing」の考え方を、JavaScript で実現したもの
* Web ブラウザでそのまま実行できる
* アートやデザイン、インタラクティブなメディア作品の制作に適している
* シンプルな書き方で、初心者でも直感的に使え、プログラミングの学習にも向いている
* 公式サイトに、多くのチュートリアルやリファレンスがある
* 活発なコミュニティによるサポートがある

インストールは不要で、ブラウザで [p5.js Web Editor](https://editor.p5js.org/) を開けば、すぐにプログラムを書いて実行できます。

### p5.js でどんなことができるのか - OpenProcessing

[![](https://yoppa.org/wp-content/uploads/2024/11/image-5-1024x527.png)](https://openprocessing.org/)

<small>画像出典: [OpenProcessing](https://openprocessing.org/)</small>

[OpenProcessing](https://openprocessing.org/) は、p5.js を使ったプログラムを、オンラインで作成し、共有できるサービスです。世界中のクリエイティブコーダーの作品を、ソースコードも含めて見ることができます。

### 簡単なプログラム例

p5.js のプログラムは、次のような形をしています。

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

実行すると、画面の中央に円が描かれます。

![](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-103359-1.png)

いまの段階では、コードの意味がまったく分からなくてもかまいません。このようなプログラムを、AIの力を借りて生成してみましょう。

### p5.js のバージョンについて

2026年8月から、p5.js Web Editor で最初に選ばれているバージョンが、p5.js 2.x (2026年11月現在は 2.3.4) になりました。上のような基本的なプログラムは、1.x でも 2.x でも同じように動きます。

ただし、画像や音声などのファイルを読み込む方法 (preload) など、いくつかの書き方が 2.x で変わりました。AIは、これまで主流だった 1.x の書き方でコードを生成することがあり、そのままでは動かない場合があります。うまく動かないときは、次の方法を試してください。

* AIへの依頼に「p5.js 2.x で」と書き添える
* 表示されたエラーメッセージを、そのままAIに伝えて修正してもらう
* p5.js Web Editor の右上にあるバージョンの表示 (p5.js 2.3.4 など) をクリックして設定 (Settings > Library Management) を開き、1.x の書き方を使えるようにする互換アドオン (Preload など) をオンにするか、p5.js Version を 1.x に切り替える

## AIによるコーディング 1: 対話型AIに質問する

### ChatGPT に質問する

もっとも手軽に始められる方法は、ChatGPT などの対話型AIに、作りたいプログラムを言葉で伝えることです。たとえば、次のように質問します。

```text
ブラウザの画面中央に円を描くプログラムを作りたいです。どのようにすればよいでしょうか?
表示領域はフルスクリーンにしてください。使用する開発環境は、p5.jsを使用してください。
```

ChatGPT に質問すると、次のようなコードが返ってきました。

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

コードといっしょに、その説明と、実行するための手順も示されます。

* **setup 関数**: createCanvas(windowWidth, windowHeight) で、ブラウザのウィンドウ全体をキャンバスにする
* **draw 関数**: background(220) で背景を塗りつぶし、ellipse() で画面の中心に直径100の円を描く
* **windowResized 関数**: ウィンドウの大きさが変わったときに、キャンバスの大きさを合わせる
* **実行の手順**: p5.js Web Editor を開き、コードをコピー&ペーストして、再生ボタンを押す

これは2024年11月に、当時の ChatGPT (GPT-4o) に質問したときの回答です。GPT-4o は2026年2月に ChatGPT での提供を終え、モデルは新しいものに入れ替わっていますが、同じように質問できます。同じ質問をしても、返ってくるコードや説明は毎回少しずつ変わります。

### 実行結果

![](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-110352-1.png)

生成されたコードを [p5.js Web Editor](https://editor.p5js.org/) にコピー&ペーストして実行すると、依頼したとおり、画面の中央に円が描かれました。

### 対話型AIを使うときのヒント

* 最初に「p5.js で」と、制作に使う環境を伝える
* ChatGPT だけでなく、Gemini や Claude でも同じように質問できる
* コードの意味が分からないときは、「このコードを1行ずつ説明して」と頼む
* 思ったとおりにならないときは、何が違うのかを言葉にして、修正を頼む
* ChatGPT や Gemini の Canvas、Claude のアーティファクトのように、生成したコードをチャットの画面のなかで動かして確かめられる機能もある (サービスやプランによって使える範囲が異なる)

### 実習: 対話型AIによるコード生成を試してみる

1. ChatGPT などの対話型AIに、p5.js で作りたいものをリクエストする
2. 生成されたコードを [p5.js Web Editor](https://editor.p5js.org/) にコピー&ペーストする
3. 再生ボタンを押して、コードを実行する
4. 結果を見て、修正や追加を頼む

## AIによるコーディング 2: AI機能を搭載したエディターを使う

### もっと高度な機能を利用したい

対話型AIに質問する方法では、コードをコピー&ペーストして行き来する手間がかかります。次のようなことができると、もっと便利です。

* 生成された結果を見ながら、対話を重ねてAIのサポートを受けたい
* エラーが出たときにも、AIに助けてほしい
* すでにあるコードを、AIに改良してほしい

### p5.CodingWithAI を使ってみる

[![](https://kyabe.net/static/fdec8457230ed05b1fea8500a5215ef2/thumbnail.png)](https://app.kyabe.net/p5-coding-with-ai/)

<small>画像出典: [きゃべ / Masaya Kurahashi「p5.CodingWithAI」](https://kyabe.net/works/p5-coding-with-ai/)</small>

[p5.CodingWithAI](https://app.kyabe.net/p5-coding-with-ai/) は、[きゃべ / Masaya Kurahashi](https://kyabe.net/) さんが開発した、ChatGPT との連携機能を備えた p5.js の Web エディタです。

* 画面は、コード、実行結果のプレビュー、AIとのチャットに分かれている
* チャットに言葉でリクエストを送ると、AIが解説とともに、リクエストに合わせたコードの変更を提案する
* 提案を受け入れるかどうかは、そのつど自分で選ぶ
* 提案されたコードをもとに人間が工夫を重ねて作品をつくる、人間とAIの共創の可能性を探るプロジェクト
* 無料で公開されている。最初の読み込みには少し時間がかかる
* 試験的なプロジェクトのため、予告なく提供を終了する可能性がある

詳しい使い方は、実際にデモをしながら解説します。

![](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-115424-1.png)

先ほど ChatGPT にしたのと同じ質問を、p5.CodingWithAI に送ってみました。エディタにコードが入力され、そのまま右側に実行結果が表示されます。

p5.CodingWithAI が使えない場合は、第1回で紹介した [Text-GPT-p5](https://text-gpt-p5.vercel.app/) でも、対話しながら p5.js のコードを生成できます。

### 実習: p5.CodingWithAI でコード生成

1. 最初に、プロンプトから基本になるコードを生成する。または、[OpenProcessing](https://openprocessing.org/) などから気になるコードを選んで、コピー&ペーストする
2. リクエストをくりかえして、少しずつ自分の好みの結果に近づけていく
3. 提案されたコードを受け入れるかどうかは、そのつど吟味する

最終的にどのようなコードができあがるでしょうか。

## AIによるコーディング 3: さらに高度なAIとの連携

### GitHub Copilot を使用してみる

[GitHub Copilot](https://github.com/features/copilot) は、GitHub が提供する、プログラミングを支援するAIです。2021年に、書きかけのコードの続きを提案する「AIペアプログラマー」として登場しました。当初は OpenAI のモデル Codex をもとにしていましたが、現在は OpenAI、Anthropic、Google など複数の企業のAIモデルを使い、ファイルの作成からプログラムの実行、エラーの修正までを自律的に進める「コーディングエージェント」へと発展しています。VS Code をはじめ、Visual Studio、JetBrains、Xcode など多くのエディタで使うことができます。

第3回では、Copilot の補完機能を使って文章を書きました。今回は、本来の用途であるプログラミングに使います。

### GitHub Copilot の主な機能

* **コード補完**: 入力中のコードの続きを予測して提案する。関数の名前やコメントから、コード全体を生成することもできる
* **チャット**: 言葉で質問や指示をすると、コードの説明や修正案を返す
* **インラインチャット**: エディタのなかで、選択した部分について直接指示する
* **エージェント**: 指示を受けて、ファイルの作成や編集、プログラムの実行、エラーの修正までを自分で進める
* **クラウドエージェント**: GitHub 上で作業を任せ、結果を変更の提案 (プルリクエスト) として受け取る
* **コードレビュー**: 書いたコードの問題点や改善点を指摘する
* **モデルの選択**: 複数のAIモデルから選んで使う (Copilot Free と Copilot Student は自動選択のみ)
* **多言語への対応**: JavaScript、Python、TypeScript など、多くのプログラミング言語で使える

使える機能や回数は、プランによって異なります (2026年11月現在)。無料の Copilot Free では、補完は月2,000回まで、チャットとエージェントは決められた利用枠の範囲で使えます。クラウドエージェントは Copilot Free には含まれず、コードレビューも一部の機能に限られます。利用枠を使い切った場合は、第1段階や第2段階の方法に切り替えてください。

### GitHub Copilot を使用するための準備

VS Code のインストール、GitHub アカウントの作成、Copilot へのサインインは、第3回で済ませています。まだの人は、[第3回の資料](https://yoppa.org/geidai-ai26/19817.html) の手順1から4を行ってください。

今回は、p5.js のプログラムをブラウザで表示するために、拡張機能をひとつ追加します。

1. VS Code の左側にある拡張機能 (Extensions) のアイコンをクリックする
2. 「Live Server」を検索して、インストールする

### GitHub Copilot を使用したコード生成

Copilot のエージェントに依頼して、p5.js のプログラムを作ります。

1. 作業用のフォルダ (例: p5-copilot) を作り、VS Code の File > Open Folder で開く
2. チャットを開く (タイトルバーの Copilot アイコンをクリック。Windows は <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>I</kbd>、macOS は <kbd>Ctrl</kbd>+<kbd>Cmd</kbd>+<kbd>I</kbd>)
3. チャットの入力欄で、エージェントを **Agent** に切り替える
4. 作りたいものを言葉で依頼する
5. 作成されたファイルの内容を確認し、変更を採用する
6. index.html を開いた状態で、右下の **Go Live** をクリックすると、ブラウザに結果が表示される
7. 結果を見ながら、修正や追加を依頼する

たとえば、次のように依頼します。

```text
p5.jsを使用して、かわいいキャラクターを描いてください。
画面はフルスクリーンで、カラフルで愛らしいキャラクターにしてください。
index.html と sketch.js を作成し、p5.js は CDN から読み込んでください。
```

エージェントは、p5.js を読み込む index.html と、プログラムの本体である sketch.js を作成します。index.html は、たとえば次のような内容になります。

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

![](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-121622-1.png)

<small>2024年11月時点の画面です。現在の VS Code では、画面の構成や選べるモデルが変わっています。</small>

左側のエディタにコードが書き込まれ、右側のチャットで Copilot とやりとりをします。生成された「かわいいキャラクター」は、次のようになりました。

![](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-121932-1-1.png)

思ったとおりにならないときは、「もっとカラフルに」「マウスの位置に合わせて目が動くように」などと、言葉で修正を重ねていきます。エラーが出たときは、エラーの内容をそのまま伝えて、修正を頼みます。

### 参考: YCAM ワークショップ「AIを使ったコード生成」

[![](https://yoppa.org/wp-content/uploads/2024/11/image.jpg)](https://yoppa.org/ycam24/16647.html)

<small>画像出典: [YCAM InterLab Camp vol.5「ホモ・コーデンス—AI時代、人類はどう描くのか」](https://www.ycam.jp/events/2024/interlab-camp-vol5/)</small>

GitHub Copilot を使ったコード生成は、2024年に山口情報芸術センター (YCAM) で行ったワークショップでも取り上げました。資料は「[ハンズオン: AIを使ったコード生成 (YCAMワークショップ 2024)](https://yoppa.org/ycam24/16647.html)」で公開しています。ただし、Copilot の登録方法や画面は当時のものです。準備の手順は、第3回の資料を参照してください。

### 参考: そのほかのコーディングエージェント

AIにプログラミングを任せるツールは、GitHub Copilot のほかにも数多くあります。

* [Claude Code](https://claude.com/product/claude-code) (Anthropic)
* [Codex](https://openai.com/codex/) (OpenAI)
* [Antigravity](https://antigravity.google/) (Google)
* [Cursor](https://cursor.com/)

どのツールも、言葉で依頼し、AIが作業を進め、人間がその結果を確認する、という流れは共通しています。

## まとめ: AIにどこまで任せるか

今日は、AIを活用したコーディングを、3つの段階で体験しました。

* **対話型AIに質問する**: AIが書いたコードを、人間がコピー&ペーストで運び、実行する
* **AI機能を搭載したエディターを使う**: エディタがコードをAIに渡し、人間はAIの提案を受け入れるかどうかを選ぶ
* **エージェントに任せる**: AIがファイルを作り、コードを書き、エラーの修正まで進める

段階が進むほど、AIに任せる範囲は広がり、人間が手を動かす部分は減っていきます。それでも、何を作りたいのかを言葉にすること、返ってきた結果を見て判断することは、人間の側に残ります。第3回で考えた「AIの提案を受け入れるか、書き換えるか、断るかを、自分で選べること」は、コードでも同じです。

プログラミングの経験がなくても、言葉で依頼すれば、動くものを作れるようになりました。前回構想した作品の一部を、まず小さなプログラムとして試してみることもできます。そのときは、動いたところで終わりにせず、コードが何をしているのかをAIに説明してもらいましょう。しくみが分かるほど、次に頼めることが具体的になっていきます。

## 関連リンク

* [p5.js](https://p5js.org/)
* [p5.js Web Editor](https://editor.p5js.org/)
* [OpenProcessing](https://openprocessing.org/)
* [The Coding Train](https://thecodingtrain.com/)
* [ChatGPT](https://chatgpt.com/)
* [Gemini](https://gemini.google.com/)
* [Claude](https://claude.ai/)
* [p5.CodingWithAI](https://app.kyabe.net/p5-coding-with-ai/)
* [きゃべ / Masaya Kurahashi「p5.CodingWithAIのこれまでを振り返る 2024」](https://kyabe.net/blog/2024-p5-coding-with-ai/)
* [Text-GPT-p5](https://text-gpt-p5.vercel.app/)
* [GitHub Copilot](https://github.com/features/copilot)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Live Server (Visual Studio Marketplace)](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
* [ハンズオン: AIを使ったコード生成 (YCAMワークショップ 2024)](https://yoppa.org/ycam24/16647.html)
* [人工知能と創作 2025「AIを活用したプログラミング入門」](https://yoppa.org/geidai-ai25/18650.html)

## 参考文献

* [p5.js. "p5.js v2 Transition Guide for Middle School and High School Educators."](https://p5js.org/tutorials/v2_transition/)
* [Processing Foundation. "p5.js-compatibility."](https://github.com/processing/p5.js-compatibility)
* [GitHub Docs「GitHub Copilot のプラン」](https://docs.github.com/ja/copilot/get-started/plans)
* [Visual Studio Code Docs. "GitHub Copilot in VS Code."](https://code.visualstudio.com/docs/copilot/overview)
* [OpenAI Help Center. "Retiring GPT-4o and other ChatGPT models."](https://help.openai.com/en/articles/20001051-retiring-gpt-4o-and-other-chatgpt-models) 2026.
