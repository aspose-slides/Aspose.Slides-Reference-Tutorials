---
title: 在 Java 投影片中加入甜甜圈標註
linktitle: 在 Java 投影片中加入甜甜圈標註
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 學習使用 Aspose.Slides for Java 在 Java 投影片中加入甜甜圈標註。帶有原始程式碼的分步指南，用於增強演示。
type: docs
weight: 12
url: /zh-hant/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## 使用 Aspose.Slides for Java 在 Java 投影片中加入甜甜圈標註的簡介

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 將 Donut Callout 新增至 Java 投影片的過程。圓環標註是一種圖表元素，可用於突顯圓環圖中的特定資料點。為了您的方便，我們將為您提供逐步說明和完整的原始程式碼。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1. Java開發環境
2. Aspose.Slides for Java 函式庫
3. 整合開發環境 (IDE)，例如 Eclipse 或 IntelliJ IDEA
4. 若要在其中加入甜甜圈標註的 PowerPoint 簡報

## 第 1 步：設定您的 Java 項目

1. 在您選擇的 IDE 中建立一個新的 Java 專案。
2. 將 Aspose.Slides for Java 程式庫作為依賴項新增至您的專案中。

## 第 2 步：初始化簡報

首先，您需要初始化 PowerPoint 簡報並建立一張投影片，在其中新增圓環標註。這是實現此目的的程式碼：

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

確保更換`"Your Document Directory"`與 PowerPoint 簡報文件的實際路徑。

## 第 3 步：建立圓環圖

接下來，您將在投影片上建立一個圓環圖。您可以根據您的要求自訂圖表的位置和大小。以下是新增圓環圖的程式碼：

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 第 4 步：自訂圓環圖

現在，是時候自訂圓環圖了。我們將設定各種屬性，例如刪除圖例、配置孔尺寸以及調整第一個切片角度。這是代碼：

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

此程式碼片段設定圓環圖的屬性。您可以調整這些值以滿足您的特定需求。

## 第 5 步：將資料新增至圓環圖

現在，讓我們為圓環圖新增資料。我們還將自訂資料點的外觀。這是完成此操作的程式碼：

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        //在此自訂資料點外觀
        i++;
    }
    categoryIndex++;
}
```

在此程式碼中，我們為圓環圖新增類別和資料點。您可以根據需要進一步自訂資料點的外觀。

## 第 6 步：儲存簡報

最後，不要忘記添加甜甜圈標註後保存簡報。這是保存簡報的程式碼：

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

確保更換`"chart.pptx"`與您想要的檔案名稱。

恭喜！您已使用 Aspose.Slides for Java 成功將 Donut Callout 新增至 Java 投影片中。現在，您可以執行 Java 應用程式來產生具有圓環圖和標註的 PowerPoint 簡報。

## 在 Java 投影片中加入甜甜圈標註的完整原始碼

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
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
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

在本教程中，我們介紹了使用 Aspose.Slides for Java 將 Donut Callout 新增至 Java 投影片的過程。您已經學習如何建立圓環圖、自訂其外觀以及新增資料點。請隨意使用這個強大的庫進一步增強您的簡報並探索更多圖表選項。

## 常見問題解答

### 如何更改甜甜圈標註的外觀？

您可以透過修改圖表中資料點的屬性來自訂圓環標註的外觀。在提供的程式碼中，您可以看到如何設定資料點的填滿顏色、線條顏色、字體樣式和其他屬性。

### 我可以為圓環圖添加更多數據點嗎？

是的，您可以根據需要向圓環圖添加任意數量的資料點。只需擴展程式碼中新增類別和資料點的循環，並提供適當的資料和格式即可。

### 如何調整投影片上圓環圖的位置和大小？

您可以透過修改中的參數來改變圓環圖的位置和大小`addChart`方法。此方法中的四個數字分別對應於圖表左上角的 X 和 Y 座標及其寬度和高度。