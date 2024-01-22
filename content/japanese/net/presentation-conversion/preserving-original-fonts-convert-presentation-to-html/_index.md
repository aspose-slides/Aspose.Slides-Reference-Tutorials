---
title: オリジナルのフォントの保持 - プレゼンテーションを HTML に変換する
linktitle: オリジナルのフォントの保持 - プレゼンテーションを HTML に変換する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーションを HTML に変換する際に、元のフォントを保持する方法を学びます。フォントの一貫性と視覚的なインパクトを簡単に確保します。
type: docs
weight: 14
url: /ja/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

この包括的なガイドでは、Aspose.Slides for .NET を使用してプレゼンテーションを HTML に変換するときに、元のフォントを保持するプロセスについて説明します。必要な C# ソース コードを提供し、各手順を詳しく説明します。このチュートリアルを終了するまでに、変換された HTML ドキュメント内のフォントが元のプレゼンテーションに忠実であることを確認できるようになります。

## 1. はじめに

PowerPoint プレゼンテーションを HTML に変換する場合、コンテンツの視覚的な一貫性を確保するために元のフォントを維持することが重要です。 Aspose.Slides for .NET は、これを実現するための強力なソリューションを提供します。このチュートリアルでは、変換プロセス中に元のフォントを保持するために必要な手順を説明します。

## 2. 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Visual Studio がマシンにインストールされていること。
- Aspose.Slides for .NET ライブラリがプロジェクトに追加されました。

## 3. プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.Slides for .NET ライブラリを参照として追加します。

## 4. プレゼンテーションのロード

次のコードを使用して、PowerPoint プレゼンテーションをロードします。

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    //コードはここにあります
}
```

交換する`"Your Document Directory"`プレゼンテーション ファイルへのパスを含めます。

## 5. デフォルトフォントの除外

Calibri や Arial などのデフォルトのフォントを除外するには、次のコードを使用します。

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

必要に応じてこのリストをカスタマイズできます。

## 6. すべてのフォントを埋め込む

次に、すべてのフォントを HTML ドキュメントに埋め込みます。これにより、元のフォントが確実に保持されます。次のコードを使用します。

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. HTMLとして保存する

ここで、フォントが埋め込まれた HTML ドキュメントとしてプレゼンテーションを保存します。

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

交換する`"output.html"`希望の出力ファイル名を付けます。

## 8. 結論

このチュートリアルでは、Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを HTML に変換するときに、元のフォントを保持する方法を説明しました。これらの手順に従うことで、変換された HTML ドキュメントが元のプレゼンテーションの視覚的な整合性を維持していることを確認できます。

## 9. よくある質問

### Q1: 除外されるフォントのリストをカスタマイズできますか?

はい、できます。を変更します。`fontNameExcludeList`配列を使用して、要件に応じて特定のフォントを含めたり除外したりできます。

### Q2: すべてのフォントを埋め込みたくない場合はどうすればよいですか?

特定のフォントのみを埋め込みたい場合は、それに応じてコードを変更できます。詳細については、Aspose.Slides for .NET のドキュメントを参照してください。

### Q3: Aspose.Slides for .NET を使用するためのライセンス要件はありますか?

はい、プロジェクトで Aspose.Slides for .NET を使用するには、有効なライセンスが必要な場合があります。ライセンス情報については、Aspose Web サイトを参照してください。

### Q4: Aspose.Slides for .NET を使用して他のファイル形式を HTML に変換できますか?

Aspose.Slides for .NET は主に PowerPoint プレゼンテーションに焦点を当てています。他のファイル形式を HTML に変換するには、それらの形式に合わせた他の Aspose 製品を検討する必要がある場合があります。

### Q5: 追加のリソースやサポートにはどこでアクセスできますか?

 Aspose Web サイトでは、その他のドキュメント、チュートリアル、サポートを見つけることができます。訪問[Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/)詳細については。
