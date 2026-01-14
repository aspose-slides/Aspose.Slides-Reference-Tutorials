---
date: '2026-01-14'
description: 学习如何使用 Aspose.Slides 在 Java 中创建簇状柱形图。一步步指南，涵盖空白演示文稿、向演示文稿添加图表以及管理系列。
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 如何在 Java 中使用 Aspose.Slides 创建聚簇柱形图
url: /zh/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握 Java 中使用 Aspose.Slides 创建图表

## 使用 Aspose.Slides for Java 创建和管理图表

### 介绍
创建动态演示文稿通常需要通过图表对数据进行可视化。借助 **Aspose.Slides for Java**，您可以轻松 **创建聚类柱形图** 并管理各种图表类型，提升清晰度和冲击力。本教程将指导您创建空白演示文稿、向演示文稿添加聚类柱形图、管理系列以及自定义数据点的反转——全部使用 Aspose.Slides for Java。

**您将学到：**
- 如何设置 Aspose.Slides for Java。
- **创建空白演示文稿** 并向演示文稿添加图表的步骤。
- 有效管理图表系列和数据点的技巧。
- 条件性反转负值数据点以获得更佳可视化的方法。
- 如何安全地保存演示文稿。

在开始之前，让我们先了解一下前置条件。

## 快速答案
- **启动的主要类是什么？** `Presentation` 来自 `com.aspose.slides`。
- **哪个图表类型用于创建聚类柱形图？** `ChartType.ClusteredColumn`。
- **如何向幻灯片添加图表？** 在幻灯片的形状集合上使用 `addChart()`。
- **可以反转负值吗？** 可以，使用数据点的 `invertIfNegative(true)`。
- **需要哪个版本？** Aspose.Slides for Java 25.4 或更高。

## 什么是聚类柱形图？
聚类柱形图在每个类别中并排显示多个数据系列，非常适合比较不同组之间的数值。Aspose.Slides 让您无需打开 PowerPoint，即可以编程方式生成此类图表。

## 为什么使用 Aspose.Slides for Java 向演示文稿添加图表？
- **完全控制** 图表数据、外观和布局。
- **服务器上无需安装 Office**。
- **支持所有主流图表类型**，包括聚类柱形图。
- **易于集成** 到 Maven/Gradle 构建中。

## 前置条件
在开始之前，请确保具备以下条件：

1. **必需的库：**
   - Aspose.Slides for Java（版本 25.4 或更高）。

2. **环境搭建要求：**
   - 兼容的 JDK 版本（例如 JDK 16）。
   - 如需依赖管理，请安装 Maven 或 Gradle。

3. **知识前提：**
   - 基本的 Java 编程了解。
   - 熟悉在开发环境中处理依赖项。

## 设置 Aspose.Slides for Java
要开始使用 Aspose.Slides，请按以下步骤操作：

**Maven 安装：**  
在 `pom.xml` 文件中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 安装：**  
在 `build.gradle` 中添加以下行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载：**  
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

### 许可证获取
- **免费试用：** 您可以先使用免费试用版探索功能。  
- **临时许可证：** 在评估期间获取临时许可证以获得完整访问权限。  
- **购买：** 如满足长期需求，可考虑购买正式许可证。

### 基本初始化
下面是创建新演示文稿实例所需的最小代码：

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 实现指南
接下来，让我们将每个功能拆解为可管理的步骤。

### 使用聚类柱形图创建演示文稿
#### 概述
本节展示如何 **创建空白演示文稿**、添加 **聚类柱形图** 并将其定位在第一张幻灯片上。

**步骤：**
1. **初始化 Presentation 对象** – 创建一个新的 `Presentation`。
2. **添加聚类柱形图** – 使用适当的类型和尺寸调用 `addChart()`。

**代码示例：**
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

### 管理图表系列
#### 概述
学习如何清除默认系列、添加新系列，并用正负值填充数据。

**步骤：**
1. **清除现有系列** – 移除任何预填充的数据。
2. **添加新系列** – 使用工作簿单元格作为系列名称。
3. **插入数据点** – 添加包括负数在内的值，以便后续演示反转。

**代码示例：**
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

### 根据条件反转系列数据点
#### 概述
默认情况下，Aspose.Slides 可能会反转负值。您可以全局和针对单个数据点控制此行为。

**步骤：**
1. **设置全局反转** – 为整个系列禁用自动反转。
2. **应用条件反转** – 仅对特定负数点启用反转。

**代码示例：**
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

### 常见问题及解决方案
| 问题 | 解决方案 |
|------|----------|
| 图表显示为空白 | 确认幻灯片索引 (`0`) 存在，且图表尺寸在幻灯片范围内。 |
| 负值未被反转 | 检查系列上已设置 `invertIfNegative(false)`，并在特定数据点上设置 `invertIfNegative(true)`。 |
| 许可证异常 | 在创建 `Presentation` 对象之前应用有效的 Aspose 许可证。 |

## 常见问答

**问：我可以添加除聚类柱形图之外的其他图表类型吗？**  
答：可以，Aspose.Slides 支持折线图、饼图、条形图、面积图等多种图表类型。

**问：开发阶段需要许可证吗？**  
答：免费试用可用于评估，但生产环境必须使用商业许可证。

**问：如何将图表导出为图片？**  
答：在渲染后使用 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`。

**问：可以对图表进行样式设置（颜色、字体）吗？**  
答：当然。每个 `IChartSeries` 和 `IChartDataPoint` 都提供样式属性。

**问：如果想向已有的 PPTX 文件添加图表怎么办？**  
答：使用 `new Presentation("existing.pptx")` 加载文件，然后在目标幻灯片上添加图表。

## 结论
本教程中，您学习了如何在 Java 中使用 Aspose.Slides **创建聚类柱形图**、管理系列以及条件性反转负值数据点。掌握这些技术后，您即可以编程方式构建引人注目、数据驱动的演示文稿。

**后续步骤：**
- 试验 Aspose.Slides for Java 提供的其他图表类型。  
- 深入探索高级样式选项，如自定义颜色、数据标签和坐标轴格式。  
- 将图表生成集成到您的报告或分析流水线中。

---

**最后更新：** 2026-01-14  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}