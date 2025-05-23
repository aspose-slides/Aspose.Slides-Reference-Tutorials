---
"date": "2025-04-15"
"description": "學習使用 Aspose.Slides 透過 ActiveX 控制項自動化和自訂 PowerPoint 簡報。有效地存取、修改和移動控制項。"
"title": "使用 Aspose.Slides for .NET 掌握 PowerPoint 中的 ActiveX 控制項"
"url": "/zh-hant/net/ole-objects-embedding/mastering-activex-controls-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for .NET 掌握 PowerPoint 中的 ActiveX 控制項

## 介紹

您是否希望使用 ActiveX 控制項來自動化或增強您的 PowerPoint 簡報？許多開發人員在存取和操作 PPTM 檔案中的這些元素時遇到挑戰。本指南將示範如何 **Aspose.Slides for .NET** 可以幫助您有效地更新文字、圖像以及移動 PowerPoint 簡報中的 ActiveX 框架。

### 您將學到什麼
- 使用 Aspose.Slides 存取和修改 ActiveX 控制項
- 更改文字方塊文字並建立替代圖像
- 使用視覺替代來更新命令按鈕標題
- 在投影片內移動 ActiveX 框架
- 儲存已編輯的簡報或刪除所有控件

讓我們探索如何利用這些功能進行動態演示。

## 先決條件

在開始之前，請確保您已準備好以下內容：

- **庫和依賴項**：從以下位置下載並安裝 Aspose.Slides for .NET [Aspose](https://releases。aspose.com/slides/net/).
- **環境設定**：本指南假設安裝了 .NET Core 或 Framework 的 Visual Studio 基本設定。
- **知識前提**：建議熟悉 C# 程式設計和在 .NET 中處理文件。

## 設定 Aspose.Slides for .NET

### 安裝

首先，使用下列方法之一安裝 Aspose.Slides 函式庫：

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**套件管理器**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI**：搜尋“Aspose.Slides”並安裝。

### 許可證獲取
- **免費試用**：從下載免費試用版 [Aspose 網站](https://releases。aspose.com/slides/net/).
- **臨時執照**：如需延長測試時間，請申請臨時許可證 [購買 Aspose](https://purchase。aspose.com/temporary-license/).
- **購買**：從購買商業許可證 [Aspose 商店](https://purchase.aspose.com/buy) 如果需要的話。

### 基本初始化
```csharp
using Aspose.Slides;

// 使用您的 .pptm 檔案路徑初始化 Presentation 對象
Presentation presentation = new Presentation("path_to_your_presentation.pptm");
```

## 實施指南

詳細探索每個功能，包括實施和解決常見問題。

### 使用 ActiveX 控制項存取簡報

**概述**：本節介紹如何使用 Aspose.Slides 開啟包含 ActiveX 控制項的 PowerPoint 文件。

#### 開幕式
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY" + "/ActiveX.pptm";
Presentation presentation = new Presentation(documentPath);
ISlide slide = presentation.Slides[0];
```

### 更改文字方塊文字和替換圖像

**概述**：更新文字方塊的文字內容並將其替換為替代圖像。

#### 更新文字並建立圖像
```csharp
IControl control = slide.Controls[0];
if (control.Name == "TextBox1" && control.Properties != null)
{
    string newText = "Changed text";
    control.Properties["Value"] = newText;

    // 生成圖像作為 TextBox 內容的視覺替代
    Bitmap image = new Bitmap((int)control.Frame.Width, (int)control.Frame.Height);
    Graphics graphics = Graphics.FromImage(image);

    Brush brush = new SolidBrush(Color.FromKnownColor(KnownColor.Window));
    graphics.FillRectangle(brush, 0, 0, image.Width, image.Height);

    System.Drawing.Font font = new System.Drawing.Font(control.Properties["FontName"], 14);
    brush = new SolidBrush(Color.FromKnownColor(KnownColor.WindowText));
    graphics.DrawString(newText, font, brush, 10, 4);

    // 繪製邊框並將生成的圖像添加到簡報中
    control.SubstitutePictureFormat.Picture.Image = presentation.Images.AddImage(image);
}
```
**解釋**：此程式碼更新 TextBox 的文字並使用 GDI+ 建立圖像替代以實現視覺表示。

### 更改按鈕標題和替換圖像

**概述**：更改 CommandButton 控制項的標題並產生更新的替代圖像。

#### 更新按鈕標題
```csharp
IControl control = slide.Controls[1];
if (control.Name == "CommandButton1" && control.Properties != null)
{
    String newCaption = "MessageBox";
    control.Properties["Caption"] = newCaption;

    Bitmap image = new Bitmap((int)control.Frame.Width, (int)control.Frame.Height);
    Graphics graphics = Graphics.FromImage(image);

    Brush brush = new SolidBrush(Color.FromKnownColor(KnownColor.Control));
    graphics.FillRectangle(brush, 0, 0, image.Width, image.Height);

    System.Drawing.Font font = new System.Drawing.Font(control.Properties["FontName"], 14);
    SizeF textSize = graphics.MeasureString(newCaption, font, int.MaxValue);

    brush = new SolidBrush(Color.FromKnownColor(KnownColor.WindowText));
    graphics.DrawString(newCaption, font, brush, (image.Width - textSize.Width) / 2, (image.Height - textSize.Height) / 2);

    using (MemoryStream ms = new MemoryStream())
    {
        image.Save(ms, ImageFormat.Png);
        IImage img = Images.FromStream(ms);
        control.SubstitutePictureFormat.Picture.Image = presentation.Images.AddImage(img);
    }
}
```
**解釋**：此部分更新按鈕的標題並建立相關的替代圖像以直觀地反映變更。

### 移動 ActiveX 框架

**概述**：了解如何透過調整座標來移動投影片上的 ActiveX 框架。

#### 向下移動框架
```csharp
foreach (Control ctl in slide.Controls)
{
    IShapeFrame frame = ctl.Frame;
    ctl.Frame = new ShapeFrame(frame.X, frame.Y + 100, frame.Width, frame.Height, frame.FlipH, frame.FlipV, frame.Rotation);
}
```
**解釋**：此程式碼片段將投影片上的所有 ActiveX 框架向下移動 100 點。

### 使用 ActiveX 控制項儲存已編輯的簡報

**概述**：編輯 ActiveX 控制項後儲存簡報以保留變更。

#### 儲存變更
```csharp
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDirectory + "/withActiveX-edited_out.pptm", Aspose.Slides.Export.SaveFormat.Pptm);
```

### 刪除並儲存已清除的 ActiveX 控件

**概述**：從幻燈片中刪除所有控件，然後將簡報儲存為清除狀態。

#### 清晰的控制
```csharp
slide.Controls.Clear();
presentation.Save(outputDirectory + "/withActiveX.cleared_out.pptm", Aspose.Slides.Export.SaveFormat.Pptm);
```

## 實際應用
- **自動報告**：使用 ActiveX 控制項自訂具有動態內容的報告。
- **互動式演示**：透過即時更新控製字幕來增強觀眾參與度。
- **模板定制**：透過調整文字和圖像來修改模板以滿足特定的品牌需求。
- **數據集成**：將 ActiveX 控制項連結到外部資料來源以進行即時更新。
- **教育工具**：建立具有可自訂元素的互動式學習模組。

## 性能考慮
- **優化資源使用**：透過在使用後處置圖形物件來最大限度地減少記憶體使用。
- **批次處理**：批量處理多張投影片或簡報以減少處理時間。
- **高效率的影像處理**：使用串流進行影像處理，以避免不必要的檔案 I/O 操作。

## 結論

您已經掌握了使用 Aspose.Slides for .NET 在 PowerPoint 中存取和修改 ActiveX 控制項。利用這些技術，您可以創建適合您需求的動態且引人入勝的簡報。繼續探索 Aspose.Slides 文件並嘗試更多高級功能以增強您的自動化能力。

準備好將您的技能提升到新的水平了嗎？嘗試在您的下一個專案中使用 Aspose.Slides 實現自訂解決方案！

## 常見問題部分

1. **什麼是 Aspose.Slides for .NET？**
   Aspose.Slides for .NET 是一個函式庫，可讓開發人員以程式設計方式建立、編輯和操作 PowerPoint 簡報。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}