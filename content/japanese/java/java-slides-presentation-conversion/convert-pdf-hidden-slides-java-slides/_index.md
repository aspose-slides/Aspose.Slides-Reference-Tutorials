---
title: Java スライドで非表示スライドを PDF に変換する
linktitle: Java スライドで非表示スライドを PDF に変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションを非表示のスライドを含む PDF に変換する方法を学びます。ソース コードを含むステップ バイ ステップ ガイドに従って、シームレスな PDF 生成を実現してください。
type: docs
weight: 27
url: /ja/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

## Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを非表示スライド付きの PDF に変換する方法の紹介

このステップバイステップ ガイドでは、Aspose.Slides for Java を使用して、非表示のスライドを保持しながら PowerPoint プレゼンテーションを PDF に変換する方法を説明します。非表示のスライドとは、通常のプレゼンテーションでは表示されないものの、PDF 出力に含めることができるスライドのことです。このタスクを実行するためのソース コードと詳細な手順を提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Slides for Java ライブラリ: Java プロジェクトに Aspose.Slides for Java ライブラリが設定されていることを確認してください。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).

2. Java 開発環境: システムに Java 開発環境がインストールされている必要があります。

## ステップ 1: Aspose.Slides for Java をインポートする

まず、Aspose.Slides ライブラリを Java プロジェクトにインポートする必要があります。プロジェクトのビルド パスにライブラリを追加したことを確認してください。

```java
import com.aspose.slides.*;
```

## ステップ2: PowerPointプレゼンテーションを読み込む

まず、PDFに変換したいPowerPointプレゼンテーションを読み込みます。`"Your Document Directory"`そして`"HiddingSlides.pptx"`適切なファイル パスを使用します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## ステップ3: PDFオプションを設定する

PDF出力に非表示のスライドを含めるには、PDFオプションを設定します。`setShowHiddenSlides`の財産`PdfOptions`クラスに`true`.

```java
//PdfOptionsクラスをインスタンス化する
PdfOptions pdfOptions = new PdfOptions();
//生成されたドキュメントに非表示のスライドを含めるように指定します
pdfOptions.setShowHiddenSlides(true);
```

## ステップ4: プレゼンテーションをPDFとして保存する

次に、指定したオプションでプレゼンテーションをPDFファイルに保存します。`"PDFWithHiddenSlides_out.pdf"`希望する出力ファイル名を入力します。

```java
//指定したオプションでプレゼンテーションをPDFに保存する
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## ステップ5: リソースのクリーンアップ

プレゼンテーションが終了したら、プレゼンテーションで使用したリソースを必ず解放してください。

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Java スライドで隠しスライドを PDF に変換するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	//PdfOptionsクラスをインスタンス化する
	PdfOptions pdfOptions = new PdfOptions();
	//生成されたドキュメントに非表示のスライドを含めるように指定します
	pdfOptions.setShowHiddenSlides(true);
	//指定したオプションでプレゼンテーションをPDFに保存する
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

この包括的なガイドでは、Aspose.Slides for Java を使用して、非表示のスライドを保持しながら PowerPoint プレゼンテーションを PDF に変換する方法を学習しました。このタスクをシームレスに実行するために必要なソース コードとともに、ステップ バイ ステップのチュートリアルを提供しました。

## よくある質問

### PowerPoint プレゼンテーションでスライドを非表示にするにはどうすればよいでしょうか?

PowerPoint プレゼンテーションでスライドを非表示にするには、次の手順に従います。
1. スライド ソーター ビューで非表示にするスライドを選択します。
2. 選択したスライドを右クリックします。
3. コンテキスト メニューから [スライドを非表示] を選択します。

### Aspose.Slides for Java でプログラムによって非表示のスライドを表示できますか?

はい、Aspose.Slides for Javaでは、プログラムで非表示のスライドを表示することができます。`Hidden`の財産`Slide`クラスに`false`以下に例を示します。

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // slideIndexを非表示スライドのインデックスに置き換えます
slide.setHidden(false);
```

### Aspose.Slides for Java をダウンロードするにはどうすればいいですか?

Aspose.Slides for JavaはAsposeのWebサイトからダウンロードできます。[Aspose.Slides for Java のダウンロード ページ](https://releases.aspose.com/slides/java/)最新バージョンを入手してください。