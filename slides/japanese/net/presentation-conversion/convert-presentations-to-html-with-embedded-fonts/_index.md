---
"description": "Aspose.Slides for .NET を使用して、PowerPoint プレゼンテーションを埋め込みフォント付きの HTML に変換します。オリジナリティをシームレスに維持します。"
"linktitle": "プレゼンテーションを埋め込みフォント付き HTML に変換する"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "プレゼンテーションを埋め込みフォント付き HTML に変換する"
"url": "/ja/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# プレゼンテーションを埋め込みフォント付き HTML に変換する


今日のデジタル時代では、プレゼンテーションやドキュメントをオンラインで共有することが当たり前になっています。しかし、プレゼンテーションをHTMLに変換する際、フォントが正しく表示されるかどうかという問題がよく発生します。このステップバイステップのチュートリアルでは、Aspose.Slides for .NETを使用してプレゼンテーションを埋め込みフォント付きのHTMLに変換する手順を解説し、ドキュメントが意図したとおりに表示されるようにします。

## Aspose.Slides for .NET の紹介

チュートリアルに進む前に、Aspose.Slides for .NETについて簡単に紹介しましょう。これは、開発者が.NETアプリケーションでPowerPointプレゼンテーションを操作できるようにする強力なライブラリです。Aspose.Slidesを使用すると、プログラムからPowerPointファイルを作成、変更、変換できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Aspose.Slides for .NET: プロジェクトにAspose.Slidesライブラリがインストールされている必要があります。ダウンロードはこちらから。 [ここ](https://releases。aspose.com/slides/net/).

## ステップ1: プロジェクトの設定

1. 希望する .NET 開発環境で新しいプロジェクトを作成するか、既存のプロジェクトを開きます。

2. プロジェクトに Aspose.Slides ライブラリへの参照を追加します。

3. コードに必要な名前空間をインポートします。

   ```csharp
   using Aspose.Slides;
   ```

## ステップ2: プレゼンテーションを読み込む

まず、HTMLに変換するプレゼンテーションを読み込む必要があります。 `"Your Document Directory"` プレゼンテーション ファイルが配置されている実際のディレクトリに置き換えます。

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // ここにコードを入力してください
}
```

## ステップ3: デフォルトのプレゼンテーションフォントを除外する

このステップでは、埋め込みから除外したいデフォルトのプレゼンテーションフォントを指定できます。これにより、生成されるHTMLファイルのサイズを最適化できます。

```csharp
string[] fontNameExcludeList = { };
```

## ステップ4: HTMLコントローラーを選択する

HTML にフォントを埋め込むには、次の 2 つのオプションがあります。

### オプション1: すべてのフォントを埋め込む

プレゼンテーションで使用されているすべてのフォントを埋め込むには、 `EmbedAllFontsHtmlController`。

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### オプション2: すべてのフォントをリンクする

プレゼンテーションで使用されているすべてのフォントにリンクするには、 `LinkAllFontsHtmlController`システム上でフォントが配置されているディレクトリを指定する必要があります。

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## ステップ5: HTMLオプションを定義する

作成する `HtmlOptions` オブジェクトを作成し、HTML フォーマッタを前の手順で選択したものに設定します。

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // すべてのフォントを埋め込むにはembedFontsControllerを使用します
};
```

## ステップ6: HTMLとして保存

最後に、プレゼンテーションをHTMLファイルとして保存します。 `SaveFまたはmat.Html` or `SaveFormat.Html5` ご要望に応じて。

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## 結論

おめでとうございます！Aspose.Slides for .NET を使用して、プレゼンテーションを埋め込みフォント付きのHTMLに変換できました。これにより、プレゼンテーションをオンラインで共有する際にフォントが正しく表示されるようになります。

これで、美しくフォーマットされたプレゼンテーションを、視聴者があなたの意図したとおりに見られることを確信して、自信を持って簡単に共有できるようになります。

詳しい情報と詳細なAPIリファレンスについては、 [Aspose.Slides for .NET ドキュメント](https://reference。aspose.com/slides/net/).

## よくある質問

### 1. Aspose.Slides for .NET をバッチ モードで使用して、PowerPoint プレゼンテーションを HTML に変換できますか?

はい、Aspose.Slides for .NET を使用してプレゼンテーション ファイルをループし、各ファイルに変換プロセスを適用することで、複数のプレゼンテーションを一括して HTML に変換できます。

### 2. HTML 出力の外観をカスタマイズする方法はありますか?

もちろんです! Aspose.Slides for .NET には、色、フォント、レイアウトの調整など、HTML 出力の外観と書式をカスタマイズするためのさまざまなオプションが用意されています。

### 3. Aspose.Slides for .NET を使用して HTML にフォントを埋め込む場合、制限はありますか?

Aspose.Slides for .NET は優れたフォント埋め込み機能を備えていますが、フォントを埋め込むと HTML ファイルのサイズが大きくなる可能性があることにご注意ください。Web での使用に適したフォントを選択してください。

### 4. Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを他の形式に変換できますか?

はい、Aspose.Slides for .NET は PDF、画像など、幅広い出力形式をサポートしています。プレゼンテーションをお好みの形式に簡単に変換できます。

### 5. Aspose.Slides for .NET に関する追加のリソースとサポートはどこで入手できますか?

ドキュメントを含む豊富なリソースにアクセスできます。 [Aspose.Slides for .NET API リファレンス](https://reference。aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}