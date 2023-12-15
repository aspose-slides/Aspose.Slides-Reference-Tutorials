---
title: 在 Aspose.Slides .NET 中的数据点上使用图表标记选项
linktitle: 数据点上的图表标记选项
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for .NET 增强 PowerPoint 图表。使用图像自定义数据点标记。创建引人入胜的演示文稿。
type: docs
weight: 11
url: /zh/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

在处理演示和数据可视化时，Aspose.Slides for .NET 提供了广泛的强大功能来创建、自定义和操作图表。在本教程中，我们将探讨如何在数据点上使用图表标记选项来增强图表演示。本分步指南将引导您完成整个过程，从先决条件和导入命名空间开始，到将每个示例分解为多个步骤。

## 先决条件

在我们深入研究在数据点上使用图表标记选项之前，请确保您具备以下先决条件：

-  Aspose.Slides for .NET：确保您已安装 Aspose.Slides for .NET。您可以从[网站](https://releases.aspose.com/slides/net/).

- 示例演示文稿：在本教程中，我们将使用名为“Test.pptx”的示例演示文稿。您应该将此演示文稿放在您的文档目录中。

现在，我们首先导入必要的命名空间。

## 导入命名空间

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

我们已经导入了所需的命名空间并初始化了我们的演示文稿。现在，让我们继续在数据点上使用图表标记选项。

## 第 1 步：创建默认图表

```csharp

//文档目录的路径。
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//创建默认图表
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

我们在幻灯片上的指定位置和大小处创建一个“LineWithMarkers”类型的默认图表。

## 第2步：获取默认图表数据工作表索引

```csharp
//获取默认图表数据工作表索引
int defaultWorksheetIndex = 0;
```

在这里，我们获取默认图表数据工作表的索引。

## 第 3 步：获取图表数据工作表

```csharp
//获取图表数据工作表
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

我们获取图表数据工作簿来处理图表数据。

## 步骤 4：修改图表系列

```csharp
//删除演示系列
chart.ChartData.Series.Clear();

//添加新系列
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

在此步骤中，我们删除任何现有的演示系列并向图表添加一个名为“Series 1”的新系列。

## 第5步：设置数据点的图片填充

```csharp
//设置标记的图片
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

//获取第一个图表系列
IChartSeries series = chart.ChartData.Series[0];

//添加带有图片填充的新数据点
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

我们为数据点设置图片标记，允许您自定义每个数据点在图表上的显示方式。

## 步骤 6：更改图表系列标记大小

```csharp
//更改图表系列标记大小
series.Marker.Size = 15;
```

在这里，我们调整图表系列标记的大小，使其具有视觉吸引力。

## 第 7 步：保存演示文稿

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

最后，我们使用新的图表设置保存演示文稿。

## 结论

Aspose.Slides for .NET 使您能够使用各种自定义选项创建令人惊叹的图表演示文稿。在本教程中，我们重点关注在数据点上使用图表标记选项来增强数据的视觉表示。借助 Aspose.Slides for .NET，您可以将演示文稿提升到一个新的水平，使其更具吸引力和信息量。

如果您对 Aspose.Slides for .NET 有任何疑问或需要帮助，请随时访问[Aspose.Slides 文档](https://reference.aspose.com/slides/net/)或联系[Aspose社区](https://forum.aspose.com/)为了支持。

## 常见问题 (FAQ)

### 我可以使用自定义图像作为 Aspose.Slides for .NET 中数据点的标记吗？
是的，您可以使用自定义图像作为 Aspose.Slides for .NET 中数据点的标记，如本教程中所示。

### 如何更改 Aspose.Slides for .NET 中的图表类型？
您可以通过指定不同的图表类型来更改图表类型`ChartType`创建图表时，例如“条形图”、“饼图”或“面积图”。

### Aspose.Slides for .NET 与最新版本的 PowerPoint 兼容吗？
Aspose.Slides for .NET 设计用于处理各种 PowerPoint 格式，并定期更新以保持与最新 PowerPoint 版本的兼容性。

### 在哪里可以找到有关 Aspose.Slides for .NET 的更多教程和资源？
您可以在以下位置探索其他教程和资源[Aspose.Slides 文档](https://reference.aspose.com/slides/net/).

### 是否有 Aspose.Slides for .NET 的试用版？
是的，您可以通过下载免费试用版来尝试 Aspose.Slides for .NET[这里](https://releases.aspose.com/).