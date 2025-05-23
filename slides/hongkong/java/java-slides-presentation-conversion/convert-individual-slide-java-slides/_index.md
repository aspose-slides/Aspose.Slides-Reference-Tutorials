---
"description": "了解如何使用 Aspose.Slides for Java 的程式碼範例逐步將單一 PowerPoint 投影片轉換為 HTML。"
"linktitle": "在 Java 幻燈片中轉換單一幻燈片"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 幻燈片中轉換單一幻燈片"
"url": "/zh-hant/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 幻燈片中轉換單一幻燈片


## Java Slides 中單一幻燈片轉換簡介

在本教學中，我們將介紹使用 Aspose.Slides for Java 將 PowerPoint 簡報中的單一投影片轉換為 HTML 的過程。本逐步指南將為您提供原始程式碼和解釋，以幫助您完成此任務。

## 先決條件

在開始之前，請確保您具備以下條件：

- 已安裝 Java 函式庫的 Aspose.Slides。
- PowerPoint 簡報文件 (`Individual-Slide.pptx`) 您想要轉換的。
- Java開發環境搭建。

## 步驟 1：設定項目

1. 在您首選的開發環境中建立一個 Java 專案。
2. 將 Aspose.Slides for Java 函式庫新增至您的專案。

## 第 2 步：導入必要的類

在您的 Java 類別中，匯入所需的類別並設定初始配置。

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

## 步驟3：定義主要轉換方法

建立一種方法來執行單一幻燈片的轉換。確保更換 `"Your Document Directory"` 使用您的文件目錄的實際路徑。

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // 儲存檔案
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## 步驟 4：實作 CustomFormattingController

創建 `CustomFormattingController` 類別來處理轉換過程中的自訂格式。

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

## 步驟5：執行轉換

最後，調用 `convertIndividualSlides` 方法來執行轉換過程。

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Java 投影片中轉換單一投影片的完整原始碼

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// 儲存檔案              
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

您已成功使用 Aspose.Slides for Java 將 PowerPoint 簡報中的單一投影片轉換為 HTML。本教學為您提供了完成此任務所需的程式碼和步驟。請根據您的具體要求隨意自訂輸出和格式。

## 常見問題解答

### 我該如何進一步自訂 HTML 輸出？

您可以透過修改 `CustomFormattingController` 班級。調整 `writeSlideStart` 和 `writeSlideEnd` 改變投影片 HTML 結構和樣式的方法。

### 我可以一次轉換多個 PowerPoint 簡報嗎？

是的，您可以修改程式碼以循環遍歷多個簡報文件，並透過調用 `convertIndividualSlides` 每次演示的方法。

### 如何處理投影片中形狀和文字的附加格式？

您可以擴展 `CustomFormattingController` 透過實現來處理形狀特定的格式 `writeShapeStart` 和 `writeShapeEnd` 方法並在其中應用自訂格式邏輯。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}