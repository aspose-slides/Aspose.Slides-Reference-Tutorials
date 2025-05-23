---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides 在 .NET 簡報中自動建立圓餅圖，輕鬆增強資料視覺化。"
"title": "如何使用 Aspose.Slides 在 .NET 簡報中建立和自訂圓餅圖"
"url": "/zh-hant/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides 在 .NET 簡報中建立和自訂圓餅圖

## 介紹
無論您是在工作中展示數據還是展示最新的專案成果，創建引人入勝且資訊豐富的簡報對於有效溝通都至關重要。可視化資料的一個有效方法是透過圓餅圖，它可以簡潔地表示整體的各個部分。然而，在 PowerPoint 等簡報軟體中手動製作這些圖表可能非常耗時，並且可能缺乏動態更新所需的靈活性。

這就是 Aspose.Slides for .NET 發揮作用的地方。這個綜合庫允許您以程式設計方式建立、修改和設計演示文稿，對於想要自動化工作流程並確保簡報一致性的開發人員來說，它是一個非常寶貴的工具。

在本教學中，我們將探討如何使用 Aspose.Slides for .NET 在簡報中建立和自訂圓餅圖。您將學習如何：
- **建立簡報並存取幻燈片**
- **新增和配置餅圖**
- **自訂圖表資料和系列**
- **圓餅圖扇區樣式**
- **新增自訂標籤**
- **配置顯示屬性並儲存簡報**

準備好輕鬆創建令人驚嘆的餅圖了嗎？讓我們開始吧！

## 先決條件
在開始之前，請確保您已完成以下設定：

### 所需庫
- Aspose.Slides for .NET（建議使用 21.11 或更高版本）

### 環境設定
- 執行 .NET Framework 或 .NET Core/5+/6+ 的開發環境
- 程式碼編輯器（例如 Visual Studio）

### 知識前提
- 對 C# 程式設計有基本的了解
- 熟悉物件導向的概念

## 設定 Aspose.Slides for .NET
首先，您需要安裝 Aspose.Slides 函式庫。您可以使用下列任一方法來執行此操作：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**套件管理器控制台**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI**
- 在 Visual Studio 中開啟您的專案。
- 前往「工具」>「NuGet 套件管理器」>「管理解決方案的 NuGet 套件」。
- 搜尋“Aspose.Slides”並安裝最新版本。

### 許可證取得步驟
若要使用 Aspose.Slides，您可以下載臨時授權開始免費試用。訪問 [Aspose的網站](https://purchase.aspose.com/temporary-license/) 來獲得它。為了持續使用，請考慮購買完整許可證。

### 基本初始化和設定
安裝後，初始化代表您的 PPTX 檔案的 Presentation 類別：

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## 實施指南
我們將把餅圖創建過程分解為易於管理的部分。每個部分都專注於一個特定的功能，讓您逐步累積知識。

### 建立簡報並存取幻燈片
**概述：** 首先建立一個新的簡報並存取其第一張投影片。這為添加圖表和其他元素奠定了基礎。

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // 實例化代表 PPTX 檔案的 Presentation 類
    Presentation presentation = new Presentation();
    
    // 存取第一張投影片
    ISlide slides = presentation.Slides[0];
}
```

### 新增並配置餅圖
**概述：** 了解如何在幻燈片中添加餅圖並設定其標題以作為上下文。

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // 實例化代表 PPTX 檔案的 Presentation 類
    Presentation presentation = new Presentation();
    
    // 存取第一張投影片
    ISlide slides = presentation.Slides[0];
    
    // 將帶有預設資料的圖表新增至幻燈片
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 設定圖表標題
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### 自訂圖表資料和系列
**概述：** 自訂資料類別和系列以滿足您的特定要求。

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // 實例化代表 PPTX 檔案的 Presentation 類
    Presentation presentation = new Presentation();
    
    // 存取第一張投影片
    ISlide slides = presentation.Slides[0];
    
    // 將帶有預設資料的圖表新增至幻燈片
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 將第一個系列設定為顯示值
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // 設定圖表資料表的索引
    int defaultWorksheetIndex = 0;
    
    // 取得圖表資料工作表
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // 刪除預設產生的系列和類別
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // 新增類別
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // 新增系列
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // 現在填充系列數據
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### 自訂圓餅圖扇區樣式
**概述：** 設定餅圖各個部分的樣式以增強視覺吸引力並強調關鍵數據點。

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // 實例化代表 PPTX 檔案的 Presentation 類
    Presentation presentation = new Presentation();
    
    // 存取第一張投影片
    ISlide slides = presentation.Slides[0];
    
    // 將帶有預設資料的圖表新增至幻燈片
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 從圖表中取得系列
    IChartSeries series = chart.ChartData.Series[0];
    
    // 為系列中的每個資料點自訂磁區樣式
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // 設定扇區邊界
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // 設定扇區邊界
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // 設定扇區邊界
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### 在圓餅圖新增自訂標籤
**概述：** 透過新增自訂標籤來增強圓餅圖，以便更清晰地表示資料。

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // 根據需要調整標籤位置
    }
}
```

### 結論
現在您已經了解如何使用 Aspose.Slides 在 .NET 簡報中建立和自訂圓餅圖。這種自動化可以顯著增強您的資料視覺化效果，節省時間並確保簡報的一致性。

為了進一步探索 Aspose.Slides for .NET 的功能，請考慮深入了解其他功能，例如建立其他圖表類型或將更複雜的設計元素整合到投影片中。

編碼愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}