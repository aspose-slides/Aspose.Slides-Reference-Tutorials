---
title: 在 Java 幻灯片中编辑外部工作簿中的图表数据
linktitle: 在 Java 幻灯片中编辑外部工作簿中的图表数据
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 编辑外部工作簿中的图表数据。带有源代码的分步指南。
type: docs
weight: 17
url: /zh/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## 在 Java 幻灯片中编辑外部工作簿中的图表数据简介

在本指南中，我们将演示如何使用 Aspose.Slides for Java 编辑外部工作簿中的图表数据。您将学习如何以编程方式修改 PowerPoint 演示文稿中的图表数据。确保您的项目中安装并配置了适用于 Java 的 Aspose.Slides 库。

## 先决条件

- 用于 Java 的 Aspose.Slides
- Java开发环境

## 第 1 步：加载演示文稿

首先，我们需要加载包含要编辑其数据的图表的 PowerPoint 演示文稿。代替`"Your Document Directory"`与演示文稿文件的实际路径。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 第 2 步：访问图表

加载演示文稿后，我们需要访问演示文稿中的图表。在此示例中，我们假设图表位于第一张幻灯片上，并且是该幻灯片上的第一个形状。

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 第三步：修改图表数据

现在，我们来修改图表数据。我们将重点关注更改图表中的特定数据点。在本示例中，我们将第一个系列中的第一个数据点的值设置为 100。您可以根据需要调整该值。

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 第 4 步：保存演示文稿

对图表数据进行必要的更改后，将修改后的演示文稿保存到新文件中。您可以根据需要指定输出文件路径和格式。

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## 第 5 步：清理

不要忘记处理演示对象以释放任何资源。

```java
if (pres != null) pres.dispose();
```

现在，您已使用 Aspose.Slides for Java 成功编辑了 PowerPoint 演示文稿中外部工作簿中的图表数据。您可以自定义此代码以满足您的特定需求并将其集成到您的 Java 应用程序中。

## 完整的源代码

```java
        //请注意，外部工作簿的路径几乎不会保存在演示文稿中
        //因此，请在运行示例之前从 Data/Chart 目录 D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ 复制文件 externalWorkbook.xlsx
        //文档目录的路径。
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save(RunExamples.getOutPath() + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 结论

在本综合指南中，我们探索了如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中编辑外部工作簿中的图表数据。通过遵循分步说明和源代码示例，您已经获得了以编程方式轻松修改图表数据的知识和技能。

## 常见问题解答

### 如何指定不同的图表或幻灯片？

要访问不同的图表或幻灯片，请修改相应的索引`getSlides().get_Item()`和`getShapes().get_Item()`方法。请记住，索引从 0 开始。

### 我可以在同一演示文稿中编辑多个图表中的数据吗？

是的，您可以通过对每个图表重复图表数据修改步骤来编辑同一演示文稿中多个图表中的数据。

### 如果我想编辑具有不同格式的外部工作簿中的数据该怎么办？

您可以使用适当的 Aspose.Cells 类和方法来调整代码以处理不同的外部工作簿格式，以读取和写入该格式的数据。

### 如何针对多个演示文稿自动执行此过程？

您可以创建一个循环来处理多个演示文稿，加载每个演示文稿，进行所需的更改，然后逐个保存修改后的演示文稿。