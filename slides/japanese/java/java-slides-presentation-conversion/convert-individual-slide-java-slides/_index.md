---
title: Java スライドで個々のスライドを変換する
linktitle: Java スライドで個々のスライドを変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、コード例とともに、個々の PowerPoint スライドを HTML に変換する方法を段階的に学習します。
weight: 12
url: /ja/java/presentation-conversion/convert-individual-slide-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java スライドで個々のスライドを変換する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションの個々のスライドを HTML に変換するプロセスについて説明します。このステップ バイ ステップ ガイドでは、このタスクを実行するのに役立つソース コードと説明を提供します。

## 前提条件

始める前に、以下のものを用意してください。

- Aspose.Slides for Java ライブラリがインストールされました。
- PowerPointプレゼンテーションファイル（`Individual-Slide.pptx`）を選択します。
- Java開発環境をセットアップしました。

## ステップ1: プロジェクトを設定する

1. 好みの開発環境で Java プロジェクトを作成します。
2. Aspose.Slides for Java ライブラリをプロジェクトに追加します。

## ステップ2: 必要なクラスをインポートする

Java クラスで、必要なクラスをインポートし、初期構成を設定します。

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## ステップ3: 主な変換方法を定義する

個々のスライドの変換を実行するメソッドを作成します。必ず置き換えてください。`"Your Document Directory"`ドキュメント ディレクトリへの実際のパスを入力します。

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        //ファイルを保存しています
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## ステップ4: CustomFormattingControllerを実装する

作成する`CustomFormattingController`変換中にカスタム書式を処理するクラス。

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## ステップ5: 変換を実行する

最後に、`convertIndividualSlides`変換プロセスを実行する方法。

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Java スライドで個々のスライドを変換するための完全なソース コード

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		//ファイルを保存しています
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## 結論

Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションの個々のスライドを HTML に正常に変換できました。このチュートリアルでは、このタスクを実行するために必要なコードと手順を説明しました。特定の要件に応じて、出力と書式を自由にカスタマイズしてください。

## よくある質問

### HTML 出力をさらにカスタマイズするにはどうすればよいですか?

 HTML出力をカスタマイズするには、`CustomFormattingController`クラス。調整する`writeSlideStart`そして`writeSlideEnd`スライドの HTML 構造とスタイルを変更する方法。

### 複数の PowerPoint プレゼンテーションを一度に変換できますか?

はい、複数のプレゼンテーションファイルをループして、呼び出して個別に変換するようにコードを変更することができます。`convertIndividualSlides`各プレゼンテーションの方法。

### スライド内の図形やテキストの追加の書式設定をどのように処理すればよいですか?

延長することができます`CustomFormattingController`図形固有の書式設定を処理するクラスを実装することで、`writeShapeStart`そして`writeShapeEnd`メソッドを作成し、その中でカスタム書式設定ロジックを適用します。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
