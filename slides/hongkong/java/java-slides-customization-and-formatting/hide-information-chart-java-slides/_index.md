---
"description": "了解如何使用 Aspose.Slides for Java 隱藏 Java Slides 中的圖表元素。透過逐步指導和原始碼客製化簡報，使其更加清晰、美觀。"
"linktitle": "隱藏 Java 投影片中的圖表訊息"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "隱藏 Java 投影片中的圖表訊息"
"url": "/zh-hant/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 隱藏 Java 投影片中的圖表訊息


## Java 投影片中隱藏圖表資訊的介紹

在本教程中，我們將探討如何使用 Aspose.Slides for Java API 隱藏 Java Slides 中圖表的各種元素。您可以使用此程式碼根據簡報的需求自訂圖表。

## 步驟 1：設定環境

在開始之前，請確保您已將 Aspose.Slides for Java 庫新增至您的專案。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).

## 第 2 步：建立新簡報

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 步驟 3：為投影片新增圖表

我們將在投影片中新增帶有標記的折線圖，然後繼續隱藏圖表的各個元素。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## 步驟 4：隱藏圖表標題

您可以如下隱藏圖表標題：

```java
chart.setTitle(false);
```

## 步驟 5：隱藏值軸

若要隱藏值軸（垂直軸），請使用下列程式碼：

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## 步驟 6：隱藏分類軸

若要隱藏類別軸（水平軸），請使用以下程式碼：

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## 步驟 7：隱藏圖例

您可以像這樣隱藏圖表的圖例：

```java
chart.setLegend(false);
```

## 步驟 8：隱藏主網格線

要隱藏水平軸的主要網格線，可以使用以下程式碼：

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## 步驟 9：刪除系列

如果您要從圖表中刪除所有系列，可以使用下列循環：

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## 步驟 10：自訂圖表系列

您可以根據需要自訂圖表系列。在此範例中，我們變更標記樣式、資料標籤位置、標記大小、線條顏色和虛線樣式：

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## 步驟 11：儲存簡報

最後，將簡報儲存到文件中：

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功使用 Aspose.Slides for Java 隱藏了 Java Slides 中圖表的各種元素。您可以根據您的特定要求進一步自訂圖表和簡報。

## Java 投影片中隱藏圖表資訊的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//隱藏圖表標題
	chart.setTitle(false);
	///隱藏值軸
	chart.getAxes().getVerticalAxis().setVisible(false);
	//類別軸可見性
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//隱藏傳奇
	chart.setLegend(false);
	//隱藏主要網格線
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//設定係列線條顏色
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## 結論

在本逐步指南中，我們探討如何使用 Aspose.Slides for Java API 隱藏 Java Slides 中圖表的各種元素。當您需要自訂圖表以用於演示並使其更具視覺吸引力或滿足您的特定需求時，這會非常有用。

## 常見問題解答

### 如何進一步自訂圖表元素的外觀？

您可以透過存取圖表系列、標記、標籤和格式的相應屬性來自訂圖表元素的各種屬性，例如線條顏色、填滿顏色、標記樣式等。

### 我可以隱藏圖表中的特定數據點嗎？

是的，您可以透過操作圖表系列中的資料來隱藏特定的資料點。您可以刪除資料點或將其值設為空以隱藏它們。

### 如何為圖表添加其他系列？

您可以使用 `IChartData.getSeries().add` 方法並指定新系列的資料點。

### 是否可以動態更改圖表類型？

是的，您可以透過建立所需類型的新圖表並將資料從舊圖表複製到新圖表來動態變更圖表類型。

### 如何以程式設計方式更改圖表的標題和軸標籤？

您可以透過存取圖表和軸各自的屬性並設定所需的文字和格式來設定圖表和軸的標題和標籤。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}