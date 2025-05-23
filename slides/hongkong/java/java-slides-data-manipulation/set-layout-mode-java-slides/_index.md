---
"description": "了解如何使用 Aspose.Slides 設定 Java 投影片的版面模式。在本逐步指南中，使用原始程式碼自訂圖表定位和大小。"
"linktitle": "在 Java Slides 中設定佈局模式"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中設定佈局模式"
"url": "/zh-hant/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中設定佈局模式


## Java Slides 中設定版面模式的介紹

在本教程中，我們將學習如何使用 Aspose.Slides for Java 設定 Java 投影片中圖表的版面模式。佈局模式決定了幻燈片中圖表的位置和大小。

## 先決條件

在開始之前，請確保您已經在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 [這裡](https://releases。aspose.com/slides/java/).

## 步驟 1：建立簡報

首先，我們需要建立一個新的簡報。

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 第 2 步：新增投影片和圖表

接下來，我們將向其中添加投影片和圖表。在此範例中，我們將建立一個聚集長條圖。

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 步驟3：設定圖表佈局

現在，讓我們設定圖表的佈局。我們將使用 `setX`， `setY`， `setWidth`， `setHeight` 方法。此外，我們將設置 `LayoutTargetType` 確定佈局模式。

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

在此範例中，我們將圖表的佈局目標類型設為“內部”，這表示它將相對於投影片的內部區域進行定位和調整大小。

## 步驟 4：儲存簡報

最後，讓我們儲存帶有圖表佈局設定的簡報。

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java Slides 中設定佈局模式的完整原始碼

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

在本教學中，我們學習如何使用 Aspose.Slides for Java 設定 Java 投影片中圖表的版面模式。您可以根據具體要求，透過調整 `setX`， `setY`， `setWidth`， `setHeight`， 和 `setLayoutTargetType` 方法。這使您可以控制幻燈片內圖表的放置位置。

## 常見問題解答

### 如何更改 Aspose.Slides for Java 中圖表的版面模式？

若要變更 Aspose.Slides for Java 中圖表的版面模式，您可以使用 `setLayoutTargetType` 圖表繪圖區域上的方法。您可以將其設定為 `LayoutTargetType.Inner` 或者 `LayoutTargetType.Outer` 取決於您想要的佈局。

### 我可以自訂投影片中圖表的位置和大小嗎？

是的，您可以使用 `setX`， `setY`， `setWidth`， 和 `setHeight` 圖表繪圖區域上的方法。根據您的要求調整這些值來定位和調整圖表的大小。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多資訊？

您可以在以下位置找到有關 Aspose.Slides for Java 的更多信息 [文件](https://reference.aspose.com/slides/java/)。它包括詳細的 API 參考和範例，以幫助您在 Java 中有效地處理投影片和圖表。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}