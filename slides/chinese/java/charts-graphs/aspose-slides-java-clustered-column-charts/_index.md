---
date: '2026-08-27'
description: 了解如何在 Java 中使用 Aspose.Slides 创建 clustered column chart，添加图表，设置自动系列颜色，并将演示文稿保存为
  PPTX。
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: 了解如何在 Java 中使用 Aspose.Slides 创建 clustered column chart，添加图表，设置自动系列颜色，并将演示文稿保存为
  PPTX——提供清晰的逐步说明。
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: 在 Java 中使用 Aspose.Slides 创建 clustered column chart
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: 如何在 Java 中使用 Aspose.Slides 创建 clustered column chart
url: /zh/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Slides 在 Java 中创建簇状柱形图

## 介绍
以编程方式创建簇状柱形图可以为您节省数小时的手动格式化工作，并确保在多个演示文稿之间保持一致性。 在本教程中，您将学习如何在 Java 中使用 Aspose.Slides **创建簇状柱形图**、**添加图表**、**设置颜色**以及**将演示文稿保存为 PPTX**。 我们将涵盖从安装库到自定义系列填充颜色以及持久化文件的所有内容，让您能够在任何 PowerPoint 幻灯片中嵌入丰富的数据可视化。

## 快速答案
- **处理演示文稿的主要类是什么？** `Presentation` from the `com.aspose.slides` package.  
- **如何添加簇状柱形图？** Call `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **系列颜色可以自动设置吗？** Yes—enable `setAutomaticSeriesColor(true)` on each series.  
- **应该使用哪种格式保存文件？** `SaveFormat.Pptx` produces a standard PowerPoint file.  
- **生产环境是否需要许可证？** A trial works for development; a full license is needed for commercial use.

## 什么是簇状柱形图？
簇状柱形图在每个类别中并排显示多个数据系列，便于比较各组之间的数值。 Aspose.Slides 开箱即支持此图表类型，并允许您以编程方式控制每个视觉方面。

## 为什么使用 Aspose.Slides 创建簇状柱形图？
Aspose.Slides 能够处理 **50 多种输入和输出格式**，并在不将整个文件加载到内存的情况下处理包含 **数百张幻灯片** 的演示文稿。 这种高效性意味着您可以在服务器端环境中以最小的资源消耗生成大型演示文稿。

## 先决条件
- **Java Development Kit** 16 或更高版本。  
- **Maven** 或 **Gradle** 用于依赖管理。  
- 对 Java 语法和面向对象概念有基本了解。  

### 所需库和依赖项
您需要 Aspose.Slides for Java 库（版本 25.4 或更高）。 该库完全兼容 JDK 16，并提供丰富的图表操作 API。

### 环境设置要求
您的 IDE（IntelliJ IDEA、Eclipse、VS Code）必须配置为编译 Java 16 代码并解析 Maven/Gradle 依赖项。

### 知识先决条件
了解 PowerPoint 幻灯片结构和基本图表术语（系列、类别、数据点）将帮助您更快地跟随示例。

## 设置 Aspose.Slides for Java
使用以下方法之一将库集成到您的项目中。

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**直接下载** – 从官方发布页面获取 JAR：[Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### 获取许可证的步骤
- **免费试用** – 在 Aspose 网站注册以获取临时许可证文件。  
- **临时许可证** – 为更大的测试套件请求 30 天许可证。  
- **完整许可证** – 购买以进行无限制的生产使用。

**基本初始化和设置**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## 如何添加簇状柱形图？
`Presentation` 表示内存中的 PowerPoint 文件。

**直接答案：**  
创建一个 `Presentation` 对象，它表示内存中的 PowerPoint 文件，获取第一张幻灯片，然后调用 `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`。 此单次调用会插入一个功能完整的簇状柱形图，准备好填充数据，并将其定位在幻灯片的指定坐标上。

### 功能 1：创建簇状柱形图
`Presentation` 类表示内存中的 PowerPoint 文件，并提供对幻灯片、形状和图表对象的访问。

**步骤 1：初始化演示文稿**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**步骤 2：添加簇状柱形图**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**步骤 3：清理资源**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## 如何为图表设置颜色？
`Series` 表示图表中数据点的集合。

**直接答案：**  
在创建图表后，通过 `chart.getChartData()` 获取其图表数据并遍历每个 `Series` 对象。 对于每个系列，调用父系列的 `setAutomaticSeriesColor(true)`。 Aspose.Slides 随后会自动从其调色板中为每个系列分配不同的对比色，确保在无需手动选择颜色的情况下实现视觉清晰。

### 功能 2：设置自动系列填充颜色
`IChart` 是表示图表形状的接口；它公开 `getChartData()` 用于系列操作。

**步骤 1：访问图表并遍历系列**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**步骤 2：资源管理**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## 如何将演示文稿保存为 PPTX？
`save` 将演示文稿写入所选格式的文件。

**直接答案：**  
指定输出文件路径，例如 `"output/ClusteredColumnChart.pptx"`，并调用 `presentation.save(outputPath, SaveFormat.Pptx)`。 `save` 方法会将整个幻灯片套件（包括所有形状、图表和资源）序列化为标准 PPTX 文件，可在 PowerPoint 2010 及更高版本以及许多在线查看器中打开。

### 功能 3：将演示文稿保存到磁盘
使用 `SaveFormat.Pptx` 保存会生成兼容 PowerPoint 2010 及更高版本以及大多数在线查看器的文件。

**步骤 1：定义输出路径**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**步骤 2：保存演示文稿**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## 实际应用
- **财务报告** – 比较各产品线的季度收入。  
- **营销分析** – 按地区可视化活动表现。  
- **项目管理** – 显示冲刺速度或团队间的资源分配。  

## 性能考虑因素
- 及时释放 `Presentation` 对象以释放本机资源。  
- 在保存之前使用 `presentation.getSlides().removeUnusedResources()` 来缩小文件大小。  
- 使用轻量级集合（例如 `ArrayList<Double>`）填充图表系列，以保持内存使用低。

## 结论
您现在已经了解如何使用 Aspose.Slides for Java **创建簇状柱形图**、自动 **设置颜色**，以及 **将演示文稿保存为 PPTX**。这些步骤使您能够以编程方式生成数据驱动的幻灯片，消除重复的手动工作，并确保整个组织的视觉一致性。

**下一步：**  
探索高级自定义，例如数据标签、坐标轴格式化，以及从数据库或 CSV 文件进行动态数据绑定，以进一步丰富您的演示文稿。

## 常见问题
**Q: 我可以在 Web 应用程序中使用此代码吗？**  
A: 可以——Aspose.Slides 与平台无关，可在任何基于 Java 的服务器环境中运行，包括 Spring Boot 和 Jakarta EE。

**Q: 该库支持其他图表类型吗？**  
A: 当然。`ChartType` 枚举包括饼图、条形图、折线图、面积图、雷达图等多种类型。

**Q: 如果输出文件夹不存在怎么办？**  
A: 确保事先创建目录，或使用 `Files.createDirectories(Paths.get(folder))` 来避免 `FileNotFoundException`。

**Q: 如何处理大型数据集（数千个点）？**  
A: 使用流式 API 或批量插入来填充系列，并考虑禁用图表动画以提升渲染速度。

**Q: 我在哪里可以找到更多代码示例？**  
A: 访问官方文档和示例仓库：[Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)。

## 资源
- **文档：** [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **参考：** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **下载：** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **购买：** [Buy a License](https://purchase.aspose.com/buy)  
- **免费试用：** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **临时许可证：** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **支持：** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**最后更新：** 2026-08-27  
**测试环境：** Aspose.Slides 25.4 (JDK 16)  
**作者：** Aspose

## 相关教程
- [创建 PowerPoint 图表 Java – 使用 Aspose.Slides 保存带图表的演示文稿](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [aspose slides maven 依赖：使用 Aspose.Slides for Java 在演示文稿中添加和配置图表](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [使用 Aspose.Slides for Java 为 PowerPoint 图表添加动画 – 步骤指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}