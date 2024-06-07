---
title: プレゼンテーションを埋め込みフォント付きの HTML に変換する
linktitle: プレゼンテーションを埋め込みフォント付きの HTML に変換する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、PowerPoint プレゼンテーションを埋め込みフォント付きの HTML に変換します。独創性をシームレスに維持します。
type: docs
weight: 13
url: /ja/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

今日のデジタル時代では、プレゼンテーションやドキュメントをオンラインで共有することが一般的になっています。しかし、プレゼンテーションを HTML に変換するときにフォントが正しく表示されるようにすることが、よく発生する課題の 1 つです。このステップ バイ ステップのチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーションを埋め込みフォント付きの HTML に変換し、ドキュメントが意図したとおりに表示されるようにする手順を説明します。

## Aspose.Slides for .NET の紹介

チュートリアルに進む前に、Aspose.Slides for .NET について簡単に紹介します。これは、開発者が .NET アプリケーションで PowerPoint プレゼンテーションを操作できるようにする強力なライブラリです。Aspose.Slides を使用すると、プログラムによって PowerPoint ファイルを作成、変更、変換できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Slides for .NET: プロジェクトにAspose.Slidesライブラリがインストールされている必要があります。ダウンロードはこちらから行えます。[ここ](https://releases.aspose.com/slides/net/).

## ステップ1: プロジェクトを設定する

1. 好みの .NET 開発環境で新しいプロジェクトを作成するか、既存のプロジェクトを開きます。

2. プロジェクトに Aspose.Slides ライブラリへの参照を追加します。

3. コードに必要な名前空間をインポートします。

   ```csharp
   using Aspose.Slides;
   ```

## ステップ2: プレゼンテーションを読み込む

まず、HTMLに変換するプレゼンテーションを読み込む必要があります。`"Your Document Directory"`プレゼンテーション ファイルが配置されている実際のディレクトリに置き換えます。

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    //ここにコードを入力してください
}
```

## ステップ3: デフォルトのプレゼンテーションフォントを除外する

この手順では、埋め込みから除外するデフォルトのプレゼンテーション フォントを指定できます。これにより、生成される HTML ファイルのサイズを最適化できます。

```csharp
string[] fontNameExcludeList = { };
```

## ステップ4: HTMLコントローラーを選択する

HTML にフォントを埋め込むには、次の 2 つのオプションがあります。

### オプション1: すべてのフォントを埋め込む

プレゼンテーションで使用されているすべてのフォントを埋め込むには、`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### オプション2: すべてのフォントをリンクする

プレゼンテーションで使用されているすべてのフォントにリンクするには、`LinkAllFontsHtmlController`システム上でフォントが配置されているディレクトリを指定する必要があります。

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## ステップ5: HTMLオプションを定義する

作成する`HtmlOptions`オブジェクトを作成し、HTML フォーマッタを前の手順で選択したものに設定します。

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) //すべてのフォントを埋め込むにはembedFontsControllerを使用します
};
```

## ステップ6: HTMLとして保存

最後に、プレゼンテーションをHTMLファイルとして保存します。`SaveFormat.Html`または`SaveFormat.Html5`ご要望に応じて。

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## 結論

おめでとうございます! Aspose.Slides for .NET を使用して、プレゼンテーションを埋め込みフォント付きの HTML に正常に変換しました。これにより、プレゼンテーションをオンラインで共有するときにフォントが正しく表示されるようになります。

これで、美しくフォーマットされたプレゼンテーションを、視聴者があなたの意図したとおりに見られることを確信して、自信を持って簡単に共有できるようになります。

詳しい情報と詳細なAPIリファレンスについては、[Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/).

## よくある質問

### 1. Aspose.Slides for .NET をバッチ モードで使用して PowerPoint プレゼンテーションを HTML に変換できますか?

はい、Aspose.Slides for .NET を使用してプレゼンテーション ファイルをループし、各ファイルに変換プロセスを適用することで、複数のプレゼンテーションを一括して HTML に変換できます。

### 2. HTML 出力の外観をカスタマイズする方法はありますか?

もちろんです! Aspose.Slides for .NET には、色、フォント、レイアウトの調整など、HTML 出力の外観と書式をカスタマイズするためのさまざまなオプションが用意されています。

### 3. Aspose.Slides for .NET を使用して HTML にフォントを埋め込む場合、制限はありますか?

Aspose.Slides for .NET は優れたフォント埋め込み機能を提供しますが、フォントを埋め込むと HTML ファイルのサイズが大きくなる可能性があることに注意してください。Web での使用に合わせてフォントの選択を最適化してください。

### 4. Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを他の形式に変換できますか?

はい、Aspose.Slides for .NET は、PDF、画像など、幅広い出力形式をサポートしています。プレゼンテーションを任意の形式に簡単に変換できます。

### 5. Aspose.Slides for .NET に関する追加のリソースとサポートはどこで入手できますか?

ドキュメントを含む豊富なリソースにアクセスできます。[Aspose.Slides for .NET API リファレンス](https://reference.aspose.com/slides/net/).
