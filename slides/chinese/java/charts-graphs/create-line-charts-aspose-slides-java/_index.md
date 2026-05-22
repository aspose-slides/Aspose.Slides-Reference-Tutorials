---
date: '2026-03-23'
description: 学习如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中创建带标记的折线图、添加第二个系列并处理空数据。
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 如何使用 Aspose.Slides for Java：创建带默认标记的折线图
url: /zh/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 创建带默认标记的折线图

## 介绍
如果你想了解 **如何使用 Aspose** 自动化 PowerPoint 的创建，你来对地方了。在本教程中，我们将演示如何构建 **带标记的折线图**、添加第二个系列以及处理空值数据——全部使用 Aspose.Slides for Java。完成后，你将拥有一段可直接运行的代码片段，生成专业外观的图表，而无需手动打开 PowerPoint。

### 快速答疑
- **需要哪个库？** Aspose.Slides for Java（推荐使用最新版本）  
- **可以添加第二个系列吗？** 可以——API 轻松支持添加多个系列。  
- **空数据点如何处理？** 在单元格值中使用 `null`；图表会自动跳过该点。  
- **需要 Maven 吗？** Maven 或 Gradle 都可，参见下文 *aspose slides maven* 部分。  
- **是否需要许可证？** 开发阶段可使用免费试用版；生产环境需要商业许可证。

## 如何使用 Aspose.Slides for Java 创建折线图
以编程方式创建图表可以为你节省大量手动排版时间，并确保演示文稿的一致性。无论是为报表工具构建 **创建 PowerPoint 图表** 功能，还是即时生成幻灯片套件，Aspose.Slides 都能让你通过 Java 代码全面掌控。

## 前置条件
在开始之前，请确保你的开发环境已就绪：

1. **库与依赖**
   - Aspose.Slides for Java 库（推荐版本 25.4）——涵盖 *aspose slides maven* 场景。
   - Java Development Kit (JDK) 16 或更高版本。
2. **环境配置**
   - 支持 Maven 或 Gradle 的 IDE。
   - 如在试用期外运行代码，请准备有效的 Aspose 许可证文件。
3. **知识准备**
   - 基础 Java 编程。
   - 熟悉 Maven 或 Gradle 构建文件。

## 设置 Aspose.Slides for Java
### Maven
在 `pom.xml` 文件中添加以下依赖：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
在 `build.gradle` 文件中加入：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接下载
或者，你可以从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

**获取许可证的步骤：**
- 免费试用，请访问 [free trial page](https://releases.aspose.com/slides/java/)。
- 获取临时许可证，请前往 [temporary license page](https://purchase.aspose.com/temporary-license/)。
- 购买正式许可证，请通过其 [purchase portal](https://purchase.aspose.com/buy)。

**基本初始化：**
下面演示如何在 Java 应用中初始化 Aspose.Slides：
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

现在，让我们开始创建图表吧！

## 实现指南
### 功能 1：创建带默认标记的图表
本节演示如何创建 **带标记的折线图**，非常适合在趋势线上突出显示各个数据点。

#### 添加折线图
添加带标记的折线图的代码如下：
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### 清除系列和类别
重新开始时使用：
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 功能 2：添加系列和类别
为图表填充有意义的数据，需要添加系列和类别。

#### 创建新系列
添加名为 “Series 1” 的新系列：
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### 填充类别和数据点
添加类别及对应的数据点：
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### 功能 3：添加第二个系列并填充数据点
添加额外的系列可以为可视化分析提供更深的洞察。

#### 创建并填充第二个系列
添加 “Series 2”：
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### 功能 4：配置图表图例
配置图例可以提升图表的可读性，尤其是在 **添加第二个系列** 时。

#### 调整图例设置
配置代码如下：
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### 功能 5：保存演示文稿
图表完成后，你需要 **创建 PowerPoint 图表** 文件，以便共享或进一步编辑。

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## 实际应用场景
1. **业务报告：** 使用带标记的折线图展示季度财务趋势。  
2. **数据分析：** 可视化实验数据，每个标记对应一次测量。  
3. **教学材料：** 制作演示幻灯片，展示过程的逐步变化。  
4. **项目管理：** 在时间轴上跟踪里程碑，为关键日期添加独特标记。  
5. **营销演示：** 用清晰的标记符号展示活动表现的峰值。

## 常见问题与解决方案
- **空数据点导致错误：** 将 `null` 作为单元格值传入（如示例所示）——Aspose 会自动省略该点。  
- **图表没有标记：** 确认使用 `ChartType.LineWithMarkers` 而非 `ChartType.Line`。  
- **图例覆盖数据：** 设置 `chart.getLegend().setOverlay(false)` 使图例保持独立。

## 常见问答

**问：我可以在 Web 服务中使用此方法生成图表吗？**  
答：完全可以。该库可在任何 Java 环境中运行，包括服务器端应用。

**问：开发构建是否需要许可证？**  
答：开发和测试阶段可使用免费试用版。生产环境必须使用商业许可证。

**问：Aspose 如何处理大数据集？**  
答：API 能高效流式处理数据，但建议控制数据点数量，以免生成过大的文件。

**问：是否支持其他图表类型？**  
答：支持——Aspose.Slides 包含柱形图、饼图、散点图等多种图表类型。

**问：我可以自定义标记的形状和颜色吗？**  
答：可以，通过每个数据点的 `Marker` 属性修改标记格式。

## 结论
现在，你已经掌握 **如何使用 Aspose** 创建带默认标记的折线图、添加第二个系列、处理空数据并将结果保存为 PowerPoint 文件。这些技巧可以帮助你实现报告自动化、提升数据叙事效果，并保持演示文稿的一致性。

想了解更深入的内容，请访问 [官方文档](https://docs.aspose.com/slides/java/) 或加入社区论坛（如 Stack Overflow）。

---

**最后更新：** 2026-03-23  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}