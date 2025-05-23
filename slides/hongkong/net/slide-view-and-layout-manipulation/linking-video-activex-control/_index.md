---
"description": "了解如何使用 Aspose.Slides for .NET 將影片連結到 PowerPoint 投影片。本逐步指南包括原始程式碼和使用連結影片創建互動式、引人入勝的簡報的技巧。"
"linktitle": "透過 ActiveX 控制項連結視頻"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "在 PowerPoint 中透過 ActiveX 控制項連結視頻"
"url": "/zh-hant/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 PowerPoint 中透過 ActiveX 控制項連結視頻

使用 Aspose.Slides for .NET 在簡報中透過 ActiveX 控制項連結視頻

在 Aspose.Slides for .NET 中，您可以使用 ActiveX 控制項以程式設計方式將影片連結到簡報投影片。這使您可以建立互動式簡報，其中可以在幻燈片中直接播放影片內容。在本逐步指南中，我們將引導您完成使用 Aspose.Slides for .NET 將影片連結到簡報投影片的過程。

## 先決條件：
- Visual Studio（或任何其他.NET開發環境）
- Aspose.Slides 用於 .NET 函式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/net/).

## 步驟 1：建立新項目
在您喜歡的 .NET 開發環境（例如 Visual Studio）中建立新專案並新增對 Aspose.Slides for .NET 程式庫的參考。

## 步驟2：導入必要的命名空間
在您的專案中，匯入使用 Aspose.Slides 所需的命名空間：

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## 步驟 3：載入簡報
載入您想要新增連結影片的 PowerPoint 簡報：

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // 添加鏈接視頻的代碼將在此處
}
```

## 步驟4：新增ActiveX控件
建立一個實例 `IOleObjectFrame` 將ActiveX控制項加入投影片的介面：

```csharp
ISlide slide = presentation.Slides[0]; // 選擇要新增影片的幻燈片
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

在上面的程式碼中，我們為投影片新增了一個尺寸為 640x480 的 ActiveX 控制項框。我們正在為 ShockwaveFlash ActiveX 控制項指定 ProgID，該控制項通常用於嵌入影片。

## 步驟5：設定ActiveX控制項的屬性
設定ActiveX控制項的屬性，指定連結的視訊來源：

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // 替換為實際的視訊檔案路徑
oleObjectFrame.AlternativeText = "Linked Video";
```

代替 `"YourVideoPathHere"` 與您的視訊檔案的實際路徑。這 `AlternativeText` 屬性為連結的影片提供了描述。

## 步驟 6：儲存簡報
儲存修改後的簡報：

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## 常見問題：

### 如何指定幻燈片上連結影片的大小和位置？
您可以使用下列參數調整 ActiveX 控制項框架的尺寸和位置： `AddOleObjectFrame` 方法。四個數值參數分別表示左上角的 X 和 Y 座標以及框架的寬度和高度。

### 我可以使用這種方法連結不同格式的影片嗎？
是的，您可以連結各種格式的視頻，只要該格式有適當的 ActiveX 控制項即可。例如，本指南中使用的 ShockwaveFlash ActiveX 控制項適用於 Flash 影片（SWF）。對於其他格式，您可能需要使用不同的 ProgID。

### 連結影片的大小有限制嗎？
連結影片的大小可能會影響簡報的整體大小和效能。建議在將影片連結到簡報之前，先對其進行最佳化以適合網路播放。

### 結論：
透過遵循本指南中概述的步驟，您可以使用 Aspose.Slides for .NET 在簡報中輕鬆地透過 ActiveX 控制項連結影片。此功能使您能夠創建無縫融合多媒體內容的引人入勝且互動的簡報。

有關更多詳細資訊和進階選項，您可以參考 [Aspose.Slides for .NET 文檔](https://reference。aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}