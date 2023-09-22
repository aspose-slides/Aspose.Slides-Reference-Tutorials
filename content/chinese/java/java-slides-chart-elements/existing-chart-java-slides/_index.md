---
title: Java 幻灯片中的现有图表
linktitle: Java 幻灯片中的现有图表
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 使用 Aspose.Slides for Java 增强您的 PowerPoint 演示文稿。学习以编程方式修改现有图表。带有图表定制源代码的分步指南。
type: docs
weight: 12
url: /zh/java/chart-elements/existing-chart-java-slides/
---

## 使用 Aspose.Slides for Java 介绍 Java 幻灯片中的现有图表

在本教程中，我们将演示如何使用 Aspose.Slides for Java 修改 PowerPoint 演示文稿中的现有图表。我们将完成更改图表数据、类别名称、系列名称以及向图表添加新系列的步骤。确保您的项目中设置了 Aspose.Slides for Java。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

1. Aspose.Slides for Java 库包含在您的项目中。
2. 包含要修改的图表的现有 PowerPoint 演示文稿。
3. Java开发环境搭建。

## 第 1 步：加载演示文稿

```java
//文档目录的路径。
String dataDir = "Your Document Directory";

//实例化表示 PPTX 文件的演示文稿类
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## 第 2 步：访问幻灯片和图表

```java
//访问第一张幻灯片
ISlide sld = pres.getSlides().get_Item(0);

//访问幻灯片上的图表
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 步骤 3：更改图表数据和类别名称

```java
//设置图表数据表的索引
int defaultWorksheetIndex = 0;

//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//更改图表类别名称
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## 第 4 步：更新第一个图表系列

```java
//获取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//更新系列名称
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

//更新系列数据
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## 第 5 步：更新第二个图表系列

```java
//采取第二个图表系列
series = chart.getChartData().getSeries().get_Item(1);

//更新系列名称
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

//更新系列数据
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## 第 6 步：向图表添加新系列

```java
//添加新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

//采取第三个图表系列
series = chart.getChartData().getSeries().get_Item(2);

//填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## 第 7 步：更改图表类型

```java
//将图表类型更改为簇状柱形图
chart.setType(ChartType.ClusteredCylinder);
```

## 步骤 8：保存修改后的演示文稿

```java
//使用修改后的图表保存演示文稿
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

恭喜！您已使用 Aspose.Slides for Java 成功修改了 PowerPoint 演示文稿中的现有图表。现在，您可以使用此代码以编程方式自定义 PowerPoint 演示文稿中的图表。

## Java 幻灯片中现有图表的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//实例化表示 PPTX 文件的演示文稿类//实例化表示 PPTX 文件的演示文稿类
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
//访问第一张幻灯片标记
ISlide sld = pres.getSlides().get_Item(0);
//添加带有默认数据的图表
IChart chart = (IChart) sld.getShapes().get_Item(0);
//设置图表数据表索引
int defaultWorksheetIndex = 0;
//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//更改图表类别名称
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
//获取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//现已更新系列数据
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");//修改系列名称
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
//采取第二个图表系列
series = chart.getChartData().getSeries().get_Item(1);
//现已更新系列数据
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");//修改系列名称
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
//现在，添加一个新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
//采取第三个图表系列
series = chart.getChartData().getSeries().get_Item(2);
//现在正在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
//保存带有图表的演示文稿
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## 结论

在这个综合教程中，我们学习了如何使用 Aspose.Slides for Java 修改 PowerPoint 演示文稿中的现有图表。通过遵循分步指南并利用源代码示例，您可以轻松自定义和更新图表以满足您的特定要求。以下是我们所涵盖内容的回顾：

## 常见问题解答

### 如何更改图表类型？

您可以使用以下命令更改图表类型`chart.setType(ChartType.ChartTypeHere)`方法。代替`ChartTypeHere`与所需的图表类型，例如`ChartType.ClusteredCylinder`在我们的例子中。

### 我可以向系列添加更多数据点吗？

是的，您可以使用以下命令向系列添加更多数据点`series.getDataPoints().addDataPointForBarSeries(cell)`方法。确保提供适当的单元格数据。

### 如何更新类别名称？

您可以使用以下方法更新类别名称`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`设置新的类别名称。

### 如何修改系列名称？

要修改系列名称，请使用`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`设置新系列名称。

### 有没有办法从图表中删除系列？

是的，您可以使用以下命令从图表中删除系列：`chart.getChartData().getSeries().removeAt(index)`方法，其中`index`是您要删除的系列的索引。