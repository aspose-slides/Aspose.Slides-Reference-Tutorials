---
title: 在 Java 投影片中設定位置軸
linktitle: 在 Java 投影片中設定位置軸
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides for Java 增強您的圖表。了解如何在 Java 投影片中設定位置軸、建立令人驚嘆的簡報以及輕鬆自訂圖表佈局。
weight: 16
url: /zh-hant/java/customization-and-formatting/setting-position-axis-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java中設定位置軸簡介

在本教程中，我們將學習如何使用 Aspose.Slides for Java 在圖表中設定位置軸。當您想要自訂圖表的外觀和佈局時，定位軸非常有用。我們將建立一個聚集長條圖並調整類別之間水平軸的位置。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從以下位置下載該程式庫[這裡](https://releases.aspose.com/slides/java/).

## 第 1 步：建立簡報

首先，讓我們建立一個新的簡報來使用：

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

確保更換`"Your Document Directory"`與文檔目錄的實際路徑。

## 第 2 步：新增圖表

接下來，我們將在投影片中新增聚集長條圖。我們指定圖表類型、位置（x、y 座標）和圖表尺寸（寬度和高度）：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

在這裡，我們在位置 (50, 50) 中新增了一個寬度為 450、高度為 300 的聚集長條圖。

## 第三步：設定位置軸

若要設定類別之間的位置軸，可以使用下列代碼：

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

此程式碼設定在類別之間顯示的水平軸，這對於某些圖表佈局非常有用。

## 步驟 4：儲存簡報

最後，讓我們保存帶有圖表的簡報：

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

代替`"AsposeClusteredColumnChart.pptx"`與您想要的檔案名稱。

就是這樣！您已成功建立了一個簇狀長條圖，並使用 Aspose.Slides for Java 設定了類別之間的位置軸。

## 完整的原始碼
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教程中，我們探索如何使用 Aspose.Slides for Java 在圖表中設定位置軸。透過遵循本指南中概述的步驟，您已了解如何建立聚集長條圖並透過在類別之間定位水平軸來自訂其外觀。 Aspose.Slides for Java 提供了處理圖表和簡報的強大功能，使其成為 Java 開發人員的寶貴工具。

## 常見問題解答

### 如何進一步自訂圖表？

您可以自訂圖表的各個方面，包括資料系列、圖表標題、圖例等。請參閱[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/)取得詳細說明和範例。

### 我可以更改圖表類型嗎？

是的，您可以透過修改`ChartType`新增圖表時的參數。 Aspose.Slides for Java 支援各種圖表類型，如長條圖、折線圖等。

### 在哪裡可以找到更多範例和文件？

您可以在以下位置找到全面的文件和更多範例[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/)頁。

請記得在使用完演示物件後將其丟棄以釋放系統資源：

```java
if (pres != null) pres.dispose();
```

這就是本教學的內容。您已經學習如何使用 Aspose.Slides for Java 在圖表中設定位置軸。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
