---
"description": "了解如何使用 Aspose.Slides for Java 在 Java Slides 中設定外部工作簿。利用 Excel 資料整合建立動態簡報。"
"linktitle": "在 Java Slides 中設定外部工作簿"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中設定外部工作簿"
"url": "/zh-hant/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中設定外部工作簿


## Java 投影片中設定外部工作簿的介紹

在本教程中，我們將探討如何使用 Aspose.Slides 在 Java Slides 中設定外部工作簿。您將學習如何建立帶有引用外部 Excel 工作簿資料的圖表的 PowerPoint 簡報。在本指南結束時，您將清楚地了解如何將外部資料整合到 Java Slides 簡報中。

## 先決條件

在深入實施之前，請確保您符合以下先決條件：

- 您的系統上安裝了 Java 開發工具包 (JDK)。
- Aspose.Slides for Java 函式庫已新增至您的專案中。
- 包含您想要在簡報中引用的資料的 Excel 工作簿。

## 步驟 1：建立新簡報

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

我們首先使用 Aspose.Slides 建立一個新的 PowerPoint 簡報。

## 第 2 步：新增圖表

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

接下來，我們在簡報中插入一個圓餅圖。您可以根據需要自訂圖表類型和位置。

## 步驟 3：存取外部工作簿

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

要存取外部工作簿，我們使用 `setExternalWorkbook` 方法並提供包含資料的 Excel 工作簿的路徑。

## 步驟4：綁定圖表數據

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

我們透過指定係列和類別的儲存格參考將圖表綁定到外部工作簿中的資料。

## 步驟 5：儲存簡報

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

最後，我們將帶有外部工作簿引用的簡報儲存為 PowerPoint 文件。

## Java 投影片中設定外部工作簿的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides 在 Java Slides 中設定外部工作簿。現在您可以建立動態引用 Excel 工作簿中的資料的演示文稿，從而增強幻燈片的靈活性和互動性。

## 常見問題解答

### 如何安裝 Aspose.Slides for Java？

可以透過將程式庫新增至 Java 專案來安裝 Aspose.Slides for Java。您可以從 Aspose 網站下載該庫並按照文件中提供的安裝說明進行操作。

### 我可以在外部工作簿中使用不同的圖表類型嗎？

是的，您可以使用 Aspose.Slides 支援的各種圖表類型並將它們綁定到外部工作簿的資料。根據您選擇的圖表類型，該過程可能會略有不同。

### 如果我的外部工作簿的資料結構發生變化怎麼辦？

如果外部工作簿的資料結構發生變化，您可能需要更新 Java 程式碼中的儲存格引用，以確保圖表資料保持準確。

### Aspose.Slides 是否與最新的 Java 版本相容？

Aspose.Slides for Java 定期更新以確保與最新的 Java 版本相容。請務必檢查更新並使用最新版本的庫以獲得最佳效能和相容性。

### 我可以新增引用同一外部工作簿的多個圖表嗎？

是的，您可以為簡報新增多個圖表，所有圖表都引用同一個外部工作簿。只需對要建立的每個圖表重複本教程中概述的步驟即可。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}