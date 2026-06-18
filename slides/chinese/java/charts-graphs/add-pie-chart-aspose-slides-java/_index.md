---
date: '2026-05-29'
description: 了解如何使用 Aspose.Slides Maven 创建饼图 Aspose，将 Java 饼图添加到幻灯片，并自定义图表数据。提供 Maven
  设置和实际案例的分步指南。
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: 创建饼图 Aspose – 使用 Maven 向演示文稿添加图表
url: /zh/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides Java 在演示文稿中添加饼图

## 介绍
在本指南中，您将 **create pie chart aspose** 使用 Aspose.Slides Maven，并了解如何将其嵌入 PowerPoint 幻灯片。创建视觉上吸引人的演示文稿对于有效传递信息至关重要，尤其是当数据可视化发挥关键作用时。如果您希望使用 **aspose slides maven** 自动化此过程，您来对地方了。我们将演示如何将图表添加到幻灯片 — 具体为饼图 — 并针对实际场景进行自定义。

### 您将学习
- 如何在 Java 中初始化演示文稿对象。  
- 在演示文稿的第一张幻灯片上 **add a pie chart java** 的步骤。  
- 访问图表数据工作簿并列出其中的工作表。  

让我们深入了解如何利用 Aspose.Slides Java 为您的演示文稿增添动态图表！

## 快速答疑
- **What library adds charts via Maven?** aspose slides maven  
- **Which chart type is demonstrated?** Pie chart (add chart to slide)  
- **Minimum Java version required?** JDK 16 or later  
- **Do I need a license for testing?** A free trial works; production needs a license  
- **Where can I find the Maven dependency?** In the setup section below  

## 什么是 Aspose Slides Maven？
Aspose.Slides for Java 是一个强大的 API，允许开发者以编程方式创建、修改和渲染 PowerPoint 文件。Maven 包 (`aspose-slides`) 简化了依赖管理，使您能够专注于构建和自定义幻灯片——例如添加饼图——而无需处理底层文件操作。

## 为什么使用 Aspose.Slides Maven 将图表添加到幻灯片？
使用 Aspose.Slides Maven 可以直接从 Java 代码生成图表，无需手动编辑 PowerPoint。它提供对图表类型、数据源和样式的完整编程控制，确保品牌一致性和数据准确性。Maven 构件还处理所有必需的依赖，简化构建并实现与 CI/CD 流水线的无缝集成。

## 先决条件
- **Aspose.Slides for Java** 版本 25.4 或更高（Maven/Gradle）。  
- 已安装 JDK 16+。  
- 一个 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知识以及对 Maven 或 Gradle 的熟悉。

## 设置 Aspose.Slides for Java
首先，通过 Maven 或 Gradle 将 Aspose.Slides 包含到项目中。

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，您可以直接从 Aspose 官方网站 [download the latest release](https://releases.aspose.com/slides/java/)。

### 许可证获取
Aspose.Slides for Java 提供带有临时许可证的免费试用版用于测试。若需无限制的生产使用，请通过 [purchase page](https://purchase.aspose.com/buy) 购买许可证。

## 实现指南
下面我们将解决方案拆分为两个功能：添加饼图和访问其数据工作簿。

### 功能 1：创建演示文稿并添加图表
#### 概述
本部分展示如何创建新演示文稿并 **add a pie chart** 到第一张幻灯片。

#### 如何创建饼图 aspose？
加载 `Presentation` 类，添加类型为 `ChartType.Pie` 的图表，并保存文件。整个操作仅需三次 API 调用，且在典型的 10 张幻灯片的演示文稿中运行时间不足一秒，非常适合自动化报表生成。

#### 分步操作

**Step 1: Initialize a New Presentation Object**  
`Presentation` 类是 Aspose.Slides 的顶层对象，表示内存中的 PowerPoint 文件。  
```java
Presentation pres = new Presentation();
```
*Creates the `Presentation` instance that will hold all slides.*

**Step 2: Add a Pie Chart**  
`ChartType.Pie` 告诉 Aspose 渲染饼图。  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Places a pie chart at coordinates (50, 50) with a width of 400 and height of 500.*

**Step 3: Dispose of Resources**  
调用 `dispose()` 释放本机资源并防止内存泄漏。  
```java
if (pres != null) pres.dispose();
```
*Releases native resources; always call `dispose()` when you’re done.*

### 功能 2：访问图表数据工作簿和工作表
#### 概述
了解如何获取存储图表数据的底层工作簿并遍历其工作表。

#### 如何访问图表数据工作簿？
从图表中检索 `IChartDataWorkbook`，然后遍历其 `Worksheets` 集合。该工作簿模拟 Excel 文件，允许您以编程方式读取、修改或添加数据系列，图表将在运行时刷新时即时反映更改，无需重新启动。

#### 分步操作

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Same as Feature 1, Step 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*Same as Feature 1, Step 2.*

**Step 3: Get the Chart Data Workbook**  
`IChartDataWorkbook` 是提供对图表内部类 Excel 工作簿读写访问的接口。  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Retrieves the `IChartDataWorkbook` linked to the chart.*

**Step 4: Iterate Through Worksheets**  
`Worksheet` 对象代表工作簿内的各个工作表。  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Prints each worksheet’s name, letting you verify the data structure.*

**Step 5: Dispose of Resources**  
*Same as Feature 1, Step 3.*

## 实际应用
- **Data Reporting:** 自动生成包含最新指标的幻灯片套件，用于商业智能。  
- **Academic Presentations:** 在学术报告中可视化研究结果，无需手动创建图表。  
- **Marketing Material:** 即时展示产品表现或调查结果。

## 性能考虑
- Aspose.Slides 能处理 **50+ 输入和输出格式**，并在不将整个文件加载到内存的情况下处理数百页的演示文稿。  
- 保持幻灯片和图表数量在合理范围；每个图表都会消耗本机内存。  
- 始终调用 `dispose()` 及时释放资源。  
- 优化工作簿数据处理——避免将海量数据加载到单个图表中。

## 结论
我们已经介绍了 **aspose slides maven** 如何以编程方式 **add chart to slide**，以及如何使用图表的数据工作簿。借助这些构建块，您可以自动化任何需要精美 PowerPoint 输出的报表工作流。

### 后续步骤
- 探索图表样式选项（颜色、图例、数据标签）。  
- 连接外部数据源（CSV、数据库）以动态填充图表。  
- 在同一演示文稿中组合多种图表类型，以实现更丰富的叙事。

## 常见问题

**Q: How do I install Aspose.Slides for Java?**  
A: Use the Maven or Gradle dependency shown above, or download the library from the releases page.

**Q: What are the system requirements for Aspose.Slides?**  
A: JDK 16 or later; the library runs on any platform that supports Java.

**Q: Can I add other chart types besides pie charts?**  
A: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20 chart types.

**Q: How should I handle large presentations efficiently?**  
A: Dispose of objects promptly, limit high‑resolution images, and reuse chart templates to keep memory usage low.

**Q: Where can I find more details about Aspose.Slides features?**  
A: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/) for a complete API reference.

**Q: Is a license required for commercial use?**  
A: A valid license is required for production; a free trial is available for evaluation.

**Q: Does the Maven package include all chart capabilities?**  
A: Yes, the `aspose-slides` Maven artifact contains the full charting engine.

## 资源
- 文档: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- 下载: [Latest Releases](https://releases.aspose.com/slides/java/)
- 购买与试用: [Purchase Page](https://purchase.aspose.com/buy)
- 免费试用: [Trial Downloads](https://releases.aspose.com/slides/java/)
- 临时许可证: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- 支持论坛: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## 相关教程

- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Create a Pie of Pie Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}