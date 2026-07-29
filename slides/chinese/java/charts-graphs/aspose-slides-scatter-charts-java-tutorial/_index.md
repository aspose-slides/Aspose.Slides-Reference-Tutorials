---
date: '2026-07-27'
description: 如何使用 Aspose.Slides for Java 自定义图表。学习创建 PowerPoint 图表、设置散点系列样式，并高效保存演示文稿。
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: 使用 Aspose.Slides for Java 自定义图表的指南。展示如何创建 PowerPoint 图表、设置散点点的样式以及导出演示文稿。
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 如何自定义图表：Java 中的 Aspose 散点图
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 如何自定义图表：Java 中的 Aspose 散点图
url: /zh/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 Java 中自定义 Aspose 散点图

在本教程中，您将了解 **如何自定义图表** — 特别是散点图 — 使用强大的 Aspose.Slides for Java 库。我们将逐步演示项目设置、创建散点图、调整系列类型和标记，最后保存演示文稿。完成后，您将能够以编程方式生成专业外观的散点图，并根据品牌或报告需求定制每个视觉细节。

## 快速答案
- **需要哪个库？** Aspose.Slides for Java (v25.4+).  
- **支持哪个 Java 版本？** JDK 8 or higher.  
- **我可以更改标记形状吗？** 是的 – 使用 `MarkerStyleType` 选择星形、圆形等。  
- **如何保存文件？** Call `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **是否需要许可证？** 免费试用可用于开发；生产环境需要商业许可证。

## 如何使用 Aspose.Slides 在 Java 中自定义图表？
`Presentation` 是 Aspose.Slides 类，表示内存中的整个 PowerPoint 文件。加载一个新的 `Presentation`，在第一张幻灯片上添加散点图，配置系列和标记样式，然后调用 `save`。这一工作流只需几行 Java 代码即可创建完整样式的图表，随时可嵌入任何 PowerPoint 演示文稿。

## 什么是 “customize scatter chart aspose”？
使用 Aspose 自定义散点图是指通过编程方式定义图表的数据、外观和行为——从点坐标到标记符号——而无需手动打开 PowerPoint。这种方法非常适合自动化报告、数据驱动的演示或任何需要可重复、高质量可视化的场景。

## 为什么使用 Aspose.Slides 自定义散点图？
Aspose.Slides 为开发者提供对图表外观的完整编程控制，能够自动创建高质量可视化，轻松集成到报告流水线，并且可以在不手动打开 PowerPoint 的情况下自定义每个视觉元素，从而节省时间并确保演示文稿的一致性。

- **完全控制** – 通过 Java 代码修改系列类型、标记样式、颜色等。  
- **自动化** – 在仪表板或批量报告中即时生成数十个图表。  
- **跨平台** – 在任何支持 Java 的操作系统上运行，无需安装 Office。  
- **性能** – 轻量级 API，可处理 **150+ 图表类型**，并在不将整个文件加载到内存的情况下处理数百页的演示文稿。

## 前置条件

要跟随本教程，请确保您拥有：

- **Aspose.Slides for Java**（v25.4 或更高）。  
- **Java Development Kit (JDK)** 8 及以上已安装。  
- Maven 或 Gradle 用于依赖管理（或可手动下载 JAR）。  
- 基本的 Java 知识以及对所选构建工具的熟悉。

## 设置 Aspose.Slides for Java

使用以下方法之一将库集成到您的项目中。

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或从 [Aspose Releases](https://releases.aspose.com/slides/java/) 获取最新发布版本。

#### 许可证获取
- **Free Trial** – 30 天评估。  
- **Temporary License** – 延长测试期。  
- **Full License** – 生产使用并提供高级支持。

## 步骤指南：自定义 Aspose 散点图

### 1️⃣ 为演示文件准备文件夹
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*为什么这很重要:* 确保输出文件夹存在，可防止在后续保存 PPTX 时出现 `FileNotFoundException`。

### 2️⃣ 创建新演示文稿并获取第一张幻灯片
`Presentation` 代表 PowerPoint 文档，并提供对幻灯片和形状的访问。`Presentation` 类在内存中表示整个 PowerPoint 文件。  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ 添加带平滑线的散点图
`ChartType.ScatterWithSmoothLines` 创建一个点通过平滑线连接的散点图。  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ 清除所有默认系列并添加自定义系列
`IChartSeries` 表示图表中的数据系列。  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ 用数据点填充第一个系列
`addDataPointForScatterSeries` 向散点系列添加单个 X‑Y 点。  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ 自定义系列类型和标记外观
`Marker` 控制图表系列中每个数据点使用的视觉符号。  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ 保存演示文稿
`save` 将演示文稿写入指定格式的文件。  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 定制散点图的常见用例
- **Financial dashboards** – 绘制股票价格与成交量的关系。  
- **Scientific research** – 使用误差标记显示实验测量值。  
- **Project management** – 对比任务的计划工作量与实际工作量。

## 性能提示
- 保存后调用 `pres.dispose()` 以释放本机内存。  
- 对于大数据集，先填充工作簿再绑定系列，以避免重复的 UI 刷新。  
- 在添加多个系列时复用单个 `IChartDataWorkbook` 实例，以降低内存使用。

## 常见问题

**Q: 如何更改标记的颜色？**  
A: 使用 `series.getMarker().getFillFormat().setFillColor(Color)`，其中 `Color` 为 `java.awt.Color` 实例，例如 `Color.RED`。

**Q: 我可以向散点图添加超过两个系列吗？**  
A: 可以。对每个额外的系列调用 `chart.getChartData().getSeries().add(...)`，并相应地填充其数据点。

**Q: 能为每个系列设置自定义图例吗？**  
A: 完全可以。在创建系列后，调用 `series.getLegend().setText("Your Legend Text")` 来覆盖默认名称。

**Q: 如何将图表导出为图像而不是 PPTX？**  
A: 在配置图表后，调用 `chart.getImage().save("chart.png", ImageFormat.Png)`。这将生成独立的 PNG 文件。

**Q: 如果需要为散点添加动画怎么办？**  
A: Aspose.Slides 支持动画效果。使用 `chart.getTimeline().getMainSequence().addEffect(...)` 为图表或单个系列添加进入或强调动画。

---

**最后更新：** 2026-07-27  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Slides 在 Java 中创建和自定义 PowerPoint 图表](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中创建气泡图（教程）](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [在 Aspose.Slides for Java 中创建和自定义带趋势线的图表](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}