---
date: '2026-09-12'
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中创建簇状柱形图、获取其数据范围，并高效导出图表图片。
keywords:
- create clustered column chart
- update powerpoint chart data
- export powerpoint chart image
- create pie chart java
- create powerpoint presentation java
- author: Aspose
  dateModified: '2026-09-12'
  description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  headline: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  type: TechArticle
- description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  name: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  steps:
  - name: Create the Presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: Add a Clustered Column Chart
    text: 'Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters Explained**:
      - `ChartType.ClusteredColumn`: Defines the type of chart. - `(10, 10)`: X and
      Y coordinates for positioning the chart on the slide. - `(400, 300)`: Width
      and height of the chart.'
  - name: Retrieve the Data Range
    text: 'Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving Data**: This method gives you a snapshot of your chart''s
      data, useful for debugging or display purposes.'
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
lastmod: '2026-09-12'
og_description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中创建簇状柱形图、获取其数据范围，并高效导出图表图片。支持更新
  PowerPoint 图表数据并导出图表图片。
og_image_alt: 'Developer guide: create clustered column chart in PowerPoint using
  Aspose.Slides for Java'
og_title: 如何使用 Aspose.Slides for Java 创建簇状柱形图
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  headline: How to create clustered column chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  name: How to create clustered column chart with Aspose.Slides for Java
  steps:
  - name: create the presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: add a clustered column chart
    text: Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters explained**
      - `ChartType.ClusteredColumn` – selects the clustered column visual. - `(10,
      10)` – X and Y coordinates (points) for the chart’s top‑left corner.
  - name: add a clustered column chart
    text: Firstly, add a clustered column chart as described previously.
  - name: retrieve the data range
    text: Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving data** – this method gives you a snapshot of your chart's
      data, useful for debugging or display purposes.
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides Java
- PowerPoint chart generation
- Java presentation automation
- chart data retrieval
title: 如何使用 Aspose.Slides for Java 创建簇状柱形图
url: /zh/java/charts-graphs/create-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Slides for Java 在 PowerPoint 中创建簇状柱形图

创建 PowerPoint 文件中的簇状柱形图过去需要繁琐的 XML 操作或完整的 Office 安装。使用 **Aspose.Slides for Java**，您可以以编程方式生成图表、调整数据，并在几秒钟内导出可视化效果。本教程将指导您构建演示文稿、插入簇状柱形图，并读取底层数据范围，以便后续验证或记录。更多背景信息，请访问 [Aspose website](https://releases.aspose.com/slides/java/)。

## 快速答案
- **哪个库在 Java 中创建 PowerPoint 图表？** Aspose.Slides for Java。  
- **示例使用的图表类型是什么？** 簇状柱形图。  
- **运行示例是否需要许可证？** 免费试用可用于评估；生产环境需要商业许可证。  
- **创建后我可以检索图表数据吗？** 可以——在图表对象上调用 `getChartData().getRange()`。  
- **支持哪个 Java 版本？** JDK 16 及更高版本。

## Aspose.Slides for Java 是什么？

`Aspose.Slides for Java` 是一个 **stand‑alone API**，无需 Microsoft Office 即可创建、编辑和渲染 PowerPoint 文件。它支持 **50+ 输入和输出格式**，并且能够在 **使用不到 200 MB RAM 的情况下处理包含数百张幻灯片的演示文稿**。

## 为什么使用 Aspose.Slides for Java 生成图表？

Aspose.Slides 处理 **50+ 图表类型**，在典型服务器硬件上 **最高可达 30 fps** 渲染，并且在 **不将整个文件加载到内存中** 的情况下操作演示文稿。这使其非常适合需要每日生成数千个图表且保持 CPU 和内存占用低的自动化报告流水线。

## 前置条件

- **Java Development Kit (JDK)** 16 或更高版本已安装。  
- 如 **IntelliJ IDEA** 或 **Eclipse** 等 IDE。  
- **Maven** 或 **Gradle** 用于依赖管理。  

### 必需的库和依赖

使用以下代码片段将 Aspose.Slides 添加到项目中。

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

或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新的 JAR 包。

### 许可证获取

先使用免费试用或申请临时许可证以解锁全部功能。生产使用时，请从 [Aspose's purchasing page](https://purchase.aspose.com/buy) 购买许可证。

## 设置 Aspose.Slides for Java

`Presentation` 类是创建和操作 PowerPoint 文件的主要入口。添加依赖后，在代码中初始化 API。

1. **添加依赖**，使用上面展示的 Maven 或 Gradle。  
2. **创建 `Presentation` 实例**——该对象将保存您的幻灯片和图表。  

```java
Presentation pres = new Presentation();
```  

3. **完成后释放演示文稿**，以释放本地资源。  

```java
if (pres != null) pres.dispose();
```  

## 如何在 Java 中创建包含簇状柱形图的 PowerPoint 演示文稿？

加载一个新的 `Presentation`，添加幻灯片，并在一次流式调用中插入簇状柱形图。`Presentation` 对象在内存中表示整个 PowerPoint 文件，而 `addChart` 方法在指定的幻灯片上创建图表形状。以下是核心步骤，代码行数不足十行即可完成。

### 步骤 1：创建演示文稿  

`Presentation` 类是 Aspose.Slides 的顶层对象，表示内存中的 PowerPoint 文件。  

```java
Presentation pres = new Presentation();
```  

### 步骤 2：添加簇状柱形图  

使用 `addChart` 方法将图表插入演示文稿。指定图表类型、位置（x、y 坐标）和大小。  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

- **参数说明**  
  - `ChartType.ClusteredColumn` – 选择簇状柱形图。  
  - `(10, 10)` – 图表左上角的 X、Y 坐标（点）。  
  - `(400, 300)` – 图表的宽度和高度（点）。

## 如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中检索图表的数据范围？

在图表对象上调用 `getChartData().getRange()`；它会立即返回类似 `"Sheet1!A1:B5"` 的字符串，反映支撑图表的 Excel 样式范围。此方法提供了数据源的简洁文本表示，无需加载完整工作簿，适合在自动化流水线中进行日志记录、调试或快速验证。

### 步骤 1：添加簇状柱形图  

首先，按照前述方式添加簇状柱形图。  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

### 步骤 2：检索数据范围  

使用 `getChartData().getRange()` 获取数据范围的字符串表示。  

```java
String result = chart.getChartData().getRange();
// Output omitted for clarity
```  

- **检索数据** – 此方法为您提供图表数据的快照，便于调试或展示。

## 实际应用

1. **业务报告**——生成在源数据更改时自动更新的 KPI 仪表板。  
2. **数据驱动的演示文稿**——构建能够实时反映最新销售或库存数据的幻灯片，无需手动编辑。  
3. **教育工具**——为教程、测验或交互式教材创建动态图表。

## 性能考虑

- **及时释放对象**——在 `finally` 块中调用 `presentation.dispose()` 以释放本地内存。  
- **避免完整文档加载**——处理大于 200 MB 的演示文稿时使用流式 API。  
- **仅检索所需范围**——`getChartData().getRange()` 可避免加载整个图表数据集，从而降低 CPU 使用率。

## 常见问题与解决方案

- **演示文稿崩溃**——始终在 `try‑catch` 块中包装文件 I/O，并确保在 `finally` 子句中调用 `dispose()`。  
- **图表尺寸不正确**——确认 X、Y、宽度和高度值位于幻灯片的 960 × 720 点画布范围内。  
- **许可证错误**——在创建任何 `Presentation` 对象之前加载许可证文件：`License license = new License(); license.setLicense("Aspose.Slides.lic");`。

## 常见问答

**Q: 如何安装 Aspose.Slides for Java？**  
A: 使用 Maven、Gradle，或从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载 JAR 包。

**Q: 我可以创建其他类型的图表吗？**  
A: 可以，Aspose.Slides 支持超过 50 种图表类型，包括条形图、折线图、饼图和雷达图。

**Q: 如果我的演示文稿在处理过程中崩溃怎么办？**  
A: 确保正确释放资源，并在代码中使用 try‑catch 块来处理 `IOException` 和 `Exception`。

**Q: 使用 Aspose.Slides 是否有许可证费用？**  
A: 提供免费试用。持续使用时，请考虑购买许可证或申请临时许可证。

**Q: 遇到问题如何获取支持？**  
A: 访问 [Aspose's support forum](https://forum.aspose.com/c/slides/11) 获取社区和 Aspose 专家的帮助。

## 资源
- **文档**：[Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **下载**：[Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **购买**：[Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **免费试用**：[Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **临时许可证**：[Request Temporary License](https://purchase.aspose.com/temporary-license/)

祝您使用 Aspose.Slides for Java 绘图愉快！

---

**Last Updated:** 2026-09-12  
**Tested With:** Aspose.Slides for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

## 相关教程

- [掌握 Aspose.Slides Java 的 PowerPoint 操作：演示文稿操作全指南](/slides/java/presentation-operations/aspose-slides-java-manipulate-pptx-presentations/)
- [掌握 Aspose.Slides Java 的 PowerPoint 幻灯片自动化：批量处理全指南](/slides/java/batch-processing/automate-powerpoint-slides-aspose-slides-java/)
- [使用 Aspose.Slides 在 Java 中创建旭辉图：完整指南](/slides/java/charts-graphs/create-sunburst-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}