---
"description": "了解如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為具有隱藏投影片的 PDF。請按照我們的逐步指南和原始程式碼進行無縫 PDF 生成。"
"linktitle": "使用 Java Slides 中的隱藏幻燈片轉換為 PDF"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "使用 Java Slides 中的隱藏幻燈片轉換為 PDF"
"url": "/zh-hant/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java Slides 中的隱藏幻燈片轉換為 PDF


## 使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為帶有隱藏投影片的 PDF 的簡介

在本逐步指南中，您將學習如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 PDF，同時保留隱藏的投影片。隱藏幻燈片是在常規簡報過程中不會顯示但可以包含在 PDF 輸出中的幻燈片。我們將為您提供完成此任務的原始程式碼和詳細說明。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

1. Aspose.Slides for Java 函式庫：確保您已在 Java 專案中設定了 Aspose.Slides for Java 函式庫。您可以從 [Aspose.Slides for Java 文檔](https://reference。aspose.com/slides/java/).

2. Java 開發環境：您的系統上應該安裝 Java 開發環境。

## 步驟1：導入 Aspose.Slides for Java

首先，您需要將 Aspose.Slides 庫匯入到您的 Java 專案中。確保已將庫新增至專案的建置路徑。

```java
import com.aspose.slides.*;
```

## 第 2 步：載入 PowerPoint 簡報

首先載入要轉換為 PDF 的 PowerPoint 簡報。代替 `"Your Document Directory"` 和 `"HiddingSlides.pptx"` 使用適當的文件路徑。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## 步驟 3：配置 PDF 選項

配置 PDF 選項以在 PDF 輸出中包含隱藏幻燈片。您可以透過設定 `setShowHiddenSlides` 的財產 `PdfOptions` 班級 `true`。

```java
// 實例化 PdfOptions 類
PdfOptions pdfOptions = new PdfOptions();
// 指定產生的文件應包含隱藏投影片
pdfOptions.setShowHiddenSlides(true);
```

## 步驟 4：將演示文稿儲存為 PDF

現在，使用指定的選項將簡報儲存為 PDF 檔案。代替 `"PDFWithHiddenSlides_out.pdf"` 使用您想要的輸出檔名。

```java
// 使用指定選項將簡報儲存為 PDF
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 步驟5：清理資源

演示完成後，請確保釋放其所使用的資源。

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Java Slides 中將隱藏幻燈片轉換為 PDF 的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// 實例化 PdfOptions 類
	PdfOptions pdfOptions = new PdfOptions();
	// 指定產生的文件應包含隱藏投影片
	pdfOptions.setShowHiddenSlides(true);
	// 使用指定選項將簡報儲存為 PDF
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本綜合指南中，您將學習如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 PDF，同時保留隱藏的投影片。我們為您提供了逐步教學以及無縫完成此任務所需的原始程式碼。

## 常見問題解答

### 如何隱藏 PowerPoint 簡報中的投影片？

若要隱藏 PowerPoint 簡報中的投影片，請依照下列步驟操作：
1. 在投影片檢視檢視中選擇要隱藏的投影片。
2. 右鍵點選選定的幻燈片。
3. 從上下文選單中選擇“隱藏幻燈片”。

### 我可以透過程式方式取消隱藏 Aspose.Slides for Java 中的投影片嗎？

是的，您可以透過設定 `Hidden` 的財產 `Slide` 班級 `false`。以下是一個例子：

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // 將 slideIndex 替換為隱藏投影片的索引
slide.setHidden(false);
```

### 如何下載適用於 Java 的 Aspose.Slides？

您可以從 Aspose 網站下載適用於 Java 的 Aspose.Slides。訪問 [Aspose.Slides for Java下載頁面](https://releases.aspose.com/slides/java/) 取得最新版本。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}