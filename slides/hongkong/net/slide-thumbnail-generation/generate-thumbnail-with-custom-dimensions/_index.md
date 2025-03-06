---
title: 在具有自訂尺寸的幻燈片中產生縮圖
linktitle: 產生具有自訂尺寸的縮圖
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for .NET 從 PowerPoint 簡報產生自訂縮圖。增強使用者體驗和功能。
weight: 13
url: /zh-hant/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


無論您是建立互動式應用程式、增強使用者體驗或優化各種平台的內容，建立 PowerPoint 簡報的自訂縮圖都是一項寶貴的資產。在本教學中，我們將引導您完成使用 Aspose.Slides for .NET 函式庫從 PowerPoint 簡報產生自訂縮圖的過程。這個功能強大的程式庫可讓您在 .NET 應用程式中以程式設計方式操作、轉換和增強 PowerPoint 檔案。

## 先決條件

在我們深入產生自訂縮圖之前，請確保您符合以下先決條件：

### 1..NET 的 Aspose.Slides

您需要在專案中安裝 Aspose.Slides for .NET 程式庫。如果您還沒有，您可以找到必要的文件和下載鏈接[這裡](https://reference.aspose.com/slides/net/).

### 2. PowerPoint 演示

確保您擁有要從中產生自訂縮圖的 PowerPoint 簡報。該簡報應該可以在您的專案目錄中存取。

### 三、開發環境

要學習本教學課程，您應該具備使用 C# 進行 .NET 程式設計的實用知識，並設定開發環境（例如 Visual Studio）。

現在我們已經介紹了先決條件，讓我們將產生自訂縮圖的過程分解為逐步說明。

## 導入命名空間

首先，您需要在 C# 程式碼中包含所需的命名空間。這些命名空間可讓您使用 Aspose.Slides 並操作 PowerPoint 簡報。

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 第 1 步：載入簡報

首先，載入要從中產生自訂縮圖的 PowerPoint 簡報。這是使用 Aspose.Slides 函式庫實現的。

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

//實例化表示簡報文件的簡報類
using (Presentation pres = new Presentation(srcFileName))
{
    //您的縮圖產生程式碼將位於此處
}
```

## 第 2 步：存取投影片

在載入的簡報中，您需要存取要從中產生自訂縮圖的特定投影片。您可以透過索引選擇幻燈片。

```csharp
//存取第一張投影片（您可以根據需要更改索引）
ISlide sld = pres.Slides[0];
```

## 第 3 步：定義自訂縮圖尺寸

指定自訂縮圖所需的尺寸。您可以根據應用程式的要求定義寬度和高度（以像素為單位）。

```csharp
int desiredX = 1200; //寬度
int desiredY = 800;  //高度
```

## 第 4 步：計算比例因子

若要維持投影片的縱橫比，請根據投影片的尺寸和所需尺寸計算 X 和 Y 尺寸的縮放係數。

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 第 5 步：產生縮圖

使用指定的自訂尺寸建立投影片的全尺寸影像，並將其以 JPEG 格式儲存到磁碟。

```csharp
//建立全尺寸影像
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

//將影像以 JPEG 格式儲存到磁碟
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

現在您已經執行了這些步驟，您應該已經成功地從 PowerPoint 簡報產生了自訂縮圖。

## 結論

使用 Aspose.Slides for .NET 從 PowerPoint 簡報產生自訂縮圖是一項寶貴的技能，可增強應用程式的使用者體驗和功能。透過遵循本教程中概述的步驟，您可以輕鬆建立滿足您的特定要求的自訂縮圖。

---

## 常見問題（常見問題）

### 什麼是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一個功能強大的程式庫，可讓開發人員在 .NET 應用程式中以程式設計方式處理 PowerPoint 簡報。

### 在哪裡可以找到 Aspose.Slides for .NET 的文檔？
你可以找到文檔[這裡](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET 可以免費使用嗎？
 Aspose.Slides for .NET 是一個商業函式庫。您可以找到定價和許可信息[這裡](https://purchase.aspose.com/buy).

### 我需要高級程式設計技能才能使用 Aspose.Slides for .NET 嗎？
雖然了解一些 .NET 程式設計知識是有益的，但 Aspose.Slides for .NET 提供了一個使用者友善的 API，可以簡化 PowerPoint 簡報的使用。

### Aspose.Slides for .NET 是否提供技術支援？
是的，您可以訪問技術支援和社區論壇[這裡](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
