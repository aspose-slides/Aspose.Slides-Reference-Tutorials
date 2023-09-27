---
title: Java 幻灯片中的圆环图孔
linktitle: Java 幻灯片中的圆环图孔
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 使用 Aspose.Slides for Java 在 Java 幻灯片中创建具有自定义孔尺寸的圆环图。带有图表定制源代码的分步指南。
type: docs
weight: 11
url: /zh/java/chart-elements/doughnut-chart-hole-java-slides/
---

## Java 幻灯片中带洞的圆环图简介

在本教程中，我们将指导您使用 Aspose.Slides for Java 创建带孔的圆环图。本分步指南将通过源代码示例引导您完成整个过程。

## 先决条件

在开始之前，请确保您已在 Java 项目中安装并设置了 Aspose.Slides for Java 库。您可以从[Aspose.Slides for Java 文档](https://reference.aspose.com/slides/java/).

## 第 1 步：导入所需的库

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 第 2 步：初始化演示文稿

```java
//文档目录的路径。
String dataDir = "Your Document Directory";

//创建Presentation类的实例
Presentation presentation = new Presentation();
```

## 第 3 步：创建圆环图

```java
try {
    //在第一张幻灯片上创建圆环图
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    //设置圆环图中孔的大小（以百分比表示）
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    //将演示文稿保存到磁盘
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    //处理演示对象
    if (presentation != null) presentation.dispose();
}
```

## 第 4 步：运行代码

在 IDE 或文本编辑器中运行 Java 代码以创建具有指定孔大小的圆环图。确保更换`"Your Document Directory"`与您要保存演示文稿的实际路径。

## Java 幻灯片中圆环图孔的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建Presentation类的实例
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

在本教程中，您学习了如何使用 Aspose.Slides for Java 创建带孔的圆环图。您可以通过调整来自定义孔的大小`setDoughnutHoleSize`方法参数。

## 常见问题解答

### 如何更改图表部分的颜色？

要更改图表部分的颜色，您可以使用`setDataPointsInLegend`方法上的`IChart`对象并为每个数据点设置所需的颜色。

### 我可以向圆环图分段添加标签吗？

是的，您可以使用以下命令向圆环图段添加标签`setDataPointsLabelValue`方法上的`IChart`目的。

### 是否可以为图表添加标题？

当然！您可以使用以下命令向图表添加标题`setTitle`方法上的`IChart`对象并提供所需的标题文本。