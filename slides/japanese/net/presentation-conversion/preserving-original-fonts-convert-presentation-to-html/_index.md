---
"description": "Aspose.Slides for .NET を使用して、プレゼンテーションをHTMLに変換する際に元のフォントを維持する方法を学びます。フォントの一貫性と視覚的なインパクトを簡単に確保できます。"
"linktitle": "元のフォントを保持 - プレゼンテーションをHTMLに変換する"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "元のフォントを保持 - プレゼンテーションをHTMLに変換する"
"url": "/ja/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 元のフォントを保持 - プレゼンテーションをHTMLに変換する


この包括的なガイドでは、Aspose.Slides for .NET を使用してプレゼンテーションを HTML に変換する際、元のフォントを保持するプロセスを詳しく説明します。必要な C# ソースコードを提供し、各ステップを詳細に説明します。このチュートリアルを完了すると、変換された HTML ドキュメントのフォントが元のプレゼンテーションのフォントに忠実であることを確認できるようになります。

## 1. はじめに

PowerPointプレゼンテーションをHTMLに変換する際、コンテンツの視覚的な一貫性を保つために、元のフォントを維持することが重要です。Aspose.Slides for .NETは、これを実現するための強力なソリューションを提供します。このチュートリアルでは、変換プロセス中に元のフォントを維持するために必要な手順を説明します。

## 2. 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Visual Studio がマシンにインストールされています。
- Aspose.Slides for .NET ライブラリがプロジェクトに追加されました。

## 3. プロジェクトの設定

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.Slides for .NET ライブラリを参照として追加します。

## 4. プレゼンテーションの読み込み

PowerPoint プレゼンテーションを読み込むには、次のコードを使用します。

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // ここにあなたのコード
}
```

交換する `"Your Document Directory"` プレゼンテーション ファイルへのパスを入力します。

## 5. デフォルトフォントの除外

Calibri や Arial などのデフォルトのフォントを除外するには、次のコードを使用します。

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

必要に応じてこのリストをカスタマイズできます。

## 6. すべてのフォントを埋め込む

次に、HTMLドキュメントにすべてのフォントを埋め込みます。これにより、元のフォントが保持されます。以下のコードを使用してください。

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. HTMLとして保存

次に、プレゼンテーションを埋め込みフォントを含む HTML ドキュメントとして保存します。

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

交換する `"output.html"` 希望する出力ファイル名を入力します。

## 8. 結論

このチュートリアルでは、Aspose.Slides for .NET を使用してPowerPointプレゼンテーションをHTMLに変換する際、元のフォントを保持する方法を示しました。これらの手順に従うことで、変換されたHTMLドキュメントで元のプレゼンテーションの視覚的な整合性を維持できます。

## 9. よくある質問

### Q1: 除外フォントのリストをカスタマイズできますか?

はい、できます。 `fontNameExcludeList` 要件に応じて特定のフォントを含めたり除外したりする配列。

### Q2: すべてのフォントを埋め込みたくない場合はどうすればよいでしょうか?

特定のフォントのみを埋め込みたい場合は、コードを修正してください。詳細については、Aspose.Slides for .NET のドキュメントをご覧ください。

### Q3: Aspose.Slides for .NET を使用するにはライセンス要件がありますか?

はい、Aspose.Slides for .NET をプロジェクトで使用するには、有効なライセンスが必要になる場合があります。ライセンス情報については、Aspose の Web サイトをご覧ください。

### Q4: Aspose.Slides for .NET を使用して他のファイル形式を HTML に変換できますか?

Aspose.Slides for .NETは主にPowerPointプレゼンテーションに特化しています。他のファイル形式をHTMLに変換するには、それらの形式に特化した他のAspose製品を検討する必要があるかもしれません。

### Q5: 追加のリソースやサポートにはどこでアクセスできますか?

詳細なドキュメント、チュートリアル、サポートについては、Aspose の Web サイトをご覧ください。 [Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/) 詳細情報については。


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}