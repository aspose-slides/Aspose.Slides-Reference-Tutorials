---
title: 將媒體檔案從簡報匯出為 HTML
linktitle: 將媒體檔案從簡報匯出為 HTML
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 使用 Aspose.Slides for .NET 優化您的簡報分享！在此逐步指南中了解如何將簡報中的媒體檔案匯出為 HTML。
weight: 15
url: /zh-hant/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


在本教學中，我們將引導您完成使用 Aspose.Slides for .NET 將簡報中的媒體檔案匯出為 HTML 的過程。 Aspose.Slides 是一個功能強大的 API，可讓您以程式設計方式處理 PowerPoint 簡報。讀完本指南後，您將能夠輕鬆地將簡報轉換為 HTML 格式。那麼，就讓我們開始吧！

## 一、簡介

PowerPoint 簡報通常包含影片等多媒體元素，您可能需要將這些簡報匯出為 HTML 格式以實現 Web 相容性。 Aspose.Slides for .NET 提供了一種以程式設計方式完成此任務的便利方法。

## 2. 前提條件

在我們開始之前，請確保您具備以下先決條件：

-  Aspose.Slides for .NET：您應該安裝 Aspose.Slides for .NET 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/net/).

## 3. 載入簡報

首先，您需要載入要轉換為 HTML 的 PowerPoint 簡報。您還需要指定保存 HTML 檔案的輸出目錄。這是載入簡報的程式碼：

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

//載入簡報
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    //你的程式碼在這裡
}
```

## 4. 設定 HTML 選項

現在，讓我們設定用於轉換的 HTML 選項。我們將配置 HTML 控制器、HTML 格式化程式和幻燈片影像格式。此程式碼將確保您的 HTML 檔案包含顯示多媒體元素所需的元件。

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/”；

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

//設定 HTML 選項
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. 儲存 HTML 文件

配置 HTML 選項後，現在可以儲存 HTML 檔案。這`Save`演示物件的方法將產生嵌入多媒體元素的 HTML 檔案。

```csharp
//儲存檔案
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 六，結論

恭喜！您已使用 Aspose.Slides for .NET 成功將 PowerPoint 簡報中的媒體檔案匯出為 HTML。這使您可以輕鬆在線共享演示文稿，並確保多媒體元素正確顯示。

## 7. 常見問題解答

### Q1：Aspose.Slides for .NET 是免費的函式庫嗎？
 A1：Aspose.Slides for .NET 是一個商業庫，但您可以從以下位置免費試用[這裡](https://releases.aspose.com/)嘗試一下。

### Q2：我可以進一步自訂 HTML 輸出嗎？
A2：是的，您可以透過修改程式碼中的 HTML 選項來自訂 HTML 輸出。

### Q3：Aspose.Slides for .NET 支援其他匯出格式嗎？
A3：是的，Aspose.Slides for .NET 支援各種匯出格式，包括 PDF、影像格式等。

### 問題 4：在哪裡可以獲得 Aspose.Slides for .NET 的支援？
 A4：您可以在 Aspose 論壇上尋求支援並提出問題[這裡](https://forum.aspose.com/).

### Q5：如何購買 Aspose.Slides for .NET 的授權？
 A5：您可以從以下位置購買許可證：[這個連結](https://purchase.aspose.com/buy).

現在您已完成本教學課程，您已經掌握了使用 Aspose.Slides for .NET 將 PowerPoint 簡報中的媒體檔案匯出為 HTML 的技能。享受在線分享您豐富的多媒體簡報！
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
