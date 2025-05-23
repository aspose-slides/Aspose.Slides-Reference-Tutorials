---
"description": "學習使用 Aspose.Slides for .NET 建立具有特定邊界的 PowerPoint 縮圖。按照我們的逐步指南實現無縫整合。"
"linktitle": "在 Aspose.Slides 中建立具有形狀縮放因子的縮圖"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "在 Aspose.Slides 中建立具有形狀縮放因子的縮圖"
"url": "/zh-hant/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Slides 中建立具有形狀縮放因子的縮圖

## 介紹
歡迎閱讀我們關於在 Aspose.Slides for .NET 中建立帶有形狀邊界的縮圖的綜合指南。 Aspose.Slides 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中無縫地處理 PowerPoint 簡報。在本教程中，我們將深入研究使用 Aspose.Slides 為簡報中的形狀產生具有特定邊界的縮圖的過程。
## 先決條件
在開始之前，請確保您已滿足以下先決條件：
- Aspose.Slides for .NET：確保您已安裝 Aspose.Slides 函式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/net/).
- 開發環境：在您的機器上設定適合 .NET 的開發環境，例如 Visual Studio。
## 導入命名空間
在您的 .NET 應用程式中，首先匯入必要的命名空間以存取 Aspose.Slides 功能：
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## 步驟 1：設定簡報
首先實例化一個代表您要使用的 PowerPoint 簡報檔案的 Presentation 類別：
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // 產生縮圖的程式碼在此處
}
```
## 步驟 2：建立全尺寸影像
在演示區塊中，建立要產生縮圖的形狀的全尺寸影像：
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // 保存圖像的程式碼在此處
}
```
## 步驟 3：將影像儲存到磁碟
將產生的映像儲存到磁碟，指定格式（在本例中為 PNG）：
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## 結論
恭喜！您已成功學習如何使用 Aspose.Slides for .NET 建立具有形狀邊界的縮圖。當您需要以程式設計方式在 PowerPoint 簡報中產生特定大小的形狀圖像時，此功能非常有用。
## 常見問題
### 問題 1：我可以將 Aspose.Slides 與其他 .NET 框架一起使用嗎？
是的，Aspose.Slides 與各種 .NET 框架相容，可靈活地整合到不同類型的應用程式中。
### 問題2：Aspose.Slides 有試用版嗎？
是的，您可以透過下載試用版來探索 Aspose.Slides 的功能 [這裡](https://releases。aspose.com/).
### Q3：如何取得 Aspose.Slides 的臨時授權？
您可以透過造訪取得 Aspose.Slides 的臨時許可證 [此連結](https://purchase。aspose.com/temporary-license/).
### 問題 4：在哪裡可以找到對 Aspose.Slides 的額外支援？
如有任何疑問或需要協助，請隨時造訪 Aspose.Slides 支援論壇 [這裡](https://forum。aspose.com/c/slides/11).
### 問題5：我可以購買 Aspose.Slides for .NET 嗎？
當然！要購買 Aspose.Slides for .NET，請造訪購買頁面 [這裡](https://purchase。aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}