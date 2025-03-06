---
title: 在 Java 投影片中設定自動圓餅圖切片顏色
linktitle: 在 Java 投影片中設定自動圓餅圖切片顏色
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中建立具有自動切片色彩的動態圓餅圖。帶有原始程式碼的分步指南。
weight: 24
url: /zh-hant/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中設定自動圓餅圖切片顏色


## 在 Java 投影片中設定自動餅圖切片顏色的簡介

在本教程中，我們將探討如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立圓餅圖並為圖表設定自動切片顏色。我們將提供逐步指導以及原始程式碼。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 Aspose 網站下載該資料庫：[下載 Java 版 Aspose.Slides](https://releases.aspose.com/slides/java/).

## 步驟1：導入所需的套件

首先，您需要從 Aspose.Slides for Java 匯入必要的套件：

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## 步驟 2：建立 PowerPoint 簡報

實例化`Presentation`建立新的 PowerPoint 簡報的類別：

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 第 3 步：新增投影片

存取簡報的第一張投影片並新增包含預設資料的圖表：

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## 第 4 步：設定圖表標題

設定圖表標題：

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 第5步：配置圖表數據

設定圖表以顯示第一個系列的值並配置圖表資料：

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 第 6 步：新增類別和系列

將新類別和系列新增至圖表：

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## 第 7 步：填充系列數據

填充圓餅圖的系列數據：

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## 第 8 步：啟用不同的切片顏色

為圓餅圖啟用不同的切片顏色：

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## 第 9 步：儲存簡報

最後，將簡報儲存到 PowerPoint 檔案：

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## 在 Java 幻燈片中設定自動餅圖切片顏色的完整原始程式碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//實例化表示 PPTX 檔案的簡報類
Presentation presentation = new Presentation();
try
{
	//存取第一張投影片
	ISlide slides = presentation.getSlides().get_Item(0);
	//新增帶有預設資料的圖表
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	//設定圖表標題
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	//將第一個系列設定為“顯示值”
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	//設定圖表資料表索引
	int defaultWorksheetIndex = 0;
	//取得圖表資料工作表
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	//刪除預設產生的系列和類別
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	//新增類別
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	//新增系列
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	//現在正在填充系列數據
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

您已使用 Aspose.Slides for Java 在 PowerPoint 簡報中成功建立了圓餅圖，並將其配置為具有自動切片顏色。本逐步指南為您提供了實現此目的所需的原始程式碼。您可以根據需要進一步自訂圖表和簡報。

## 常見問題解答

### 如何自訂餅圖中各個切片的顏色？

要自訂餅圖中各個切片的顏色，您可以使用`getAutomaticSeriesColors`方法檢索預設配色方案，然後根據需要修改顏色。這是一個例子：

```java
//取得預設配色方案
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

//根據需要修改顏色
colors.get_Item(0).setColor(Color.RED); //將第一個切片的顏色設定為紅色
colors.get_Item(1).setColor(Color.BLUE); //將第二個切片的顏色設定為藍色
//根據需要添加更多顏色修改
```

### 如何為餅圖添加圖例？

若要為圓餅圖新增圖例，您可以使用`getLegend`方法並配置如下：

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); //設定圖例位置
legend.setOverlay(true); //在圖表上顯示圖例
```

### 我可以更改標題字體和样式嗎？

是的，您可以變更標題字體和樣式。使用以下程式碼設定標題字體和樣式：

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); //設定字體大小
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); //將標題加粗
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); //將標題設為斜體
```

您可以根據需要調整字體大小、粗細和斜體樣式。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
