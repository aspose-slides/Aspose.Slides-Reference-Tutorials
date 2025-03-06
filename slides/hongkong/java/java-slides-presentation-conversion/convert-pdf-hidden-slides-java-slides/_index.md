---
title: 使用 Java 幻燈片中的隱藏幻燈片轉換為 PDF
linktitle: 使用 Java 幻燈片中的隱藏幻燈片轉換為 PDF
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為具有隱藏投影片的 PDF。請按照我們的逐步指南和原始程式碼進行無縫 PDF 生成。
weight: 27
url: /zh-hant/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## 使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為帶有隱藏投影片的 PDF 的簡介

在本逐步指南中，您將了解如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 PDF，同時保留隱藏的投影片。隱藏幻燈片是指在常規簡報過程中不會顯示但可以包含在 PDF 輸出中的幻燈片。我們將為您提供原始程式碼和完成此任務的詳細說明。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1.  Aspose.Slides for Java Library：確保您在 Java 專案中設定了 Aspose.Slides for Java 函式庫。您可以從[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/).

2. Java 開發環境：您的系統上應該安裝有 Java 開發環境。

## 第 1 步：匯入 Java 版 Aspose.Slides

首先，您需要將 Aspose.Slides 庫匯入到您的 Java 專案中。確保您已將庫新增至專案的建置路徑。

```java
import com.aspose.slides.*;
```

## 第 2 步：載入 PowerPoint 簡報

首先，您將載入要轉換為 PDF 的 PowerPoint 簡報。代替`"Your Document Directory"`和`"HiddingSlides.pptx"`與適當的文件路徑。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## 步驟 3：配置 PDF 選項

配置 PDF 選項以在 PDF 輸出中包含隱藏的幻燈片。您可以透過設定來做到這一點`setShowHiddenSlides`的財產`PdfOptions`上課到`true`.

```java
//實例化 PdfOptions 類
PdfOptions pdfOptions = new PdfOptions();
//指定產生的文件應包含隱藏的投影片
pdfOptions.setShowHiddenSlides(true);
```

## 步驟 4：將演示文稿另存為 PDF

現在，使用指定的選項將簡報儲存到 PDF 檔案。代替`"PDFWithHiddenSlides_out.pdf"`與您想要的輸出檔名。

```java
//使用指定選項將簡報儲存為 PDF
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 第 5 步：清理資源

確保在完成簡報後釋放簡報使用的資源。

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## 使用 Java 投影片中的隱藏投影片轉換為 PDF 的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	//實例化 PdfOptions 類
	PdfOptions pdfOptions = new PdfOptions();
	//指定產生的文件應包含隱藏的投影片
	pdfOptions.setShowHiddenSlides(true);
	//使用指定選項將簡報儲存為 PDF
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本綜合指南中，您了解如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 PDF，同時保留隱藏的投影片。我們為您提供了逐步教學以及無縫完成此任務所需的原始程式碼。

## 常見問題解答

### 如何隱藏 PowerPoint 簡報中的投影片？

若要隱藏 PowerPoint 簡報中的投影片，請依照下列步驟操作：
1. 在「投影片排序器」檢視中選擇要隱藏的投影片。
2. 右鍵點選選定的幻燈片。
3. 從上下文選單中選擇“隱藏幻燈片”。

### 我可以透過程式方式取消隱藏 Aspose.Slides for Java 中的隱藏投影片嗎？

是的，您可以透過設定在 Aspose.Slides for Java 中以程式方式取消隱藏隱藏的幻燈片`Hidden`的財產`Slide`上課到`false`。這是一個例子：

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); //將slideIndex 替換為隱藏投影片的索引
slide.setHidden(false);
```

### 如何下載 Java 版 Aspose.Slides？

您可以從 Aspose 網站下載 Aspose.Slides for Java。參觀[Aspose.Slides for Java 下載頁面](https://releases.aspose.com/slides/java/)取得最新版本。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
