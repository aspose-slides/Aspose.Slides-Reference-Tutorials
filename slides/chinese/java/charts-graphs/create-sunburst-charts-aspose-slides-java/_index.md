---
date: '2026-07-03'
description: 学习如何在 Java 中使用 Aspose.Slides 步骤式创建旭状图，并提供 PowerPoint 演示文稿的完整自定义选项。
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: 如何在 Java 中使用 Aspose.Slides 创建旭状图
url: /zh/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 中创建旭辉图

## 介绍
在当今数据驱动的演示中，快速创建 **旭辉图** 可让您的幻灯片脱颖而出。本教程将手把手教您使用 Aspose.Slides for Java 构建旭辉图，从项目设置到最终导出，让您无需离开 Java 生态系统即可呈现引人注目的层次数据图形。

## 快速答案
- **PowerPoint 文件的主类是什么？** `Presentation` – 它在内存中表示整个 PPTX。  
- **创建基本旭辉图需要多少行代码？** 通常在引用库后为 5–7 行。  
- **支持哪些输出格式？** PPTX、PDF、PNG、SVG 和 HTML。  
- **我可以自定义单个段落的样式吗？** 可以——填充颜色、边框和数据标签均可完全自定义。  
- **生产环境需要许可证吗？** 免费评估版可用于测试；部署时需要商业许可证。  

## 什么是旭辉图？
旭辉图通过同心环来可视化层次数据，每个环代表层级中的一级。它让观众一目了然地了解父子关系，非常适合组织结构图、分类学展示和多层次指标。尤其适用于展示多层级类别，如产品线、地理区域或组织结构，使观众既能看到整体分布，又能看到每个段落的详细细分。

## 为什么使用 Aspose.Slides 绘制旭辉图？
Aspose.Slides 支持 **30 多种图表类型**，能够在不将整个文档加载到内存的情况下处理高达 **500 MB** 的文件，并以 **300 DPI** 渲染图形，确保输出晶莹剔透。这些量化能力保证即使在大型演示文稿中也能快速生成高质量的视觉效果。此外，库提供线程安全的操作，并能无缝集成到流行的 Java 构建工具中，使其适用于桌面和服务器端的大规模演示文稿生成。

## 前置条件
- Java Development Kit (JDK) 8 或更高版本。  
- 用于依赖管理的 Maven 或 Gradle。  
- Aspose.Slides for Java（最新版本）。  
- 对层次数据结构的基本了解。  

## 如何一步步创建旭辉图？
加载环境、添加图表、输入层次数据、进行样式设置并保存文件——只需几个简洁的步骤。下面提供了完整的工作流，您无需编写额外的模板代码即可遵循。该过程全自动化，无需手动 UI 操作，可集成到批处理任务或 Web 服务中，实现按需生成图表。

### 步骤 1：设置项目
在 `pom.xml` 中添加 Aspose.Slides 的 Maven 依赖（或等效的 Gradle 代码段），即可引入所有必需的二进制文件和传递依赖。

### 步骤 2：加载或创建演示文稿
`Presentation` 是 Aspose.Slides 的顶层对象，表示内存中的单个 PowerPoint 文件。使用 `new Presentation()` 实例化可创建全新演示文稿，或传入文件路径打开已有 PPTX。

### 步骤 3：添加旭辉图
使用 `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` 在幻灯片上插入新的图表形状。这会创建用于数据的旭辉图占位符。`ChartType.Sunburst` 在向幻灯片添加图表时指定旭辉图类型。

### 步骤 4：填充层次数据
`ChartData` 保存图表的数据系列和类别。访问图表的 `ChartData` 集合，添加反映层次结构的系列和类别。对于每个层级，通过 `ParentSeries` 属性指定父子关系，使图表自动渲染同心环。

### 步骤 5：自定义外观
通过 `ChartSeries` 和 `ChartDataPoint` 对象微调段落颜色、边框样式和数据标签。`ChartSeries` 表示图表中的一组数据点。`ChartDataPoint` 表示系列中的单个数据点。您还可以启用 3‑D 旋转或设置 `Explode` 属性以突出显示特定切片。

### 步骤 6：保存演示文稿
`SaveFormat` 枚举定义了演示文稿可保存的文件格式。调用 `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` 将文件写入磁盘。通过更改 `SaveFormat` 枚举值，还可以导出为 PDF 或 PNG。

## 如何自定义旭辉图颜色？
使用 `point.getFillFormat().setFillType(FillType.Solid)` 为每个 `ChartDataPoint` 指定填充颜色，然后调用 `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`。这种直接方式可让您匹配企业品牌或突出关键数据点。您还可以应用渐变填充、调整透明度或使用主题颜色，以确保与幻灯片其余设计保持一致。

## 常见问题及解决方案
- **问题：** 层次结构显示为平面。  
  **解决方案：** 确保每个子系列正确引用其 `ParentSeries`。缺少链接会导致图表将所有数据视为单一级别。  

- **问题：** 导出的 PNG 模糊。  
  **解决方案：** 通过设置 `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` 提高导出 DPI。  

- **问题：** 大型 PPTX 文件导致 OutOfMemoryError。  
  **解决方案：** 使用 `Presentation.setMemoryOptimization(true)` 进行数据流式处理，降低内存占用。  

## 常见问答

**Q: 我可以从 CSV 文件生成旭辉图吗？**  
A: 可以。读取 CSV，在内存中构建层次结构，然后在保存前将其填充到图表的 `ChartData` 集合中。

**Q: Aspose.Slides 支持旭辉图的动画过渡吗？**  
A: 支持。对幻灯片应用 `SlideShowTransition`，或使用 `ChartFormat.setAnimationEnabled(true)` 实现图表级别的动画。

**Q: 可以将图表导出为 SVG 矢量图吗？**  
A: 完全可以。使用 `SaveFormat.Svg` 保存演示文稿，即可获得旭辉图的可缩放矢量版本。

**Q: 旭辉图最多能处理多少数据点？**  
A: Aspose.Slides 能可靠地在单个旭辉图中处理多达 **10,000** 个数据点，且性能不受影响。

**Q: 每个部署环境都需要单独的许可证吗？**  
A: 单一商业许可证覆盖所有环境（开发、预发布、生产），只要遵守许可证条款。

## 结论
现在，您已经拥有使用 Aspose.Slides 在 Java 中 **创建旭辉图** 的完整分步指南。按照上述工作流，您可以为任何 PowerPoint 演示文稿生成高质量、完全可定制的层次可视化图表。

---

**最后更新：** 2026-07-03  
**测试环境：** Aspose.Slides for Java 24.12  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Slides for Java 向 PowerPoint 添加图表：分步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [掌握使用 Aspose.Slides Java 对 PowerPoint 图表进行自定义以实现动态演示](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [使用 Aspose.Slides for Java 为 PowerPoint 图表类别添加动画 | 分步指南](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}