---
date: '2026-03-20'
description: 了解如何在 PowerPoint 演示文稿中添加簇状柱形图、定制 PowerPoint 图表，以及使用 Aspose.Slides for
  Java 插入数据系列图表。
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: 如何使用 Aspose.Slides for Java 在 PowerPoint 中添加簇状柱形图
url: /zh/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 在 PowerPoint 中添加簇状柱形图

## 介绍

当您需要在 PowerPoint 演示文稿中**添加簇状柱形图**时，清晰的可视化可以将原始数字转化为一目了然的故事。手动在 PowerPoint 中完成此操作可能耗时，尤其是需要以编程方式生成大量幻灯片时。**Aspose.Slides for Java** 消除了这些障碍——只需几行代码即可创建、定制 PowerPoint 图表并插入数据系列图表。

在本教程中，您将学习如何：
- 使用 Aspose.Slides for Java 初始化一个新的 PowerPoint 演示文稿。
- **向幻灯片添加图表** 并将其配置为簇状柱形图。
- **通过为类别定义分组层级** 创建分组柱形图。
- **插入数据系列图表**，以正确显示您的数据。
- 将完成的演示文稿保存为 PPTX 文件。

在深入代码之前，让我们确保您已准备好所有必需的内容。

## 快速答疑
- **主要类是什么？** `Presentation` 来自 `com.aspose.slides`。
- **使用的图表类型是什么？** `ChartType.ClusteredColumn`。
- **测试是否需要许可证？** 免费试用可用，但许可证可去除评估限制。
- **支持的 Java 版本是什么？** JDK 16 或更高（示例使用 JDK 16）。
- **如何运行示例？** 添加 Maven/Gradle 依赖，编译并运行 `main` 方法。

## 什么是“添加簇状柱形图”？

*簇状柱形图*（也称为分组柱形图）在每个类别中并排显示多个数据系列，便于比较各组之间的数值。在 PowerPoint 中，此图表类型非常适合季度销售、调查结果或任何需要在同一类别中对比多个数据集的场景。

## 为什么使用 Aspose.Slides 添加簇状柱形图？

- **完整自动化** – 无需手动即可生成数十张幻灯片。
- **细粒度定制** – 控制颜色、标签、分组层级等。
- **跨平台** – 在任何支持 Java 的操作系统上运行。
- **无需安装 Office** – 可在服务器或 CI 流水线中生成 PPTX 文件。

## 前提条件

- **Aspose.Slides for Java** 库（建议使用最新版本）。
- JDK 16 或更高。
- Maven 或 Gradle 构建工具（或手动添加 JAR）。
- 用于运行 Java 代码的 IDE 或文本编辑器。

## 设置 Aspose.Slides for Java

使用以下构建脚本之一将库添加到项目中。

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

或者，您可以直接从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新发布版本。

### 许可证获取

在部署到生产环境之前，请获取许可证：

- **免费试用** – 在不购买的情况下探索所有功能。
- **临时许可证** – 在短期内评估扩展功能。
- **完整许可证** – 解锁无限使用。请从 [Aspose's purchase page](https://purchase.aspose.com/buy) 获取。

## 实现指南

我们将逐步演示每一步，同时解释**如何添加图表**以及**如何定制 PowerPoint 图表**。

### 初始化演示文稿

首先，创建一个新的 `Presentation` 对象并获取默认幻灯片。

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 向幻灯片添加图表

现在，我们使用 `ClusteredColumn` 类型**向幻灯片添加图表**并清除所有默认数据。

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### 准备图表数据工作簿

图表将数据存储在内部工作簿中。我们清除它以重新开始。

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### 添加带分组层级的类别

对类别进行分组可产生**分组柱形图**效果。每个类别可以属于一个逻辑组。

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### 向图表添加数据系列

这里我们**插入数据系列图表**条目，这些条目将以独立的柱形显示。

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### 保存带图表的演示文稿

最后，将 PPTX 文件写入磁盘。

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 实际应用

- **商业报告** – 比较各地区的季度收入。
- **学术研究** – 展示按测试条件分组的实验结果。
- **项目管理** – 在单张幻灯片上可视化多个团队的任务完成率。

## 性能考虑

- **内存管理** – 使用后释放大型工作簿。
- **批量操作** – 避免在紧密循环中更新图表；先收集数据，再一次性应用。
- **内置优化** – Aspose.Slides 提供如 `Presentation.optimize()` 的方法用于大型文件。

## 常见陷阱与技巧

- **陷阱：** 忘记清除已有的系列/类别可能导致数据重复。  
  **技巧：** 在填充新数据之前始终调用 `clear()`。

- **陷阱：** 使用错误的单元格地址（例如 `"c2"` 而不是 `"C2"`）。  
  **技巧：** 单元格引用不区分大小写，但为可读性请保持一致。

- **技巧：** 使用 `setGroupingItem` 创建有意义的分组标签；它们会自动出现在图例中。

## 常见问题解答

**Q1: 如何向图表添加多个系列？**  
A1: 反复调用 `ch.getChartData().getSeries().add()`，为每个系列提供唯一名称和数据点。

**Q2: Aspose.Slides 图表常见的哪些问题？**  
A2: 问题通常源于数据范围不匹配或缺少工作簿单元格。请确认每个类别和数据点都有对应的单元格。

**Q3: 我可以在其他编程语言中使用 Aspose.Slides 吗？**  
A3: 可以，Aspose 为 .NET、C++、Python 等提供了等效库。

**Q4: 如何更新演示文稿中已有的图表？**  
A4: 加载演示文稿，通过 `slide.getShapes().get_Item(index)` 定位图表，然后根据需要修改其系列或格式。

**Q5: Aspose.Slides 对图表类型有何限制？**  
A5: 该库支持广泛的图表类型，但请始终查阅最新文档以了解任何新添加或已弃用的类型。

## 资源

- **文档**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **下载**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **购买**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **免费试用**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **临时许可证**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **支持论坛**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-03-20  
**测试环境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose