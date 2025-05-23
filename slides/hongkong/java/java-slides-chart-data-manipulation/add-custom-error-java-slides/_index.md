---
"description": "了解如何使用 Aspose.Slides 為 Java Slides 中的 PowerPoint 圖表新增自訂誤差線。帶有原始程式碼的分步指南，用於精確的資料視覺化。"
"linktitle": "在 Java 投影片中新增自訂錯誤"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 投影片中新增自訂錯誤"
"url": "/zh-hant/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中新增自訂錯誤


## 使用 Aspose.Slides 在 Java Slides 中新增自訂誤差線的簡介

在本教學中，您將學習如何使用 Aspose.Slides for Java 為 PowerPoint 簡報中的圖表新增自訂誤差線。誤差線可用於顯示圖表上資料點的變化或不確定性。

## 先決條件

在開始之前，請確保您已具備以下條件：

- 在您的專案中安裝並設定 Java 程式庫的 Aspose.Slides。
- Java 開發環境已設定。

## 步驟 1：建立空白簡報

首先，建立一個空的 PowerPoint 簡報。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立空白簡報
Presentation presentation = new Presentation();
```

## 第 2 步：新增氣泡圖

接下來，我們將在簡報中新增氣泡圖。

```java
// 創建氣泡圖
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## 步驟 3：新增自訂誤差線

現在，讓我們為圖表系列新增自訂誤差線。

```java
// 新增自訂誤差線並設定其格式
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## 步驟4：設定誤差線數據

在此步驟中，我們將存取圖表系列資料點並為每個點設定自訂誤差線值。

```java
// 存取圖表系列資料點並設定各點的誤差線值
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// 為圖表系列點設定誤差線
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## 步驟 5：儲存簡報

最後，儲存帶有自訂誤差線的簡報。

```java
// 儲存簡報
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功使用 Aspose.Slides for Java 將自訂誤差線新增至 PowerPoint 簡報中的圖表中。

## 在 Java 投影片中新增自訂錯誤的完整原始程式碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立空白簡報
Presentation presentation = new Presentation();
try
{
	// 創建氣泡圖
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// 新增自訂誤差線並設定其格式
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// 存取圖表系列資料點並設定單一點的誤差線值
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// 為圖表系列點設定誤差線
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// 儲存簡報
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本綜合教學中，您將學習如何使用 Aspose.Slides for Java 為圖表新增自訂誤差線來增強 PowerPoint 簡報。誤差線提供了有關數據變化和不確定性的寶貴見解，使您的圖表更具資訊量和視覺吸引力。

## 常見問題解答

### 如何自訂誤差線的外觀？

您可以透過修改 `IErrorBarsFormat` 對象，例如線條樣式、線條顏色和誤差線寬度。

### 我可以為其他圖表類型添加誤差線嗎？

是的，您可以將誤差線新增至 Aspose.Slides for Java 支援的各種圖表類型，包括長條圖、折線圖和散佈圖。

### 如何為每個數據點設定不同的誤差線值？

您可以循環遍歷資料點並為每個點設定自訂誤差線值，如上面的程式碼所示。

### 是否可以隱藏特定資料點的誤差線？

是的，您可以透過設定 `setVisible` 的財產 `IErrorBarsFormat` 目的。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}