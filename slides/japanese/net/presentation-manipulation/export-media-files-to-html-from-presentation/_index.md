---
title: プレゼンテーションからメディアファイルを HTML にエクスポート
linktitle: プレゼンテーションからメディアファイルを HTML にエクスポート
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーションの共有を最適化します。このステップ バイ ステップ ガイドで、プレゼンテーションからメディア ファイルを HTML にエクスポートする方法を学びます。
weight: 15
url: /ja/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プレゼンテーションからメディアファイルを HTML にエクスポート


このチュートリアルでは、Aspose.Slides for .NET を使用して、プレゼンテーションからメディア ファイルを HTML にエクスポートする手順を説明します。Aspose.Slides は、PowerPoint プレゼンテーションをプログラムで操作できる強力な API です。このガイドを読み終えると、プレゼンテーションを HTML 形式に簡単に変換できるようになります。それでは、始めましょう。

## 1. はじめに

PowerPoint プレゼンテーションにはビデオなどのマルチメディア要素が含まれることが多く、Web 互換性のためにこれらのプレゼンテーションを HTML 形式にエクスポートする必要がある場合があります。Aspose.Slides for .NET は、このタスクをプログラムで実行する便利な方法を提供します。

## 2. 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Slides for .NET: Aspose.Slides for .NETライブラリがインストールされている必要があります。ダウンロードはこちらから行えます。[ここ](https://releases.aspose.com/slides/net/).

## 3. プレゼンテーションの読み込み

まず、HTML に変換する PowerPoint プレゼンテーションを読み込む必要があります。また、HTML ファイルを保存する出力ディレクトリも指定する必要があります。プレゼンテーションを読み込むためのコードは次のとおりです。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

//プレゼンテーションの読み込み
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    //ここにあなたのコード
}
```

## 4. HTMLオプションの設定

次に、変換用の HTML オプションを設定しましょう。HTML コントローラー、HTML フォーマッタ、スライド画像フォーマットを構成します。このコードにより、HTML ファイルにマルチメディア要素を表示するために必要なコンポーネントが含まれるようになります。

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// HTMLオプションの設定
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. HTMLファイルの保存

HTMLオプションを設定したら、HTMLファイルを保存できます。`Save`プレゼンテーション オブジェクトのメソッドは、埋め込まれたマルチメディア要素を含む HTML ファイルを生成します。

```csharp
//ファイルの保存
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. 結論

おめでとうございます! Aspose.Slides for .NET を使用して、PowerPoint プレゼンテーションからメディア ファイルを HTML にエクスポートできました。これにより、プレゼンテーションをオンラインで簡単に共有し、マルチメディア要素が適切に表示されるようになります。

## 7. よくある質問

### Q1: Aspose.Slides for .NET は無料のライブラリですか?
 A1: Aspose.Slides for .NETは商用ライブラリですが、無料トライアル版を入手できます。[ここ](https://releases.aspose.com/)試してみる。

### Q2: HTML 出力をさらにカスタマイズできますか?
A2: はい、コード内の HTML オプションを変更することで HTML 出力をカスタマイズできます。

### Q3: Aspose.Slides for .NET は他のエクスポート形式をサポートしていますか?
A3: はい、Aspose.Slides for .NET は、PDF、画像形式など、さまざまなエクスポート形式をサポートしています。

### Q4: Aspose.Slides for .NET のサポートはどこで受けられますか?
 A4: Asposeフォーラムでサポートを見つけたり質問したりできます。[ここ](https://forum.aspose.com/).

### Q5: Aspose.Slides for .NET のライセンスを購入するにはどうすればよいですか?
 A5: ライセンスは以下から購入できます。[このリンク](https://purchase.aspose.com/buy).

このチュートリアルを完了すると、Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションからメディア ファイルを HTML にエクスポートするスキルが身につきます。マルチメディアを豊富に含んだプレゼンテーションをオンラインで共有しましょう。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
