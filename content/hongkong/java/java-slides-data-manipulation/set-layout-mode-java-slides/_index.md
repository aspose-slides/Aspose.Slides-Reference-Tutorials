---
title: 在 Java 投影片中設定版面模式
linktitle: 在 Java 投影片中設定版面模式
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 設定 Java 投影片的版面模式。在本逐步指南中使用原始程式碼自訂圖表位置和大小。
type: docs
weight: 23
url: /zh-hant/java/data-manipulation/set-layout-mode-java-slides/
---

## Java投影片設定版面配置模式簡介

在本教程中，我們將學習如何使用 Aspose.Slides for Java 在 Java 投影片中設定圖表的版面模式。佈局模式決定幻燈片中圖表的位置和大小。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從以下位置下載該程式庫[這裡](https://releases.aspose.com/slides/java/).

## 第 1 步：建立簡報

首先，我們需要建立一個新的簡報。

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 第 2 步：新增投影片和圖表

接下來，我們將向其添加投影片和圖表。在此範例中，我們將建立一個聚集長條圖。

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 第 3 步：設定圖表佈局

現在，讓我們設定圖表的佈局。我們將使用以下命令調整幻燈片中圖表的位置和大小`setX`, `setY`, `setWidth`, `setHeight`方法。此外，我們將設置`LayoutTargetType`來確定佈局模式。

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

在此範例中，我們將圖表的佈局目標類型設為“內部”，這表示它將相對於投影片的內部區域進行定位和調整大小。

## 第 4 步：儲存簡報

最後，讓我們使用圖表佈局設定來儲存簡報。

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java 投影片中設定版面模式的完整原始碼

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 在 Java 投影片中設定圖表的版面模式。您可以根據您的具體要求透過調整中的值來自訂圖表的位置和大小`setX`, `setY`, `setWidth`, `setHeight`， 和`setLayoutTargetType`方法。這使您可以控制幻燈片中圖表的位置。

## 常見問題解答

### 如何更改 Aspose.Slides for Java 中圖表的版面模式？

若要變更 Aspose.Slides for Java 中圖表的版面模式，您可以使用`setLayoutTargetType`圖表繪圖區域上的方法。您可以將其設定為`LayoutTargetType.Inner`或者`LayoutTargetType.Outer`取決於您想要的佈局。

### 我可以自訂投影片中圖表的位置和大小嗎？

是的，您可以使用`setX`, `setY`, `setWidth`， 和`setHeight`圖表繪圖區域上的方法。根據您的要求調整這些值以定位圖表並調整圖表的大小。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多資訊？

您可以在以下位置找到有關 Aspose.Slides for Java 的更多資訊：[文件](https://reference.aspose.com/slides/java/)。它包含詳細的 API 參考和範例，可協助您在 Java 中有效地使用投影片和圖表。