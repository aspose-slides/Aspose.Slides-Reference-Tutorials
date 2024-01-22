---
title: プレゼンテーションからメディア ファイルを HTML にエクスポート
linktitle: プレゼンテーションからメディア ファイルを HTML にエクスポート
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーションの共有を最適化します。このステップバイステップのガイドでは、プレゼンテーションからメディア ファイルを HTML にエクスポートする方法を学びます。
type: docs
weight: 15
url: /ja/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

このチュートリアルでは、Aspose.Slides for .NET を使用して、プレゼンテーションからメディア ファイルを HTML にエクスポートするプロセスについて説明します。 Aspose.Slides は、PowerPoint プレゼンテーションをプログラムで操作できるようにする強力な API です。このガイドを終えると、プレゼンテーションを HTML 形式に簡単に変換できるようになります。それでは、始めましょう!

## 1. はじめに

PowerPoint プレゼンテーションにはビデオなどのマルチメディア要素が含まれることが多く、Web との互換性を確保するために、これらのプレゼンテーションを HTML 形式にエクスポートする必要がある場合があります。 Aspose.Slides for .NET は、このタスクをプログラムで実行する便利な方法を提供します。

## 2. 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Slides for .NET: Aspose.Slides for .NET ライブラリがインストールされている必要があります。からダウンロードできます[ここ](https://releases.aspose.com/slides/net/).

## 3. プレゼンテーションのロード

まず、HTML に変換する PowerPoint プレゼンテーションをロードする必要があります。 HTML ファイルが保存される出力ディレクトリも指定する必要があります。プレゼンテーションをロードするコードは次のとおりです。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

//プレゼンテーションをロードしています
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    //コードはここにあります
}
```

## 4. HTML オプションの設定

次に、変換用の HTML オプションを設定しましょう。 HTML コントローラー、HTML フォーマッタ、およびスライド画像形式を構成します。このコードは、HTML ファイルにマルチメディア要素を表示するために必要なコンポーネントが含まれていることを確認します。

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// HTML オプションの設定
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. HTMLファイルの保存

HTML オプションを構成したら、HTML ファイルを保存できるようになります。の`Save`プレゼンテーション オブジェクトのメソッドは、マルチメディア要素が埋め込まれた HTML ファイルを生成します。

```csharp
//ファイルを保存する
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. 結論

おめでとう！ Aspose.Slides for .NET を使用して、PowerPoint プレゼンテーションからメディア ファイルを HTML に正常にエクスポートできました。これにより、プレゼンテーションをオンラインで簡単に共有し、マルチメディア要素が適切に表示されるようにすることができます。

## 7. よくある質問

### Q1: Aspose.Slides for .NET は無料のライブラリですか?
 A1: Aspose.Slides for .NET は商用ライブラリですが、以下から無料試用版を入手できます。[ここ](https://releases.aspose.com/)それを試してみることに。

### Q2: HTML 出力をさらにカスタマイズできますか?
A2: はい、コード内の HTML オプションを変更することで HTML 出力をカスタマイズできます。

### Q3: Aspose.Slides for .NET は他のエクスポート形式をサポートしていますか?
A3: はい、Aspose.Slides for .NET は、PDF、画像形式などを含むさまざまなエクスポート形式をサポートしています。

### Q4: Aspose.Slides for .NET のサポートはどこで受けられますか?
 A4: Aspose フォーラムでサポートを見つけたり、質問したりできます。[ここ](https://forum.aspose.com/).

### Q5: Aspose.Slides for .NET のライセンスはどのように購入すればよいですか?
 A5: ライセンスは以下から購入できます。[このリンク](https://purchase.aspose.com/buy).

このチュートリアルを完了すると、Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションからメディア ファイルを HTML にエクスポートするスキルが得られます。マルチメディアを多用したプレゼンテーションをオンラインで共有して楽しんでください。