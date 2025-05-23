---
"date": "2025-04-15"
"description": "学习如何使用 Aspose.Slides for .NET 创建动态圆环图。请按照本指南获取分步说明，包括设置和高级功能。"
"title": "分步指南&#58;使用 Aspose.Slides .NET 创建甜甜圈图 | 图表和图形"
"url": "/zh/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 分步指南：使用 Aspose.Slides .NET 创建甜甜圈图

## 介绍

想象一下，您需要向团队或客户展示数据分析结果，并且需要一种引人入胜的方式来可视化这些信息。这时，圆环图就派上用场了——它是一款多功能工具，可以将原始数据转化为易于理解的见解。使用 Aspose.Slides for .NET，在演示文稿幻灯片中创建自定义圆环图变得简单高效。本指南将指导您使用 Aspose.Slides 创建视觉上引人入胜的圆环图，并完成定制的系列配置。

**您将学到什么：**
- 使用 Aspose.Slides for .NET 设置您的开发环境
- 在演示文稿中创建和自定义圆环图
- 实现类别名称和引导线等高级功能
- 优化大型数据集的性能

让我们深入了解您开始所需的先决条件。

## 先决条件

在实现此功能之前，请确保您的开发环境已正确设置。本教程假设您具备 .NET 编程的基础知识，并熟悉 Visual Studio 或类似的 IDE。

### 所需的库和版本
- **Aspose.Slides for .NET**：通过检查其是否与最新版本兼容 [官方文档](https://reference。aspose.com/slides/net/).

### 环境设置要求
- 一个有效的 .NET 环境。
- 访问代码编辑器，例如 Visual Studio。

### 知识前提
- 对 C# 和 .NET 框架有基本的了解。
- 熟悉演示软件概念（可选但有帮助）。

## 设置 Aspose.Slides for .NET

要在您的项目中开始使用 Aspose.Slides，您需要通过 NuGet 安装它。以下是可用的方法：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**使用包管理器：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 包管理器 UI：**
搜索“Aspose.Slides”并安装最新版本。

### 许可证获取步骤

1. **免费试用**：从 [免费试用](https://releases.aspose.com/slides/net/) 探索基本功能。
2. **临时执照**：如果您需要访问完整功能进行评估，请访问以下网址获取临时许可证 [这里](https://purchase。aspose.com/temporary-license/).
3. **购买**：对于商业用途，请从 [Aspose 网站](https://purchase。aspose.com/buy).

安装并获得许可后，在您的项目中初始化 Aspose.Slides：
```csharp
using Aspose.Slides;

// 初始化 Aspose.Slides for .NET
var presentation = new Presentation();
```

## 实施指南

### 创建新的演示文稿并添加圆环图

#### 概述
我们将首先创建一个新的演示文稿，并在第一张幻灯片中添加一个圆环图。本节介绍如何加载现有演示文稿、访问幻灯片以及插入图表。

**步骤 1：加载或创建演示文稿**
首先，指定您的文档目录并加载现有的演示文稿：
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
如果您没有现有文件，请使用以下命令创建一个新文件 `new Presentation()`。

**第 2 步：访问第一张幻灯片**
进入第一张幻灯片，我们将在其中添加图表：
```csharp
ISlide slide = pres.Slides[0];
```

**步骤 3：添加圆环图**
在指定的坐标和尺寸处添加一个圆环图：
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 配置数据工作簿

#### 概述
本节介绍如何配置与圆环图相关的数据工作簿。

**步骤 4：访问并清除现有数据**
访问图表的数据工作簿。然后清除所有现有系列或类别：
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**步骤 5：禁用图例并添加系列**
禁用图例以保持图表整洁，然后使用自定义配置添加最多 15 个系列：
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

### 添加类别和数据点

#### 概述
现在，让我们用每个系列的类别和数据点填充图表。

**步骤 6：添加类别**
循环添加 15 个类别：
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**步骤 7：填充数据点**
为当前类别中的每个系列添加数据点：
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // 自定义外观
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // 配置最后一个系列的标签格式
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

        // 配置标签显示
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

### 保存演示文稿

**步骤8：保存文件**
最后，将您的演示文稿保存到指定目录：
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}