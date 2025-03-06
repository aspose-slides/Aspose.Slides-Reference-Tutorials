---
title: Java 幻灯片中的图表实体
linktitle: Java 幻灯片中的图表实体
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 学习使用 Aspose.Slides 创建和自定义 Java Slides 图表。使用强大的图表实体增强您的演示文稿。
type: docs
weight: 13
url: /zh/java/data-manipulation/chart-entities-java-slides/
---

## Java 幻灯片中的图表实体简介

图表是用于在演示文稿中可视化数据的强大工具。无论您是创建业务报告、学术演示文稿还是任何其他形式的内容，图表都有助于有效地传达信息。Aspose.Slides for Java 提供了强大的图表处理功能，使其成为 Java 开发人员的首选。

## 先决条件

在深入研究图表实体的世界之前，请确保您已满足以下先决条件：

- 已安装 Java 开发工具包 (JDK)
- Aspose.Slides for Java 库已下载并添加到您的项目中
- Java 编程基础知识

现在，让我们开始使用 Aspose.Slides for Java 创建和自定义图表。

## 步骤 1：创建演示文稿

第一步是创建一个新的演示文稿，在其中添加图表。以下是创建演示文稿的代码片段：

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 步骤 2：添加图表

演示文稿准备好后，就可以添加图表了。在此示例中，我们将添加带有标记的简单折线图。操作方法如下：

```java
//访问第一张幻灯片
ISlide slide = pres.getSlides().get_Item(0);

//添加示例图表
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 步骤 3：自定义图表标题

一个定义良好的图表应该有一个标题。让我们为图表设置一个标题：

```java
//设置图表标题
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## 步骤 4：格式化网格线

您可以设置图表的主要和次要网格线的格式。让我们为垂直轴网格线设置一些格式：

```java
//设置数值轴的主要网格线格式
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//设置数值轴的次网格线格式
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 步骤 5：自定义值轴

您可以控制数值轴的数字格式、最大值和最小值。自定义方法如下：

```java
//设定值轴号格式
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

//设置图表最大值、最小值
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## 步骤 6：添加值轴标题

为了使您的图表更具信息量，您可以为数值轴添加标题：

```java
//设置数值轴标题
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## 步骤 7：格式化分类轴

类别轴通常表示数据类别，也可以自定义：

```java
//设置分类轴的主网格线格式
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//设置分类轴的次要网格线格式
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 步骤 8：添加图例

图例有助于解释图表中的数据系列。让我们自定义图例：

```java
//设置图例文本属性
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

//设置显示图表图例而不重叠图表
chart.getLegend().setOverlay(true);
```

## 步骤 9：保存演示文稿

最后，使用图表保存您的演示文稿：

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中图表实体的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//如果目录尚不存在，则创建目录。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
//实例化演示//实例化演示
Presentation pres = new Presentation();
try
{
	//访问第一张幻灯片
	ISlide slide = pres.getSlides().get_Item(0);
	//添加示例图表
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	//设置图表标题
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	//设置数值轴的主要网格线格式
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	//设置数值轴的次网格线格式
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//设定值轴号格式
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	//设置图表最大值、最小值
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	//设置数值轴文本属性
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	//设置数值轴标题
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	//设置值轴线格式 : 现已过时
	//图表.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	//图表.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	//图表.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	//设置分类轴的主网格线格式
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//设置分类轴的次要网格线格式
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//设置分类轴文本属性
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	//设置类别标题
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	//设置分类轴标签位置
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	//设置分类轴标签旋转角度
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	//设置图例文本属性
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	//设置显示图表图例而不重叠图表
	chart.getLegend().setOverlay(true);
	//在次要数值轴上绘制第一个系列
	//图表.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	//设置图表背景墙颜色
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//设置绘图区域颜色
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	//保存演示文稿
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本文中，我们使用 Aspose.Slides for Java 探索了 Java Slides 中的图表实体世界。您已经学习了如何创建、自定义和操作图表以增强您的演示文稿。图表不仅可以使您的数据具有视觉吸引力，还可以帮助您的受众更轻松地理解复杂信息。

## 常见问题解答

### 如何更改图表类型？

要更改图表类型，请使用`chart.setType()`方法并指定所需的图表类型。

### 我可以向图表添加多个数据系列吗？

是的，您可以使用`chart.getChartData().getSeries().addSeries()`方法。

### 如何自定义图表颜色？

您可以通过设置各种图表元素（例如网格线、标题和图例）的填充格式来自定义图表颜色。

### 我可以创建 3D 图表吗？

是的，Aspose.Slides for Java 支持创建 3D 图表。您可以设置`ChartType`转换为 3D 图表类型来创建一个。

### Aspose.Slides for Java 是否与最新的 Java 版本兼容？

是的，Aspose.Slides for Java 会定期更新以支持最新的 Java 版本，并提供与各种 Java 环境的兼容性。