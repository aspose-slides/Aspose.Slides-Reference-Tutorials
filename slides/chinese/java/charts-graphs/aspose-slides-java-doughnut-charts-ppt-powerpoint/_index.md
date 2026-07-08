---
date: '2026-07-08'
description: 了解如何使用 Aspose 在 PowerPoint 中使用 Java 创建环形图。此分步指南展示了如何以编程方式添加图表数据点、定制标签以及以高保真度保存
  PPTX。
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: 使用 Aspose 可在 PowerPoint 中通过 Java 创建环形图。按照本教程添加数据点、定制标签，并以高保真度保存 PPTX。
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 如何使用 Aspose：在 PowerPoint (Java) 中创建环形图
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: 如何使用 Aspose 在 PowerPoint (Java) 中创建环形图
url: /zh/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint（Java）中使用 Aspose 创建环形图

## 介绍
创建引人入胜的演示文稿往往不仅仅需要文字和图片；图表能够通过有效地可视化数据显著提升叙事效果。**如何使用 Aspose** 进行图表生成让您无需打开 PowerPoint 即可实现编程控制。本文教程将手把手教您构建环形图、配置数据点并保存高保真 PPTX。您只需具备基本的 Java 知识，几分钟即可完成环境搭建。

`Aspose.Slides for Java` 是一个 Java 库，可在不依赖 Microsoft Office 的情况下创建、操作和转换 PowerPoint 文件。

## 快速答案
- **哪个库可以在 PowerPoint 中创建环形图？** Aspose.Slides for Java  
- **可以通过代码添加图表数据点吗？** 可以，使用图表 API  
- **生产环境需要许可证吗？** 需要有效的 Aspose.Slides 许可证  
- **支持哪些 Java 版本？** Java 8 及以上（示例中使用 JDK 16 分类器）  
- **最多可以添加多少系列？** 示例最多添加 15 系列，您可以根据需要自行调整  

## PowerPoint 中的环形图是什么？
环形图是一种圆形图表，类似于饼图，但中心为空心，可同时显示多个系列。它在保持布局紧凑、易读的同时，突出部分与整体的关系。

## 为什么使用 Aspose.Slides for Java 创建环形图？
Aspose.Slides for Java 支持超过 50 种输入和输出格式，且可在不将整个文件加载到内存的情况下生成最高 500 MB 的演示文稿。它在任何 Java 平台上提供对图表外观、数据和布局的完整编程控制，消除 COM 互操作，并且在普通服务器上可在两秒内渲染 100 张包含图表的幻灯片。

## 前置条件
- 基础的 Java 编程知识。  
- IntelliJ IDEA 或 Eclipse 等 IDE。  
- 用于依赖管理的 Maven 或 Gradle。  
- 有效的 Aspose.Slides for Java 许可证（提供免费试用）。

## 设置 Aspose.Slides for Java
选择适合您项目的依赖管理工具。

**Maven**  
在 `pom.xml` 中添加以下依赖（将版本号替换为最新发布）：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
在 `build.gradle` 中添加此行：

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

如果您更倾向于直接下载，请访问 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 页面。

### 许可证获取
您可以先使用免费试用版探索 Aspose.Slides 功能。若需长期使用，请购买许可证或从 [Aspose 的网站](https://purchase.aspose.com/temporary-license/) 申请临时许可证。按照提供的说明设置环境并在应用程序中初始化 Aspose.Slides。

## 如何使用 Aspose.Slides for Java 在 PowerPoint 中创建环形图
构建环形图的步骤如下：加载或创建 `Presentation`，添加 `ChartType.Doughnut` 类型的图表形状，清除默认系列，设置孔径大小，然后在图表工作簿中填充类别名称和数值。最后，调整标签格式并保存 PPTX。

### 步骤 1：初始化演示文稿
创建一个新的演示文稿或打开已有文件以获取幻灯片集合。

`Presentation` 是表示 PowerPoint 文件的主要类。  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 步骤 2：向幻灯片添加环形图
插入图表形状，移除默认系列/类别，并配置基本视觉设置，如环形孔径大小。

`Chart`（或图表形状）代表放置在幻灯片上的图表对象。  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 步骤 3：添加图表数据点并自定义标签
填充类别名称，为每个系列添加数据点，并微调标签格式（字体、颜色、位置）。此步骤演示了“添加图表数据点”的能力。

`Workbook` 提供对图表底层电子表格数据的访问，可在其中填充单元格。  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 步骤 4：保存更新后的演示文稿
将更改持久化为磁盘上的新 PPTX 文件。

`save` 将演示文稿写入指定格式的文件。  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## 实际应用场景
环形图非常适用于：
- **财务报告：** 可视化预算分配或费用构成。  
- **市场分析：** 展示竞争对手之间的市场份额分布。  
- **调查结果：** 以紧凑形式呈现分类调查数据。  
- **仪表板生成：** 结合数据库查询生成实时更新的幻灯片。

## 性能考虑
- **释放资源：** 保存后调用 `pres.dispose()` 以释放本机内存。  
- **限制图表数量：** 添加数百个图表会增加内存占用，必要时采用批处理。  
- **使用流式处理：** 对于海量数据集，直接从流填充工作簿，而非使用内存数组。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **图表显示为空白** | 数据单元格未正确填充 | 确认 `workBook.getCell(...)` 引用了正确的行/列索引。 |
| **标签重叠** | 类别过多导致空间不足 | 增大 `DoughnutHoleSize` 或调整 `FirstSliceAngle`。 |
| **OutOfMemoryError** | 大型演示文稿未释放资源 | 保存后调用 `pres.dispose()`，并考虑增大 JVM 堆大小。 |

## 常见问答

**问：可以在商业应用中使用 Aspose.Slides for Java 吗？**  
答：可以，但需要有效的商业许可证。提供免费试用供评估。

**问：如何添加超过 15 系列？**  
答：在“添加环形图”步骤中增加循环上限，并确保工作簿中有足够的行。

**问：创建后可以修改环形孔径大小吗？**  
答：可以，在保存前调用 `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`。

**问：能将图表导出为图像而不是 PPTX 吗？**  
答：完全可以。使用 `chart.getImage()` 并将返回的 `java.awt.image.BufferedImage` 保存为所需格式。

**问：Aspose.Slides 支持动画图表吗？**  
答：可以通过 `ISlide.getTimeline()` API 添加动画，但超出本教程范围。

## 结论
现在，您已经掌握了使用 Aspose.Slides for Java **创建环形图 PowerPoint** 文件的完整、可投入生产的方法，包括如何 **添加图表数据点**、自定义标签以及处理性能问题。尝试不同的配色、数据源和图表类型，让您的演示文稿真正脱颖而出。

---

**最后更新：** 2026-07-08  
**测试环境：** Aspose.Slides for Java 25.4（JDK 16 分类器）  
**作者：** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 相关教程

- [如何使用 Aspose.Slides for Java 向 PowerPoint 添加图表：分步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [如何使用 Aspose.Slides for Java 编辑 PowerPoint 图表数据：完整指南](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [使用 Aspose.Slides for Java 为 PowerPoint 动画图表 – 分步指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}