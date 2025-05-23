---
"date": "2025-04-15"
"description": "学习如何使用 Aspose.Slides for .NET 创建和自定义图表，包括将百分比显示为数据标签。请遵循本分步指南。"
"title": "如何使用 Aspose.Slides .NET 创建和自定义图表 - 将百分比显示为标签"
"url": "/zh/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides .NET 创建和自定义图表：将百分比显示为标签

## 介绍

在许多领域，有效地呈现数据至关重要，而图表在将复杂信息转化为清晰的视觉效果方面发挥着至关重要的作用。创建完美的图表需要自定义任务，例如在标签上显示百分比——而使用 Aspose.Slides for .NET 可以更轻松地完成这项任务。这个库简化了在 PowerPoint 演示文稿中创建和修改图表的过程。

在本教程中，您将学习如何使用 Aspose.Slides for .NET 从零开始创建堆叠柱形图，并通过将百分比值显示为数据标签来自定义图表。按照以下步骤操作，您将能够使用精准且视觉上美观的数据呈现方式来增强幻灯片的美感。

**您将学到什么：**
- 初始化 Aspose.Slides for .NET
- 创建堆积柱形图
- 计算并显示数据标签上的百分比
- 优化图表性能最佳实践

在我们深入实施之前，让我们确保您已做好一切准备。

## 先决条件

为了有效地遵循本教程，请确保您已：
- **.NET Core SDK** 安装在您的机器上。
- 对 C# 和 .NET 应用程序开发有基本的了解。
- Visual Studio 或类似的 IDE，用于编写和运行 C# 代码。

您需要 Aspose.Slides for .NET 来创建图表，因此请确保按照下面的说明进行设置。

## 设置 Aspose.Slides for .NET

Aspose.Slides for .NET 是一个功能强大的库，允许您以编程方式处理 PowerPoint 演示文稿。以下是如何将其添加到您的项目中：

### 安装

**.NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**程序包管理器控制台：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 包管理器 UI：** 
- 打开 NuGet 包管理器并搜索“Aspose.Slides”。安装最新版本。

### 许可证获取

要充分利用 Aspose.Slides，请先免费试用。如需长期使用，请考虑购买临时许可证或从 [Aspose](https://purchase.aspose.com/buy). 按照他们的指导在您的项目环境中设置您的许可证。

### 基本初始化

安装完成后，初始化 `Presentation` 类开始创建幻灯片：
```csharp
using Aspose.Slides;

// 初始化Presentation类实例
tPresentation presentation = new Presentation();
```

现在，让我们继续使用 Aspose.Slides for .NET 实现图表创建和自定义功能。

## 实施指南

### 创建堆积柱形图

我们的目标是创建一个堆叠柱形图，并通过将百分比显示为数据标签来对其进行自定义。操作方法如下：

#### 初始化演示文稿

首先创建一个实例 `Presentation`：
```csharp
using Aspose.Slides;

// 初始化Presentation类实例
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### 向幻灯片添加图表

在第一张幻灯片中按指定的坐标和尺寸添加堆积柱形图：
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
这行代码创建了一个 `StackedColumn` 图表位于位置 (20, 20)，宽度和高度为 400。

#### 计算百分比计算的总值

要显示百分比，请计算所有系列中每个类别的总值：
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // 对每个类别的所有系列的值进行求和
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### 自定义数据标签以显示百分比值

接下来，遍历每个系列并自定义数据标签：
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // 计算百分比
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // 清晰的文本以避免重叠
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // 配置标签格式以隐藏默认数据标签
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

此部分计算每个数据点的百分比并将其设置为自定义标签，确保与默认标签不重叠。

#### 保存演示文稿

最后，保存您的演示文稿以查看结果：
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## 实际应用

在图表中显示百分比在以下情况下特别有用：
1. **财务报告：** 以百分比显示投资组合分布或投资回报。
2. **销售分析：** 以百分比表示市场份额数据，以突出各地区的表现。
3. **调查结果：** 将调查回复显示为百分比，以便进行更好的视觉比较。
4. **项目管理：** 使用带有百分比的饼图来说明资源分配。
5. **教育：** 使用清晰的基于百分比的视觉效果解释统计概念。

将这些定制图表集成到 CRM 或 ERP 等系统中可以增强仪表板和报告，从而帮助决策过程。

## 性能考虑

使用 Aspose.Slides for .NET 时，尤其是处理大型数据集时：
- **内存管理：** 正确处理演示对象以释放内存。使用 `using` 适用的声明。
- **高效的数据处理：** 尽可能在循环外执行计算以减少计算开销。
- **负载平衡：** 对于 Web 应用程序，确保服务器资源足以满足并发图表生成请求。

## 结论

本教程介绍了如何使用 Aspose.Slides for .NET 创建和自定义图表，并将百分比值显示为标签。掌握这些技巧，可以让您通过详细且视觉上引人入胜的数据呈现方式来增强演示文稿的效果。

接下来，探索 Aspose.Slides 中其他可用的图表类型和自定义选项。尝试不同的数据集，将其转换为强大的视觉效果，清晰地传达见解。

## 常见问题解答部分

**问题 1：使用 Aspose.Slides for .NET 创建图表时如何处理大型数据集？**
A1：对于大型数据集，优化计算并使用高效的内存管理技术。分解处理任务以避免内存过载。

**问题2：我可以在 Web 应用程序中使用 Aspose.Slides for .NET 吗？**
A2：是的，它可以集成到 ASP.NET 应用程序中。请确保服务器资源分配合理，以获得最佳性能。

**Q3：是否可以将使用 Aspose.Slides 创建的图表导出为其他格式？**
A3：当然！您可以使用库的功能将包含自定义图表的演示文稿导出为各种格式，例如 PDF 和图像文件。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}