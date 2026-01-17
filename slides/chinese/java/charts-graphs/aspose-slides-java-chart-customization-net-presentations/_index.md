---
date: '2026-01-17'
description: 了解如何在 .NET 演示文稿中使用 Aspose.Slides for Java 添加系列到图表并自定义堆积柱形图。
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: 在 .NET 中使用 Aspose.Slides for Java 向图表添加系列
url: /zh/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握在 .NET 演示文稿中使用 Aspose.Slides for Java 进行图表自定义

## 介绍
在数据驱动的演示文稿领域，图表是将原始数字转化为引人入胜的视觉故事的必备工具。当您需要以编程方式 **add series to chart**，尤其是在 .NET 演示文件内部时，这项任务可能会让人感到压力山大。幸运的是，**Aspose.Slides for Java** 提供了强大且语言无关的 API，使图表的创建和自定义变得直截了当——即使您的目标格式是 .NET PPTX。

在本教程中，您将学习如何 **add series to chart**，如何 **how to add chart** 堆叠柱形图类型，以及如何微调诸如间隙宽度等视觉细节。完成后，您将能够生成动态、数据丰富且外观精致的幻灯片。

**您将学习**
- 如何使用 Aspose.Slides 创建空白演示文稿  
- 如何 **add stacked column chart** 到幻灯片  
- 如何 **add series to chart** 并定义类别  
- 如何填充数据点并调整视觉设置  

让我们准备好开发环境。

## 快速答疑
- **启动演示文稿的主要类是什么？** `Presentation`  
- **哪个方法向幻灯片添加图表？** `slide.getShapes().addChart(...)`  
- **如何添加新系列？** `chart.getChartData().getSeries().add(...)`  
- **可以更改柱形之间的间隙宽度吗？** 可以，使用系列组上的 `setGapWidth()` 方法  
- **生产环境需要许可证吗？** 需要，有效的 Aspose.Slides for Java 许可证是必需的  

## 什么是 “add series to chart”？
向图表添加系列意味着插入一个新的数据集合，图表将其渲染为独立的可视元素（例如新的柱形、线条或切片）。每个系列可以拥有自己的数值、颜色和格式，从而实现多数据集的并排比较。

## 为什么使用 Aspose.Slides for Java 来修改 .NET 演示文稿？
- **跨平台**：一次编写 Java 代码，即可针对 .NET 应用使用的 PPTX 文件。  
- **无需 COM 或 Office 依赖**：可在服务器、CI 管道和容器中运行。  
- **丰富的图表 API**：支持 50 多种图表类型，包括堆叠柱形图。  

## 前提条件
1. **Aspose.Slides for Java** 库（版本 25.4 或更高）。  
2. Maven 或 Gradle 构建工具，或手动下载 JAR。  
3. 基础的 Java 知识以及对 PPTX 结构的了解。  

## 设置 Aspose.Slides for Java
### Maven 安装
在您的 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安装
在您的 `build.gradle` 文件中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
或者，从官方发布页面获取最新 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**许可证获取**  
先通过 [here](https://purchase.aspose.com/temporary-license/) 下载临时许可证进行免费试用。生产环境请购买完整许可证以解锁全部功能。

## 步骤实现指南
下面的每一步都附有简洁的代码片段（保持原教程不变），以及对其作用的说明。

### 步骤 1：创建空白演示文稿
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*我们从一个全新的 PPTX 文件开始，这为添加图表提供了画布。*

### 步骤 2：向幻灯片添加堆叠柱形图
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*`addChart` 方法创建一个 **add stacked column chart** 并将其放置在幻灯片的左上角。*

### 步骤 3：向图表添加系列（主要目标）
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*这里我们 **add series to chart** ——每次调用都会创建一个新的数据系列，显示为独立的柱形组。*

### 步骤 4：向图表添加类别
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*类别充当 X 轴标签，为每根柱形赋予意义。*

### 步骤 5：填充系列数据
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*数据点为每个系列提供数值，图表将其渲染为柱形的高度。*

### 步骤 6：设置图表系列组的间隙宽度
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*调整间隙宽度可以提升可读性，尤其是在类别较多时。*

## 常见使用场景
- **财务报告**——比较各业务单元的季度收入。  
- **项目仪表盘**——显示各团队的任务完成百分比。  
- **营销分析**——并排可视化不同活动的表现。  

## 性能提示
- **在创建多个图表时复用 `Presentation` 对象**，以降低内存开销。  
- **仅保留必要的数据点**，避免冗余信息影响视觉效果。  
- **在保存后调用 `presentation.dispose()`** 释放资源。  

## 常见问题解答
**Q: 我可以添加堆叠柱形图之外的其他图表类型吗？**  
A: 可以，Aspose.Slides 支持折线图、饼图、面积图等多种图表类型。

**Q: .NET 输出需要单独的许可证吗？**  
A: 不需要，同一份 Java 许可证适用于所有输出格式，包括 .NET PPTX 文件。

**Q: 如何更改图表的配色方案？**  
A: 使用 `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` 并设置所需的 `Color`。

**Q: 能否以编程方式添加数据标签？**  
A: 完全可以。调用 `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` 即可显示数值。

**Q: 如果需要更新已有的演示文稿该怎么办？**  
A: 使用 `new Presentation("existing.pptx")` 加载文件，修改图表后再保存即可。

## 结论
现在，您已经掌握了完整的 **add series to chart**、创建 **stacked column chart** 并在 .NET 演示文稿中使用 Aspose.Slides for Java 微调外观的全流程。尝试不同的图表类型、颜色和数据源，构建出能够打动利益相关者的精彩可视化报告。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose