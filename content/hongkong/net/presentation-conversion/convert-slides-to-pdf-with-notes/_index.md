---
title: 將幻燈片轉換為帶有註釋的 PDF
linktitle: 將幻燈片轉換為帶有註釋的 PDF
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 使用 Aspose.Slides for .NET 輕鬆將帶有演講者註解的簡報投影片轉換為 PDF。無縫保留內容和上下文。
type: docs
weight: 18
url: /zh-hant/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

# 使用 Aspose.Slides for .NET 將投影片轉換為帶有註解的 PDF 的逐步教學指南

您是否正在尋找一種可靠的方法將 PowerPoint 投影片轉換為 PDF 格式，同時保留所有重要註釋？別再猶豫了！在這個綜合教程中，我們將指導您逐步使用 Aspose.Slides for .NET 來完成此任務。

## 一、簡介

將 PowerPoint 投影片轉換為帶有註釋的 PDF 可以成為共享簡報的寶貴工具，同時確保保留重要的上下文和註釋。 Aspose.Slides for .NET 為這項任務提供了強大的解決方案。

## 2. 設定您的環境

在我們深入編碼過程之前，請確保您已設定必要的環境。你需要：

- Visual Studio 或您首選的 .NET 開發環境。
- 安裝了 Aspose.Slides for .NET 函式庫。
- 包含要轉換的註釋的 PowerPoint 簡報。

## 3. 載入簡報

在 C# 程式碼中，您需要載入要轉換的 PowerPoint 簡報。您可以這樣做：

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. 克隆投影片

為了確保您的 PDF 包含所有必要的投影片和註釋，您可以從原始簡報中複製它們。就是這樣：

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. 調整投影片大小

您可能需要調整投影片大小以適合您的 PDF。 Aspose.Slides for .NET 可以讓您輕鬆做到這一點：

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. 配置 PDF 選項

若要控制筆記在 PDF 中的顯示方式，您可以設定 PDF 選項：

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7.另存為附註解的PDF

最後，您可以將簡報儲存為帶有註釋的 PDF：

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 八、結論

恭喜！您已成功將 PowerPoint 投影片轉換為 PDF 格式，同時保留了所有重要註解。 Aspose.Slides for .NET 讓這個過程簡單而有效率。

## 9. 常見問題解答

### Q1：我可以自訂PDF中註解的佈局嗎？

是的，您可以使用以下命令自訂筆記的佈局`INotesCommentsLayoutingOptions`在 PDF 選項中。

### Q2：Aspose.Slides for .NET 是否支援 PDF 以外的其他輸出格式？

是的，Aspose.Slides for .NET 支援各種輸出格式，包括 PPTX、DOCX 等。

### Q3：Aspose.Slides for .NET 有試用版嗎？

是的，您可以在以下網址取得 Aspose.Slides for .NET 的免費試用版：[https://releases.aspose.com/](https://releases.aspose.com/).

### 問題 4：在哪裡可以獲得 Aspose.Slides for .NET 的支援？

您可以在以下位置找到支持和社區討論：[https://forum.aspose.com/](https://forum.aspose.com/).

### Q5：我可以購買 Aspose.Slides for .NET 的臨時授權嗎？

是的，您可以在以下位置購買臨時許可證：[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

總而言之，使用 Aspose.Slides for .NET，您可以輕鬆地將 PowerPoint 投影片轉換為 PDF 格式，並保留完整的註解。對於需要與同事和客戶分享簡報同時確保重要背景不會失去的專業人士來說，這是一個有價值的工具。