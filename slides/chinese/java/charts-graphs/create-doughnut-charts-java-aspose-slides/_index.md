---
date: '2026-08-16'
description: 了解如何在 Java 中使用 Aspose.Slides 添加环形图。本分步指南涵盖 Maven 依赖设置、图表配置、颜色、标签以及保存
  PPTX。
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: 如何在 Java 中使用 Aspose.Slides 添加环形图。按照本指南设置 Maven、定制颜色、标签并生成 PPTX 文件。
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: 如何在 Java 中使用 Aspose.Slides 添加环形图
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: 如何在 Java 中使用 Aspose.Slides 添加环形图
url: /zh/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose.Slides 添加环形图

## 介绍

创建 **环形图** 的程序化方法可以将原始数字转化为引人注目的可视化效果，瞬间讲述一个故事。在 Java 中，**Aspose.Slides** 使这一过程变得简单，允许您在不打开 PowerPoint 的情况下生成可直接用于演示的图表。在本教程中，您将一步步学习 **如何向 PPTX 文件添加环形图**——从设置 Maven Aspose Slides 依赖到自定义系列、类别、颜色和标签，最后保存演示文稿。

通过本指南，您将能够将动态环形图嵌入任何 PPTX 文件，适用于报告、仪表盘或自动化幻灯片套件。

### 快速回答
- **使用的库是什么？** Aspose.Slides for Java  
- **主要任务？** 在 PPTX 文件中添加环形图  
- **如何添加库？** 使用 Maven Aspose Slides 依赖（或 Gradle）  
- **最低 Java 版本？** JDK 16 或更高  
- **可以自定义颜色和标签吗？** 可以，API 提供完整的格式控制  

## 什么是环形图以及为什么使用它？

环形图是带有空心中心的饼图变体，允许将多个数据系列显示为同心环。**它在多个类别之间可视化整体占比，同时在中心保留空间用于额外信息。** 这使其非常适合比较多个季度的地区销售、部门预算分配，或任何需要展示层级比例数据的场景。

## 为什么使用 Aspose.Slides for Java？

您可以在不安装 Microsoft Office 的情况下添加环形图，且该库支持 **超过 50 种输入和输出格式**，能够处理超过 500 张幻灯片的演示文稿。Aspose.Slides 在相同硬件上相比本地 Office 自动化 **渲染速度提升至 3 倍**，并且兼容 Windows、Linux 和 macOS。这些量化优势意味着您可以在无头服务器上生成大型幻灯片套件，性能可预测。

## 前置条件

- **必需的库**  
  - Aspose.Slides for Java 25.4 或更高（用于添加环形图的库）。  

- **环境**  
  - 已在机器上安装 JDK 16 或更高版本。  
  - 使用 IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE。  

- **知识**  
  - 基础 Java 语法和面向对象概念。  
  - 熟悉 Maven 或 Gradle 进行依赖管理。  

## Maven Aspose Slides 依赖

将以下 Maven 依赖添加到您的 `pom.xml` 中。这是您需要的 **maven aspose slides 依赖**，用于将库拉入项目。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

如果您更喜欢 Gradle，请使用下面的等效代码片段。

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

您也可以直接从官方发布页面下载 JAR 包：  
[ Aspose.Slides for Java 发布 ](https://releases.aspose.com/slides/java/)

### 获取许可证

要去除评估水印并解锁全部功能：

- **免费试用** – 使用临时许可证开始。  
- **临时许可证** – 从 [Aspose 网站](https://purchase.aspose.com/temporary-license/) 请求。  
- **商业许可证** – 购买用于生产环境。

在代码中应用许可证：

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## 实施指南

### 初始化演示文稿并添加环形图

Presentation 是 Aspose.Slides 中表示 PowerPoint 演示文稿的类。  
加载已有的 PPTX 或创建新的 `Presentation` 对象，然后在第一张幻灯片上添加环形图。

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### 配置图表数据工作簿并清除现有数据

工作簿是内部电子表格，用于存储图表的数据。  
获取支撑图表的工作簿，然后清除任何默认的系列或类别，以便从干净的状态开始。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 向图表添加系列

系列代表在图表上绘制的一组数据点。  
您可以添加最多 15 个系列。每个系列都可以自定义——这里我们设置了爆炸效果、环形孔大小和首片角度。

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### 添加类别和数据点

类别是图表轴上每个数据点的标签。  
创建 15 个类别并为每个系列填充数据点。最后一个系列会使用特殊的标签格式。

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### 自定义颜色和数据标签

`FillType.Solid` 指定图表元素的实色填充。  
为每个系列设置实色填充并启用数据标签。对于最后一个系列，我们还会更改标签字体颜色。

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### 保存演示文稿

`save` 将演示文稿写入指定格式的文件。  
将更新后的演示文稿以 PPTX 格式写入磁盘，或根据需要导出为 PDF。

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## 常见问题及解决方案

- **未找到许可证** – 验证 `license.lic` 的路径是否正确且文件可读。  
- **图表显示为空白** – 确保在添加新系列/类别之前已清除现有的系列/类别。  
- **颜色不正确** – 确认 `FillType.Solid` 已同时用于填充和线条格式。  
- **大量系列的性能问题** – 限制系列/类别的数量或复用工作簿单元格，以控制内存使用。  

## 常见问答

**Q: 能否在没有预先存在的 PPTX 文件的情况下生成环形图？**  
A: 可以，实例化 `new Presentation()` 从空白幻灯片套件开始，然后按上文所示添加图表。

**Q: Aspose.Slides 是否支持导出为 PDF？**  
A: 当然。创建图表后，调用 `pres.save("output.pdf", SaveFormat.Pdf);` 即可获得幻灯片的 PDF 版本。

**Q: 如何更改环形孔的大小？**  
A: 使用 `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`，其中 `value` 的取值范围为 0 到 100。

**Q: 是否可以为所有系列添加数据标签，而不仅仅是最后一个？**  
A: 可以，将标签格式化代码块移出 `if (i == ...)` 条件，应用到每个 `dataPoint`。

**Q: 支持哪些 Java 版本？**  
A: Aspose.Slides 25.4 支持 JDK 16 及以上。较早的 JDK 需要在 Maven 依赖中使用相应的 classifier。

---

**最后更新:** 2026-08-16  
**测试环境:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 相关教程

- [如何使用 Aspose.Slides for Java 向 PowerPoint 添加图表：一步步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [如何在 Java 中使用 Aspose.Slides 自定义饼图颜色 – 完整指南](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [使用 Aspose.Slides for Java 为 PowerPoint 图表类别添加动画 | 步骤指南](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}