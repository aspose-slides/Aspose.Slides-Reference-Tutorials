---
title: 在 Java 投影片中新增誤差線
linktitle: 在 Java 投影片中新增誤差線
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 在 Java 中為 PowerPoint 圖表新增誤差線。包含用於自訂誤差線的原始程式碼的逐步指南。
type: docs
weight: 13
url: /zh-hant/java/chart-data-manipulation/add-error-bars-java-slides/
---

## 使用 Aspose.Slides 在 Java 投影片中新增誤差線的簡介

在本教學中，我們將示範如何使用 Aspose.Slides for Java 將誤差線新增至 PowerPoint 投影片中的圖表。誤差線提供有關圖表中數據點的可變性或不確定性的有價值的資訊。我們將創建一個氣泡圖並向其添加誤差線。讓我們開始吧！

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從以下位置下載該程式庫[阿斯普斯網站](https://downloads.aspose.com/slides/java).

## 第 1 步：建立一個空簡報

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立空白簡報
Presentation presentation = new Presentation();
```

在此步驟中，我們建立一個空白演示文稿，在其中添加帶有誤差線的圖表。

## 第 2 步：建立氣泡圖

```java
//創建氣泡圖
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

在這裡，我們建立一個氣泡圖並指定其在投影片上的位置和尺寸。

## 第三步：新增誤差線並設定格式

```java
//新增誤差線並設定其格式
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

在此步驟中，我們將誤差線新增至圖表中並設定其格式。您可以透過變更值、類型和其他屬性來自訂誤差線。

- `errBarX`表示沿 X 軸的誤差線。
- `errBarY`表示沿 Y 軸的誤差線。
- 我們使 X 和 Y 誤差線都可見。
- `setValueType`指定誤差線的值類型（例如，固定或百分比）。
- `setValue`設定誤差線的值。
- `setType`定義誤差線的類型（例如，加號或減號）。
- 我們使用以下方法設定誤差線的寬度`getFormat().getLine().setWidth(2)`.
- `setEndCap`指定是否在誤差條上包含端蓋。

## 第 4 步：儲存簡報

```java
//儲存簡報
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

最後，我們將新增了誤差線的簡報儲存到指定位置。

就是這樣！您已使用 Aspose.Slides for Java 成功將誤差線新增至 PowerPoint 投影片的圖表中。

## 在 Java 投影片中新增誤差線的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立空白簡報
Presentation presentation = new Presentation();
try
{
	//創建氣泡圖
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	//新增誤差線並設定其格式
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
	//儲存簡報
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教學中，我們探索如何使用 Aspose.Slides for Java 為圖表新增誤差線來增強 PowerPoint 簡報。誤差線提供了有關數據可變性和不確定性的寶貴見解，使您的簡報資訊更豐富且更具視覺吸引力。

## 常見問題解答

### 如何進一步自訂誤差線的外觀？

您可以透過修改誤差線的屬性（例如線條樣式、顏色和寬度）來自訂誤差線，如步驟 3 所示。

### 我可以為不同的圖表類型添加誤差線嗎？

是的，您可以將誤差線新增至 Aspose.Slides for Java 支援的各種圖表類型中。只需建立所需的圖表類型並遵循相同的誤差線自訂步驟即可。

### 如何調整投影片上圖表的位置和大小？

您可以透過調整中的參數來控制圖表的位置和尺寸`addChart`方法，如步驟2所示。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多資訊？

您可以參考[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/)有關使用圖書館的詳細資訊。