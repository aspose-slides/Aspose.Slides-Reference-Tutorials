---
"description": "使用 Aspose.Slides for Java 增強 Java Slides 中的圖表字體屬性。自訂字體大小、樣式和顏色，以獲得具有影響力的簡報。"
"linktitle": "Java 投影片中圖表的字型屬性"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中圖表的字型屬性"
"url": "/zh-hant/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中圖表的字型屬性


## Java 投影片中圖表字型屬性介紹

本指南將引導您使用 Aspose.Slides 設定 Java Slides 中圖表的字體屬性。您可以自訂圖表文字的字體大小和外觀，以增強簡報的視覺吸引力。

## 先決條件

在開始之前，請確保已將 Aspose.Slides for Java API 整合到您的專案中。如果你還沒有下載，你可以從 [Aspose.Slides for Java 文檔](https://reference。aspose.com/slides/java/).

## 步驟 1：建立簡報

首先，使用以下程式碼建立一個新的簡報：

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：新增圖表

現在，讓我們在簡報中新增一個簇狀長條圖：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

在這裡，我們在第一張投影片的座標 (100, 100) 處新增一個簇狀長條圖，寬度為 500 個單位，高度為 400 個單位。

## 步驟3：自訂字體屬性

接下來，我們將自訂圖表的字體屬性。在此範例中，我們將所有圖表文字的字體大小設為 20：

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

此程式碼將圖表中所有文字的字體大小設定為 20 磅。

## 步驟 4：顯示資料標籤

您也可以使用以下程式碼在圖表上顯示資料標籤：

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

這行程式碼為圖表中第一個系列啟用資料標籤，並在圖表列上顯示值。

## 步驟 5：儲存簡報

最後，使用自訂的圖表字體屬性儲存簡報：

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

此程式碼將簡報儲存到指定目錄，檔案名稱為「FontPropertiesForChart.pptx」。

## Java 投影片中圖表字型屬性的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 自訂 Java Slides 中圖表的字型屬性。您可以應用這些技術來增強圖表和簡報的外觀。探索更多選項 [Aspose.Slides for Java 文檔](https://reference。aspose.com/slides/java/).

## 常見問題解答

### 我怎麼能更改字體顏色？

若要變更圖表文字的字體顏色，請使用 `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`，替換 `Color.RED` 並採用所需的顏色。

### 我可以更改字體樣式（粗體、斜體等）嗎？

是的，您可以變更字體樣式。使用 `chart.getTextFormat().getPortionFormat().setFontBold(true);` 使字體變粗。類似地，您可以使用 `setFontItalic(true)` 使其變為斜體。

### 如何自訂特定圖表元素的字體屬性？

若要自訂特定圖表元素（例如軸標籤或圖例文字）的字體屬性，您可以存取這些元素並使用與上方類似的方法設定其字體屬性。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}