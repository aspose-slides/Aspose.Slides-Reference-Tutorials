---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 建立和自訂圖表，包括將百分比顯示為資料標籤。請按照本逐步指南進行操作。"
"title": "如何使用 Aspose.Slides .NET&#58; 建立和自訂圖表將百分比顯示為標籤"
"url": "/zh-hant/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides .NET 建立和自訂圖表：將百分比顯示為標籤

## 介紹

在許多領域，有效地呈現數據至關重要，而圖表透過將複雜的資訊轉化為清晰的視覺效果發揮著至關重要的作用。建立完美的圖表涉及自訂任務，例如在標籤上顯示百分比 - 使用 Aspose.Slides for .NET 可以更輕鬆地完成這項任務。該程式庫簡化了在 PowerPoint 簡報中建立和修改圖表的過程。

在本教程中，您將學習如何使用 Aspose.Slides for .NET 從頭開始建立堆積長條圖，並透過將百分比值顯示為資料標籤來進行自訂。透過遵循這些步驟，您將使用精確且視覺吸引力的資料表示來增強您的投影片。

**您將學到什麼：**
- 初始化 Aspose.Slides for .NET
- 創建堆積長條圖
- 計算並顯示數據標籤上的百分比
- 優化圖表效能最佳實踐

在我們深入實施之前，讓我們確保您已做好一切準備。

## 先決條件

為了有效地遵循本教程，請確保您已：
- **.NET Core SDK** 安裝在您的機器上。
- 對 C# 和 .NET 應用程式開發有基本的了解。
- Visual Studio 或類似的 IDE，用於編寫和執行 C# 程式碼。

您需要 Aspose.Slides for .NET 來建立圖表，因此請確保按照下面的說明進行設定。

## 設定 Aspose.Slides for .NET

Aspose.Slides for .NET 是一個功能強大的函式庫，可讓您以程式設計方式處理 PowerPoint 簡報。將其添加到您的項目的方法如下：

### 安裝

**.NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**套件管理器控制台：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI：** 
- 開啟 NuGet 套件管理員並蒐尋「Aspose.Slides」。安裝最新版本。

### 許可證獲取

要充分利用 Aspose.Slides，請先免費試用。如需延長使用時間，請考慮取得臨時許可證或從 [Aspose](https://purchase.aspose.com/buy)。按照他們的指南在您的專案環境中設定您的許可證。

### 基本初始化

安裝完成後，初始化 `Presentation` 類別開始建立投影片：
```csharp
using Aspose.Slides;

// 初始化Presentation類別實例
tPresentation presentation = new Presentation();
```

現在，讓我們繼續使用 Aspose.Slides for .NET 實作圖表建立和自訂功能。

## 實施指南

### 創建堆積長條圖

我們的目標是創建一個堆積長條圖並透過顯示百分比作為資料標籤來進行自訂。方法如下：

#### 初始化簡報

首先建立一個實例 `Presentation`：
```csharp
using Aspose.Slides;

// 初始化Presentation類別實例
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### 在投影片中新增圖表

在第一張投影片中按指定的座標和尺寸新增堆疊長條圖：
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
這行程式碼創建了一個 `StackedColumn` 圖表位於位置 (20, 20)，寬度和高度為 400。

#### 計算百分比計算的總值

若要顯示百分比，請計算所有系列中每個類別的總值：
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // 對每個類別的所有系列的值進行求和
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### 自訂資料標籤以顯示百分比值

接下來，遍歷每個系列並自訂資料標籤：
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // 計算百分比
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // 清晰的文本以避免重疊
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // 配置標籤格式以隱藏預設資料標籤
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

此部分計算每個資料點的百分比並將其設定為自訂標籤，確保與預設標籤不重疊。

#### 儲存簡報

最後，儲存您的簡報以查看結果：
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## 實際應用

在圖表中顯示百分比在以下情況下特別有用：
1. **財務報告：** 以百分比顯示投資組合分佈或投資回報。
2. **銷售分析：** 以百分比表示市佔率數據，以突顯各地區的表現。
3. **調查結果：** 將調查回應顯示為百分比，以便進行更好的視覺比較。
4. **專案管理：** 使用帶有百分比的圓餅圖來說明資源分配。
5. **教育：** 使用清晰的基於百分比的視覺效果解釋統計概念。

將這些客製化圖表整合到 CRM 或 ERP 等系統中可以增強儀表板和報告，從而幫助決策過程。

## 性能考慮

使用 Aspose.Slides for .NET 時，特別是處理大型資料集時：
- **記憶體管理：** 正確處理演示物件以釋放記憶體。使用 `using` 適用的聲明。
- **高效率的資料處理：** 盡可能在循環外執行計算以減少計算開銷。
- **負載平衡：** 對於 Web 應用程序，請確保伺服器資源足以滿足並發圖表生成請求。

## 結論

本教學課程說明如何使用 Aspose.Slides for .NET 透過將百分比值顯示為標籤來建立和自訂圖表。掌握這些技術可以讓您透過詳細且視覺上吸引人的數據表示來增強您的簡報。

下一步，探索 Aspose.Slides 中可用的其他圖表類型和自訂選項。嘗試不同的資料集，將它們轉換成能夠清晰傳達見解的強大視覺效果。

## 常見問題部分

**問題 1：使用 Aspose.Slides for .NET 建立圖表時如何處理大型資料集？**
A1：對於大型資料集，優化計算並使用高效的記憶體管理技術。分解處理任務以避免記憶體過載。

**問題2：我可以在 Web 應用程式中使用 Aspose.Slides for .NET 嗎？**
A2：是的，它可以整合到 ASP.NET 應用程式中。確保適當的伺服器資源分配以獲得最佳效能。

**Q3：是否可以將使用 Aspose.Slides 建立的圖表匯出為其他格式？**
A3：當然！您可以使用庫的功能將包含自訂圖表的簡報匯出為各種格式，例如 PDF 和圖像檔案。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}