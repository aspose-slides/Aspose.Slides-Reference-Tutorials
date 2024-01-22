---
title: 使用 Java 投影片中的註解將投影片轉換為 PDF
linktitle: 使用 Java 投影片中的註解將投影片轉換為 PDF
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 將 PowerPoint 投影片轉換為帶有 Java 註解的 PDF。 Java 開發人員的逐步指南。增強您的簡報共享。
type: docs
weight: 19
url: /zh-hant/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Java 中使用註解將投影片轉換為 PDF 的簡介

在數位簡報領域，將投影片轉換為 PDF 並附帶註釋的能力是一項很有價值的功能。 Java 開發人員可以使用 Aspose.Slides for Java 程式庫來實現此目的，該程式庫提供了一組強大的工具，用於以程式設計方式處理 PowerPoint 簡報。在本逐步指南中，我們將探索如何使用 Java 和 Aspose.Slides for Java 將投影片轉換為帶有註解的 PDF。

## 先決條件

在我們深入研究程式碼之前，請確保您具備以下先決條件：

- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Slides。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).

現在我們已經有了大綱，讓我們逐步深入實施。
## 第 1 步：設定項目

首先，建立一個 Java 專案並將 Aspose.Slides for Java 函式庫新增至專案的依賴項。

## 第 2 步：載入簡報

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 步驟 3：建立新簡報

```java
Presentation auxPresentation = new Presentation();
```

## 第 4 步：複製投影片

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## 第 5 步：調整投影片大小

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 步驟 6：配置 PDF 選項

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## 第7步：另存為PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 在 Java 幻燈片中將幻燈片轉換為帶有註釋的 PDF 的完整原始程式碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//實例化表示簡報文件的簡報對象
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		//設定投影片類型和尺寸
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(),presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 將投影片轉換為具有 Java 註解的 PDF。我們介紹了設定項目、載入簡報、建立新簡報、複製投影片、調整投影片大小、配置 PDF 選項，最後將簡報另存為帶有註釋的 PDF。

## 常見問題解答

### 如何安裝 Aspose.Slides for Java？

若要安裝 Aspose.Slides for Java，請依照下列步驟操作：
1. 從以下位置下載庫[這裡](https://releases.aspose.com/slides/java/).
2. 將 JAR 檔案加入到 Java 專案的類別路徑中。

### 我可以自訂生成的 PDF 中的註釋位置嗎？

是的，您可以透過修改來自訂註解位置`NotesPositions`PDF 選項中的列舉。在本教程中，我們將其設定為`BottomFull`，但您也可以探索其他選項。

### 使用 Aspose.Slides for Java 有任何授權要求嗎？

是的，Aspose.Slides for Java 是一個商業庫，您可能需要獲得許可證才能在生產中使用它。請造訪 Aspose 網站以了解許可詳細資訊。

### 我可以一次轉換多張投影片嗎？

當然！您可以循環瀏覽簡報中的投影片並將它們複製到新簡報中，從而允許您一次將多張投影片轉換為帶有註釋的 PDF。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多文件？

您可以在以下網站上找到 Aspose.Slides for Java 的詳細文件：[Aspose.Slides Java API 參考](https://reference.aspose.com/slides/java/).