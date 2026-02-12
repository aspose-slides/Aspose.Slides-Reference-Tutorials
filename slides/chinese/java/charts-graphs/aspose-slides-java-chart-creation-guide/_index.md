---
date: '2026-02-12'
description: 学习如何使用 Aspose.Slides for Java 创建图表并管理图表。本教程展示了如何创建簇状柱形图、处理数据系列以及自定义可视化。
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 使用 Aspose.Slides 在 Java 中创建图表：全面指南
url: /zh/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose.Slides 创建图表

## 在 Java 中创建图表：简介
创建动态演示文稿通常需要通过图表来可视化数据。使用 **Aspose.Slides for Java**，您可以轻松 **创建图表** 对象，提升清晰度，并对观众产生更强的影响。本教程将指导您完成库的设置、添加 **聚簇柱形图**、管理系列以及有条件地反转负数据点的过程。

**您将学习**
- 如何设置 Aspose.Slides for Java。
- 在演示文稿中 **创建聚簇柱形图** 的步骤。
- 管理图表系列和数据点的技术。
- 有条件地反转负数据点以获得更好可视化的方法。
- 如何安全地保存演示文稿。

### 快速答案
- **使用的库是什么？** Aspose.Slides for Java。
- **演示的图表类型是什么？** 聚簇柱形图。
- **我可以反转负值吗？** 可以，使用 `invertIfNegative`。
- **需要哪个 Java 版本？** JDK 16 或更高。
- **生产环境需要许可证吗？** 是的，需要有效的 Aspose 许可证。

## 什么是聚簇柱形图？
聚簇柱形图在每个类别中并排显示多个数据系列，便于比较各组之间的数值。它非常适用于财务报告、销售仪表盘以及任何需要对比多个指标的场景。

## 为什么使用 Aspose.Slides 创建图表？
- **完全控制** 图表外观，无需依赖 PowerPoint UI。
- **编程生成** 使自动化报告流水线成为可能。
- **跨平台** 支持确保代码在任何兼容 Java 的系统上运行。
- **丰富的 API** 用于细粒度定制（颜色、数据标签、反转等）。

## 前置条件
1. **必需的库**
   - Aspose.Slides for Java（版本 25.4 或更高）。

2. **环境**
   - JDK 16 或更高。
   - Maven 或 Gradle 用于依赖管理。

3. **知识**
   - 基础 Java 编程。
   - 熟悉构建工具（Maven/Gradle）。

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
也可以从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

### 许可证获取
- **免费试用：** 在没有许可证的情况下探索功能。
- **临时许可证：** 评估期间使用。
- **正式许可证：** 购买用于生产部署。

### 基本初始化
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 步骤指南

### 步骤 1：创建演示文稿并添加聚簇柱形图
在此步骤中，我们 **创建图表** 对象并在第一页幻灯片上放置一个 **聚簇柱形图**。

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
默认情况下，Aspose.Slides 不会反转负值。我们仅为需要的点启用反转。

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

### 常见问题与技巧
- **忘记释放 `Presentation` 对象？** 始终在 `finally` 块中调用 `dispose()` 以释放本机资源。
- **负值未显示为反转？** 确保在添加数据点 **之后** 调用 `invertIfNegative(true)`。
- **图表尺寸问题：** 坐标 (X, Y) 和尺寸 (宽度, 高度) 使用点为单位；根据幻灯片布局进行调整。

## 常见问答

**Q: 我可以用相同的方法创建其他图表类型吗？**  
A: 是的，只需将 `ChartType.ClusteredColumn` 替换为其他 `ChartType` 枚举值（例如 `Line`、`Pie`）。

**Q: 开发构建需要许可证吗？**  
A: 开发构建需要临时或评估许可证才能完整使用功能；否则，库以试用模式运行，带有水印限制。

**Q: 添加图表后如何导出为 PDF？**  
A: 在完成图表操作后使用 `pres.save("output.pdf", SaveFormat.Pdf);` 导出为 PDF。

**Q: 能否为单个柱形设置样式（颜色、边框）？**  
A: 可以，每个 `IChartDataPoint` 都提供格式化选项，例如 `getFillFormat().setFillType(FillType.Solid)` 和 `getLineFormat()`。

**Q: 保存演示文稿后需要更新图表数据怎么办？**  
A: 使用 `new Presentation("file.pptx")` 重新加载演示文稿，修改图表数据后重新保存。

---

**Last Updated:** 2026-02-12  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}