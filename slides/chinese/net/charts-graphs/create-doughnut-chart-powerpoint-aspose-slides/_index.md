---
"date": "2025-04-15"
"description": "了解如何使用强大的 Aspose.Slides for .NET 库在 PowerPoint 演示文稿中创建动态且具有视觉吸引力的圆环图。"
"title": "如何使用 Aspose.Slides for .NET 在 PowerPoint 中创建圆环图"
"url": "/zh/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 在 PowerPoint 中创建圆环图
创建视觉上引人入胜的图表对于有效呈现数据至关重要。圆环图非常适合展示整体的各个部分，因此非常适合基于百分比的数据可视化。本教程将指导您使用强大的 Aspose.Slides for .NET 库在 PowerPoint 中创建动态圆环图。

## 介绍
演示文稿通常需要以可视化的方式呈现复杂的数据集，而传统的条形图或折线图可能无法满足需求。环形图作为一种多功能工具，能够以时尚清晰的方式有效传达基于百分比的数据。在本教程中，我们将探索 Aspose.Slides for .NET 如何简化在 PowerPoint 中直接创建这些图表的过程。

**您将学到什么：**
- 设置 Aspose.Slides for .NET
- 创建圆环图的分步说明
- 向图表添加系列和类别
- 配置数据标签以增强清晰度
- 保存最终演示文稿

让我们深入了解如何利用 Aspose.Slides for .NET 通过自定义环形图增强您的演示文稿。

## 先决条件
在开始之前，请确保您已准备好以下事项：
- **Aspose.Slides for .NET 库**：可通过 NuGet 或直接下载获得。
- **开发环境**：建议使用 Visual Studio 来开发 .NET 项目。
- 具备 C# 基础知识并熟悉 PowerPoint 的结构。

## 设置 Aspose.Slides for .NET
要开始创建图表，首先需要在项目中设置 Aspose.Slides 库。以下是几种安装方法：

**使用 .NET CLI：**

```bash
dotnet add package Aspose.Slides
```

**使用包管理器控制台：**

```powershell
Install-Package Aspose.Slides
```

**通过 NuGet 包管理器 UI：**
搜索“Aspose.Slides”并安装最新版本。

安装完成后，您就可以开始设置项目了。如果您是 Aspose.Slides 的新用户，可以考虑获取临时许可证或免费试用版，以不受限制地探索其全部功能。

### 初始化你的项目
以下是如何在应用程序中初始化 Aspose.Slides：

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // 创建 Presentation 类的实例
        Presentation presentation = new Presentation();
        
        // 用于操作演示文稿的代码放在这里
        
        // 保存演示文稿
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## 实施指南
### 创建圆环图
#### 概述
首先，我们将在 PowerPoint 幻灯片中创建一个空的圆环图。这将作为添加数据和自定义其外观的基础。

**步骤 1：添加圆环图**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // 在第一张幻灯片中，位置 (10, 10) 处添加一个圆环图，大小为 (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // 清除现有系列和类别
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // 禁用图例以获得更清晰的外观
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**解释：**
- **添加图表**：在幻灯片上插入新的圆环图。
- **获取图表数据工作簿**：提供对图表中数据单元的访问以进行操作。

### 添加系列和类别
#### 概述
接下来，我们将通过添加系列和类别来填充有意义的数据到您的图表中。

**步骤 2：添加数据系列**

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

        // 添加系列
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // 自定义甜甜圈孔和起始角度
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // 添加类别
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

                // 格式化数据点的填充和线条
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

**解释：**
- **添加**：将新的系列和类别插入图表中。
- **设置甜甜圈洞大小**：配置甜甜圈孔的大小，增强其视觉吸引力。

### 配置数据标签
#### 概述
数据标签为您的图表数据提供上下文。让我们通过自定义标签来增强可读性。

**步骤3：自定义数据标签**

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

                // 自定义数据标签
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

**解释：**
- **数据标签**：自定义数据标签，以提高清晰度和呈现效果。
- **设置中心文本**， **显示百分比**：通过居中文本和显示百分比来增强标签的可读性。

## 结论
通过本指南，您学习了如何使用 Aspose.Slides for .NET 在 PowerPoint 中创建动态圆环图。这个强大的库支持广泛的自定义功能，使您能够根据演示需求精确定制图表。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}