---
title: 从图表恢复工作簿
linktitle: 从图表恢复工作簿
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for .NET 从图表中恢复工作簿。以编程方式提取图表数据并创建 Excel 工作簿。
type: docs
weight: 12
url: /zh/net/additional-chart-features/chart-recover-workbook/
---

## 介绍

意外可能会发生，您可能会发现自己需要从图表中恢复工作簿。 Aspose.Slides for .NET 在这种情况下可以发挥作用。这个功能强大的库允许您从演示文稿中的图表中提取数据并将其转换为新的工作簿。在本分步指南中，我们将引导您完成使用 Aspose.Slides for .NET 从图表中恢复工作簿的过程。

## 先决条件

在开始之前，请确保您已具备以下条件：

- Visual Studio：下载并安装 Visual Studio，这对于 .NET 开发至关重要。
-  Aspose.Slides for .NET：您可以从以下位置下载该库：[这里](https://downloads.aspose.com/slides/net).

## 第 1 步：安装 Aspose.Slides for .NET

如果您尚未安装，请下载并安装 Aspose.Slides for .NET。该库提供了以编程方式处理 PowerPoint 演示文稿的全面功能。

## 第 2 步：加载演示文稿

首先，在 Visual Studio 中创建一个新的 C# 项目。添加对必要的 Aspose.Slides 程序集的引用。加载包含要从中恢复数据的图表的 PowerPoint 演示文稿。

```csharp
//加载演示文稿
Presentation presentation = new Presentation("your-presentation.pptx");
```

## 第 3 步：识别图表

确定要从中恢复数据的幻灯片和图表。您可以使用以下方式访问幻灯片`presentation.Slides`使用集合和图表`slide.Shapes`收藏。

```csharp
//获取包含图表的幻灯片
ISlide slide = presentation.Slides[0];

//获取图表
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## 第 4 步：从图表中提取数据

使用 Aspose.Slides 的 API 从图表中提取数据。您可以从图表系列和类别中检索值。

```csharp
//提取图表数据
IChartData chartData = chart.ChartData;
```

## 第 5 步：创建新工作簿

使用 EPPlus 或 ClosedXML 等库创建新的 Excel 工作簿。

```csharp
//创建新的 Excel 工作簿
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    //在此处添加代码以填充工作表标题
}
```

## 第 6 步：使用图表数据填充工作簿

使用从图表中提取的数据填充 Excel 工作表。

```csharp
//使用图表数据填充 Excel 工作表
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    //在此处添加代码以使用系列数据填充工作表
    rowIndex++;
}
```

## 第 7 步：保存工作簿

保存包含恢复的图表数据的 Excel 工作簿。

```csharp
//保存 Excel 工作簿
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## 结论

使用 Aspose.Slides for .NET 可以轻松地从图表中恢复工作簿。通过执行以下步骤，您可以以编程方式从 PowerPoint 演示文稿中的图表中提取数据，并使用恢复的数据创建新的 Excel 工作簿。当发生事故并且需要抢救数据时，此过程可以成为救星。

## 常见问题解答

### 如何安装 Aspose.Slides for .NET？

您可以从以下位置下载 Aspose.Slides for .NET[这里](https://downloads.aspose.com/slides/net).

### 我可以从不同类型的图表中恢复数据吗？

是的，Aspose.Slides for .NET 支持各种图表类型，包括条形图、折线图、饼图等。

### Aspose.Slides for .NET 适合专业用途吗？

绝对地！ Aspose.Slides for .NET 是一个强大的库，开发人员可以使用它来高效地处理 PowerPoint 演示文稿。

### 使用 Aspose.Slides for .NET 有任何许可要求吗？

是的，Aspose.Slides for .NET 需要有效的商业用途许可证。您可以在以下位置找到许可详细信息[阿斯普斯网站](https://purchase.aspose.com).

### 我可以自定义恢复的 Excel 工作簿的外观吗？

是的，您可以使用 EPPlus 或 ClosedXML 等库自定义 Excel 工作簿的外观和格式。