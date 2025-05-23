---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides 在 .NET 演示文稿中自动创建饼图，轻松增强数据可视化。"
"title": "如何使用 Aspose.Slides 在 .NET 演示文稿中创建和自定义饼图"
"url": "/zh/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides 在 .NET 演示文稿中创建和自定义饼图

## 介绍
无论您是在工作中展示数据，还是展示最新的项目成果，创建引人入胜且信息丰富的演示文稿对于有效沟通都至关重要。饼图是可视化数据的有效方法之一，它可以简洁地呈现整体的各个部分。然而，在 PowerPoint 等演示软件中手动制作这些图表可能非常耗时，并且可能缺乏动态更新所需的灵活性。

这就是 Aspose.Slides for .NET 发挥作用的地方。这个功能全面的库允许您以编程方式创建、修改和设置演示文稿的样式，对于希望自动化工作流程并确保演示文稿一致性的开发人员来说，它是一个非常宝贵的工具。

在本教程中，我们将探索如何使用 Aspose.Slides for .NET 在演示文稿中创建和自定义饼图。您将学习如何：
- **创建演示文稿并访问幻灯片**
- **添加和配置饼图**
- **自定义图表数据和系列**
- **饼图扇区样式**
- **添加自定义标签**
- **配置显示属性并保存演示文稿**

准备好轻松创建精美的饼图了吗？让我们开始吧！

## 先决条件
在开始之前，请确保您已完成以下设置：

### 所需库
- Aspose.Slides for .NET（建议使用 21.11 或更高版本）

### 环境设置
- 运行 .NET Framework 或 .NET Core/5+/6+ 的开发环境
- 代码编辑器（例如 Visual Studio）

### 知识前提
- 对 C# 编程有基本的了解
- 熟悉面向对象的概念

## 设置 Aspose.Slides for .NET
首先，您需要安装 Aspose.Slides 库。您可以使用以下任一方法安装：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**程序包管理器控制台**
```powershell
Install-Package Aspose.Slides
```

**NuGet 包管理器 UI**
- 在 Visual Studio 中打开您的项目。
- 转到“工具”>“NuGet 包管理器”>“管理解决方案的 NuGet 包”。
- 搜索“Aspose.Slides”并安装最新版本。

### 许可证获取步骤
要使用 Aspose.Slides，您可以下载临时许可证，开始免费试用。访问 [Aspose的网站](https://purchase.aspose.com/temporary-license/) 获取它。如需持续使用，请考虑购买完整许可证。

### 基本初始化和设置
安装后，初始化代表您的 PPTX 文件的 Presentation 类：

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## 实施指南
我们将把饼图的创建过程分解成几个易于理解的部分。每个部分都侧重于一个特定的功能，以便您逐步积累知识。

### 创建演示文稿并访问幻灯片
**概述：** 首先创建一个新的演示文稿并访问其第一张幻灯片。这为添加图表和其他元素奠定了基础。

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // 实例化代表 PPTX 文件的 Presentation 类
    Presentation presentation = new Presentation();
    
    // 访问第一张幻灯片
    ISlide slides = presentation.Slides[0];
}
```

### 添加并配置饼图
**概述：** 了解如何在幻灯片中添加饼图并设置其标题以作为上下文。

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // 实例化代表 PPTX 文件的 Presentation 类
    Presentation presentation = new Presentation();
    
    // 访问第一张幻灯片
    ISlide slides = presentation.Slides[0];
    
    // 将带有默认数据的图表添加到幻灯片
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 设置图表标题
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### 自定义图表数据和系列
**概述：** 自定义数据类别和系列以满足您的特定要求。

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // 实例化代表 PPTX 文件的 Presentation 类
    Presentation presentation = new Presentation();
    
    // 访问第一张幻灯片
    ISlide slides = presentation.Slides[0];
    
    // 将带有默认数据的图表添加到幻灯片
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 将第一个系列设置为显示值
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // 设置图表数据表的索引
    int defaultWorksheetIndex = 0;
    
    // 获取图表数据工作表
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // 删除默认生成的系列和类别
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // 添加新类别
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // 添加新系列
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // 现在填充系列数据
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### 自定义饼图扇区样式
**概述：** 设置饼图各个部分的样式以增强视觉吸引力并强调关键数据点。

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // 实例化代表 PPTX 文件的 Presentation 类
    Presentation presentation = new Presentation();
    
    // 访问第一张幻灯片
    ISlide slides = presentation.Slides[0];
    
    // 将带有默认数据的图表添加到幻灯片
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 从图表中获取系列
    IChartSeries series = chart.ChartData.Series[0];
    
    // 为系列中的每个数据点自定义扇区样式
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // 设置扇区边界
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // 设置扇区边界
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // 设置扇区边界
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### 向饼图添加自定义标签
**概述：** 通过添加自定义标签来增强饼图，以便更清晰地表示数据。

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // 根据需要调整标签位置
    }
}
```

### 结论
现在您已经学习了如何使用 Aspose.Slides 在 .NET 演示文稿中创建和自定义饼图。这种自动化功能可以显著增强您的数据可视化效果，节省时间并确保演示文稿的一致性。

为了进一步探索 Aspose.Slides for .NET 的功能，请考虑深入了解其他功能，例如创建其他图表类型或将更复杂的设计元素集成到幻灯片中。

编码愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}