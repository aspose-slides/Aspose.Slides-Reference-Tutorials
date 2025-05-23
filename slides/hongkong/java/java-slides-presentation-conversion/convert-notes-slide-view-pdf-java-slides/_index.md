---
"description": "了解如何使用 Aspose.Slides for Java 將帶有註解的 PowerPoint 簡報轉換為 PDF。請按照我們的逐步指南和原始程式碼進行操作。"
"linktitle": "在 Java Slides 中將 Notes 幻燈片視圖轉換為 PDF"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中將 Notes 幻燈片視圖轉換為 PDF"
"url": "/zh-hant/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中將 Notes 幻燈片視圖轉換為 PDF


## Java Slides 中將筆記投影片檢視轉換為 PDF 的簡介

在本教程中，我們將指導您使用 Aspose.Slides for Java 庫將帶有註釋幻燈片視圖的 PowerPoint 簡報轉換為 PDF 的過程。該程式庫為使用 Java 處理 PowerPoint 簡報提供了強大的功能。

## 先決條件
1. 已安裝 Java 開發工具包 (JDK)。
2. Aspose.Slides for Java 函式庫已新增至您的專案中。

## 步驟 1：導入必要的類
首先，您需要從 Aspose.Slides 庫匯入必要的類別。以下是實現該功能的程式碼：

```java
import com.aspose.slides.*;
```

## 第 2 步：載入 PowerPoint 簡報
您應該已經準備好 PowerPoint 簡報文件。代替 `"Your Document Directory"` 使用簡報檔案所在目錄的路徑。以下是載入簡報的程式碼：

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## 步驟 3：配置 PDF 選項
現在，讓我們配置 PDF 匯出選項。具體來說，我們將註釋位置設為“BottomFull”，以便在 PDF 中的幻燈片下方包含註釋。程式碼如下：

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

您可以根據您的要求自訂其他 PDF 選項。

## 步驟 4：將演示文稿儲存為帶有註釋的 PDF
最後，讓我們將簡報（包括註釋）儲存為 PDF 檔案。您可以指定輸出檔案名稱（例如， `"Pdf_Notes_out.pdf"`）並選擇格式（`SaveFormat.Pdf`）。以下是實現該功能的程式碼：

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 步驟 5：清理資源
演示完成後，不要忘記釋放資源：

```java
if (presentation != null) presentation.dispose();
```

## Java 投影片中將筆記投影片檢視轉換為 PDF 的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 實例化代表演示檔案的 Presentation 對象
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// 將簡報儲存為 PDF 筆記
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教學中，我們探討如何使用 Aspose.Slides for Java 函式庫將帶有註解投影片檢視的 PowerPoint 簡報轉換為 PDF。我們按照帶有原始程式碼的逐步指南來實現這種轉換。以下是關鍵要點：

## 常見問題解答

### 如何更改 PDF 中的註釋位置？

您可以透過修改 `setNotesPosition` 方法參數。例如，您可以將其設定為 `NotesPositions.RightFull` 將註釋放置在投影片的右側。

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### 我可以進一步自訂 PDF 匯出嗎？

是的，您可以透過調整 `PdfOptions` 目的。例如，您可以根據需要設定品質、壓縮和其他參數。

### 如何取得適用於 Java 的 Aspose.Slides？

您可以從以下網站下載 Aspose.Slides for Java： [這裡](https://releases。aspose.com/slides/java/).

### 使用 Aspose.Slides 有任何許可要求嗎？

是的，Aspose.Slides 需要有效的許可證才能用於商業用途。您可以從 Aspose 網站取得許可證。

### 在哪裡可以找到更多文件和範例？

您可以在以下位置找到 Aspose.Slides for Java 的全面文件和範例 [這裡](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}