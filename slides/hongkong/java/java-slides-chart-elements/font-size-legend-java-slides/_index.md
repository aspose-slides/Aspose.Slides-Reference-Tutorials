---
"description": "使用 Aspose.Slides for Java 增強 PowerPoint 簡報。在我們的逐步指南中了解如何自訂圖例字體大小等。"
"linktitle": "Java 投影片中的字體大小圖例"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的字體大小圖例"
"url": "/zh-hant/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的字體大小圖例


## Java 投影片中的字體大小圖例介紹

在本教學中，您將學習如何使用 Aspose.Slides for Java 自訂 PowerPoint 投影片中圖例的字體大小。我們將提供逐步說明和原始程式碼來完成此任務。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 [這裡](https://releases。aspose.com/slides/java/).

## 步驟 1：初始化簡報

首先，匯入必要的類別並初始化您的 PowerPoint 簡報。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

代替 `"Your Document Directory"` 使用 PowerPoint 檔案的實際路徑。

## 第 2 步：新增圖表

接下來，我們將在投影片中新增圖表，並設定圖例的字體大小。

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

在這段程式碼中，我們在第一張投影片上建立一個簇狀長條圖，並將圖例文字的字體大小設定為 20 磅。您可以調整 `setFontHeight` 值來根據需要更改字體大小。

## 步驟 3：自訂軸值

現在，讓我們自訂圖表的垂直軸值。

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

在這裡，我們設定垂直軸的最小值和最大值。您可以根據資料要求修改值。

## 步驟 4：儲存簡報

最後，將修改後的簡報儲存到新文件中。

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

此程式碼將修改後的簡報作為「output.pptx」儲存在指定目錄中。

## Java 投影片中字體大小圖例的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

您已成功使用 Aspose.Slides for Java 自訂 Java PowerPoint 投影片中圖例的字體大小。您可以進一步探索 Aspose.Slides 的功能來創建互動式且具有視覺吸引力的簡報。

## 常見問題解答

### 如何更改圖表中圖例文字的字體大小？

若要變更圖表中圖例文字的字體大小，可以使用以下程式碼：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

在這段程式碼中，我們建立一個圖表，並將圖例文字的字體大小設為 20 磅。您可以調整 `setFontHeight` 值來改變字體大小。

### 我可以自訂圖表中圖例的其他屬性嗎？

是的，您可以使用 Aspose.Slides 自訂圖表中圖例的各種屬性。您可以自訂的一些常見屬性包括文字格式、位置、可見性等。例如，要變更圖例的位置，您可以使用：

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

此程式碼將圖例設定為出現在圖表的底部。探索 Aspose.Slides 文件以取得更多自訂選項。

### 如何設定圖表中垂直軸的最小值和最大值？

要設定圖表中垂直軸的最小值和最大值，可以使用以下程式碼：

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

在這裡，我們禁用自動軸縮放並指定垂直軸的最小值和最大值。根據圖表資料的需要調整值。

### 在哪裡可以找到有關 Aspose.Slides 的更多資訊和文件？

您可以在 Aspose 文件網站上找到 Aspose.Slides for Java 的全面文件和 API 參考。訪問 [這裡](https://reference.aspose.com/slides/java/) 有關使用該庫的詳細資訊。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}