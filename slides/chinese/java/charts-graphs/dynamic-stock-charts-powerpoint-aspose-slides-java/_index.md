---
date: '2026-09-12'
description: 了解如何使用 Maven Aspose Slides 在 PowerPoint 中通过 Java 添加和自定义动态股票图表。内容包括环境设置、添加数据系列、线条格式化以及保存。
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides 教程展示了如何使用 Java 在 PowerPoint 中创建和自定义动态股票图表，涵盖数据系列、线条格式化和保存。
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: Maven Aspose Slides 指南：在 PowerPoint 中创建动态股票图表
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: Maven Aspose Slides：使用 Java 在 PowerPoint 中创建动态股票图表
url: /zh/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides：使用 Java 在 PowerPoint 中创建动态图表

## 介绍

**Maven Aspose Slides** 让您可以使用 Java 以编程方式生成复杂的 PowerPoint 演示文稿。在本教程中，您将学习如何创建动态图表、添加和格式化数据系列、定制图表线条，最后保存文件。无论您是准备季度报告的金融分析师，还是构建自动化幻灯片的开发者，以下步骤都提供了完整的生产就绪解决方案。

**您将学习**
- 如何使用 Maven 设置 Aspose.Slides for Java  
- 如何添加股票图表并清除默认数据  
- 如何**添加数据系列图表**并**格式化图表线条**  
- 如何**customize chart java**‑特定的可视元素  
- 如何保存更新后的演示文稿

准备好将原始数字转换为引人注目的股票可视化了吗？让我们开始吧！

## 快速答案
- **需要哪个 Maven 构件？** `aspose-slides` 版本 25.4（或更高）。  
- **可以在任何操作系统上运行吗？** 是的——该库是纯 Java 的，可在 Windows、macOS 和 Linux 上运行。  
- **开发需要许可证吗？** 免费的临时许可证可用于测试；生产环境需要正式许可证。  
- **支持哪些图表类型？** 超过 70 种内置图表类型，包括 Stock、Line 和 Bar 图表。  
- **我可以处理多大的演示文稿？** Aspose.Slides 能在不将整个文件加载到内存的情况下处理 500+ 幻灯片的文件。

## 什么是 Maven Aspose Slides？

`Aspose.Slides for Java` 是一个 Java API，能够在没有 Microsoft Office 的情况下创建、操作和转换 PowerPoint 文件。Maven 集成简化了依赖管理，让您可以直接从 Maven Central 拉取库。

## 为什么在股票图表中使用 Maven Aspose Slides？

Aspose.Slides 支持 **70+ 图表类型**，并且能够在典型服务器硬件上在不到一秒的时间内渲染数百页的演示文稿。其 **high‑low line** 和 **up/down bar** 功能为您提供对金融可视化的精确控制，远超 PowerPoint UI 所能提供的。

## 前置条件

- **Java Development Kit (JDK)** – 版本 11 或更高。  
- **IDE** – IntelliJ IDEA、Eclipse 或您喜欢的任何编辑器。  
- **Aspose.Slides for Java** – 版本 25.4（撰写时的最新版本）。  

### 设置 Aspose.Slides for Java

#### Maven
要使用 Maven 将 Aspose.Slides 集成到项目中，请在 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
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

#### Gradle
对于 Gradle 用户，请在 `build.gradle` 中加入以下内容：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接下载
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新的 JAR。

**许可证获取** – 首先使用免费试用或请求临时许可证。商业使用需购买正式许可证。

有关详细的 API 参考，请参阅 [Aspose.Slides documentation](https://docs.aspose.com/slides/java/)。

## 如何一步步创建动态图表

加载演示文稿，添加股票图表，清除默认数据，然后注入您自己的系列和类别。核心问题的直接答案是：

> 加载现有的 PPTX（使用 `new Presentation("template.pptx")`），添加类型为 `ChartType.Stock` 的 `Chart`，清除其默认系列和类别，然后使用您自己的数据点和格式选项填充。最后，调用 `presentation.save("output.pptx", SaveFormat.Pptx)`。

### 初始化演示文稿
#### 概述
首先加载现有的 PowerPoint 文件，以便就地修改。

#### 步骤说明
1. **导入库** – `Presentation` 类是所有幻灯片操作的入口点。  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **加载演示文稿文件** – 提供模板 PPTX 的路径。  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 向幻灯片添加股票图表
#### 概述
在演示文稿的第一页插入股票图表。

`Chart` 类表示可以添加到幻灯片的图表形状。

#### 直接答案
通过调用 `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` 来添加股票图表。这会创建一个可立即操作的图表对象。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 清除图表中现有的数据系列和类别
#### 概述
移除任何预先填充的系列或类别，以便从干净的数据集开始。

`ChartData` 对象保存图表的系列和类别。

#### 直接答案
调用 `chart.getChartData().getSeries().clear()` 和 `chart.getChartData().getCategories().clear()`，在添加自己的内容之前清除默认数据。

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 向图表数据添加类别
#### 概述
定义 X 轴类别（例如日期），用于分组您的股票数值。

`ChartCategory` 表示图表的 X 轴标签。

#### 直接答案
使用 `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` 为每个标签创建新的 `ChartCategory`，并对每个月或期间重复此操作。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 向图表添加数据系列
#### 概述
添加四个关键系列：Open、High、Low 和 Close。

`ChartSeries` 保存图表中特定系列的数据点集合。

#### 直接答案
对于每个系列，调用 `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`。这会将系列注册到图表的数据工作簿中。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 向系列添加数据点
#### 概述
为每个系列填充代表股票价格的数值。

`DataPoint` 表示系列中的单个数值。

#### 直接答案
遍历您的数据集合，使用 `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)`（或适用于该系列类型的相应方法）插入每个点。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 格式化高低线和上下条形
#### 概述
调整高低连接线和上下条形填充的视觉样式。

`Marker` 定义数据点的可视符号。

#### 直接答案
设置 `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` 并配置 `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` 以控制线条粗细和颜色。

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### 显示上下条形
使用图表的 `setShowUpDownBars(true)` 方法使上下条形可见。

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### 自定义高低线上的数据标签
#### 概述
在高低线上直接显示数值，以便快速参考。

`DataLabel` 控制附加到数据点的标签外观。

#### 直接答案
使用 `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` 启用数据标签，并根据需要进行样式设置。

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### 设置上下条形填充颜色
#### 概述
为上升条形设置绿色填充，为下降条形设置红色填充，以直观传达市场走势。

`UpDownBars` 对象提供对上升和下降条形格式的访问。

#### 直接答案
使用 `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` 并将实色设置为 `Color.GREEN`；对下降条形使用 `Color.RED` 重复相同操作。

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### 保存 PowerPoint 文件
#### 概述
将更改持久化为新的 PPTX 文件。

`save` 方法将演示文稿以指定格式写入磁盘。

#### 直接答案
调用 `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` —— 这会将修改后的演示文稿以标准 PowerPoint 格式写入磁盘。

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## 常见问题与故障排除

- **图表未显示** – 确保图表的 X/Y 坐标和尺寸在幻灯片范围内。  
- **数据点缺失** – 验证数据工作簿的单元格索引与您要填充的系列/行匹配。  
- **许可证异常** – 临时试用许可证在 30 天后过期；在生产构建中请使用永久许可证。  
- **大文件性能下降** – 如果批量处理数千张幻灯片，可使用 `Presentation.setCacheSize(0)` 禁用缓存。

## 常见问答

**问：我可以在 Web 应用程序中使用此代码吗？**  
答：可以。该库是纯 Java 的，您可以在任何 servlet 容器或 Spring Boot 服务中运行。

**问：Aspose.Slides 除了 Stock 外还支持其他图表类型吗？**  
答：当然。它支持超过 70 种图表类型，包括 Line、Bar、Pie 和 Radar 图表。

**问：如何以编程方式添加图表标题？**  
答：使用 `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`，然后根据需要格式化标题。

**问：每个系列的数据点数量有上限吗？**  
答：实际上，您可以添加数万条数据点；内存使用呈线性增长，库会流式处理数据以保持占用低。

**问：最新版本应使用哪个 Maven 坐标？**  
答：最新版本始终可在 Maven Central 上通过 `com.aspose:aspose-slides:25.4`（或更高）获取。

---

**最后更新：** 2026-09-12  
**测试环境：** Aspose.Slides for Java 25.4  
**作者：** Aspose

## 相关教程

- [aspose slides maven 依赖：使用 Aspose.Slides for Java 在演示文稿中添加和配置图表](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [创建 PowerPoint 图表 Java – 使用 Aspose.Slides 保存带图表的演示文稿](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [创建并格式化 PowerPoint 图表 Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}