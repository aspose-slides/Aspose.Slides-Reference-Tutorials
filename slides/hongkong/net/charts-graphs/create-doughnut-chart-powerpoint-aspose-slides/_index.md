---
"date": "2025-04-15"
"description": "了解如何使用強大的 Aspose.Slides for .NET 程式庫在 PowerPoint 簡報中建立動態且具有視覺吸引力的圓環圖。"
"title": "如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立圓環圖"
"url": "/zh-hant/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立圓環圖
創建視覺上引人入勝的圖表對於有效的數據呈現至關重要。環形圖非常適合展示整體的各個部分，使其成為基於百分比的資料視覺化的理想選擇。本教學將引導您使用強大的 Aspose.Slides for .NET 函式庫在 PowerPoint 中建立動態圓環圖。

## 介紹
演示通常需要以視覺方式呈現複雜的資料集，而傳統的長條圖或折線圖可能無法滿足需求。環形圖是一種多功能工具，可以有效、清楚地傳達基於百分比的數據。在本教學中，我們將探討 Aspose.Slides for .NET 如何簡化在 PowerPoint 中直接建立這些圖表的過程。

**您將學到什麼：**
- 設定 Aspose.Slides for .NET
- 建立圓環圖的逐步說明
- 在圖表中新增系列和類別
- 配置資料標籤以增強清晰度
- 儲存最終簡報

讓我們深入了解如何利用 Aspose.Slides for .NET 透過自訂環形圖增強您的簡報。

## 先決條件
在開始之前，請確保您已準備好以下事項：
- **Aspose.Slides for .NET 函式庫**：可透過 NuGet 或直接下載取得。
- **開發環境**：建議使用 Visual Studio 來開發 .NET 專案。
- 具備 C# 基礎並熟悉 PowerPoint 的架構。

## 設定 Aspose.Slides for .NET
要開始建立圖表，首先需要在專案中設定 Aspose.Slides 庫。以下是幾種安裝方法：

**使用 .NET CLI：**

```bash
dotnet add package Aspose.Slides
```

**使用套件管理器控制台：**

```powershell
Install-Package Aspose.Slides
```

**透過 NuGet 套件管理器 UI：**
搜尋“Aspose.Slides”並安裝最新版本。

安裝完成後，您就可以開始設定您的專案。如果您是 Aspose.Slides 的新用戶，請考慮取得臨時授權或免費試用版，以不受限制地探索其全部功能。

### 初始化你的項目
以下是如何在應用程式中初始化 Aspose.Slides：

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // 建立 Presentation 類別的實例
        Presentation presentation = new Presentation();
        
        // 用於操作簡報的程式碼放在這裡
        
        // 儲存簡報
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## 實施指南
### 建立圓環圖
#### 概述
首先，我們將在 PowerPoint 投影片中建立一個空的圓環圖。這是添加數據和自訂其外觀的基礎。

**步驟 1：新增圓環圖**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // 在第一張投影片中，位置 (10, 10) 處增加一個圓環圖，大小為 (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // 清除現有系列和類別
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // 禁用圖例以獲得更清晰的外觀
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**解釋：**
- **新增圖表**：在投影片上插入新的圓環圖。
- **取得圖表數據工作簿**：提供對圖表中資料單元的存取以進行操作。

### 新增系列和類別
#### 概述
接下來，我們將透過新增系列和類別來填充有意義的資料到您的圖表中。

**步驟 2：新增資料系列**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // 新增系列
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // 自訂甜甜圈孔和起始角度
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // 新增類別
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // 格式化資料點的填滿和線條
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**解釋：**
- **添加**：將新的系列和類別插入圖表中。
- **設定甜甜圈洞大小**：配置甜甜圈孔的大小，增強其視覺吸引力。

### 配置資料標籤
#### 概述
數據標籤為圖表數據提供背景。讓我們透過自訂來增強可讀性。

**步驟3：自訂資料標籤**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // 自訂資料標籤
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**解釋：**
- **數據標籤**：自訂資料標籤，以提高清晰度和呈現效果。
- **設定中心文本**， **顯示百分比**：透過居中文字和顯示百分比來增強標籤的可讀性。

## 結論
透過遵循本指南，您已經學習如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立動態圓環圖。這個強大的庫允許進行廣泛的自定義，使您能夠根據演示需求精確地定製圖表。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}