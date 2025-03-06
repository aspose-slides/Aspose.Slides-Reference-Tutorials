---
title: 在 Java 投影片中將 Notes 投影片檢視轉換為 PDF
linktitle: 在 Java 投影片中將 Notes 投影片檢視轉換為 PDF
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 將註解的 PowerPoint 簡報轉換為 PDF。請按照我們的原始碼逐步指南進行操作。
weight: 16
url: /zh-hant/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 在 Java 投影片中將 Notes 投影片檢視轉換為 PDF 簡介

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 程式庫將帶有筆記投影片檢視的 PowerPoint 簡報轉換為 PDF 的過程。該程式庫提供了使用 Java 處理 PowerPoint 簡報的強大功能。

## 先決條件
1. 安裝了 Java 開發工具包 (JDK)。
2. Aspose.Slides for Java 函式庫已新增至您的專案中。

## 步驟1：導入必要的類
首先，您需要從 Aspose.Slides 庫匯入必要的類別。這是執行此操作的程式碼：

```java
import com.aspose.slides.*;
```

## 第 2 步：載入 PowerPoint 簡報
您應該準備好 PowerPoint 簡報文件。代替`"Your Document Directory"`以及簡報文件所在目錄的路徑。這是載入簡報的程式碼：

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## 步驟 3：配置 PDF 選項
現在，讓我們配置 PDF 匯出選項。具體來說，我們將註釋位置設為“BottomFull”，以將註釋包含在 PDF 投影片下方。這是代碼：

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

您可以根據您的要求自訂其他 PDF 選項。

## 步驟 4：將演示文稿另存為已註釋的 PDF
最後，讓我們將簡報儲存為 PDF 文件，包括註釋。您可以指定輸出檔案名稱（例如，`"Pdf_Notes_out.pdf"`）並選擇格式（`SaveFormat.Pdf`）。這是執行此操作的程式碼：

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 第 5 步：清理資源
完成演示後，不要忘記釋放資源：

```java
if (presentation != null) presentation.dispose();
```

## 在 Java 投影片中將 Notes Slide View 轉換為 PDF 的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//實例化表示簡報文件的簡報對象
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	//將簡報儲存為 PDF 筆記
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教學中，我們探索如何使用 Aspose.Slides for Java 程式庫將帶有筆記投影片檢視的 PowerPoint 簡報轉換為 PDF。我們按照原始程式碼的逐步指南來實現此轉換。以下是重點：

## 常見問題解答

### 如何更改 PDF 中的註釋位置？

您可以透過修改註釋來變更 PDF 中的註釋位置`setNotesPosition`方法參數。例如，您可以將其設定為`NotesPositions.RightFull`將註釋放置在投影片的右側。

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### 我可以進一步自訂 PDF 匯出嗎？

是的，您可以透過調整中的各種選項來自訂 PDF 匯出`PdfOptions`目的。例如，您可以根據需要設定品質、壓縮等參數。

### 如何取得 Aspose.Slides for Java？

您可以從以下網站下載 Aspose.Slides for Java：[這裡](https://releases.aspose.com/slides/java/).

### 使用 Aspose.Slides 是否有任何許可要求？

是的，Aspose.Slides 需要有效的商業用途授權。您可以從 Aspose 網站取得許可證。

### 在哪裡可以找到更多文件和範例？

您可以在以下位置找到 Aspose.Slides for Java 的綜合文件和範例：[這裡](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
