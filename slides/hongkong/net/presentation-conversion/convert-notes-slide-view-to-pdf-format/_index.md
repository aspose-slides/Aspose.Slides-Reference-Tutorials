---
title: 將筆記投影片檢視轉換為 PDF 格式
linktitle: 將筆記投影片檢視轉換為 PDF 格式
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 使用 Aspose.Slides for .NET 將 PowerPoint 中的講者筆記轉換為 PDF。輕鬆保留上下文並自訂佈局。
weight: 15
url: /zh-hant/net/presentation-conversion/convert-notes-slide-view-to-pdf-format/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


在這份綜合指南中，我們將引導您完成使用 Aspose.Slides for .NET 將 Notes Slide View 轉換為 PDF 格式的流程。您將找到詳細的說明和程式碼片段來輕鬆完成此任務。

## 一、簡介

在處理 PowerPoint 簡報時，將 Notes 投影片檢視轉換為 PDF 格式是一項常見要求。 Aspose.Slides for .NET 提供了一組強大的工具來有效地完成此任務。

## 2. 前提條件

在我們開始之前，請確保您具備以下先決條件：

- Visual Studio 或任何 C# 開發環境。
-  Aspose.Slides for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/slides/net/).

## 3. 設定您的環境

首先，在您的開發環境中建立一個新的 C# 專案。確保在專案中引用 Aspose.Slides for .NET 函式庫。

## 4. 載入簡報

在 C# 程式碼中，載入要轉換為 PDF 的 PowerPoint 簡報。代替`"Your Document Directory"`與簡報文件的實際路徑。

```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation(dataDir + "NotesFile.pptx"))
{
    //你的程式碼在這裡
}
```

## 5. 配置 PDF 選項

若要設定註解投影片檢視的 PDF 選項，請使用下列程式碼片段：

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 6. 將簡報儲存為 PDF

現在，使用以下程式碼將簡報另存為帶有註釋投影片檢視的 PDF 檔案：

```csharp
presentation.Save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 七、結論

恭喜！您已使用 Aspose.Slides for .NET 成功將 Notes Slide View 轉換為 PDF 格式。這個強大的程式庫簡化了此類複雜的任務，使其成為以程式設計方式處理 PowerPoint 簡報的絕佳選擇。

## 8. 常見問題解答

### Q1：我可以在商業專案中使用Aspose.Slides for .NET嗎？

是的，Aspose.Slides for .NET 可用於個人和商業用途。

### Q2：對於我遇到的任何問題或疑問，如何獲得支援？

您可以在以下位置找到支持[Aspose.Slides for .NET 網站](https://forum.aspose.com/slides/net/).

### Q3：我可以自訂 PDF 輸出的佈局嗎？

絕對地！ Aspose.Slides for .NET 提供了各種選項來自訂 PDF 輸出，包括佈局和格式。

### Q4：在哪裡可以找到更多 Aspose.Slides for .NET 教學和範例？

您可以探索其他教學和範例[Aspose.Slides for .NET API 文檔](https://reference.aspose.com/slides/net/).

現在您已成功將 Notes Slide View 轉換為 PDF 格式，您可以探索 Aspose.Slides for .NET 的更多特性和功能來增強您的 PowerPoint 自動化任務。快樂編碼！
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
