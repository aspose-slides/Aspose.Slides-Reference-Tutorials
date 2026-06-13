---
date: '2026-03-07'
description: 学习如何使用 Aspose.Slides 在 Java 中创建环形图。本分步指南涵盖 Maven Aspose Slides 依赖设置、图表配置以及保存演示文稿。
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: 使用 Aspose.Slides 在 Java 中创建环形图指南
url: /zh/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 的 Java 环形图创建指南

## 介绍

以编程方式创建**环形图**可以将原始数字转化为引人注目的可视化效果，瞬间讲述故事。在 Java 中，**Aspose.Slides** 使此过程变得简单，让您无需打开 PowerPoint 即可生成可直接用于演示的图表。在本教程中，您将学习如何一步步**创建 Java 环形图**——从设置 Maven Aspose Slides 依赖到自定义系列、类别，最后保存演示文稿。

通过本指南，您将能够将动态环形图嵌入任何 PPTX 文件，非常适用于报告、仪表板或自动化幻灯片。

### 快速回答
- **使用的库是什么？** Aspose.Slides for Java  
- **主要任务？** 在 PPTX 文件中创建 Java 环形图  
- **如何添加库？** 使用 Maven Aspose Slides 依赖（或 Gradle）  
- **最低 Java 版本？** JDK 16 或更高  
- **我可以自定义颜色和标签吗？** 可以，API 提供完整的格式控制  

## 什么是环形图以及为何使用它？

环形图是带有空心中心的饼图变体，允许您在同心环中显示多个数据系列。这使其非常适合在多个类别中比较整体的各部分——比如按地区划分的多季度销售额或部门预算分配。

## 为什么使用 Aspose.Slides for Java？

- **无需安装 Office** – 在任何服务器上生成 PPTX 文件。  
- **丰富的 API** – 完全控制图表类型、数据点和样式。  
- **高性能** – 针对大型演示文稿进行优化。  
- **跨平台** – 在 Windows、Linux 和 macOS 上均可运行。  

## 前提条件

- **必需的库：**  
  - Aspose.Slides for Java 版本 25.4 或更高。  

- **环境设置：**  
  - JDK 16 或更高。  
  - 您喜欢的 IDE（IntelliJ IDEA、Eclipse、NetBeans 等）。  

- **知识前提：**  
  - 基础 Java 编程。  
  - 熟悉 Maven 或 Gradle 进行依赖管理。  

## Maven Aspose Slides 依赖

在您的 `pom.xml` 中添加以下 Maven 依赖。这是您需要将库引入项目的 **Maven Aspose Slides 依赖**。

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
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

您也可以直接从官方发布页面下载 JAR：  
[ Aspose.Slides for Java 发布 ](https://releases.aspose.com/slides/java/)

### 获取许可证

要去除评估水印并解锁完整功能集：

- **免费试用** – 使用临时许可证开始。  
- **临时许可证** – 从[ Aspose 网站](https://purchase.aspose.com/temporary-license/)请求。  
- **商业许可证** – 购买用于生产使用。  

在代码中应用许可证：

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 实现指南

### 初始化演示文稿并添加环形图

首先，创建或加载演示文稿，并在第一张幻灯片上添加环形图。

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 配置图表数据工作簿并清除现有数据

接下来，获取支撑图表的工作簿，并清除任何默认的系列或类别。

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### 向图表添加系列

现在我们将添加最多 15 个系列。每个系列都可以自定义——这里我们设置了爆炸半径、环形孔大小和第一切片角度。

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

### 添加类别和数据点

我们将创建 15 个类别，并为每个系列填充一个数据点。最后一个系列会使用特殊的标签格式。

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

### 保存演示文稿

最后，将更新后的演示文稿写入磁盘。

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 常见问题及解决方案

- **未找到许可证** – 验证 `license.lic` 的路径是否正确且文件可读。  
- **图表为空白** – 确保在添加新系列/类别之前已清除现有的系列/类别。  
- **颜色不正确** – 检查填充和线条格式是否都设置为 `FillType.Solid`。  
- **大量系列的性能** – 限制系列/类别的数量或复用工作簿单元格。  

## 常见问答

**问：我可以在没有预先存在的 PPTX 文件的情况下生成环形图吗？**  
**答：** 可以，实例化 `new Presentation()` 从空白幻灯片开始。

**问：Aspose.Slides 是否支持导出为 PDF？**  
**答：** 当然。创建图表后，调用 `pres.save("output.pdf", SaveFormat.Pdf);`。

**问：如何更改环形孔的大小？**  
**答：** 使用 `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`，其中 value 为 0‑100。

**问：是否可以为所有系列添加数据标签，而不仅仅是最后一个？**  
**答：** 可以，将标签格式化块移出 `if (i == ...)` 条件，并对每个 `dataPoint` 应用。

**问：支持哪些 Java 版本？**  
**答：** Aspose.Slides 25.4 支持 JDK 16 及更高版本。较早的 JDK 需要相应的分类器。

---

**最后更新：** 2026-03-07  
**测试环境：** Aspose.Slides for Java 25.4（jdk16 分类器）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}