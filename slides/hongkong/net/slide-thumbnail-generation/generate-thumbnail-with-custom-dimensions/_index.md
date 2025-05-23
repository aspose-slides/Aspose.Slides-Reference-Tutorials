---
"description": "了解如何使用 Aspose.Slides for .NET 從 PowerPoint 簡報產生自訂縮圖。增強使用者體驗和功能。"
"linktitle": "產生自訂尺寸的縮圖"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "使用自訂尺寸在投影片中產生縮圖"
"url": "/zh-hant/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用自訂尺寸在投影片中產生縮圖


無論您是建立互動式應用程式、增強使用者體驗或優化各種平台的內容，建立 PowerPoint 簡報的自訂縮圖都是一項寶貴的資產。在本教學中，我們將指導您使用 Aspose.Slides for .NET 函式庫從 PowerPoint 簡報產生自訂縮圖的過程。這個強大的程式庫可讓您在 .NET 應用程式中以程式設計方式操作、轉換和增強 PowerPoint 檔案。

## 先決條件

在深入產生自訂縮圖之前，請確保您已滿足以下先決條件：

### 1. Aspose.Slides for .NET

您需要在專案中安裝 Aspose.Slides for .NET 程式庫。如果你還沒有，你可以找到必要的文件和下載鏈接 [這裡](https://reference。aspose.com/slides/net/).

### 2. PowerPoint簡報

確保您擁有要從中產生自訂縮圖的 PowerPoint 簡報。該簡報應該可以在您的專案目錄中存取。

### 3.開發環境

要學習本教學課程，您應該具備使用 C# 進行 .NET 程式設計的工作知識以及已設定的開發環境（例如 Visual Studio）。

現在我們已經介紹了先決條件，讓我們將產生自訂縮圖的過程分解為逐步說明。

## 導入命名空間

首先，您需要在 C# 程式碼中包含所需的命名空間。這些命名空間可讓您使用 Aspose.Slides 並操作 PowerPoint 簡報。

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 步驟 1：載入簡報

首先，載入您想要產生自訂縮圖的 PowerPoint 簡報。這是使用 Aspose.Slides 函式庫實現的。

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// 實例化代表演示檔案的 Presentation 類
using (Presentation pres = new Presentation(srcFileName))
{
    // 您的縮圖產生程式碼將放在此處
}
```

## 第 2 步：存取投影片

在載入的簡報中，您需要存取要從中產生自訂縮圖的特定投影片。您可以根據索引選擇幻燈片。

```csharp
// 存取第一張投影片（您可以根據需要更改索引）
ISlide sld = pres.Slides[0];
```

## 步驟 3：定義自訂縮圖尺寸

指定自訂縮圖所需的尺寸。您可以根據應用程式的要求以像素為單位定義寬度和高度。

```csharp
int desiredX = 1200; // 寬度
int desiredY = 800;  // 高度
```

## 步驟 4：計算縮放因子

為了保持投影片的縱橫比，請根據投影片的大小和所需尺寸計算 X 和 Y 尺寸的縮放係數。

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 步驟5：產生縮圖

建立具有指定自訂尺寸的幻燈片的全尺寸影像，並以 JPEG 格式將其儲存到磁碟。

```csharp
// 建立全尺寸影像
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// 將影像以 JPEG 格式儲存到磁碟
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

現在您已按照這些步驟操作，您應該已經成功地從 PowerPoint 簡報中產生了自訂縮圖。

## 結論

使用 Aspose.Slides for .NET 從 PowerPoint 簡報產生自訂縮圖是一項有價值的技能，可增強使用者體驗和應用程式的功能。透過遵循本教學中概述的步驟，您可以輕鬆建立滿足特定要求的自訂縮圖。

---

## 常見問題解答

### 什麼是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一個功能強大的程式庫，可讓開發人員在 .NET 應用程式中以程式設計方式處理 PowerPoint 簡報。

### 在哪裡可以找到 Aspose.Slides for .NET 的文檔？
您可以找到文檔 [這裡](https://reference。aspose.com/slides/net/).

### Aspose.Slides for .NET 可以免費使用嗎？
Aspose.Slides for .NET 是一個商業函式庫。您可以找到定價和許可信息 [這裡](https://purchase。aspose.com/buy).

### 我需要高級程式設計技能才能使用 Aspose.Slides for .NET 嗎？
雖然一些 .NET 程式設計知識是有益的，但 Aspose.Slides for .NET 提供了一個使用者友善的 API，簡化了 PowerPoint 簡報的處理。

### Aspose.Slides for .NET 是否提供技術支援？
是的，您可以訪問技術支援和社區論壇 [這裡](https://forum。aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}