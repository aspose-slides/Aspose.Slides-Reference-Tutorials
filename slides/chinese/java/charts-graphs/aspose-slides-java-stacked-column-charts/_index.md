---
date: '2026-07-22'
description: 了解 Aspose Slides Maven Dependency，使用 Java 创建 Stacked Column Chart，添加
  Data Labels，修改 Vertical Axis Number Format，并将结果导出为 PPTX 文件。
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency 让您在 Java 中构建 Stacked Column Chart，自定义
  Data Labels，调整 Vertical Axis Format，并以 PPTX 保存——全部使用简洁、可投入生产的代码。
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: Aspose Slides Maven Dependency：Java 中的 Stacked Column Chart
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: Aspose Slides Maven Dependency：Java 中的 Stacked Column Chart
url: /zh/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven 依赖项：Java 中的堆叠柱形图

## 介绍

通过 **Aspose.Slides for Java** 的强大功能，将深刻的数据可视化融入演示文稿，提升展示效果。在本指南中，您将 **创建一个专业的堆叠柱形图**，无论是编写业务报告还是展示项目统计数据。完成本教程后，您将能够：

- 使用 **Aspose Slides Maven 依赖项** 设置开发环境
- 从零创建演示文稿
- **添加百分比堆叠图表** 并自定义外观
- **格式化图表数据标签** 并 **更改纵轴数字格式**
- 仅用一行代码 **将演示文稿保存为 PPTX** 文件

## 快速答案
- **需要哪个库？** 添加 `aspose-slides` Maven/Gradle 依赖（见下文 “Aspose Slides Maven 依赖项”）。  
- **哪种图表类型可以实现堆叠视图？** 使用 `ChartType.PercentsStackedColumn` 创建百分比堆叠柱形图。  
- **如何更改坐标轴数字格式？** 调用 `IAxis.setNumberFormat()` 并设置 `setNumberFormatLinkedToSource(false)`。  
- **可以自定义数据标签吗？** 可以——遍历每个 `IChartDataPoint` 并分配自定义的 `ITextFrame`。  
- **如何保存文件？** 调用 `presentation.save("output.pptx", SaveFormat.Pptx)`。

## 什么是堆叠柱形图？
堆叠柱形图在每个类别的柱子中垂直堆叠多个数据系列，**百分比堆叠** 变体会将每根柱子规范化为 100 %，便于比例比较。此格式使观众能够快速评估各组成部分在不同类别中的贡献，使趋势和相对大小一目了然。

## 为什么使用 Aspose.Slides for Java？
Aspose.Slides for Java 让您 **无需 Microsoft Office** 即可生成、编辑和转换 PowerPoint 文件，并支持 **50 多种输出格式**，兼容 Windows、Linux 和 macOS。该库完全运行在 JRE 上，适合服务器端自动化和高吞吐量报表。它还提供对图表对象、幻灯片布局和文档属性的细粒度控制，是企业级演示文稿生成的理想选择。

## 前置条件
- **Java Development Kit (JDK)：** 8 或更高版本  
- **IDE：** IntelliJ IDEA、Eclipse 或任意 Java 兼容编辑器  
- **构建工具：** Maven 或 Gradle（可选，但推荐）  
- **基本的 Java 知识** —— 您应熟悉类和方法的使用  

## 设置 Aspose.Slides for Java
首先，将 Aspose.Slides 库添加到项目中。

### Aspose Slides Maven 依赖项
在 `pom.xml` 中加入以下内容（这就是您需要的 **aspose slides maven 依赖项**）：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 替代方案
如果您更喜欢 Gradle，请在 `build.gradle` 中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新的 JAR 包。

### 许可证获取
您可以先使用免费试用版来探索 Aspose.Slides 功能。若要解除评估限制，请考虑获取临时或正式许可证。

- **免费试用：** 在不产生费用的情况下访问受限功能。  
- **临时许可证：** 通过 [Aspose 的网站](https://purchase.aspose.com/temporary-license/) 申请。  
- **购买：** 前往购买页面获取完整授权。

### 基本初始化
`Presentation` 是 Aspose.Slides 的核心类，表示内存中的 PowerPoint 文件。以下最小代码片段展示了如何创建 `Presentation` 对象：

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## 实现指南

### 创建演示文稿并添加幻灯片
**概述：**  
首先，我们将创建一个空白演示文稿，并验证幻灯片已成功创建。

#### 步骤 1：初始化 Presentation 对象
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 步骤 2：保存演示文稿
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### 向幻灯片添加百分比堆叠柱形图
**概述：**  
接下来，我们将在第一张幻灯片上放置一个 **百分比堆叠图表**。

`ChartType.PercentsStackedColumn` 指定了百分比堆叠柱形图类型。

#### 步骤 1：初始化并访问幻灯片
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### 步骤 2：向幻灯片添加图表
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### 自定义图表坐标轴数字格式
**概述：**  
为了提升可读性，我们将 **更改纵轴格式** 以显示百分比。

`IAxis` 是表示图表坐标轴的接口，允许进行格式和刻度的调整。

#### 步骤 1：添加并访问图表
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### 步骤 2：设置自定义数字格式
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### 向图表添加系列和数据点
**概述：**  
我们将为图表填充示例数据系列。

#### 步骤 1：初始化演示文稿和图表
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 步骤 2：添加数据系列
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### 格式化系列填充颜色
**概述：**  
为每个系列指定不同的颜色，使图表更易阅读。

#### 步骤 1：初始化并访问图表
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### 步骤 2：设置填充颜色
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### 格式化数据标签
**概述：**  
现在我们将 **格式化图表数据标签**，使其显示自定义文本。

`IChartDataPoint` 表示图表系列中的单个数据点，`ITextFrame` 保存标签文本。

#### 步骤 1：访问图表系列和数据点
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 步骤 2：自定义数据标签
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## 常见问题与解决方案
- **图表为空白：** 确保在保存之前已添加至少一个数据系列和数据点。  
- **坐标轴数字未显示百分比：** 记得设置 `verticalAxis.setNumberFormatLinkedToSource(false)`，否则自定义格式会被忽略。  
- **许可证评估信息仍然显示：** 在创建 `Presentation` 对象之前应用有效的许可证文件，以抑制评估横幅。

## 常见问答

**问：我可以在 Java 11 或更高版本中使用此代码吗？**  
**答：** 可以。库支持 JDK 8+；只需使用相应的分类器（例如 `jdk16` 适用于 JDK 16 及以上）。

**问：如何将图表导出为图像而不是 PPTX？**  
**答：** 在将图表添加到幻灯片后，使用 `chart.getImage().save("chart.png", ImageFormat.Png);`。

**问：是否可以为堆叠柱形图添加图例？**  
**答：** 完全可以。调用 `chart.getChartTitle().addTextFrameForOverriding("My Chart");` 并根据需要配置 `chart.getLegend()`。

**问：如果需要在生成演示文稿后更新数据怎么办？**  
**答：** 您可以修改 `ChartDataWorkbook` 单元格，然后调用 `chart.refresh();` 以反映更改。

**问：Aspose.Slides 能在 Linux 服务器上运行吗？**  
**答：** 能。该库是纯 Java 实现，可在任何装有兼容 JRE 的操作系统上运行。

## 结论
通过本指南，您已经学会了如何使用 **Aspose Slides Maven 依赖项** 在 Java 中 **创建堆叠柱形图**，从环境搭建到细致的视觉样式调优。尝试不同的数据集、颜色和标签格式，让您的报告真正脱颖而出。

---

**最后更新：** 2026-07-22  
**已测试版本：** Aspose.Slides 25.4（jdk16 分类器）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [How to create clustered column chart in Java with Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [How to Set Number Formats in Chart Data Points Using Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}