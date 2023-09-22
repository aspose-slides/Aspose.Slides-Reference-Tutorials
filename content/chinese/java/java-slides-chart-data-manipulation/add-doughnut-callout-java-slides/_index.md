---
title: 在 Java 幻灯片中添加甜甜圈标注
linktitle: 在 Java 幻灯片中添加甜甜圈标注
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 学习使用 Aspose.Slides for Java 在 Java 幻灯片中添加甜甜圈标注。带有源代码的分步指南，用于增强演示。
type: docs
weight: 12
url: /zh/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## 使用 Aspose.Slides for Java 在 Java 幻灯片中添加甜甜圈标注的简介

在本教程中，我们将引导您完成使用 Aspose.Slides for Java 将 Donut Callout 添加到 Java 幻灯片的过程。圆环标注是一种图表元素，可用于突出显示圆环图中的特定数据点。为了您的方便，我们将为您提供分步说明和完整的源代码。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. Java开发环境
2. Aspose.Slides for Java 库
3. 集成开发环境 (IDE)，例如 Eclipse 或 IntelliJ IDEA
4. 要在其中添加甜甜圈标注的 PowerPoint 演示文稿

## 第 1 步：设置您的 Java 项目

1. 在您选择的 IDE 中创建一个新的 Java 项目。
2. 将 Aspose.Slides for Java 库作为依赖项添加到您的项目中。

## 第 2 步：初始化演示文稿

首先，您需要初始化 PowerPoint 演示文稿并创建一张幻灯片，在其中添加圆环标注。这是实现此目的的代码：

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

确保更换`"Your Document Directory"`与 PowerPoint 演示文稿文件的实际路径。

## 第 3 步：创建圆环图

接下来，您将在幻灯片上创建一个圆环图。您可以根据您的要求自定义图表的位置和大小。以下是添加圆环图的代码：

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 第 4 步：自定义圆环图

现在，是时候自定义圆环图了。我们将设置各种属性，例如删除图例、配置孔尺寸以及调整第一个切片角度。这是代码：

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

此代码片段设置圆环图的属性。您可以调整这些值以满足您的特定需求。

## 第 5 步：将数据添加到圆环图

现在，让我们向圆环图添加数据。我们还将自定义数据点的外观。这是完成此操作的代码：

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        //在此自定义数据点外观
        i++;
    }
    categoryIndex++;
}
```

在此代码中，我们向圆环图添加类别和数据点。您可以根据需要进一步自定义数据点的外观。

## 第 6 步：保存演示文稿

最后，不要忘记添加甜甜圈标注后保存演示文稿。这是保存演示文稿的代码：

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

确保更换`"chart.pptx"`与您想要的文件名。

恭喜！您已使用 Aspose.Slides for Java 成功将 Donut Callout 添加到 Java 幻灯片中。现在，您可以运行 Java 应用程序来生成带有圆环图和标注的 PowerPoint 演示文稿。

## 在 Java 幻灯片中添加甜甜圈标注的完整源代码

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
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
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## 结论

在本教程中，我们介绍了使用 Aspose.Slides for Java 将 Donut Callout 添加到 Java 幻灯片的过程。您已经学习了如何创建圆环图、自定义其外观以及添加数据点。请随意使用这个强大的库进一步增强您的演示文稿并探索更多图表选项。

## 常见问题解答

### 如何更改甜甜圈标注的外观？

您可以通过修改图表中数据点的属性来自定义圆环标注的外观。在提供的代码中，您可以看到如何设置数据点的填充颜色、线条颜色、字体样式和其他属性。

### 我可以向圆环图添加更多数据点吗？

是的，您可以根据需要向圆环图添加任意数量的数据点。只需扩展代码中添加类别和数据点的循环，并提供适当的数据和格式即可。

### 如何调整幻灯片上圆环图的位置和大小？

您可以通过修改中的参数来改变圆环图的位置和大小`addChart`方法。该方法中的四个数字分别对应于图表左上角的 X 和 Y 坐标及其宽度和高度。