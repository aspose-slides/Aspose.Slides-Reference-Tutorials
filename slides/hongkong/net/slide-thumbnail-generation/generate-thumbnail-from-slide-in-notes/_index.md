---
"description": "了解如何使用 Aspose.Slides for .NET 從簡報註解部分的投影片產生縮圖。增強您的視覺內容！"
"linktitle": "從筆記中的幻燈片產生縮圖"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "從筆記中的幻燈片產生縮圖"
"url": "/zh-hant/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 從筆記中的幻燈片產生縮圖


在現代示範世界中，視覺內容為王。製作吸引人的幻燈片對於有效溝通至關重要。增強簡報的一種方法是從投影片產生縮圖，尤其是當您想要強調特定細節或分享概述時。 Aspose.Slides for .NET 是一款功能強大的工具，可以幫助您無縫實現這一目標。在本逐步指南中，我們將引導您完成使用 Aspose.Slides for .NET 從簡報的註解部分中的投影片產生縮圖的過程。

## 先決條件

在深入討論細節之前，您應該滿足以下先決條件：

### 1. Aspose.Slides for .NET

請確定您已安裝並設定 Aspose.Slides for .NET。您可以從下載 [這裡](https://releases。aspose.com/slides/net/).

### 2. .NET 環境

您的系統上應該已經準備好.NET 開發環境。

### 3. 示範文件

有一個演示文件（例如， `ThumbnailFromSlideInNotes.pptx`)，從中產生縮圖。

現在，讓我們將這個過程分解為幾個步驟：

## 步驟 1：導入命名空間

首先，您需要匯入必要的命名空間才能使用 Aspose.Slides。在 C# 腳本的開頭新增以下程式碼：

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 第 2 步：載入簡報

接下來，您需要載入包含註釋的投影片的簡報檔案。使用以下程式碼實例化 `Presentation` 班級：

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // 您的程式碼在此處
}
```

## 步驟 3：存取投影片

您可以選擇簡報中要產生縮圖的投影片。在此範例中，我們將存取第一張投影片：

```csharp
ISlide sld = pres.Slides[0];
```

## 步驟 4：定義所需尺寸

指定要產生的縮圖的尺寸（寬度和高度）。例如：

```csharp
int desiredX = 1200; // 寬度
int desiredY = 800;  // 高度
```

## 步驟5：計算縮放因子

為了確保縮圖符合所需尺寸，請以以下方式計算縮放因子：

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 步驟 6：建立縮圖

現在，使用計算出的縮放因子建立全尺寸影像縮圖：

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## 步驟 7：儲存縮圖

最後，將產生的縮圖儲存為 JPEG 影像：

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

就是這樣！您已成功使用 Aspose.Slides for .NET 從簡報的註解部分中的投影片產生縮圖。

## 結論

將縮圖添加到簡報中可以顯著提高其視覺吸引力和有效性。 Aspose.Slides for .NET 讓這個過程變得簡單，讓您可以輕鬆地從投影片中建立自訂縮圖。

## 常見問題解答

### 我可以將生成的縮圖保存為什麼格式？
根據您的需要，您可以以各種格式儲存縮圖，包括 JPEG、PNG 等。

### 我可以一次為多張投影片產生縮圖嗎？
是的，您可以循環播放簡報中的投影片並為每張投影片產生縮圖。

### Aspose.Slides for .NET 是否與不同的 .NET 框架相容？
是的，Aspose.Slides for .NET 與各種 .NET 框架相容，包括 .NET Core 和 .NET Framework。

### 我可以自訂生成的縮圖的外觀嗎？
絕對地！ Aspose.Slides for .NET 提供了自訂縮圖外觀的選項，例如尺寸、品質等。

### 我可以在哪裡獲得有關 Aspose.Slides for .NET 的支援或進一步協助？
您可以在以下位置尋求協助並參與 Aspose 社區 [Aspose 支援論壇](https://forum。aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}