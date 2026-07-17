---
date: '2026-07-17'
description: 学习如何使用 Aspose Slides for Java 在 PowerPoint 中添加 Sunburst 图表。逐步指南涵盖设置、图表创建、定制以及实际使用案例。
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: 如何在 PowerPoint 中使用 Aspose Slides for Java 添加 Sunburst 图表。按照本教程设置库、创建图表、定制数据点，并将其应用于实际项目。
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: 如何在 PowerPoint 中使用 Aspose (Java) 添加 Sunburst 图表
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: 如何在 PowerPoint 中使用 Aspose (Java) 添加 Sunburst 图表
url: /zh/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint 中使用 Aspose (Java) 添加旭状图

## 介绍

在 PowerPoint 演示文稿中添加旭状图可以瞬间将平面的数据表转换为引人入胜的层次可视化。在本教程中，您将学习 **如何添加旭状图**，使用 Aspose.Slides for Java，从环境搭建到细致的颜色和标签调优。无论您是构建销售仪表板、项目任务分解，还是教育类幻灯片，下面的步骤都能为您提供可直接投入生产的解决方案。

**您将学习**
- 如何在 Maven 或 Gradle 项目中配置 Aspose.Slides  
- 如何创建新演示文稿并插入旭状图  
- 如何自定义数据点、标签和填充颜色  
- 旭状图发挥优势的真实场景  

让我们开始吧，看看将原始层次数据转化为精美 PowerPoint 可视化有多么简单。

## 快速答案
- **主要库？** Aspose.Slides for Java  
- **支持的图表类型？** Sunburst (径向层次结构)  
- **最低 Java 版本？** JDK 16  
- **典型实现时间？** 基础图表 10‑15 分钟  
- **生产环境需要许可证？** 是，需要有效的 Aspose 许可证  

## 什么是旭状图？
旭状图是一种径向图表，通过从中心点向外嵌套环形来可视化层次数据。它非常适合展示多层级关系，如组织结构、产品类别或文件系统树。每个同心环代表层级的一级，环段的大小反映其定量值，使观众能够快速理解结构和规模。

## 为什么使用 Aspose.Slides for Java？
Aspose.Slides 支持 **50+ 图表类型**，并且能够在 **最多 10,000 张幻灯片** 的演示文稿上进行操作，而无需将整个文件加载到内存中，从而为企业级报表提供高性能。它跨平台运行，提供丰富的 API 覆盖，并包含强大的授权选项，可去除评估限制，使其非常适合生产环境。

## 前置条件
- **Java 开发工具包 (JDK)** 16 或更高  
- **IDE** – IntelliJ IDEA、Eclipse 或任何兼容 Java 的编辑器  
- 基本熟悉 Java 语法以及 Maven/Gradle 构建工具  

## 设置 Aspose.Slides for Java

### Maven 依赖
将 Aspose.Slides Maven 构件添加到您的 `pom.xml` 中：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 依赖
如果您更喜欢 Gradle，请在 `build.gradle` 中加入以下行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
您也可以直接从官方发布页面下载最新的 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

### 获取许可证
要在无评估限制的情况下运行，请获取许可证：
- **免费试用** – 用于快速评估的临时许可证。  
- **临时许可证** – 可从 [Aspose 网站](https://purchase.aspose.com/temporary-license) 请求。  
- **完整购买** – 购买订阅以实现无限制的生产使用。

### 基本初始化
`Presentation` 类是创建或打开 PowerPoint 文件的入口。

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## 实施指南

### 如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中添加旭状图？

加载一个新的 `Presentation`，添加幻灯片，插入类型为 `ChartType.Sunburst` 的 `IChart`，然后调用 `save`。这种简洁的三步模式即可创建一个功能完整的旭状图，供后续自定义使用。

#### 步骤 1：初始化 Presentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### 步骤 2：添加旭状图
`IChart` 接口定义了可以放置在任意幻灯片上的图表对象。这里我们在坐标 (100, 100) 处添加一个大小为 450 × 400 点的旭状图。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### 步骤 3：保存演示文稿
始终通过调用 `save` 来持久化更改。您可以选择 PPTX、PDF 或任何 50+ 支持的输出格式。

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 修改图表中的数据点

#### 概述
您可以通过图表的数据点集合定制旭状图的每个切片——标签、颜色和可见性。

#### 步骤 1：访问数据点集合
图表的第一系列包含一组 `IChartDataPoint` 对象，代表每个切片。

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### 步骤 2：显示特定数据点的数值
在目标数据点上将 `IsValueShown` 设置为 `true`，即可在切片上直接显示其数值。

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### 步骤 3：修改标签格式
调整标签可见性、字体颜色和背景，以提升可读性。

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### 步骤 4：设置数据点的填充颜色
自定义各切片的填充颜色，以匹配品牌配色或突出关键部分。

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### 步骤 5：保存修改后的演示文稿
通过再次保存演示文稿来持久化自定义的图表。

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 实际应用

1. **业务分析** – 在单一径向视图中可视化地区 → 产品线 → SKU 的销售情况。  
2. **项目管理** – 展示工作分解结构，从阶段到任务再到子任务。  
3. **教育** – 绘制课程层次结构，例如系部 → 课程 → 模块。  

## 性能考虑

- **内存效率：** Aspose.Slides 采用流式处理，即使是包含多个图表的 500 页演示文稿也保持在 200 MB 以下的内存占用。  
- **垃圾回收：** 当幻灯片对象不再使用时调用 (`slide.dispose()`) 释放，以避免内存泄漏。  

## 常见问题

**Q: 什么是旭状图？**  
A: 旭状图通过同心环可视化层次数据，每个环代表层级的一级。

**Q: 如何使用 Maven 安装 Aspose.Slides for Java？**  
A: 将 “Maven 依赖” 部分显示的 Maven 依赖添加到 `pom.xml`，然后运行 `mvn clean install`。

**Q: 我可以使用 Aspose.Slides 定制其他图表类型吗？**  
A: 可以，库支持超过 50 种图表类型，包括柱形图、折线图、饼图和雷达图等。

**Q: 我的演示文稿未保存——我应该检查什么？**  
A: 确认文件路径正确、目录存在且具有写入权限。同时确保已调用 `Presentation.save()` 方法。

**Q: 我在哪里可以获取更多帮助或示例？**  
A: 访问 [Aspose 论坛](https://forum.aspose.com/c/slides/11) 或查阅官方的 [Aspose.Slides 参考文档](https://reference.aspose.com/slides/java/)。

## 资源
- **文档：** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **参考（小写）：** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **社区论坛：** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **下载：** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**最后更新：** 2026-07-17  
**测试环境：** Aspose.Slides for Java 24.12  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.Slides for Java 向 PowerPoint 添加图表：分步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [使用 Aspose.Slides for Java 为 PowerPoint 动画图表 – 分步指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [在 Java 中使用 Aspose.Slides 创建图表 – 添加与验证图表](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}