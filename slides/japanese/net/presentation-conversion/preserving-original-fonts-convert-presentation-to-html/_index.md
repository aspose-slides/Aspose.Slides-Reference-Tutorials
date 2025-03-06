---
title: 元のフォントの保持 - プレゼンテーションを HTML に変換する
linktitle: 元のフォントの保持 - プレゼンテーションを HTML に変換する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーションを HTML に変換しながら元のフォントを保持する方法を学びます。フォントの一貫性と視覚的なインパクトを簡単に確保します。
weight: 14
url: /ja/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 元のフォントの保持 - プレゼンテーションを HTML に変換する


この包括的なガイドでは、Aspose.Slides for .NET を使用してプレゼンテーションを HTML に変換するときに元のフォントを保持するプロセスについて説明します。必要な C# ソース コードを提供し、各手順を詳しく説明します。このチュートリアルの最後には、変換された HTML ドキュメントのフォントが元のプレゼンテーションに忠実であることを確認できるようになります。

## 1. はじめに

PowerPoint プレゼンテーションを HTML に変換する場合、コンテンツの視覚的な一貫性を保つために元のフォントを維持することが重要です。Aspose.Slides for .NET は、これを実現するための強力なソリューションを提供します。このチュートリアルでは、変換プロセス中に元のフォントを維持するために必要な手順を説明します。

## 2. 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- マシンに Visual Studio がインストールされています。
- Aspose.Slides for .NET ライブラリがプロジェクトに追加されました。

## 3. プロジェクトの設定

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.Slides for .NET ライブラリを参照として追加します。

## 4. プレゼンテーションの読み込み

PowerPoint プレゼンテーションを読み込むには、次のコードを使用します。

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    //ここにあなたのコード
}
```

交換する`"Your Document Directory"`プレゼンテーション ファイルへのパスを入力します。

## 5. デフォルトフォントを除外する

Calibri や Arial などのデフォルトのフォントを除外するには、次のコードを使用します。

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

必要に応じてこのリストをカスタマイズできます。

## 6. すべてのフォントを埋め込む

次に、すべてのフォントを HTML ドキュメントに埋め込みます。これにより、元のフォントが保持されます。次のコードを使用します。

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

交換する`"output.html"`希望する出力ファイル名を入力します。

## 8. 結論

このチュートリアルでは、Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを HTML に変換するときに元のフォントを保持する方法について説明しました。これらの手順に従うことで、変換された HTML ドキュメントで元のプレゼンテーションの視覚的な整合性が維持されることを保証できます。

## 9. よくある質問

### Q1: 除外フォントのリストをカスタマイズできますか?

はい、できます。`fontNameExcludeList`要件に応じて特定のフォントを含めたり除外したりする配列。

### Q2: すべてのフォントを埋め込みたくない場合はどうすればいいですか?

特定のフォントのみを埋め込む場合は、それに応じてコードを変更できます。詳細については、Aspose.Slides for .NET のドキュメントを参照してください。

### Q3: Aspose.Slides for .NET を使用するにはライセンス要件がありますか?

はい、プロジェクトで Aspose.Slides for .NET を使用するには、有効なライセンスが必要になる場合があります。ライセンス情報については、Aspose の Web サイトを参照してください。

### Q4: Aspose.Slides for .NET を使用して他のファイル形式を HTML に変換できますか?

Aspose.Slides for .NET は主に PowerPoint プレゼンテーションに重点を置いています。他のファイル形式を HTML に変換するには、それらの形式に合わせて調整された他の Aspose 製品を調べる必要がある場合があります。

### Q5: 追加のリソースやサポートにはどこでアクセスできますか?

詳細なドキュメント、チュートリアル、サポートについては、Aspose Webサイトをご覧ください。[Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/)詳細情報については。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
