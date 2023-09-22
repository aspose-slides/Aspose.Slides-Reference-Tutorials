---
title: 在 Java 幻灯片中设置带有更新图表数据的外部工作簿
linktitle: 在 Java 幻灯片中设置带有更新图表数据的外部工作簿
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 设置外部工作簿并更新 Java Slides 中的图表数据。增强您的 PowerPoint 自动化技能。
type: docs
weight: 20
url: /zh/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

## 在 Java 幻灯片中设置带有更新图表数据的外部工作簿简介

在本综合指南中，我们将引导您完成使用 Aspose.Slides for Java API 在 Java Slides 中设置包含更新图表数据的外部工作簿的过程。这个功能强大的库允许您以编程方式操作 PowerPoint 演示文稿，从而轻松自动执行任务，例如从外部源更新图表数据。在本教程结束时，您将清楚地了解如何通过分步说明和随附的 Java 代码来完成此任务。

## 先决条件

在我们深入实施之前，请确保您具备以下先决条件：

1.  Aspose.Slides for Java：您应该安装 Aspose.Slides for Java 库。您可以从以下位置下载：[这里](https://releases.aspose.com/slides/java/).

2. Java 开发环境：确保您的系统上设置了 Java 开发环境。

## 第 1 步：创建新演示文稿

首先，让我们使用 Aspose.Slides for Java 创建一个新的 PowerPoint 演示文稿。下面是执行此操作的 Java 代码：

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：添加图表

现在，让我们在演示文稿中添加一个图表。我们将在此示例中创建一个饼图：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## 第三步：设置外部工作簿

我们在这里将外部工作簿设置为图表的数据源。您需要提供外部工作簿的 URL，即使它目前不存在：

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://路径/不存在/存在”，假）；
```

## 第 4 步：保存演示文稿

最后，使用更新的图表数据保存演示文稿：

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## 在 Java 幻灯片中更新图表数据的设置外部工作簿的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://路径/不存在/存在”，假）；
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

恭喜！您已经了解了如何使用 Aspose.Slides for Java 在 Java Slides 中设置包含更新图表数据的外部工作簿。这对于从外部数据源动态更新 PowerPoint 演示文稿中的图表非常有用。

## 常见问题解答

### 如何更新图表的外部工作簿数据？

要更新图表的外部工作簿数据，您只需修改指定 URL 处的外部工作簿中的数据即可。下次打开演示文稿时，Aspose.Slides for Java 将从外部工作簿中获取更新的数据并相应地更新图表。

### 我可以使用本地文件作为外部工作簿吗？

是的，您可以通过提供文件路径而不是 URL 来使用本地文件作为外部工作簿。只需确保文件路径正确并且可以从 Java 应用程序访问即可。

### 通过 Aspose.Slides for Java 使用外部工作簿是否有任何限制？

虽然使用外部工作簿是一项强大的功能，但请记住，外部工作簿数据的可用性取决于其在所提供的 URL 或文件路径上的可访问性。确保打开演示文稿时外部数据源可用，以避免数据检索问题。

### 设置外部工作簿后可以自定义图表外观吗？

是的，即使在设置外部工作簿之后，您也可以自定义图表的外观，包括其标题、标签、颜色等。 Aspose.Slides for Java 提供了广泛的图表格式化选项来满足您的需求。

### 在哪里可以找到有关 Aspose.Slides for Java 的更多文档和资源？

有关详细文档和其他资源，请访问 Aspose.Slides for Java 文档：[这里](https://reference.aspose.com/slides/java/).