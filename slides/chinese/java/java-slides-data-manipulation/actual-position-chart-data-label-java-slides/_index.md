---
title: 获取 Java Slides 中图表数据标签的实际位置
linktitle: 获取 Java Slides 中图表数据标签的实际位置
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 获取 Java Slides 中图表数据标签的实际位置。带有源代码的分步指南。
weight: 18
url: /zh/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 获取 Java Slides 中图表数据标签的实际位置


## Java Slides 中获取图表数据标签实际位置的介绍

在本教程中，您将学习如何使用 Aspose.Slides for Java 检索图表数据标签的实际位置。我们将创建一个 Java 程序，该程序生成带有图表的 PowerPoint 演示文稿，自定义数据标签，然后添加表示这些数据标签位置的形状。

## 先决条件

开始之前，请确保您已在 Java 项目中设置了 Aspose.Slides for Java 库。

## 步骤 1：创建 PowerPoint 演示文稿

首先，让我们创建一个新的 PowerPoint 演示文稿并向其中添加图表。我们将在本教程的后面部分自定义图表的数据标签。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## 第 2 步：自定义数据标签
现在，让我们自定义图表系列的数据标签。我们将设置它们的位置并显示值。

```java
try {
    // ...（前一个代码）
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ...（剩余代码）
} finally {
    if (pres != null) pres.dispose();
}
```

## 步骤 3：获取数据标签的实际位置
在此步骤中，我们将遍历图表系列的数据点并检索值大于 4 的数据标签的实际位置。然后我们将添加省略号来表示这些位置。

```java
try {
    // ...（前一个代码）
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ...（剩余代码）
} finally {
    if (pres != null) pres.dispose();
}
```

## 步骤 4：保存演示文稿
最后，将生成的演示文稿保存到文件中。

```java
try {
    // ...（前一个代码）
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 获取 Java 幻灯片中图表数据标签实际位置的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//去做
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java 检索 Java Slides 中图表数据标签的实际位置。现在，您可以使用这些知识通过自定义数据标签及其位置的视觉表示来增强您的 PowerPoint 演示文稿。

## 常见问题解答

### 如何自定义图表中的数据标签？

要自定义图表中的数据标签，您可以使用`setDefaultDataLabelFormat`方法并设置位置和可见性等属性。例如：
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### 如何添加形状来表示数据标签位置？

您可以遍历图表系列的数据点并使用`getActualX`, `getActualY`, `getActualWidth`， 和`getActualHeight`方法获取其位置。然后，您可以使用`addAutoShape`方法。以下是示例：
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### 如何保存生成的演示文稿？

您可以使用`save`方法。提供所需的文件路径和`SaveFormat`作为参数。例如：
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
