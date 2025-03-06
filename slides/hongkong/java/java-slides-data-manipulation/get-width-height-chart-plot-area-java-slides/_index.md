---
title: 從 Java 投影片中的圖表繪圖區域取得寬度和高度
linktitle: 從 Java 投影片中的圖表繪圖區域取得寬度和高度
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java Slides 中擷取圖表繪圖區域尺寸。增強您的 PowerPoint 自動化技能。
weight: 21
url: /zh-hant/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## 介紹

圖表是在 PowerPoint 簡報中視覺化資料的有效方式。有時，您可能會因為各種原因需要了解圖表繪圖區域的尺寸，例如調整圖表中元素的大小或重新定位。本指南將示範如何使用 Java 和 Aspose.Slides for Java 取得繪圖區域的寬度和高度。

## 先決條件

在我們深入研究程式碼之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 Aspose 網站下載該庫[這裡](https://releases.aspose.com/slides/java/).

## 第 1 步：設定環境

確保您已將 Aspose.Slides for Java 程式庫新增至您的 Java 專案中。您可以透過將庫包含在專案的依賴項或手動新增 JAR 檔案來完成此操作。

## 步驟 2：建立 PowerPoint 簡報

我們首先建立一個 PowerPoint 簡報並在其中新增一張投影片。這將作為我們圖表的容器。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

代替`"Your Document Directory"`與您的文檔目錄的路徑。

## 第 3 步：新增圖表

現在，讓我們為投影片添加聚集長條圖。我們還將驗證圖表佈局。

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

此代碼在位置 (100, 100) 處建立尺寸為 (500, 350) 的聚集長條圖。

## 第 4 步：取得繪圖區域尺寸

要檢索圖表繪圖區域的寬度和高度，我們可以使用以下程式碼：

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

現在，變數`x`, `y`, `w`， 和`h`包含繪圖區域的 X 座標、Y 座標、寬度和高度的對應值。

## 第 5 步：儲存簡報

最後，儲存帶有圖表的簡報。

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

確保更換`"Chart_out.pptx"`與您想要的輸出檔名。

## 從 Java 投影片中的圖表繪圖區域取得寬度和高度的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	//儲存帶有圖表的簡報
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本文中，我們介紹如何使用 Aspose.Slides for Java API 來取得 Java Slides 中圖表繪圖區域的寬度和高度。當您需要動態調整 PowerPoint 簡報中的圖表佈局時，此資訊可能非常有價值。

## 常見問題解答

### 如何將圖表類型變更為除簇狀長條圖之外的其他類型？

您可以透過替換來更改圖表類型`ChartType.ClusteredColumn`具有所需的圖表類型枚舉，例如`ChartType.Line`或者`ChartType.Pie`.

### 我可以修改圖表的其他屬性嗎？

是的，您可以使用 Aspose.Slides for Java API 修改圖表的各種屬性，例如資料、標籤和格式。請參閱文件以了解更多詳細資訊。

### Aspose.Slides for Java 適合專業 PowerPoint 自動化嗎？

是的，Aspose.Slides for Java 是一個功能強大的函式庫，用於在 Java 應用程式中自動執行 PowerPoint 任務。它提供了用於處理簡報、幻燈片、形狀、圖表等的全面功能。

### 我如何了解有關 Aspose.Slides for Java 的更多資訊？

您可以在 Aspose.Slides for Java 文件頁面上找到大量文件和範例[這裡](https://reference.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
