---
title: PPTをPPTX形式に変換する
linktitle: PPTをPPTX形式に変換する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PPT を PPTX に簡単に変換する方法を学びます。シームレスなフォーマット変換のためのコード例を含むステップバイステップのガイド。
type: docs
weight: 25
url: /ja/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

.NET を使用して PowerPoint ファイルを古い PPT 形式から新しい PPTX 形式に変換する必要がある場合は、ここが正しい場所です。このステップバイステップのチュートリアルでは、Aspose.Slides for .NET API を使用するプロセスを説明します。この強力なライブラリを使用すると、そのような変換を簡単に簡単に処理できます。始めましょう！

## 前提条件

コードに入る前に、次の設定がされていることを確認してください。

- Visual Studio: Visual Studio がインストールされており、.NET 開発の準備ができていることを確認します。
-  Aspose.Slides for .NET: Aspose.Slides for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/slides/net/).

## プロジェクトのセットアップ

1. 新しいプロジェクトを作成する: Visual Studio を開き、新しい C# プロジェクトを作成します。

2. Aspose.Slides への参照を追加する: ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択して、「Aspose.Slides」を検索します。パッケージをインストールします。

3. 必要な名前空間をインポートします。

```csharp
using Aspose.Slides;
```

## PPT から PPTX への変換

プロジェクトのセットアップが完了したので、PPT ファイルを PPTX に変換するコードを作成しましょう。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// PPT ファイルを表すプレゼンテーション オブジェクトをインスタンス化する
Presentation pres = new Presentation(srcFileName);

//プレゼンテーションを PPTX 形式で保存する
pres.Save(outPath, SaveFormat.Pptx);
```

このコード スニペットでは次のようになります。

- `dataDir`は、PPT ファイルが存在するディレクトリ パスに置き換える必要があります。
- `outPath`は、変換された PPTX ファイルを保存するディレクトリに置き換える必要があります。
- `srcFileName`は入力 PPT ファイルの名前です。
- `destFileName`出力 PPTX ファイルの任意の名前です。

## 結論

おめでとう！ Aspose.Slides for .NET API を使用して、PowerPoint プレゼンテーションを PPT から PPTX 形式に変換することに成功しました。この強力なライブラリは、このような複雑なタスクを簡素化し、.NET 開発エクスペリエンスをよりスムーズにします。

まだお持ちでない場合は、[.NET 用 Aspose.Slides をダウンロード](https://releases.aspose.com/slides/net/)そしてその機能をさらに探求してください。

さらに詳しいチュートリアルとヒントについては、こちらをご覧ください。[ドキュメンテーション](https://reference.aspose.com/slides/net/).

## よくある質問

### 1. Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、開発者がプログラムで PowerPoint プレゼンテーションを作成、操作、変換できるようにする .NET ライブラリです。

### 2. Aspose.Slides for .NET を使用して他の形式を PPTX に変換できますか?
はい、Aspose.Slides for .NET は、PPT、PPTX、ODP などを含むさまざまな形式をサポートしています。

### 3. Aspose.Slides for .NET は無料で使用できますか?
いいえ、これは商用ライブラリですが、[無料トライアル](https://releases.aspose.com/)その機能を評価します。

### 4. Aspose.Slides for .NET でサポートされている他のドキュメント形式はありますか?
はい。Aspose.Slides for .NET は、Word ドキュメント、Excel スプレッドシート、およびその他のファイル形式の操作もサポートしています。

### 5. Aspose.Slides for .NET に関するサポートや質問はどこで受けられますか?
質問への回答を見つけたり、サポートを求めることができます。[Aspose.Slides フォーラム](https://forum.aspose.com/).

