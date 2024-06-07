---
title: Java 幻灯片中数据点上的图表标记选项
linktitle: Java 幻灯片中数据点上的图表标记选项
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 使用自定义图表标记选项优化您的 Java 幻灯片。学习使用 Aspose.Slides for Java 以视觉方式增强数据点。探索分步指导和常见问题解答。
type: docs
weight: 14
url: /zh/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Java 幻灯片中数据点上的图表标记选项简介

在创建有影响力的演示文稿时，自定义和操作数据点上的图表标记的能力可以发挥重要作用。使用 Aspose.Slides for Java，您可以将图表转换为动态且具有视觉吸引力的元素。

## 先决条件

在深入编码部分之前，请确保您已满足以下先决条件：

- Java 开发环境
- Aspose.Slides for Java 库
- Java 集成开发环境 (IDE)
- 示例演示文档（例如“Test.pptx”）

## 步骤 1：设置环境

首先，确保您已安装并准备好必要的工具。在 IDE 中创建一个 Java 项目并导入 Aspose.Slides for Java 库。

## 第 2 步：加载演示文稿

首先，加载您的示例演示文稿文档。在提供的代码中，我们假设文档名为“Test.pptx”。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## 步骤 3：创建图表

现在，让我们在演示文稿中创建一个图表。在此示例中，我们将使用带标记的折线图。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## 步骤 4：处理图表数据

要操作图表数据，我们需要访问图表数据工作簿并准备数据系列。我们将清除默认系列并添加自定义数据。

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## 步骤 5：添加自定义标记

接下来是令人兴奋的部分 - 自定义数据点上的标记。我们将在此示例中使用图像作为标记。

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//向数据点添加自定义标记
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

//对其他数据点重复上述操作
//...

//更改图表系列标记大小
series.getMarker().setSize(15);
```

## 步骤 6：保存演示文稿

自定义图表标记后，请保存演示文稿以查看实际更改。

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中数据点上的图表标记选项的完整源代码

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//创建默认图表
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//获取默认图表数据工作表索引
int defaultWorksheetIndex = 0;
//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//删除演示系列
chart.getChartData().getSeries().clear();
//添加新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//设置图片
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//设置图片
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//采取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//在那里添加新观点（1：3）。
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//更改图表系列标记
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## 结论

使用 Aspose.Slides for Java，您可以通过自定义数据点上的图表标记来提升您的演示效果。这让您可以创建视觉效果惊人且信息丰富的幻灯片，吸引观众。

## 常见问题解答

### 如何更改数据点的标记大小？

要更改数据点的标记大小，请使用`series.getMarker().setSize()`方法并提供所需的大小作为参数。

### 我可以使用图像作为自定义标记吗？

是的，您可以使用图像作为数据点的自定义标记。将填充类型设置为`FillType.Picture`并提供您想要使用的图像。

### Aspose.Slides for Java 适合创建动态图表吗？

当然！Aspose.Slides for Java 提供了丰富的功能，可以在您的演示文稿中创建动态和交互式图表。

### 我可以使用 Aspose.Slides 自定义图表的其他方面吗？

是的，您可以使用 Aspose.Slides for Java 自定义图表的各个方面，包括标题、轴、数据标签等。

### 我可以在哪里访问 Aspose.Slides for Java 文档和下载？

您可以在以下位置找到文档[这里](https://reference.aspose.com/slides/java/)并下载库[这里](https://releases.aspose.com/slides/java/).