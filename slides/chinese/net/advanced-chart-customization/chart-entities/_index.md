---
"description": "学习如何使用 Aspose.Slides for .NET 创建精美的图表。遵循我们的分步指南，提升您的数据可视化水平。"
"linktitle": "图表实体和格式"
"second_title": "Aspose.Slides .NET PowerPoint 处理 API"
"title": "使用 Aspose.Slides for .NET 创建漂亮的图表"
"url": "/zh/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Slides for .NET 创建漂亮的图表


在当今数据驱动的世界中，有效的数据可视化是向受众传达信息的关键。Aspose.Slides for .NET 是一个功能强大的库，可帮助您创建令人惊叹的演示文稿和幻灯片，包括引人注目的图表。在本教程中，我们将引导您完成使用 Aspose.Slides for .NET 创建精美图表的过程。我们将每个示例分解为多个步骤，以帮助您理解和实现图表实体和格式。那么，让我们开始吧！

## 先决条件

在我们深入使用 Aspose.Slides for .NET 创建漂亮的图表之前，您需要确保满足以下先决条件：

1. Aspose.Slides for .NET：请确保您已安装 Aspose.Slides for .NET 库。您可以从 [网站](https://releases。aspose.com/slides/net/).

2. 开发环境：您应该有一个带有 Visual Studio 或任何其他支持 .NET 开发的 IDE 的工作开发环境。

3. 基本 C# 知识：熟悉 C# 编程对于本教程至关重要。

现在我们已经满足了先决条件，让我们继续使用 Aspose.Slides for .NET 创建漂亮的图表。

## 导入命名空间

首先，您需要导入必要的命名空间才能使用 Aspose.Slides for .NET：

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## 步骤 1：创建演示文稿

我们首先创建一个新的演示文稿。该演示文稿将作为我们图表的画布。

```csharp
// 文档目录的路径。
string dataDir = "Your Document Directory";

// 如果目录尚不存在，则创建该目录。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// 实例化演示
Presentation pres = new Presentation();
```

## 第 2 步：访问第一张幻灯片

让我们进入演示文稿中的第一张幻灯片，我们将在其中放置图表。

```csharp
// 访问第一张幻灯片
ISlide slide = pres.Slides[0];
```

## 步骤 3：添加示例图表

现在，我们将在幻灯片中添加一个示例图表。在本例中，我们将创建一个带有标记的折线图。

```csharp
// 添加示例图表
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 步骤4：设置图表标题

我们将为图表添加标题，使其更具信息量和视觉吸引力。

```csharp
// 设置图表标题
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## 步骤5：自定义垂直轴网格线

在此步骤中，我们将自定义垂直轴网格线，以使我们的图表更具视觉吸引力。

```csharp
// 设置数值轴的主要网格线格式
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// 设置数值轴的次要网格线格式
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// 设定值轴编号格式
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## 步骤 6：定义垂直轴范围

在此步骤中，我们将设置垂直轴的最大值、最小值和单位值。

```csharp
// 设置图表最大值、最小值
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## 步骤 7：自定义垂直轴文本

我们现在将自定义垂直轴上文本的外观。

```csharp
// 设置数值轴文本属性
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// 设置数值轴标题
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## 步骤 8：自定义横轴网格线

现在，让我们自定义水平轴的网格线。

```csharp
// 设置分类轴的主要网格线格式
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// 设置分类轴的次要网格线格式
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// 设置分类轴文本属性
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## 步骤9：自定义水平轴标签

在此步骤中，我们将调整水平轴标签的位置和旋转。

```csharp
// 设置分类轴标签位置
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// 设置分类轴标签旋转角度
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## 步骤 10：自定义图例

让我们增强图表中的图例以提高可读性。

```csharp
// 设置图例文本属性
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// 设置显示不重叠图表的图表图例
chart.Legend.Overlay = true;
```

## 步骤11：自定义图表背景

我们将定制图表、后墙和地板的背景颜色。

```csharp
// 设置图表背景墙颜色
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// 设置绘图区域颜色
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## 步骤 12：保存演示文稿

最后，让我们将带有格式化的图表保存到演示文稿中。

```csharp
// 保存演示文稿
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## 结论

现在，使用 Aspose.Slides for .NET，在演示文稿中创建美观且信息丰富的图表比以往任何时候都更加轻松。在本教程中，我们介绍了自定义图表各个方面的基本步骤，使其更具视觉吸引力并信息丰富。借助这些技巧，您可以创建令人惊叹的图表，有效地向受众传达数据。

开始尝试使用 Aspose.Slides for .NET 并将您的数据可视化提升到一个新的水平！

## 常见问题

### 1.什么是 Aspose.Slides for .NET？

Aspose.Slides for .NET 是一个功能强大的库，允许 .NET 开发人员创建、操作和转换 Microsoft PowerPoint 演示文稿。它提供了丰富的功能，可用于处理幻灯片、形状、图表等。

### 2. 在哪里可以下载 Aspose.Slides for .NET？

您可以从网站下载 Aspose.Slides for .NET [这里](https://releases。aspose.com/slides/net/).

### 3. Aspose.Slides for .NET 有免费试用版吗？

是的，您可以从以下位置免费试用 Aspose.Slides for .NET [这里](https://releases。aspose.com/).

### 4. 如何获得 Aspose.Slides for .NET 的临时许可证？

如果您需要临时驾照，可以从 [此链接](https://purchase。aspose.com/temporary-license/).

### 5. Aspose.Slides for .NET 有社区或支持论坛吗？

是的，您可以找到 Aspose.Slides 社区和支持论坛 [这里](https://forum。aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}