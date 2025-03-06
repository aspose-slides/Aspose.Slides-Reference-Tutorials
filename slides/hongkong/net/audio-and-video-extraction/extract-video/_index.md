---
title: 如何使用 Aspose.Slides for .NET 從幻燈片中提取視頻
linktitle: 從幻燈片中提取視頻
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for .NET 從 PowerPoint 投影片中擷取影片。本逐步指南為您簡化了流程。
weight: 14
url: /zh-hant/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Slides for .NET 從幻燈片中提取視頻


Aspose.Slides for .NET 是一個功能強大的程式庫，可讓您在 .NET 環境中處理 PowerPoint 簡報。它提供的有用功能之一是能夠從幻燈片中提取影片。在本逐步指南中，我們將向您展示如何使用 Aspose.Slides for .NET 從 PowerPoint 投影片中擷取影片。

## 先決條件

在開始之前，請確保您具備以下先決條件：

-  Aspose.Slides for .NET：您需要安裝Aspose.Slides for .NET。您可以從[網站](https://purchase.aspose.com/buy).

- PowerPoint 簡報：準備包含要擷取的影片的 PowerPoint 簡報（例如 Video.pptx）。

## 導入命名空間

您需要匯入必要的命名空間才能使用 Aspose.Slides for .NET。您可以這樣做：

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

現在，讓我們將從幻燈片中提取影片的過程分解為多個步驟。

## 步驟1：設定文檔目錄

```csharp
string dataDir = "Your Document Directory";
```

代替`"Your Document Directory"`以及 PowerPoint 簡報所在目錄的路徑。

## 第 2 步：載入簡報

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

此程式碼初始化一個Presentation 對象，代表您的PowerPoint 簡報檔案。

## 第 3 步：迭代投影片和形狀

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

在這裡，我們循環瀏覽簡報中的每張投影片，然後迭代第一張投影片中的形狀（根據需要進行修改）。

## 步驟 4：檢查形狀是否為視訊幀

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

此步驟檢查投影片上的形狀是否為視訊幀。

## 第5步：擷取視訊數據

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

此程式碼提取有關影片的信息，包括其內容類型和二進位資料。

## 第 6 步：保存視頻

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

最後，此步驟將影片儲存到指定目錄中的新檔案中。

完成這些步驟後，您將使用 Aspose.Slides for .NET 成功從 PowerPoint 投影片中擷取影片。

## 結論

Aspose.Slides for .NET 簡化了處理 PowerPoint 簡報的過程，讓您可以輕鬆執行從幻燈片中提取影片等任務。透過遵循此逐步指南並使用 Aspose.Slides 庫，您可以透過強大的 PowerPoint 功能增強您的 .NET 應用程式。

## 常見問題 (FAQ)

### 什麼是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一個函式庫，使 .NET 應用程式能夠處理 PowerPoint 簡報，包括建立、編輯和提取內容。

### 在哪裡可以找到 Aspose.Slides for .NET 的文檔？
你可以找到文檔[這裡](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET 可以免費試用嗎？
是的，您可以從以下位置取得免費試用版[這裡](https://releases.aspose.com/).

### 如何取得 Aspose.Slides for .NET 的臨時授權？
您可以向以下機構申請臨時許可證[這個連結](https://purchase.aspose.com/temporary-license/).

### 在哪裡可以獲得 Aspose.Slides for .NET 的支援？
您可以在以下位置找到支持[Aspose.Slides 論壇](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
