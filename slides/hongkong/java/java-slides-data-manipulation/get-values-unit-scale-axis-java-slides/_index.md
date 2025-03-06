---
title: 在 Java 投影片中從 Axis 取得值和單位比例
linktitle: 在 Java 投影片中從 Axis 取得值和單位比例
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 從 Java Slides 中的軸獲取值和單位比例。增強您的數據分析能力。
weight: 20
url: /zh-hant/java/data-manipulation/get-values-unit-scale-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 投影片中從軸取得值和單位比例的簡介

在本教程中，我們將探索如何使用 Aspose.Slides for Java API 從 Java Slides 中的軸檢索值和單位比例。無論您是從事數據視覺化專案還是需要分析 Java 應用程式中的圖表數據，了解如何存取軸值都是至關重要的。我們將逐步引導您完成整個過程，並一路提供程式碼範例。

## 先決條件

在我們深入研究程式碼之前，請確保您具備以下先決條件：

1. Java 開發環境：確保您的系統上安裝了 Java 並且熟悉 Java 程式設計概念。

2.  Aspose.Slides for Java：從下列位置下載並安裝 Aspose.Slides for Java 函式庫[下載連結](https://releases.aspose.com/slides/java/).

## 第 1 步：建立簡報

首先，讓我們使用 Aspose.Slides for Java 建立一個新的簡報：

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

代替`"Your Document Directory"`以及要儲存簡報的目錄的路徑。

## 第 2 步：新增圖表

接下來，我們將向簡報新增圖表。在此範例中，我們將建立面積圖：

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
chart.validateChartLayout();
```

我們在簡報的第一張投影片中新增了面積圖。您可以根據需要自訂圖表類型和位置。

## 步驟 3：檢索縱軸值

現在，讓我們從圖表的垂直軸檢索值：

```java
double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
```

在這裡，我們取得垂直軸的最大值和最小值。這些值對於各種數據分析任務非常有用。

## 步驟 4：檢索水平軸值

同樣，我們可以從水平軸檢索值：

```java
double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
```

這`majorUnit`和`minorUnit`值分別表示水平軸上的主要單位和次要單位。

## 第 5 步：儲存簡報

一旦我們檢索到軸值，我們就可以儲存簡報：

```java
pres.save(dataDir + "ChartValues.pptx", SaveFormat.Pptx);
```

此程式碼將簡報與檢索到的軸值儲存到 PowerPoint 文件中。

## 在 Java 投影片中從軸取得值和單位比例的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
	chart.validateChartLayout();
	double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
	double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
	double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
	double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
	//儲存簡報
	pres.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教程中，我們探索如何使用 Aspose.Slides for Java 從 Java Slides 中的軸獲取值和單位比例。當在 Java 應用程式中處理圖表和分析資料時，這非常有價值。 Aspose.Slides for Java 提供了以程式設計方式處理簡報所需的工具，讓您可以控制圖表資料等。

## 常見問題解答

### 如何在 Aspose.Slides for Java 中自訂圖表類型？

要自訂圖表類型，只需替換`ChartType.Area`將圖表新增至簡報時使用所需的圖表類型。

### 我可以更改圖表軸標籤的外觀嗎？

是的，您可以使用 Aspose.Slides for Java 自訂圖表軸標籤的外觀。請參閱文件以取得詳細指導。

### Aspose.Slides for Java 與最新的 Java 版本相容嗎？

Aspose.Slides for Java 定期更新以支援最新的 Java 版本，確保與最新的 Java 開發相容。

### 我可以在商業專案中使用 Aspose.Slides for Java 嗎？

是的，您可以在商業專案中使用Aspose.Slides for Java。它提供許可選項來滿足各種項目要求。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多資源和文件？

您可以在以下位置找到全面的文件和其他資源[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/)網站。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
