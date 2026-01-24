---
date: '2026-01-24'
description: 学习如何使用 Aspose.Slides for Java 创建图表，包括百分比堆叠柱形图设置、坐标轴格式化和数据标签自定义。
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: 如何使用 Aspose.Slides Java 创建堆叠柱形图表
url: /zh/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握 Java 中的堆叠柱形图（使用 Aspose.Slides）：全面指南

## Introduction

通过使用 Aspose.Slides for Java 的强大功能，将深入的数据可视化融入您的演示文稿，提升其表现力。在本教程图表**驱动的幻灯片，将原始数据转化为清晰的故事——无论是编写业务报告、项目仪表盘还是形图**以及自定义坐标轴、系列和数据标签，使最终的幻灯片呈现出精致专业的效果。  
让我们开始创建能够吸引观众的演示文 **主要库是什么？** Aspose.Slides for Java
- **哪个 Maven 构件添加该库？** `com.aspose:aspose-slides`（参见 *aspose slides maven* 部分）
- **如何添加百分比堆叠柱形图？** 在调用 `addChart` 时使用 `ChartType.PercentsStackedColumn`
- **可以格式化图表坐标将多个数据子中，使您能够在比较整体规模的同时，仍然看到每个组成部分的贡献。**百分比堆叠柱形图**则将每根柱子标准化为 100 %，非常适合展示各类别的比例数据。

## Why Use Aspose.Slides for Java?
- **无需安装 Office** – 可在任何服务器上生成 PPTX 文件。
- **功能完整的图表 API** – 支持所有图表类型，包括百分比堆叠柱形图。
- **跨平台兼容** – 可在 Windows、Linux 和 macOS 上运行。
- **轻松的 Maven/Gradle 集成** – 请参见下面的 *aspose slides maven* 代码片段。

## Prerequisites
- **Java 开发工具包 (JDK)：** 8 或更高版本。
- **IDE：** IntelliJ IDEA、Eclipse 或任何兼容 Java 的编辑器。
- **构建工具（可选）：** 用于依赖管理的 Maven 或 Gradle。
- **基本的 Java 知识** – 您应熟悉类、方法和集合。

## Setting Up Aspose.Slides for Java
要开始使用，您需要在项目中引入 Aspose.Slides 库。

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载：**  
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新的 JAR。

### License Acquisition
您可以先使用免费试用版来体验 Aspose.Slides 功能。若要去除评估限制，请考虑获取临时或正式许可证。

- **免费试用：** 在不产生费用的情况下访问受限功能。  
- **临时许可证：** 可通过 [Aspose 的网站](https://purchase.aspose.com/temporary-license/) 申请。  
- **购买：** 前往购买页面获取完整功能。

### Basic Initialization
以下是在 Java 应用程序中初始化 Aspose.Slides 的方式：  
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

## How to Create Chart: Step-by-Step Guide

### Creating a Presentation and Adding a Slide
**概述：** 首先创建一个带有初始幻灯片的简单演示文稿。这是后续增强的基础。

#### 步骤 1：初始化演示文稿对象
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
```java
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**概述：** 通过添加**百分比堆叠柱形图**来增强幻灯片，实现轻松的数据比较。

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

### Customizing Chart Axis Number Format
**概述：** 自定义图表垂直坐标轴的数字格式，以提升可读性。

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

### Adding Series and Data Points to Chart
**概述：** 为图表添加**系列数据**，使其信息丰富且视觉上更具吸引力。

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

### Formatting Series Fill Color
**概述：**充颜色来提升图表的美观度。

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

### Formatting Data Labels
**概述：** 通过**格式化图表数据标签**显示自定义文本，使数据标签更易读。

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

## Common Use Cases
- **季度销售仪表盘** – 将产品线贡献以总收入的百分比形式可视化。  
- **项目资源分配** – 在单根柱子中展示团队成员在各任务之间的分配情况。  
- **调查结果** – 对比多个问题的答案分布。

## Frequently Asked Questions

**问：生成堆叠柱形图是否需要付费许可证？**  
答：免费试用版可以创建图表，但正式许可证会去除评估水印并解锁全部功能。

**问：创建后可以更改图表类型吗？**  
答：可以，您可以通过删除现有形状并使用不同的 `ChartType` 添加新图表来替换它。

**问：如何将演示文稿导出为 PDF？**  
答：在完成幻灯片编辑后，使用 `presentation.save("output.pdf", SaveFormat.Pdf);`。

**问：API 是否兼容 Java 11 及更高版本？**  
答：完全兼容。该库支持 JDK 8 到 JDK 21；只需选择相应的 classifier（例如 `jdk16`）。

**问：如果需要添加超过三个系列怎么办？**  
答：只需重复添加系列的代码块，并为每个新系列调整工作表单元格引用。

## Conclusion
通过设置 Maven/Gradides   
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}