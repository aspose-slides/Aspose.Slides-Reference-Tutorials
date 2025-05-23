---
"description": "了解如何使用 Aspose.Slides 從 Java Slides 中的 Excel 工作簿設定圖表資料。帶有動態演示程式碼範例的逐步指南。"
"linktitle": "在 Java Slides 中從工作簿設定圖表數據"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中從工作簿設定圖表數據"
"url": "/zh-hant/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中從工作簿設定圖表數據


## Java 投影片中從工作簿設定圖表資料的介紹

Aspose.Slides for Java 是一個功能強大的函式庫，可讓開發人員以程式設計方式處理 PowerPoint 簡報。它提供了用於建立、操作和管理 PowerPoint 投影片的廣泛功能。處理簡報時的常見要求是從外部資料來源（例如 Excel 工作簿）動態設定圖表資料。在本教程中，我們將示範如何使用 Java 實現這一點。

## 先決條件

在深入實施之前，請確保您符合以下先決條件：

- 您的系統上安裝了 Java 開發工具包 (JDK)。
- Aspose.Slides for Java 函式庫已新增至您的專案中。
- 包含要用於圖表的資料的 Excel 工作簿。

## 步驟 1：建立簡報

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

我們首先使用 Aspose.Slides for Java 建立一個新的 PowerPoint 簡報。

## 第 2 步：新增圖表

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

接下來，我們在簡報的其中一張投影片中新增一個圖表。在此範例中，我們新增了一個圓餅圖，但您可以選擇適合您需求的圖表類型。

## 步驟3：清除圖表數據

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

我們清除圖表中的所有現有數據，以便為 Excel 工作簿中的新數據做好準備。

## 步驟 4：載入 Excel 工作簿

```java
Workbook workbook = new Workbook("Your Document Directory";
```

我們載入包含想要用於圖表的資料的 Excel 工作簿。代替 `"book1.xlsx"` 以及您的 Excel 檔案的路徑。

## 步驟5：將工作簿流寫入圖表數據

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

我們將Excel工作簿資料轉換為串流並將其寫入圖表資料。

## 步驟6：設定圖表數據範圍

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

我們從 Excel 工作簿中指定套用於圖表資料的儲存格範圍。根據您的數據需要調整範圍。

## 步驟 7：自訂圖表系列

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

您可以自訂圖表系列的各種屬性以滿足您的要求。在這個例子中，我們為圖表系列啟用了不同的顏色。

## 步驟 8：儲存簡報

```java
pres.save(outPath, SaveFormat.Pptx);
```

最後，我們將包含更新的圖表資料的簡報儲存到指定的輸出路徑。

## Java 投影片中從工作簿設定圖表資料的完整原始碼

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

在本教學中，我們學習如何使用 Aspose.Slides for Java 函式庫從 Java Slides 中的 Excel 工作簿設定圖表資料。透過遵循逐步指南並使用提供的原始程式碼範例，您可以輕鬆地將動態圖表資料整合到 PowerPoint 簡報中。

## 常見問題解答

### 如何自訂簡報中圖表的外觀？

您可以透過修改顏色、字體、標籤等屬性來自訂圖表的外觀。有關圖表自訂選項的詳細信息，請參閱 Aspose.Slides for Java 文件。

### 我可以使用來自不同 Excel 檔案的資料來製作圖表嗎？

是的，您可以透過在程式碼中載入工作簿時指定正確的檔案路徑來使用任何 Excel 檔案中的資料。

### 我可以使用 Aspose.Slides for Java 建立哪些其他類型的圖表？

Aspose.Slides for Java 支援各種圖表類型，包括長條圖、折線圖、散點圖等。您可以選擇最適合您的資料表示需求的圖表類型。

### 是否可以在正在運行的簡報中動態更新圖表資料？

是的，您可以透過修改底層工作簿然後刷新圖表資料來動態更新簡報中的圖表資料。

### 在哪裡可以找到更多使用 Aspose.Slides for Java 的範例和資源？

您可以在 [Aspose 網站](https://www.aspose.com/)。此外，Aspose.Slides for Java 文件提供了有關使用該程式庫的全面指導。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}