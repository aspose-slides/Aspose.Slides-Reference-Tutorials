---
title: Java スライドの非表示スライドを含む PDF に変換する
linktitle: Java スライドの非表示スライドを含む PDF に変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションを非表示のスライドを含む PDF に変換する方法を学びます。シームレスな PDF 生成のためのソース コードを含むステップバイステップ ガイドに従ってください。
type: docs
weight: 27
url: /ja/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

## Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを非表示のスライドを含む PDF に変換する方法の概要

このステップバイステップのガイドでは、Aspose.Slides for Java を使用して、非表示のスライドを保持しながら PowerPoint プレゼンテーションを PDF に変換する方法を学習します。非表示のスライドは、通常のプレゼンテーション中には表示されませんが、PDF 出力には含めることができるスライドです。このタスクを達成するためのソース コードと詳細な手順を提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Slides for Java ライブラリ: Java プロジェクトに Aspose.Slides for Java ライブラリが設定されていることを確認します。からダウンロードできます。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).

2. Java 開発環境: システムに Java 開発環境がインストールされている必要があります。

## ステップ 1: Aspose.Slides for Java をインポートする

まず、Aspose.Slides ライブラリを Java プロジェクトにインポートする必要があります。ライブラリがプロジェクトのビルド パスに追加されていることを確認してください。

```java
import com.aspose.slides.*;
```

## ステップ 2: PowerPoint プレゼンテーションをロードする

まず、PDF に変換する PowerPoint プレゼンテーションをロードします。交換する`"Your Document Directory"`そして`"HiddingSlides.pptx"`適切なファイルパスを使用してください。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## ステップ 3: PDF オプションを構成する

 PDF 出力に非表示のスライドを含めるように PDF オプションを構成します。これを行うには、`setShowHiddenSlides`の財産`PdfOptions`クラスへ`true`.

```java
//PdfOptions クラスをインスタンス化する
PdfOptions pdfOptions = new PdfOptions();
//生成されたドキュメントに非表示のスライドを含めるよう指定します
pdfOptions.setShowHiddenSlides(true);
```

## ステップ 4: プレゼンテーションを PDF として保存する

ここで、指定したオプションを使用してプレゼンテーションを PDF ファイルに保存します。交換する`"PDFWithHiddenSlides_out.pdf"`希望の出力ファイル名を付けます。

```java
//指定したオプションを使用してプレゼンテーションを PDF に保存します
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## ステップ 5: リソースをクリーンアップする

プレゼンテーションが終了したら、プレゼンテーションで使用したリソースを必ず解放してください。

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Java スライドの非表示スライドを含む PDF に変換するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	//PdfOptions クラスをインスタンス化する
	PdfOptions pdfOptions = new PdfOptions();
	//生成されたドキュメントに非表示のスライドを含めるよう指定します
	pdfOptions.setShowHiddenSlides(true);
	//指定したオプションを使用してプレゼンテーションを PDF に保存します
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

この包括的なガイドでは、Aspose.Slides for Java を使用して非表示のスライドを保持しながら PowerPoint プレゼンテーションを PDF に変換する方法を学習しました。このタスクをシームレスに実行するために必要なソース コードとともに、ステップバイステップのチュートリアルを提供しました。

## よくある質問

### PowerPoint プレゼンテーションでスライドを非表示にするにはどうすればよいですか?

PowerPoint プレゼンテーションでスライドを非表示にするには、次の手順に従います。
1. スライド並べ替えビューで非表示にするスライドを選択します。
2. 選択したスライドを右クリックします。
3. コンテキストメニューから「スライドを非表示」を選択します。

### Aspose.Slides for Java で非表示のスライドをプログラムで再表示できますか?

はい、Aspose.Slides for Java で非表示のスライドをプログラムで再表示するには、`Hidden`の財産`Slide`クラスへ`false`。以下に例を示します。

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // slideIndex を非表示のスライドのインデックスに置き換えます
slide.setHidden(false);
```

### Java 用 Aspose.Slides をダウンロードするにはどうすればよいですか?

Aspose.Slides for Java は、Aspose Web サイトからダウンロードできます。訪問[Aspose.Slides for Java のダウンロード ページ](https://releases.aspose.com/slides/java/)最新バージョンを入手するには。