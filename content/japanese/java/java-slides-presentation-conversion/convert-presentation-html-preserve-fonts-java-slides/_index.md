---
title: Java スライドで元のフォントを保持したままプレゼンテーションを HTML に変換する
linktitle: Java スライドで元のフォントを保持したままプレゼンテーションを HTML に変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、元のフォントを保持しながら PowerPoint プレゼンテーションを HTML に変換します。
type: docs
weight: 14
url: /ja/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Java スライドで元のフォントを保持したままプレゼンテーションを HTML に変換する方法の概要

このチュートリアルでは、Aspose.Slides for Java を使用して、元のフォントを保持しながら PowerPoint プレゼンテーション (PPTX) を HTML に変換する方法を検討します。これにより、結果の HTML が元のプレゼンテーションの外観によく似たものになります。

## ステップ 1: プロジェクトのセットアップ
コードに入る前に、必要な設定が整っていることを確認してください。

1. Aspose.Slides for Java をダウンロードする: まだダウンロードしていない場合は、Aspose.Slides for Java ライブラリをダウンロードしてプロジェクトに含めます。

2. Java プロジェクトを作成する: お気に入りの IDE で Java プロジェクトをセットアップし、Aspose.Slides JAR ファイルを配置できる「lib」フォルダーがあることを確認します。

3. 必要なクラスをインポートする: Java ファイルの先頭に必要なクラスをインポートします。

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ステップ 2: オリジナルのフォントを使用してプレゼンテーションを HTML に変換する

ここで、元のフォントを保持したまま PowerPoint プレゼンテーションを HTML に変換してみましょう。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーションをロードする
Presentation pres = new Presentation("input.pptx");

try {
    //Calibri や Arial などのデフォルトのプレゼンテーション フォントを除外する
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    //HTML オプションを作成し、カスタム HTML フォーマッタを設定する
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    //プレゼンテーションを HTML として保存する
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    //プレゼンテーションオブジェクトを破棄する
    if (pres != null) pres.dispose();
}
```

このコード スニペットでは次のようになります。

- 次を使用して、入力 PowerPoint プレゼンテーションを読み込みます。`Presentation`.

- フォントのリストを定義します (`fontNameExcludeList`) を HTML への埋め込みから除外したいと考えています。これは、Calibri や Arial などの一般的なフォントを除外してファイル サイズを削減する場合に便利です。

- のインスタンスを作成します`EmbedAllFontsHtmlController`そしてフォント除外リストをそれに渡します。

- 私たちが作成します`HtmlOptions`を使用してカスタム HTML フォーマッタを設定します`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- 最後に、指定したオプションを使用してプレゼンテーションを HTML として保存します。

## Java スライドの元のフォントを保持したままプレゼンテーションを HTML に変換するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
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

このチュートリアルでは、Aspose.Slides for Java を使用して、元のフォントを保持しながら PowerPoint プレゼンテーションを HTML に変換する方法を学習しました。これは、プレゼンテーションを Web 上で共有するときにプレゼンテーションの視覚的な忠実性を維持したい場合に便利です。

## よくある質問

### Java 用 Aspose.Slides をダウンロードするにはどうすればよいですか?

Aspose.Slides for Java は、Aspose Web サイトからダウンロードできます。訪問[ここ](https://downloads.aspose.com/slides/java/)最新バージョンを入手するには。

### 除外されるフォントのリストをカスタマイズできますか?

はい、カスタマイズできます`fontNameExcludeList`要件に応じて特定のフォントを含めたり除外したりする配列。

### この方法は PPT などの古い PowerPoint 形式でも機能しますか?

このコード例は PPTX ファイル用に設計されています。古い PPT ファイルを変換する必要がある場合は、コードの調整が必要になる場合があります。

### HTML 出力をさらにカスタマイズするにはどうすればよいですか?

探索することができます`HtmlOptions`クラスを使用して、スライド サイズ、画質など、HTML 出力のさまざまな側面をカスタマイズします。