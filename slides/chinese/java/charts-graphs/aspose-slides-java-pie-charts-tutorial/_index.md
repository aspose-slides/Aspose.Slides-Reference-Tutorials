---
date: '2026-07-17'
description: 了解如何使用 Aspose.Slides for Java 旋转饼图、定制饼图颜色，并将幻灯片导出为 PDF——完整的数据可视化指南。
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: 使用 Aspose.Slides for Java 旋转饼图并自定义饼图颜色。了解如何将幻灯片导出为 PDF 并处理图表数据工作表。
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: 在 Java 中旋转饼图并自定义颜色 – Aspose.Slides 指南
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: 如何在 Java 中使用 Aspose.Slides 旋转饼图并自定义颜色
url: /zh/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 创建饼图：完整教程

## 介绍
在本指南中，您将学习如何 **旋转饼图** 元素、为每个切片自定义颜色，并将最终幻灯片导出为 PDF——全部使用 Aspose.Slides for Java。无论您是在构建销售仪表板、财务报告，还是任何数据驱动的演示文稿，掌握这些技术都能让您在不依赖 Microsoft Office 的情况下呈现清晰、抢眼的可视化效果。准备好工具，开始吧。

## 快速答案
- **哪个类用于创建新演示文稿？** `Presentation` 来自 `com.aspose.slides`。
- **哪个 API 调用用于添加饼图？** `slide.addChart(ChartType.Pie, …)`。
- **如何为每个切片设置唯一颜色？** 调用 `series.setColorVaried(true)` 并为每个数据点设置实心填充。
- **哪个方法用于旋转图表？** `chart.setRotationAngle(double)` – 使用 0 到 360 的度数。
- **幻灯片可以导出为 PDF 吗？** 可以，调用 `presentation.save("output.pdf", SaveFormat.Pdf)`。

## 什么是“自定义饼图颜色”？
自定义饼图颜色指为饼图的每个切片分配不同的填充颜色，以提升可读性和视觉冲击力。在 Aspose.Slides 中，您只需启用多颜色模式，然后为各数据点设置实心填充颜色即可。这种做法确保每个数据段在演示文稿中都能清晰突出。

## 为什么使用 Aspose.Slides for Java 创建饼图？
Aspose.Slides 支持 **150+ 图表类型**，并且能够在普通服务器上在 **5 秒以内** 渲染 300 页的演示文稿，且无需安装 Microsoft Office。该库可在 Windows、Linux 和 macOS 上运行，为任何基于 Java 的数据可视化项目提供跨平台灵活性。

## 前置条件
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 或更高版本
- IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE
- 基础 Java 知识以及对 Maven 或 Gradle 的熟悉

## 设置 Aspose.Slides for Java
将库添加到构建配置中。

**Maven**  
在 `pom.xml` 文件中加入以下代码片段：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
在 `build.gradle` 文件中加入以下内容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载**  
如果您更倾向手动方式，可从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新的 JAR 包。

### 许可证获取步骤
- **免费试用** – 免费探索所有功能。  
- **临时许可证** – 在短期内扩展试用限制。  
- **购买** – 获取永久许可证用于生产环境。

**基本初始化和设置**  
`Presentation` 类表示内存中的 PowerPoint 文件，并提供操作幻灯片的方法。  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 实现指南
下面提供了一个逐步演练，涵盖从创建幻灯片到旋转最终饼图的全部过程。

### 初始化演示文稿和幻灯片
创建一个新的 `Presentation` 实例，并获取第一张幻灯片作为图表画布。  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### 向幻灯片添加饼图
`addChart` 在指定坐标处向幻灯片添加指定类型的图表形状。  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 设置图表标题
`setTitle` 为图表分配文本标题并居中显示。  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 为系列配置数据标签
`setShowValue(true)` 在系列的每个数据点上显示数值标签。  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 准备图表数据工作表
`ChartDataWorkbook` 存储为图表系列和类别提供数据的底层表格。  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 向图表添加类别
`addCategory` 为图表的数据系列创建新的类别标签。  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 添加系列并填充数据点
`addSeries` 创建数据系列，`addDataPointForBarSeries` 为每个类别插入数值。  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 自定义系列颜色和边框
`setColorVaried(true)` 启用每切片颜色，`setFillFormat` 为每个数据点分配实心填充。  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### 配置自定义数据标签
`setDataLabelFormat` 自定义标签的外观、位置和字体，以获得更清晰的图表注释。  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### 设置旋转角度并保存演示文稿
`setRotationAngle` 旋转整个饼图，`save` 将演示文稿写入文件。  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 如何旋转饼图？
加载图表对象，调用 `chart.setRotationAngle(45.0)`（或任意度数），然后保存演示文稿。旋转饼图会改变起始角度，使您能够在不改变数据的前提下突出显示特定切片。此单一方法调用适用于 Aspose.Slides 中的任何 `Chart` 实例。您还可以将旋转与多颜色切片结合使用，以强调最重要的数据点。

## 常见问题与解决方案
| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **切片全部显示相同颜色** | 未调用 `setColorVaried(true)` | 确保在系列组上启用多颜色模式。 |
| **数据标签未显示** | `showValue` 标志被禁用 | 对标签格式调用 `setShowValue(true)`。 |
| **旋转无效** | 使用了旧版本的 Aspose.Slides | 升级到 25.4 或更高版本。 |
| **运行时出现许可证异常** | 缺少或无效的许可证文件 | 在创建 `Presentation` 之前加载许可证：`License license = new License(); license.setLicense("Aspose.Slides.lic");` |

## 常见问答

**Q: 如何获取 Aspose.Slides 的 Java 许可证？**  
A: 在 Aspose 网站申请免费试用，然后购买永久许可证。运行时按上表所示加载许可证即可。

**Q: 这段代码能在旧版 JDK 上运行吗？**  
A: API 要求 JDK 16 或更高版本，不支持旧版 JDK。

**Q: 能否将图表导出为图像而不是 PPTX？**  
A: 可以——渲染后调用 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`。

**Q: 如果需要在饼图中使用多个系列怎么办？**  
A: 饼图设计为单一数据系列；若需多系列，请考虑使用环形图（doughnut chart）。

**Q: Aspose.Slides 能在 Linux 服务器上运行吗？**  
A: 完全可以——Aspose.Slides for Java 与平台无关，可在任何装有兼容 JDK 的操作系统上运行。

---

**最后更新：** 2026-07-17  
**测试环境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Slides 在 Java 演示文稿中创建饼图：完整指南](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [在 Java 中精通饼图使用 Aspose.Slides：完整指南](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [使用 Aspose.Slides 在 Java 中旋转图表文本：完整指南](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}