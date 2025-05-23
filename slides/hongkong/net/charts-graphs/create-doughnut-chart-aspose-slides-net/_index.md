---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 建立動態圓環圖。請按照本指南取得逐步說明，包括設定和進階功能。"
"title": "逐步指南&#58;使用 Aspose.Slides .NET 建立甜甜圈圖 |圖表和圖形"
"url": "/zh-hant/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 逐步指南：使用 Aspose.Slides .NET 建立甜甜圈圖

## 介紹

想像一下，您的任務是向您的團隊或客戶展示數據分析結果，並且您需要一種引人入勝的方式來視覺化資訊。輸入環形圖——一種多功能工具，可以將原始數字轉換為易於理解的見解。使用 Aspose.Slides for .NET，在簡報投影片中建立自訂環形圖變得簡單且有效率。本指南將引導您使用 Aspose.Slides 創建具有視覺吸引力的圓環圖，並配有自訂的系列配置。

**您將學到什麼：**
- 使用 Aspose.Slides for .NET 設定您的開發環境
- 在簡報中建立和自訂圓環圖
- 實現類別名稱和引導線等進階功能
- 優化大型資料集的效能

讓我們深入了解您開始所需的先決條件。

## 先決條件

在實現此功能之前，請確保您的開發環境已正確設定。本教學假設您具備 .NET 程式設計的基本知識並熟悉 Visual Studio 或類似的 IDE。

### 所需的庫和版本
- **Aspose.Slides for .NET**：透過檢查其是否與最新版本相容 [官方文檔](https://reference。aspose.com/slides/net/).

### 環境設定要求
- 一個有效的 .NET 環境。
- 存取程式碼編輯器，例如 Visual Studio。

### 知識前提
- 對 C# 和 .NET 架構有基本的了解。
- 熟悉演示軟體概念（可選但有幫助）。

## 設定 Aspose.Slides for .NET

要開始在專案中使用 Aspose.Slides，您需要透過 NuGet 安裝它。可用的方法如下：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**使用套件管理器：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI：**
搜尋“Aspose.Slides”並安裝最新版本。

### 許可證取得步驟

1. **免費試用**：從 [免費試用](https://releases.aspose.com/slides/net/) 探索基本功能。
2. **臨時執照**：如果您需要存取完整功能進行評估，請造訪以下網址以取得臨時許可證 [這裡](https://purchase。aspose.com/temporary-license/).
3. **購買**：對於商業用途，請從 [Aspose 網站](https://purchase。aspose.com/buy).

安裝並獲得許可後，在您的專案中初始化 Aspose.Slides：
```csharp
using Aspose.Slides;

// 初始化 Aspose.Slides for .NET
var presentation = new Presentation();
```

## 實施指南

### 建立新的簡報並新增圓環圖

#### 概述
我們將首先建立一個新的演示文稿，並在第一張投影片中新增一個圓環圖。本節介紹如何載入現有簡報、存取投影片以及插入圖表。

**步驟 1：載入或建立簡報**
首先，指定您的文件目錄並載入現有的簡報：
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
如果您沒有現有文件，請使用以下命令建立新文件 `new Presentation()`。

**第 2 步：存取第一張投影片**
進入第一張投影片，我們將在其中添加圖表：
```csharp
ISlide slide = pres.Slides[0];
```

**步驟 3：新增圓環圖**
在指定的座標和尺寸處新增一個圓環圖：
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 配置數據工作簿

#### 概述
本節介紹如何設定與圓環圖相關的資料工作簿。

**步驟 4：存取並清除現有數據**
存取圖表的資料工作簿。然後清除所有現有的系列或類別：
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**步驟 5：停用圖例並新增系列**
停用圖例以保持圖表整潔，然後使用自訂配置新增最多 15 個系列：
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### 新增類別和數據點

#### 概述
現在，讓我們用每個系列的類別和資料點填入圖表。

**步驟 6：新增類別**
循環新增 15 個類別：
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**步驟 7：填充數據點**
為目前類別中的每個系列新增資料點：
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // 自訂外觀
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // 配置最後一個系列的標籤格式
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // 配置標籤顯示
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### 儲存簡報

**步驟8：儲存文件**
最後，將您的簡報儲存到指定目錄：
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}