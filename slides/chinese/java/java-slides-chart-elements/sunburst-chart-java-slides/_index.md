---
title: Java 幻灯片中的旭日图
linktitle: Java 幻灯片中的旭日图
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 使用 Aspose.Slides 在 Java Slides 中创建令人惊叹的旭日图。逐步了解图表创建和数据处理。
weight: 16
url: /zh/java/chart-elements/sunburst-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 使用 Aspose.Slides 在 Java Slides 中介绍 Sunburst Chart

在本教程中，您将学习如何使用 Aspose.Slides for Java API 在 PowerPoint 演示文稿中创建旭日图。旭日图是一种用于表示分层数据的放射状图表。我们将提供分步说明以及源代码。

## 先决条件

开始之前，请确保已在 Java 项目中安装并配置了 Aspose.Slides for Java 库。您可以从以下网址下载该库[这里](https://releases.aspose.com/slides/java/).

## 步骤 1：导入所需库

首先，导入使用 Aspose.Slides 所需的库并在 Java 应用程序中创建 Sunburst 图表。

```java
import com.aspose.slides.*;
```

## 步骤 2：初始化演示文稿

初始化 PowerPoint 演示文稿并指定演示文稿文件的保存目录。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 步骤 3：创建旭日图

在幻灯片上创建旭日图。我们指定图表的位置 (X、Y) 和尺寸 (宽度、高度)。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## 步骤 4：准备图表数据

清除图表中所有现有类别和系列数据，并为图表创建数据工作簿。

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## 步骤 5：定义图表层次结构

定义旭日图的层次结构。您可以添加枝、茎、叶作为类别。

```java
//分支 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

//分支 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## 步骤 6：向图表添加数据

向 Sunburst 图表系列添加数据点。

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## 步骤 7：保存演示文稿

最后，保存带有旭日图的演示文稿。

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中旭日图的完整源代码

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//分支 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//分支 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java API 在 PowerPoint 演示文稿中创建旭日图。您已经了解了如何初始化演示文稿、创建图表、定义图表层次结构、添加数据点以及保存演示文稿。现在，您可以使用这些知识在 Java 应用程序中创建交互式信息丰富的旭日图。

## 常见问题解答

### 如何自定义旭日图的外观？

您可以通过修改颜色、标签和样式等属性来自定义 Sunburst 图表的外观。请参阅 Aspose.Slides 文档以了解详细的自定义选项。

### 我可以向图表添加更多数据点吗？

是的，您可以使用`series.getDataPoints().addDataPointForSunburstSeries()`方法适用于您想要包含的每个数据点。

### 如何向旭日图添加工具提示？

要向旭日图添加工具提示，您可以设置数据标签格式，以便在将鼠标悬停在图表段上时显示其他信息，例如值或描述。

### 是否可以使用超链接创建交互式旭日图？

是的，您可以通过向特定图表元素或部分添加超链接来创建带有超链接的交互式 Sunburst 图表。有关添加超链接的详细信息，请参阅 Aspose.Slides 文档。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
