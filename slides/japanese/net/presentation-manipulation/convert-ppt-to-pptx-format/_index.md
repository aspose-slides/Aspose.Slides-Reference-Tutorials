---
title: PPTをPPTX形式に変換する
linktitle: PPTをPPTX形式に変換する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PPT を PPTX に簡単に変換する方法を学びます。シームレスな形式変換のためのコード例を含むステップバイステップ ガイド。
weight: 25
url: /ja/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PPTをPPTX形式に変換する


.NET を使用して PowerPoint ファイルを古い PPT 形式から新しい PPTX 形式に変換する必要がある場合は、ここが最適な場所です。このステップ バイ ステップのチュートリアルでは、Aspose.Slides for .NET API を使用したプロセスについて説明します。この強力なライブラリを使用すると、このような変換を簡単に処理できます。さあ、始めましょう!

## 前提条件

コードに進む前に、次の設定がされていることを確認してください。

- Visual Studio: Visual Studio がインストールされ、.NET 開発の準備ができていることを確認します。
-  Aspose.Slides for .NET: Aspose.Slides for .NETライブラリを以下からダウンロードしてインストールします。[ここ](https://releases.aspose.com/slides/net/).

## プロジェクトの設定

1. 新しいプロジェクトを作成する: Visual Studio を開き、新しい C# プロジェクトを作成します。

2. Aspose.Slides への参照を追加します。ソリューション エクスプローラーでプロジェクトを右クリックし、「NuGet パッケージの管理」を選択して、「Aspose.Slides」を検索します。パッケージをインストールします。

3. 必要な名前空間をインポートします:

```csharp
using Aspose.Slides;
```

## PPT を PPTX に変換する

プロジェクトの設定が完了したので、PPT ファイルを PPTX に変換するコードを記述しましょう。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

//PPTファイルを表すプレゼンテーションオブジェクトをインスタンス化する
Presentation pres = new Presentation(srcFileName);

//プレゼンテーションをPPTX形式で保存する
pres.Save(outPath, SaveFormat.Pptx);
```

このコードスニペットでは:

- `dataDir`PPT ファイルが保存されているディレクトリ パスに置き換える必要があります。
- `outPath`変換された PPTX ファイルを保存するディレクトリに置き換える必要があります。
- `srcFileName`入力 PPT ファイルの名前です。
- `destFileName`出力 PPTX ファイルの希望の名前です。

## 結論

おめでとうございます! Aspose.Slides for .NET API を使用して、PowerPoint プレゼンテーションを PPT 形式から PPTX 形式に正常に変換できました。この強力なライブラリは、このような複雑なタスクを簡素化し、.NET 開発エクスペリエンスをよりスムーズにします。

まだお持ちでない場合は、[Aspose.Slides for .NET をダウンロード](https://releases.aspose.com/slides/net/)さらにその機能について探ってみましょう。

その他のチュートリアルやヒントについては、[ドキュメンテーション](https://reference.aspose.com/slides/net/).

## よくある質問

### 1. Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、開発者がプログラムで PowerPoint プレゼンテーションを作成、操作、変換できるようにする .NET ライブラリです。

### 2. Aspose.Slides for .NET を使用して他の形式を PPTX に変換できますか?
はい、Aspose.Slides for .NET は、PPT、PPTX、ODP など、さまざまな形式をサポートしています。

### 3. Aspose.Slides for .NET は無料で使用できますか?
いいえ、商業図書館ですが、[無料トライアル](https://releases.aspose.com/)その特徴を評価する。

### 4. Aspose.Slides for .NET でサポートされている他のドキュメント形式はありますか?
はい、Aspose.Slides for .NET は、Word 文書、Excel スプレッドシート、その他のファイル形式での作業もサポートしています。

### 5. Aspose.Slides for .NET に関するサポートや質問はどこで受けられますか?
質問に対する回答やサポートを求めるには[Aspose.Slides フォーラム](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
