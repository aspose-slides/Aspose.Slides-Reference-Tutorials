---
date: '2026-06-03'
description: 了解如何使用 Aspose.Slides 在 Java 中创建聚簇柱形图。本指南涵盖 Maven 依赖、图表创建步骤和数据处理。
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: 使用 Aspose.Slides 在 Java 中创建聚簇柱形图
url: /zh/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 Java 中使用 Aspose.Slides 创建簇状柱形图

## 如何在 Java 中创建图表：简介
创建动态演示文稿通常需要通过图表对数据进行可视化。使用 **Aspose.Slides for Java**，您可以轻松 **创建簇状柱形图** 对象，提升清晰度，并对观众产生更强的影响。本教程将指导您完成库的设置、添加簇状柱形图、管理系列以及有条件地反转负数据点。

**您将学到**
- 如何设置 Aspose.Slides for Java。
- 在演示文稿中 **创建簇状柱形图** 的步骤。
- 管理图表系列和数据点的技术。
- 有条件地反转负数据点以获得更好可视化的方法。
- 如何安全地保存演示文稿。

## 快速答案
- **使用的库是什么？** Aspose.Slides for Java。  
- **演示的图表类型是什么？** 簇状柱形图。  
- **我可以反转负值吗？** 可以，使用 `invertIfNegative`。  
- **需要哪个 Java 版本？** JDK 16 或更高版本。  
- **生产环境需要许可证吗？** 是的，需要有效的 Aspose 许可证。

## 什么是簇状柱形图？
簇状柱形图是一种可视化表示方式，它在每个类别中将多个数据系列并排放置，从而实现对各组之间的快速比较。它非常适用于财务报告、销售仪表盘以及任何需要一次对比多个指标的场景。

## 为什么使用 Aspose.Slides 创建图表？
Aspose.Slides 让您能够以编程方式生成并完全自定义图表，省去手动编辑 PowerPoint 的需求。它支持 **70+ 输入和输出格式**，并且能够在不将整个文件加载到内存的情况下处理 **多达 10,000 张幻灯片** 的演示文稿，确保大规模报告的高性能。

## 前置条件
1. **Required Libraries**  
   - Aspose.Slides for Java (version 25.4 or later)。  

2. **Environment**  
   - JDK 16 or newer。  
   - Maven or Gradle for dependency management。  

3. **Knowledge**  
   - Basic Java programming。  
   - Familiarity with build tools (Maven/Gradle)。  

## 设置 Aspose.Slides for Java
### Maven 安装
在您的 `pom.xml` 文件中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安装
在您的 `build.gradle` 文件中添加以下行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

### 获取许可证
- **免费试用：** 在没有许可证的情况下探索功能。  
- **临时许可证：** 在评估期间使用。  
- **正式许可证：** 购买用于生产部署。

### 基本初始化
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 如何向幻灯片添加簇状柱形图？
`Presentation` 是表示 PowerPoint 文件的核心类。加载一个新的 `Presentation`，添加一张幻灯片，然后调用 `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`。此单行调用即可在指定坐标处创建一个功能完整的簇状柱形图。随后您可以访问图表对象以修改系列、数据点和视觉样式。

## 步骤指南

### 步骤 1：创建演示文稿并添加簇状柱形图
`Presentation` 类表示 PowerPoint 文档并允许创建幻灯片。  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### 步骤 2：管理图表系列
现在我们将清除任何默认系列，添加一个新系列，并用正负值填充它。  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### 步骤 3：有条件地反转负数据点
`invertIfNegative` 方法可在图表系列中实现负值的反转。  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## 常见陷阱与技巧
- **忘记释放 `Presentation` 对象？** 始终在 `finally` 块中调用 `dispose()` 以释放本机资源。  
- **负值未显示为反转？** 确保在添加数据点 **之后** 调用 `invertIfNegative(true)`。  
- **图表尺寸问题：** 坐标 (X, Y) 和尺寸 (width, height) 使用点（points）为单位；根据幻灯片布局进行调整。  

## 常见问题解答

**Q:** 我可以使用相同的方法创建其他图表类型吗？  
A: 可以，只需将 `ChartType.ClusteredColumn` 替换为其他 `ChartType` 枚举值（例如 `Line`、`Pie`）。  

**Q:** 开发构建是否需要许可证？  
A: 需要临时或评估许可证才能完整使用功能；否则，库将在试用模式下运行，带有水印限制。  

**Q:** 添加图表后如何将演示文稿导出为 PDF？  
`SaveFormat.Pdf` 指定将演示文稿保存为 PDF 格式。完成图表操作后使用 `pres.save("output.pdf", SaveFormat.Pdf);`。  

**Q:** 能否对单个柱形进行样式设置（颜色、边框）？  
`IChartDataPoint` 表示图表中的单个数据点并允许格式化。每个 `IChartDataPoint` 提供如 `getFillFormat().setFillType(FillType.Solid)` 和 `getLineFormat()` 等选项。  

**Q:** 演示文稿保存后如果需要更新图表数据怎么办？  
A: 使用 `new Presentation("file.pptx")` 重新加载演示文稿，修改图表数据后重新保存。  

---

**最后更新：** 2026-06-03  
**测试环境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose

## 相关教程

- [如何在 Java 中使用 Aspose.Slides 创建堆叠柱形图 – 综合指南](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [如何在 Java 中使用 Aspose.Slides 创建图表 – 掌握图表创建与验证](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [使用 Aspose.Slides 在 Java 中创建与格式化图表：综合指南](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}