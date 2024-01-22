---
title: フォントが埋め込まれたプレゼンテーションを HTML に変換する
linktitle: フォントが埋め込まれたプレゼンテーションを HTML に変換する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、PowerPoint プレゼンテーションをフォントが埋め込まれた HTML に変換します。オリジナリティをシームレスに維持します。
type: docs
weight: 13
url: /ja/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

今日のデジタル時代では、プレゼンテーションやドキュメントをオンラインで共有することが一般的になっています。ただし、プレゼンテーションを HTML に変換するときにフォントが正しく表示されるかどうかが、よく発生する課題の 1 つです。このステップバイステップのチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーションをフォントが埋め込まれた HTML に変換し、ドキュメントが意図したとおりに表示されるようにするプロセスを説明します。

## Aspose.Slides for .NET の概要

チュートリアルに入る前に、Aspose.Slides for .NET について簡単に紹介しましょう。これは、開発者が .NET アプリケーションで PowerPoint プレゼンテーションを操作できるようにする強力なライブラリです。 Aspose.Slides を使用すると、PowerPoint ファイルをプログラムで作成、変更、変換できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Slides for .NET: Aspose.Slides ライブラリがプロジェクトにインストールされている必要があります。からダウンロードできます[ここ](https://releases.aspose.com/slides/net/).

## ステップ 1: プロジェクトをセットアップする

1. 新しいプロジェクトを作成するか、好みの .NET 開発環境で既存のプロジェクトを開きます。

2. プロジェクトに Aspose.Slides ライブラリへの参照を追加します。

3. 必要な名前空間をコードにインポートします。

   ```csharp
   using Aspose.Slides;
   ```

## ステップ 2: プレゼンテーションをロードする

まず、HTML に変換するプレゼンテーションをロードする必要があります。交換する`"Your Document Directory"`プレゼンテーション ファイルが配置されている実際のディレクトリに置き換えます。

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    //コードはここに入力します
}
```

## ステップ 3: デフォルトのプレゼンテーション フォントを除外する

このステップでは、埋め込みから除外するデフォルトのプレゼンテーション フォントを指定できます。これは、生成される HTML ファイルのサイズを最適化するのに役立ちます。

```csharp
string[] fontNameExcludeList = { };
```

## ステップ 4: HTML コントローラーを選択する

HTML にフォントを埋め込むには 2 つのオプションがあります。

### オプション 1: すべてのフォントを埋め込む

プレゼンテーションで使用されるすべてのフォントを埋め込むには、`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### オプション 2: すべてのフォントをリンクする

プレゼンテーションで使用されているすべてのフォントにリンクするには、`LinkAllFontsHtmlController`。システム上でフォントが配置されているディレクトリを指定する必要があります。

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## ステップ 5: HTML オプションを定義する

を作成します`HtmlOptions`オブジェクトを選択し、HTML フォーマッタを前の手順で選択したものに設定します。

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) //すべてのフォントを埋め込むには embedFontsController を使用します
};
```

## ステップ 6: HTML として保存する

最後に、プレゼンテーションを HTML ファイルとして保存します。どちらかを選択できます`SaveFormat.Html`または`SaveFormat.Html5`要件に応じて。

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## 結論

おめでとう！ Aspose.Slides for .NET を使用して、プレゼンテーションをフォントが埋め込まれた HTML に正常に変換しました。これにより、プレゼンテーションをオンラインで共有するときにフォントが正しく表示されます。

美しくフォーマットされたプレゼンテーションを自信を持って簡単に共有できるようになり、聴衆は意図したとおりにプレゼンテーションを閲覧できることがわかります。

詳細と詳細な API リファレンスについては、[Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/).

## よくある質問

### 1. Aspose.Slides for .NET をバッチ モードで使用して、PowerPoint プレゼンテーションを HTML に変換できますか?

はい、Aspose.Slides for .NET を使用してプレゼンテーション ファイルをループし、それぞれに変換プロセスを適用することで、複数のプレゼンテーションを HTML にバッチ変換できます。

### 2. HTML 出力の外観をカスタマイズする方法はありますか?

確かに！ Aspose.Slides for .NET には、色、フォント、レイアウトの調整など、HTML 出力の外観と書式設定をカスタマイズするためのさまざまなオプションが用意されています。

### 3. Aspose.Slides for .NET を使用して HTML にフォントを埋め込むことに制限はありますか?

Aspose.Slides for .NET は優れたフォント埋め込み機能を提供しますが、フォントを埋め込むと HTML ファイルのサイズが増加する可能性があることに注意してください。 Web での使用に合わせてフォントの選択を最適化してください。

### 4. Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを他の形式に変換できますか?

はい、Aspose.Slides for .NET は、PDF、画像などを含む幅広い出力形式をサポートしています。プレゼンテーションを選択した形式に簡単に変換できます。

### 5. Aspose.Slides for .NET の追加リソースとサポートはどこで入手できますか?

ドキュメントを含む豊富なリソースにアクセスできます。[Aspose.Slides for .NET API リファレンス](https://reference.aspose.com/slides/net/).
