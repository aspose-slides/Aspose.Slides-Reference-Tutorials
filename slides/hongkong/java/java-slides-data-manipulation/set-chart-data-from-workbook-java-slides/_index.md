---
title: 在 Java 投影片中設定工作簿中的圖表數據
linktitle: 在 Java 投影片中設定工作簿中的圖表數據
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 在 Java Slides 中設定 Excel 工作簿中的圖表資料。包含動態演示程式碼範例的逐步指南。
weight: 15
url: /zh-hant/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中設定工作簿中的圖表數據


## 在 Java 投影片中從工作簿設定圖表資料簡介

Aspose.Slides for Java 是一個功能強大的函式庫，可讓開發人員以程式設計方式處理 PowerPoint 簡報。它提供了用於建立、操作和管理 PowerPoint 投影片的豐富功能。使用簡報時的常見要求是從外部資料來源（例如 Excel 工作簿）動態設定圖表資料。在本教程中，我們將示範如何使用 Java 實現此目的。

## 先決條件

在我們深入實施之前，請確保您符合以下先決條件：

- 您的系統上安裝了 Java 開發工具包 (JDK)。
- Aspose.Slides for Java 函式庫已新增至您的專案中。
- 包含要用於圖表的資料的 Excel 工作簿。

## 第 1 步：建立簡報

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

我們首先使用 Aspose.Slides for Java 建立一個新的 PowerPoint 簡報。

## 第 2 步：新增圖表

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

接下來，我們將圖表新增到簡報中的一張投影片中。在此範例中，我們新增了圓餅圖，但您可以選擇適合您需求的圖表類型。

## 第3步：清除圖表數據

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

我們清除圖表中的所有現有數據，為 Excel 工作簿中的新數據做好準備。

## 第 4 步：載入 Excel 工作簿

```java
Workbook workbook = new Workbook("Your Document Directory";
```

我們載入包含要用於圖表的資料的 Excel 工作簿。代替`"book1.xlsx"`以及 Excel 檔案的路徑。

## 第 5 步：將工作簿流程寫入圖表數據

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

我們將Excel工作簿資料轉換為串流並將其寫入圖表資料。

## 第6步：設定圖表資料範圍

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

我們指定在 Excel 工作簿中套用圖表資料的儲存格範圍。根據數據需要調整範圍。

## 第 7 步：自訂圖表系列

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

您可以自訂圖表系列的各種屬性來滿足您的要求。在此範例中，我們為圖表系列啟用不同的顏色。

## 第 8 步：儲存簡報

```java
pres.save(outPath, SaveFormat.Pptx);
```

最後，我們將包含更新的圖表資料的簡報儲存到指定的輸出路徑。

## 在 Java 投影片中從工作簿設定圖表資料的完整原始碼

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.Slides for Java 函式庫在 Java Slides 中設定 Excel 工作簿中的圖表資料。透過遵循逐步指南並使用提供的原始程式碼範例，您可以輕鬆地將動態圖表資料整合到 PowerPoint 簡報中。

## 常見問題解答

### 如何自訂簡報中圖表的外觀？

您可以透過修改顏色、字體、標籤等屬性來自訂圖表的外觀。有關圖表自訂選項的詳細信息，請參閱 Aspose.Slides for Java 文件。

### 我可以將不同 Excel 檔案中的資料用於圖表嗎？

是的，您可以在程式碼中載入工作簿時透過指定正確的檔案路徑來使用任何 Excel 檔案中的資料。

### 我還可以使用 Aspose.Slides for Java 建立哪些其他類型的圖表？

Aspose.Slides for Java支援各種圖表類型，包括長條圖、折線圖、散點圖等。您可以選擇最適合您的資料表示需求的圖表類型。

### 是否可以在運行的簡報中動態更新圖表資料？

是的，您可以透過修改基礎工作簿然後刷新圖表資料來動態更新簡報中的圖表資料。

### 在哪裡可以找到更多使用 Aspose.Slides for Java 的範例和資源？

您可以探索其他範例和資源[阿斯普斯網站](https://www.aspose.com/)。此外，Aspose.Slides for Java 文件提供了有關使用該程式庫的全面指導。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
