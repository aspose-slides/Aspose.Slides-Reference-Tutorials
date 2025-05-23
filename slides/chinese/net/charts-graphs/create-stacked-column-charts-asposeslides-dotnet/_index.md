---
"date": "2025-04-15"
"description": "学习如何使用 Aspose.Slides for .NET 创建视觉效果出色、基于百分比的堆叠柱形图。按照本分步指南，实现清晰的数据可视化。"
"title": "如何使用 Aspose.Slides 在 .NET 中创建基于百分比的堆积柱形图"
"url": "/zh/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 创建基于百分比的堆积柱形图

## 介绍

在数据可视化领域，清晰有效地呈现信息对于做出有影响力的决策至关重要。为了直观地显示复杂的数据集，基于百分比的堆积柱形图是理想之选。本指南将指导您使用 Aspose.Slides for .NET（一个专为处理演示文稿文件而设计的强大库）创建此类图表。

通过学习本教程，您将了解：
- 设置图表数据并配置数字格式。
- 添加系列并自定义其外观。
- 格式化标签以增强可读性。

准备好了吗？让我们先了解一下您需要满足的先决条件！

## 先决条件

在创建基于百分比的堆积柱形图之前，请确保您的环境已正确设置。您将需要：

### 所需的库、版本和依赖项
- **Aspose.Slides for .NET**：确保此库已安装。

### 环境设置要求
- 安装了 .NET SDK 的开发环境。
- Visual Studio 或任何用于运行 C# 代码的兼容 IDE。

### 知识前提
- 对 C# 编程有基本的了解。
- 熟悉.NET项目设置和包管理。

## 设置 Aspose.Slides for .NET

要开始使用 Aspose.Slides 创建图表，请首先使用以下方法之一安装库：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**包管理器**
```powershell
Install-Package Aspose.Slides
```

**NuGet 包管理器 UI**
- 搜索“Aspose.Slides”并安装最新版本。

### 许可证获取步骤

下载临时许可证即可开始免费试用 [Aspose的网站](https://purchase.aspose.com/temporary-license/)。为了继续使用，请考虑购买完整许可证。 

设置完成后，在您的项目中启动 Aspose.Slides：
```csharp
using Aspose.Slides;
```

## 实施指南

环境准备好后，让我们将创建基于百分比的堆积柱形图分解为几个步骤。

### 创建和配置图表

#### 概述
创建一个实例 `Presentation` 类，这对于使用幻灯片至关重要。然后，在幻灯片上添加并配置堆叠柱形图。

#### 添加堆积柱形图
```csharp
// 创建 Presentation 类的实例
document = new Presentation();

// 获取第一张幻灯片的参考
slide = document.Slides[0];

// 在位置 (20, 20) 处添加尺寸为 (500x400) 的 PercentsStackedColumn 图表
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### 配置数字格式
确保您的数据以百分比显示：
```csharp
// 配置垂直轴的数字格式
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // 将数字格式设置为百分比
```

#### 添加数据系列和点
清除现有系列数据并添加新数据：
```csharp
// 清除所有现有系列数据
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// 访问图表数据工作簿
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// 添加新的数据系列“Reds”
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// 将系列的填充颜色设置为红色
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// 配置“红色”系列的标签格式属性
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // 设置百分比格式
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// 添加另一个系列“布鲁斯”
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// 将系列的填充颜色设置为蓝色
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // 设置百分比格式
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### 保存演示文稿
将您的演示文稿保存到文件中：
```csharp
// 将演示文稿保存为 PPTX 格式
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### 故障排除提示
- 确保所有命名空间都已正确导入。
- 检查属性名称和方法调用中的拼写错误。
- 验证保存文件的路径是否存在并且具有正确的权限。

## 实际应用

以下是基于百分比的堆积柱形图可能有用的一些场景：
1. **销售分析**：以总销售额的比例来显示不同地区的产品表现。
2. **预算分配**：显示各部门如何根据公司整体支出分配预算。
3. **市场调研**：比较一段时间内消费者对不同产品类别的偏好。
4. **教育数据**：显示学生各科成绩分布情况。
5. **医疗保健统计**：代表多种健康状况的患者人口统计数据。

## 性能考虑

为了获得最佳性能，请考虑：
- 将数据点的数量限制在必要的范围内。
- 预加载数据以最大限度地减少运行时处理。
- 使用 Aspose.Slides for .NET 的高效内存管理实践。

## 结论

恭喜！您已成功学习如何使用 Aspose.Slides for .NET 创建基于百分比的堆叠柱形图。此工具可使复杂数据更易于理解且更具视觉吸引力，从而增强演示文稿的效果。

接下来做什么？探索 Aspose.Slides 中可用的其他图表类型，或将此功能集成到更大的应用程序中。祝您编码愉快！

## 常见问题解答部分

**问题1：我可以免费使用 Aspose.Slides 吗？**
A1：是的，您可以先免费试用，以测试 Aspose.Slides 的功能。

**Q2：Aspose.Slides for .NET 支持哪些图表类型？**
A2：它支持饼图、条形图、柱形图、折线图等各种图表。

**问题 3：如何开始使用 Aspose.Slides for .NET？**
A3：按照上述说明使用 NuGet 或 .NET CLI 安装库。按照我们的文档创建您的第一个图表。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}