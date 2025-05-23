---
"description": "使用 Aspose.Slides for Java 在 Java 幻灯片中创建普通图表。在 PowerPoint 演示文稿中创建、自定义和保存图表的分步指南和源代码。"
"linktitle": "Java Slides 中的普通图表"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "Java Slides 中的普通图表"
"url": "/zh/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides 中的普通图表


## Java 幻灯片中的普通图表简介

在本教程中，我们将逐步讲解如何使用 Aspose.Slides for Java API 在 Java Slides 中创建普通图表。我们将使用分步说明和源代码来演示如何在 PowerPoint 演示文稿中创建簇状柱形图。

## 先决条件

开始之前，请确保您已满足以下先决条件：

1. 已安装 Aspose.Slides for Java API。
2. Java 开发环境已设置。
3. Java 编程基础知识。

## 步骤1：设置项目

确保您的项目有一个目录。我们将其命名为“您的文档目录”，如代码中所述。您可以将其替换为项目目录的实际路径。

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
// 如果目录尚不存在，则创建该目录。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## 第 2 步：创建演示文稿

现在，让我们创建一个 PowerPoint 演示文稿并访问其第一张幻灯片。

```java
// 实例化代表 PPTX 文件的 Presentation 类
Presentation pres = new Presentation();
// 访问第一张幻灯片
ISlide sld = pres.getSlides().get_Item(0);
```

## 步骤3：添加图表

我们将在幻灯片中添加一个簇状柱形图并设置其标题。

```java
// 添加带有默认数据的图表
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 设置图表标题
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 步骤4：设置图表数据

接下来，我们将通过定义系列和类别来设置图表数据。

```java
// 将第一个系列设置为显示值
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 设置图表数据表的索引
int defaultWorksheetIndex = 0;

// 获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 删除默认生成的系列和类别
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 添加新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// 添加新类别
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 步骤5：填充系列数据

现在，让我们填充图表的系列数据点。

```java
// 采取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// 设置系列的填充颜色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// 采取第二张图表系列
series = chart.getChartData().getSeries().get_Item(1);

// 填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// 设置系列的填充颜色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## 步骤6：自定义标签

让我们自定义图表系列的数据标签。

```java
// 第一个标签将显示类别名称
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// 显示带有系列名称和分隔符的第三个标签的值
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## 步骤 7：保存演示文稿

最后，将带有图表的演示文稿保存到您的项目目录中。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就这样！您已成功使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中创建了簇状柱形图。您可以根据自己的需求进一步自定义此图表。

## Java 幻灯片中普通图表的完整源代码

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
// 如果目录尚不存在，则创建该目录。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// 实例化代表 PPTX 文件的 Presentation 类
Presentation pres = new Presentation();
// 访问第一张幻灯片
ISlide sld = pres.getSlides().get_Item(0);
// 添加带有默认数据的图表
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 设置图表标题
// Chart.getChartTitle().getTextFrameForOverriding().setText("示例标题");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// 将第一个系列设置为显示值
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// 设置图表数据表的索引
int defaultWorksheetIndex = 0;
// 获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 删除默认生成的系列和类别
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// 添加新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// 添加新类别
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// 采取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 现在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// 设置系列的填充颜色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// 采取第二张图表系列
series = chart.getChartData().getSeries().get_Item(1);
// 现在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// 设置系列的填充颜色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// 第一个标签将显示类别名称
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// 显示第三个标签的值
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// 将演示文稿与图表一起保存
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java API 在 Java Slides 中创建普通图表。我们逐步讲解了如何在 PowerPoint 演示文稿中创建簇状柱形图，并附带源代码。

## 常见问题解答

### 我如何更改图表类型？

要更改图表类型，请修改 `ChartType` 使用添加图表时的参数 `sld.getShapes().addChart()`。您可以从 Aspose.Slides 中提供的各种图表类型中进行选择。

### 我可以更改图表系列的颜色吗？

是的，您可以通过设置每个系列的填充颜色来更改图表系列的颜色 `series。getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### 如何向图表添加更多类别或系列？

您可以通过使用 `chart.getChartData().getCategories().add()` 和 `chart.getChartData().getSeries().add()` 方法。

### 如何进一步自定义图表标题？

您可以通过修改以下属性来进一步自定义图表标题 `chart.getChartTitle()` 例如文本对齐方式、字体大小和颜色。

### 如何将图表保存为不同的文件格式？

要将图表保存为不同的文件格式，请更改 `SaveFormat` 参数 `pres.save()` 方法转换为所需的格式（例如 PDF、PNG、JPEG）。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}