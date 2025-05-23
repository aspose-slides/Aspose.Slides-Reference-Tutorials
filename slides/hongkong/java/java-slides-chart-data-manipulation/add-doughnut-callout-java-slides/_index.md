---
"description": "學習使用 Aspose.Slides for Java 在 Java 投影片中加入甜甜圈標註。帶有原始程式碼的逐步指南，用於增強演示效果。"
"linktitle": "在 Java 投影片中加入甜甜圈標註"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 投影片中加入甜甜圈標註"
"url": "/zh-hant/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中加入甜甜圈標註


## 使用 Aspose.Slides for Java 在 Java 投影片中加入甜甜圈標註的簡介

在本教程中，我們將引導您完成使用 Aspose.Slides for Java 在 Java 中為投影片新增 Doughnut Callout 的過程。圓環圖示註是一種圖表元素，可用於突顯圓環圖中的特定資料點。我們將為您提供逐步說明和完整的源代碼，以方便您使用。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

1. Java 開發環境
2. Aspose.Slides for Java 函式庫
3. 整合開發環境 (IDE)，例如 Eclipse 或 IntelliJ IDEA
4. 您想要新增甜甜圈標示的 PowerPoint 簡報

## 步驟 1：設定 Java 項目

1. 在您選擇的 IDE 中建立一個新的 Java 專案。
2. 將 Aspose.Slides for Java 程式庫作為依賴項新增至您的專案中。

## 步驟 2：初始化簡報

首先，您需要初始化 PowerPoint 簡報並建立要新增甜甜圈標註的投影片。以下是實現此目的的程式碼：

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

確保更換 `"Your Document Directory"` 使用 PowerPoint 簡報文件的實際路徑。

## 步驟 3：建立圓環圖

接下來，您將在投影片上建立一個圓環圖。您可以根據需要自訂圖表的位置和大小。以下是添加甜甜圈圖的程式碼：

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 步驟 4：自訂圓環圖

現在，是時候自訂圓環圖了。我們將設定各種屬性，例如刪除圖例、配置孔大小以及調整第一個切片角度。程式碼如下：

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

此程式碼片段設定了圓環圖的屬性。您可以調整這些值以滿足您的特定需求。

## 步驟 5：為圓環圖新增數據

現在，讓我們將資料新增至圓環圖。我們還將自訂資料點的外觀。以下是實現此目的的程式碼：

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // 在此自訂資料點外觀
        i++;
    }
    categoryIndex++;
}
```

在此程式碼中，我們為圓環圖新增類別和資料點。您可以根據需要進一步自訂資料點的外觀。

## 步驟 6：儲存簡報

最後，添加甜甜圈標註後，不要忘記保存您的簡報。以下是儲存簡報的程式碼：

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

確保更換 `"chart.pptx"` 使用您想要的檔案名稱。

恭喜！您已成功使用 Aspose.Slides for Java 將 Doughnut Callout 新增至 Java 投影片。現在您可以執行 Java 應用程式來產生具有圓環圖和標註的 PowerPoint 簡報。

## 在 Java 投影片中新增甜甜圈標註的完整原始碼

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.取得資料標籤格式（）。設定顯示標籤為資料標註（真）；
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## 結論

在本教學中，我們介紹了使用 Aspose.Slides for Java 為 Java 投影片新增 Doughnut Callout 的過程。您已經學習如何建立圓環圖、自訂其外觀以及新增資料點。歡迎使用這個強大的庫進一步增強您的簡報並探索更多圖表選項。

## 常見問題解答

### 如何更改甜甜圈標註的外觀？

您可以透過修改圖表中資料點的屬性來自訂甜甜圈標註的外觀。在提供的程式碼中，您可以看到如何設定資料點的填滿顏色、線條顏色、字體樣式和其他屬性。

### 我可以為圓環圖添加更多數據點嗎？

是的，您可以根據需要向圓環圖添加任意數量的資料點。只需擴展程式碼中新增類別和資料點的循環，並提供適當的資料和格式。

### 如何調整投影片上圓環圖的位置和大小？

您可以透過修改 `addChart` 方法。此方法中的四個數字分別對應於圖表左上角的 X 和 Y 座標及其寬度和高度。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}