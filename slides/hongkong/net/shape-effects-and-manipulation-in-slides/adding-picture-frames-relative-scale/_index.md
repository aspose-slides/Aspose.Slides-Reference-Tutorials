---
"description": "學習在 Aspose.Slides for .NET 中新增具有相對比例高度的圖片框。請按照本逐步指南進行操作，即可實現無縫演示。"
"linktitle": "在 Aspose.Slides 中加入具有相對比例高度的圖片框架"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "使用 Aspose.Slides .NET 新增圖片框架教學"
"url": "/zh-hant/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Slides .NET 新增圖片框架教學

## 介紹
Aspose.Slides for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中輕鬆地建立、操作和轉換 PowerPoint 簡報。在本教程中，我們將深入研究使用 Aspose.Slides for .NET 添加具有相對比例高度的圖片框的過程。請按照本逐步指南來提升您的簡報製作技巧。
## 先決條件
在開始之前，請確保您具備以下條件：
- C# 程式語言的基本知識。
- 安裝了 Visual Studio 或任何其他首選的 C# 開發環境。
- Aspose.Slides for .NET 函式庫已新增至您的專案中。
## 導入命名空間
首先將必要的命名空間匯入到您的 C# 程式碼中。此步驟可確保您可以存取 Aspose.Slides 庫提供的類別和功能。
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 步驟 1：設定您的項目
首先在您喜歡的開發環境中建立一個新的 C# 專案。確保透過引用將 Aspose.Slides for .NET 函式庫新增至您的專案中。
## 步驟 2：載入簡報和圖像
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // 載入要新增到演示圖像集合中的圖像
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // …
}
```
在這一步驟中，我們建立一個新的演示物件並載入我們想要新增到演示中的影像。
## 步驟 3：將圖片框新增至投影片
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
現在，在簡報的第一張投影片上新增一個圖片框。根據您的要求調整形狀類型、位置和尺寸等參數。
## 步驟 4：設定相對比例寬度和高度
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
設定圖片邊框的相對縮放高度和寬度，以達到想要的縮放效果。
## 步驟 5：儲存簡報
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
最後，以指定的輸出格式儲存新增了圖片框的簡報。
## 結論
恭喜！您已成功學習如何使用 Aspose.Slides for .NET 新增具有相對比例高度的圖片框。嘗試不同的圖像、位置和比例來創建符合您需求的視覺吸引力的簡報。
## 常見問題
### 我可以將 Aspose.Slides for .NET 與其他程式語言一起使用嗎？
Aspose.Slides 主要支援 .NET 語言，但您可以探索其他 Aspose 產品以實現與不同平台的兼容性。
### 在哪裡可以找到 Aspose.Slides for .NET 的詳細文件？
請參閱 [文件](https://reference.aspose.com/slides/net/) 以獲得全面的資訊和範例。
### Aspose.Slides for .NET 有免費試用版嗎？
是的，你可以得到 [免費試用](https://releases.aspose.com/) 評估圖書館的能力。
### 如何獲得 Aspose.Slides for .NET 的支援？
訪問 [Aspose.Slides論壇](https://forum.aspose.com/c/slides/11) 尋求社區和 Aspose 專家的幫助。
### 我可以在哪裡購買 Aspose.Slides for .NET？
您可以從 [購買頁面](https://purchase。aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}