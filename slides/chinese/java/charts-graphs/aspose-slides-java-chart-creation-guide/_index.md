---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides for Java 创建和管理图表。本指南涵盖簇状柱形图、数据系列管理等内容。"
"title": "掌握使用 Aspose.Slides 在 Java 中创建图表的综合指南"
"url": "/zh/java/charts-graphs/aspose-slides-java-chart-creation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 掌握 Java 图表创建

## 如何使用 Aspose.Slides for Java 创建和管理图表

### 介绍
创建动态演示文稿通常涉及通过图表可视化数据。 **Aspose.Slides for Java**，您可以轻松创建和管理各种图表类型，增强清晰度和影响力。本教程将指导您创建空白演示文稿、添加簇状柱形图、管理序列以及自定义数据点反转——所有这些都使用 Aspose.Slides for Java 完成。

**您将学到什么：**
- 如何为 Java 设置 Aspose.Slides。
- 在演示文稿中创建聚集柱形图的步骤。
- 有效管理图表系列和数据点的技术。
- 为了更好地进行可视化，有条件地反转负数据点的方法。
- 如何安全地保存演示文稿。

在开始之前，让我们先深入了解一下先决条件。

## 先决条件
在开始之前，请确保您已具备以下条件：

1. **所需库：**
   - Aspose.Slides for Java（版本 25.4 或更高版本）。

2. **环境设置要求：**
   - 兼容的 JDK 版本（例如 JDK 16）。
   - 如果您更喜欢依赖管理，请安装 Maven 或 Gradle。

3. **知识前提：**
   - 对 Java 编程有基本的了解。
   - 熟悉处理开发环境中的依赖关系。

## 设置 Aspose.Slides for Java
要开始使用 Aspose.Slides，请按照以下步骤操作：

**Maven安装：**
将以下依赖项添加到您的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 安装：**
将以下行添加到您的 `build.gradle`：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载：**
或者，从下载最新版本 [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).

### 许可证获取
- **免费试用：** 您可以先免费试用，探索其功能。
- **临时执照：** 在评估期间获取临时许可证以获得完全访问权限。
- **购买：** 如果您发现它适合您的长期需求，请考虑购买。

### 基本初始化
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// 您的代码在这里...
pres.dispose(); // 完成后务必处置演示对象。
```

## 实施指南
现在，让我们将每个功能分解为易于管理的步骤。

### 使用簇状柱形图创建演示文稿
#### 概述
本节介绍如何创建空演示文稿并在幻灯片上的特定坐标处添加簇状柱形图。

**步骤：**
1. **初始化演示对象：**
   - 创建新实例 `Presentation`。
2. **添加簇状柱形图：**
   - 使用 `getSlides().get_Item(0).getShapes().addChart()` 添加图表。
   - 指定位置、尺寸和类型。

**代码示例：**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // 在 (50, 50) 处添加一个簇状柱形图，宽度为 600，高度为 400。
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
了解如何清除现有系列并添加具有自定义数据点的新系列。

**步骤：**
1. **清除现有系列：**
   - 使用 `series.clear()` 删除任何预先存在的数据。
2. **添加新系列：**
   - 使用添加新系列 `series。add()`.
3. **插入数据点：**
   - 利用 `getDataPoints().addDataPointForBarSeries()` 用于添加值，包括负值。

**代码示例：**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // 清除现有系列并添加新系列。
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // 添加具有不同值（正值和负值）的数据点。
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

### 根据条件反转序列数据点
#### 概述
通过有条件地反转负数据点来定制其可视化。

**步骤：**
1. **设置默认反转行为：**
   - 使用 `setInvertIfNegative(false)` 确定整体反转行为。
2. **有条件地反转特定数据点：**
   - 申请 `setInvertIfNegative(true)` 如果为负数，则在特定数据点上。

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
    
    // 添加具有不同值（正值和负值）的数据点。
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
    
    // 设置默认反转行为
    series.get_Item(0).invertIfNegative(false);
    
    // 有条件地反转特定数据点
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### 结论
在本教程中，您学习了如何设置 Aspose.Slides for Java 并创建簇状柱形图。您还探索了如何管理数据系列以及如何自定义负数据点的可视化。掌握这些技能后，您现在可以自信地在 Java 应用程序中创建动态图表了。

**后续步骤：**
- 尝试使用 Aspose.Slides for Java 中可用的不同图表类型。
- 探索其他自定义选项以增强您的演示文稿。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}