---
title: 使用 Aspose.Slides .NET 新增圖片框架教學
linktitle: 在 Aspose.Slides 中加入具有相對比例高度的圖片框
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 了解在 Aspose.Slides for .NET 中新增具有相對比例高度的圖片框架。請按照此逐步指南進行無縫演示。
weight: 17
url: /zh-hant/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
Aspose.Slides for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中輕鬆建立、操作和轉換 PowerPoint 簡報。在本教程中，我們將深入研究使用 Aspose.Slides for .NET 添加具有相對比例高度的相框的過程。請按照此逐步指南來增強您的簡報建立技能。
## 先決條件
在我們開始之前，請確保您具備以下條件：
- C# 程式語言的基礎知識。
- 安裝 Visual Studio 或任何其他首選的 C# 開發環境。
- Aspose.Slides for .NET 函式庫已新增至您的專案中。
## 導入命名空間
首先將必要的命名空間匯入到 C# 程式碼中。此步驟可確保您可以存取 Aspose.Slides 庫提供的類別和功能。
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 第 1 步：設定您的項目
首先在您首選的開發環境中建立一個新的 C# 專案。確保透過引用 Aspose.Slides for .NET 程式庫將其新增至您的專案。
## 第 2 步：載入簡報和圖像
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //載入要新增到演示圖像集合中的圖像
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    //…
}
```
在此步驟中，我們建立一個新的簡報物件並載入要新增到簡報中的影像。
## 步驟 3：為投影片新增相框
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
現在，將圖片框新增至簡報的第一張投影片中。根據您的要求調整形狀類型、位置和尺寸等參數。
## 步驟 4：設定相對比例寬度和高度
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
設定圖片框的相對縮放高度和寬度，以達到所需的縮放效果。
## 第 5 步：儲存簡報
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
最後，以指定的輸出格式儲存新增了圖片框的簡報。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Slides for .NET 新增具有相對比例高度的圖片框架。嘗試不同的圖像、位置和比例，根據您的需求創建具有視覺吸引力的簡報。
## 經常問的問題
### 我可以將 Aspose.Slides for .NET 與其他程式語言一起使用嗎？
Aspose.Slides 主要支援 .NET 語言，但您可以探索其他 Aspose 產品以與不同平台相容。
### 在哪裡可以找到 Aspose.Slides for .NET 的詳細文件？
請參閱[文件](https://reference.aspose.com/slides/net/)獲取全面的資訊和範例。
### Aspose.Slides for .NET 有沒有免費試用版？
是的，您可以獲得[免費試用](https://releases.aspose.com/)評估圖書館的能力。
### 如何獲得 Aspose.Slides for .NET 支援？
參觀[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11)向社區和 Aspose 專家尋求協助。
### 在哪裡可以購買 Aspose.Slides for .NET？
您可以從以下位置購買 Aspose.Slides for .NET[購買頁面](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
