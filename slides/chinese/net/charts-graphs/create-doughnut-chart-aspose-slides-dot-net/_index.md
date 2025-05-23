---
"date": "2025-04-15"
"description": "学习如何使用 Aspose.Slides for .NET 在 PowerPoint 演示文稿中轻松创建和自定义圆环图。本指南将帮助您提升可视化数据演示效果。"
"title": "如何使用 Aspose.Slides for .NET 在 PowerPoint 中创建甜甜圈图——分步指南"
"url": "/zh/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 在 PowerPoint 中创建甜甜圈图：分步指南

## 介绍

使用视觉上美观的圆环图增强您的 PowerPoint 演示文稿，可以显著改善您的数据呈现方式。Aspose.Slides for .NET 提供了一种创建和自定义这些图表的高效方法。本教程将指导您使用 Aspose.Slides for .NET 为您的 PowerPoint 幻灯片添加可自定义的圆环图（包括调整圆环图孔径）的步骤。

**您将学到什么：**
- 设置 Aspose.Slides for .NET
- 将圆环图添加到幻灯片的步骤
- 配置圆环图孔径的技巧
- 实际应用和性能考虑

在深入研究之前，让我们先了解一下您需要什么！

## 先决条件

在开始之前，请确保您满足以下要求：

### 所需的库和版本
- Aspose.Slides for .NET（最新版本）
- Visual Studio 或任何支持 .NET 开发的兼容 IDE

### 环境设置要求
- 安装了 .NET Framework 的 Windows 环境
- C# 编程基础知识

## 设置 Aspose.Slides for .NET

首先，您需要安装 Aspose.Slides 库。以下是使用不同方法安装的方法：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**使用包管理器控制台：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 包管理器 UI：**
搜索“Aspose.Slides”并直接通过 IDE 的 NuGet 界面安装最新版本。

### 许可证获取步骤
1. **免费试用：** 首先下载免费试用版来评估功能。
2. **临时执照：** 如果您需要更多时间，请向 Aspose 申请临时许可证。
3. **购买：** 为了长期使用，请考虑购买完整版。

安装完成后，使用以下基本设置初始化您的项目：
```csharp
using Aspose.Slides;

// 初始化新的 Presentation 对象
Presentation presentation = new Presentation();
```

## 实施指南

让我们将使用 Aspose.Slides for .NET 创建圆环图的过程分解为易于管理的步骤。

### 创建圆环图

#### 概述
我们首先在 PowerPoint 幻灯片中添加一个圆环图，并设置其位置和大小。

**添加图表：**
```csharp
using Aspose.Slides.Charts;

// 访问演示文稿中的第一张幻灯片（默认情况下会创建一张）
ISlide slide = presentation.Slides[0];

// 在幻灯片的 (50, 50) 位置添加一个圆环图，宽度和高度均为 400 个单位
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **参数：** `ChartType.Doughnut`，x 位置：50，y 位置：50，宽度：400，高度：400。

### 设置孔尺寸

#### 概述
接下来，我们将配置圆环图的孔径，使其更具视觉吸引力。

**配置孔尺寸：**
```csharp
// 将圆环图的孔径设置为 90%
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **关键配置：** `DoughnutHoleSize` 确定中心被“切除”的程度。0 到 100 之间的值表示百分比。

### 保存您的演示文稿

最后，将更改保存到新的 PowerPoint 文件：
```csharp
// 定义演示文稿的保存路径
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// 将修改后的演示文稿保存为 PPTX 格式
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **笔记：** 代替 `YOUR_OUTPUT_DIRECTORY` 使用您想要的文件位置。

### 故障排除提示

- 确保 Aspose.Slides 已正确安装和导入。
- 在保存演示文稿之前，请验证您的输出目录路径是否存在。

## 实际应用

使用 Aspose.Slides for .NET 创建的甜甜圈图可用于各种场景：

1. **商业报告：** 说明预算分配或销售分配等财务数据。
2. **营销分析：** 显示不同品牌的市场份额百分比。
3. **教育材料：** 用于以视觉上引人入胜的方式解释统计概念。

将 Aspose.Slides 与其他系统集成，以便在企业环境中自动生成和分发报告。

## 性能考虑

处理大型演示文稿或大量图表时，请考虑以下提示：

- 在将数据添加到幻灯片之前优化数据处理。
- 尽可能重复使用演示对象以节省内存。
- 定期更新您的 Aspose.Slides 库以获得性能改进。

## 结论

您已经学习了如何使用 Aspose.Slides for .NET 创建和自定义圆环图。这款功能强大的工具可以增强演示文稿的视觉吸引力，使数据一目了然。

**后续步骤：**
探索 Aspose.Slides 中可用的其他图表类型或深入研究动画等高级功能。

准备好尝试了吗？前往下方的资源部分，开始尝试吧！

## 常见问题解答部分

1. **Aspose.Slides for .NET 用于什么？**  
   它是一个用于以编程方式创建、修改和转换 PowerPoint 演示文稿的库。

2. **我怎样才能改变甜甜圈部分的颜色？**  
   使用 `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` 调整填充属性。

3. **我可以在一次演示文稿中创建多个图表吗？**  
   是的，通过在不同的幻灯片或位置上重复图表创建步骤，可以根据需要添加任意数量的图表。

4. **如何获得 Aspose.Slides for .NET 的商业使用许可？**  
   通过 Aspose 官方网站购买许可证以进行商业使用。

5. **如果我的演示文稿无法正确保存，我该怎么办？**  
   检查文件路径权限并确保您的项目引用是最新的。

## 资源

- [Aspose.Slides文档](https://reference.aspose.com/slides/net/)
- [下载 Aspose.Slides for .NET](https://releases.aspose.com/slides/net/)
- [购买许可证](https://purchase.aspose.com/buy)
- [免费试用版](https://releases.aspose.com/slides/net/)
- [临时许可证申请](https://purchase.aspose.com/temporary-license/)
- [支持论坛](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}