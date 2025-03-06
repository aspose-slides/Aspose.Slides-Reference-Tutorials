---
title: Java 幻灯片中的甜甜圈图洞
linktitle: Java 幻灯片中的甜甜圈图洞
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 使用 Aspose.Slides for Java 在 Java Slides 中创建具有自定义孔尺寸的甜甜圈图。带有图表自定义源代码的分步指南。
weight: 11
url: /zh/java/chart-elements/doughnut-chart-hole-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 幻灯片中带孔甜甜圈图简介

在本教程中，我们将指导您使用 Aspose.Slides for Java 创建带孔的圆环图。本分步指南将通过源代码示例引导您完成整个过程。

## 先决条件

开始之前，请确保已在 Java 项目中安装并设置了 Aspose.Slides for Java 库。您可以从[Aspose.Slides for Java 文档](https://reference.aspose.com/slides/java/).

## 步骤 1：导入所需的库

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 步骤 2：初始化演示文稿

```java
//文档目录的路径。
String dataDir = "Your Document Directory";

//创建 Presentation 类的实例
Presentation presentation = new Presentation();
```

## 步骤 3：创建圆环图

```java
try {
    //在第一张幻灯片上创建圆环图
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    //设置圆环图中孔的大小（百分比）
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    //将演示文稿保存到磁盘
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    //处置展示对象
    if (presentation != null) presentation.dispose();
}
```

## 步骤 4：运行代码

在 IDE 或文本编辑器中运行 Java 代码，以创建具有指定孔径的圆环图。确保替换`"Your Document Directory"`与您想要保存演示文稿的实际路径。

## Java 幻灯片中甜甜圈图孔的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建 Presentation 类的实例
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	//将演示文稿写入磁盘
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java 创建带孔的圆环图。您可以通过调整`setDoughnutHoleSize`方法参数。

## 常见问题解答

### 如何更改图表部分的颜色？

要更改图表部分的颜色，您可以使用`setDataPointsInLegend`方法`IChart`对象并为每个数据点设置所需的颜色。

### 我可以为环形图的各个部分添加标签吗？

是的，您可以使用`setDataPointsLabelValue`方法`IChart`目的。

### 是否可以给图表添加标题？

当然可以！您可以使用`setTitle`方法`IChart`对象并提供所需的标题文本。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
