---
title: Java スライドで元のフォントを保持しながらプレゼンテーションを HTML に変換する
linktitle: Java スライドで元のフォントを保持しながらプレゼンテーションを HTML に変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、元のフォントを保持しながら PowerPoint プレゼンテーションを HTML に変換します。
type: docs
weight: 14
url: /ja/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Java スライドで元のフォントを保持しながらプレゼンテーションを HTML に変換する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、元のフォントを保持しながら PowerPoint プレゼンテーション (PPTX) を HTML に変換する方法について説明します。これにより、結果の HTML が元のプレゼンテーションの外観に非常に近くなります。

## ステップ1: プロジェクトの設定
コードに進む前に、必要な設定が整っていることを確認しましょう。

1. Aspose.Slides for Java をダウンロードします。まだダウンロードしていない場合は、Aspose.Slides for Java ライブラリをダウンロードしてプロジェクトに含めます。

2. Java プロジェクトを作成する: お気に入りの IDE で Java プロジェクトを設定し、Aspose.Slides JAR ファイルを配置できる "lib" フォルダーがあることを確認します。

3. 必要なクラスをインポート: Java ファイルの先頭に必要なクラスをインポートします。

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ステップ 2: プレゼンテーションをオリジナルフォントで HTML に変換する

次に、元のフォントを保持しながら PowerPoint プレゼンテーションを HTML に変換してみましょう。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーションを読み込む
Presentation pres = new Presentation("input.pptx");

try {
    //CalibriやArialなどのデフォルトのプレゼンテーションフォントを除外する
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    //HTMLオプションを作成し、カスタムHTMLフォーマッタを設定する
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    //プレゼンテーションをHTMLとして保存する
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    //プレゼンテーションオブジェクトを破棄する
    if (pres != null) pres.dispose();
}
```

このコードスニペットでは:

- 入力されたPowerPointプレゼンテーションを読み込むには、`Presentation`.

- フォントのリストを定義します（`fontNameExcludeList`) を HTML への埋め込みから除外します。これは、Calibri や Arial などの一般的なフォントを除外してファイル サイズを縮小する場合に便利です。

- インスタンスを作成します`EmbedAllFontsHtmlController`フォント除外リストを渡します。

- 私たちは創造する`HtmlOptions`そして、カスタムHTMLフォーマッタを設定するには、`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- 最後に、指定したオプションを使用してプレゼンテーションを HTML として保存します。

## Java スライドの元のフォントを保持しながらプレゼンテーションを HTML に変換するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	//デフォルトのプレゼンテーションフォントを除外する
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、元のフォントを保持しながら PowerPoint プレゼンテーションを HTML に変換する方法を学習しました。これは、Web 上でプレゼンテーションを共有するときに、プレゼンテーションの視覚的な忠実度を維持したい場合に便利です。

## よくある質問

### Aspose.Slides for Java をダウンロードするにはどうすればいいですか?

Aspose.Slides for JavaはAsposeのWebサイトからダウンロードできます。[ここ](https://downloads.aspose.com/slides/java/)最新バージョンを入手してください。

### 除外フォントのリストをカスタマイズできますか?

はい、カスタマイズできます`fontNameExcludeList`要件に応じて特定のフォントを含めたり除外したりする配列。

### この方法は、PPT などの古い PowerPoint 形式にも適用できますか?

このコード例は PPTX ファイル用に設計されています。古い PPT ファイルを変換する必要がある場合は、コードを調整する必要があるかもしれません。

### HTML 出力をさらにカスタマイズするにはどうすればよいですか?

探索することができます`HtmlOptions`スライドのサイズ、画像の品質など、HTML 出力のさまざまな側面をカスタマイズするためのクラスです。