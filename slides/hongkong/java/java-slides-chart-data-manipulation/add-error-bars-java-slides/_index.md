---
"description": "了解如何使用 Aspose.Slides 在 Java 中為 PowerPoint 圖表新增誤差線。帶有自訂誤差線原始程式碼的逐步指南。"
"linktitle": "在 Java 投影片中新增誤差線"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 投影片中新增誤差線"
"url": "/zh-hant/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中新增誤差線


## 使用 Aspose.Slides 在 Java Slides 中加入誤差線的簡介

在本教學中，我們將示範如何使用 Aspose.Slides for Java 為 PowerPoint 投影片中的圖表新增誤差線。誤差線提供了有關圖表中數據點的變化或不確定性的有價值的資訊。我們將創建一個氣泡圖並向其中添加誤差線。讓我們開始吧！

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 [Aspose 網站](https://downloads。aspose.com/slides/java).

## 步驟 1：建立空白簡報

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立空白簡報
Presentation presentation = new Presentation();
```

在此步驟中，我們建立一個空的演示文稿，我們將在其中添加帶有誤差線的圖表。

## 第 2 步：建立氣泡圖

```java
// 創建氣泡圖
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

在這裡，我們建立一個氣泡圖並指定其在投影片上的位置和尺寸。

## 步驟3：新增誤差線並設定格式

```java
// 新增誤差線並設定其格式
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

在此步驟中，我們向圖表新增誤差線並設定其格式。您可以透過變更值、類型和其他屬性來自訂誤差線。

- `errBarX` 表示沿 X 軸的誤差線。
- `errBarY` 表示沿 Y 軸的誤差線。
- 我們使 X 和 Y 誤差線都可見。
- `setValueType` 指定誤差線的值類型（例如，固定或百分比）。
- `setValue` 設定誤差線的值。
- `setType` 定義誤差線的類型（例如，加號或減號）。
- 我們使用以下方式設定誤差線的寬度 `getFormat()。getLine().setWidth(2)`.
- `setEndCap` 指定是否在誤差線上包含末端帽。

## 步驟 4：儲存簡報

```java
// 儲存簡報
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

最後，我們將新增誤差線的簡報儲存到指定位置。

就是這樣！您已成功使用 Aspose.Slides for Java 將誤差線新增至 PowerPoint 投影片中的圖表。

## Java 投影片中新增誤差線的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立空白簡報
Presentation presentation = new Presentation();
try
{
	// 創建氣泡圖
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// 新增誤差線並設定其格式
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// 儲存簡報
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教學中，我們探討如何使用 Aspose.Slides for Java 為圖表新增誤差線來增強您的 PowerPoint 簡報。誤差線提供了有關數據變化和不確定性的寶貴見解，使您的簡報更具資訊量和視覺吸引力。

## 常見問題解答

### 如何進一步自訂誤差線的外觀？

您可以透過修改誤差線的屬性（例如線條樣式、顏色和寬度）來自訂誤差線，如步驟 3 所示。

### 我可以為不同類型的圖表添加誤差線嗎？

是的，您可以為 Aspose.Slides for Java 支援的各種圖表類型新增誤差線。只需建立所需的圖表類型並按照相同的誤差線自訂步驟即可。

### 如何調整投影片上圖表的位置和大小？

您可以透過調整 `addChart` 方法，如步驟2所示。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多資訊？

您可以參考 [Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/) 有關使用該庫的詳細資訊。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}