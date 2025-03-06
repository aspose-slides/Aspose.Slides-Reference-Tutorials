---
title: 在 Java 幻灯片中创建雷达图
linktitle: 在 Java 幻灯片中创建雷达图
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java API 在 Java PowerPoint 演示文稿中创建雷达图。
weight: 10
url: /zh/java/chart-creation/radar-chart-creating-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 幻灯片中创建雷达图的简介

在本教程中，我们将指导您使用 Aspose.Slides for Java API 创建雷达图的过程。雷达图可用于以圆形模式可视化数据，从而更轻松地比较多个数据系列。我们将提供分步说明以及 Java 源代码。

## 先决条件

开始之前，请确保已将 Aspose.Slides for Java 库集成到项目中。您可以从以下网址下载该库[这里](https://releases.aspose.com/slides/java/).

## 步骤 1：设置演示文稿

让我们首先设置一个新的 PowerPoint 演示文稿并向其中添加幻灯片。

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## 步骤 2：添加雷达图

接下来，我们将在幻灯片中添加雷达图。我们将指定图表的位置和尺寸。

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## 步骤3：设置图表数据

我们现在将设置图表数据。这涉及创建数据工作簿、添加类别和添加系列。

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

//设置图表标题
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

//删除默认生成的系列和类别
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

//添加新类别
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

//添加新系列
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## 步骤 4：填充系列数据

现在，我们将填充雷达图的系列数据。

```java
//填充系列 1 的系列数据
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

//设置系列颜色
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

//填充系列 2 的系列数据
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

//设置系列颜色
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## 步骤 5：自定义轴和图例

让我们自定义雷达图的轴和图例。

```java
//设置图例位置
ichart.getLegend().setPosition(LegendPositionType.Bottom);

//设置分类轴文本属性
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

//设置图例文本属性
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

//设置数值轴文本属性
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

//设定值轴号格式
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

//设置图表主单位值
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## 步骤 6：保存演示文稿

最后，保存生成的带有雷达图的演示文稿

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

就是这样！您已成功使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中创建了雷达图。您现在可以进一步自定义此示例以满足您的特定需求。

## Java 幻灯片中创建雷达图的完整源代码

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	//访问第一张幻灯片
	ISlide sld = pres.getSlides().get_Item(0);
	//添加雷达图
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	//设置图表数据表索引
	int defaultWorksheetIndex = 0;
	//获取图表数据 WorkSheet
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	//设置图表标题
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	//删除默认生成的系列和类别
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	//添加新类别
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	//添加新系列
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	//现在填充系列数据
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	//设置系列颜色
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	//现在填充另一个系列数据
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	//设置系列颜色
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	//设置图例位置
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	//设置分类轴文本属性
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	//设置图例文本属性
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	//设置数值轴文本属性
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	//设定值轴号格式
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	//设置图表主单位值
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	//保存生成的演示文稿
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中创建雷达图。您可以应用这些概念在 Java 应用程序中有效地可视化和呈现数据。

## 常见问题解答

### 我如何更改图表标题？

要更改图表标题，请修改以下行：
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### 我可以向雷达图添加更多数据系列吗？

是的，您可以按照“步骤 3”和“步骤 4”中的步骤为要包含的每个附加系列添加更多数据系列。

### 如何自定义图表颜色？

您可以通过修改设置系列颜色的线条来自定义系列颜色`SolidFillColor`属性。例如：
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### 我如何更改轴标签和格式？

请参阅“步骤 5”自定义轴标签和格式，包括字体大小和颜色。

### 如何将图表保存为不同的文件格式？

您可以通过修改文件扩展名来更改输出格式`outPath`变量并使用适当的`SaveFormat`。例如，要保存为 PDF，请使用`SaveFormat.Pdf`.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
