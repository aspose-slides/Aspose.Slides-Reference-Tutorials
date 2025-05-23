---
"description": "了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中設定圖表資料單元格公式。使用公式建立動態圖表。"
"linktitle": "Java 投影片中的圖表資料儲存格公式"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的圖表資料儲存格公式"
"url": "/zh-hant/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的圖表資料儲存格公式


## Aspose.Slides for Java 中的圖表資料單元格公式簡介

在本教學中，我們將探討如何使用 Aspose.Slides for Java 處理圖表資料單元格公式。使用 Aspose.Slides，您可以在 PowerPoint 簡報中建立和操作圖表，包括設定資料儲存格的公式。

## 先決條件

在開始之前，請確保您已安裝 Aspose.Slides for Java 程式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).

## 步驟 1：建立 PowerPoint 簡報

首先，讓我們建立一個新的 PowerPoint 簡報並在其中新增圖表。

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // 在第一張投影片中新增圖表
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // 取得圖表資料的工作簿
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // 繼續資料單元操作
    // …
    
    // 儲存簡報
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## 步驟 2：設定資料單元格的公式

現在，讓我們為圖表中的特定資料單元設定公式。在此範例中，我們將為兩個不同的儲存格設定公式。

### 單元格 1：使用 A1 符號

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

在上面的程式碼中，我們使用 A1 符號為儲存格 B2 設定了一個公式。此公式計算儲存格 F2 至 H5 的總和，並將結果加 1。

### 單元格 2：使用 R1C1 符號

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

在這裡，我們使用 R1C1 符號為儲存格 C2 設定公式。此公式計算 R2C6 至 R5C8 範圍內的最大值，然後將其除以 3。

## 步驟3：計算公式

設定公式後，必須使用以下程式碼進行計算：

```java
workbook.calculateFormulas();
```

此步驟確保圖表反映基於公式的更新值。

## 步驟 4：儲存簡報

最後，將修改後的簡報儲存到文件中。

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Java 投影片中圖表資料儲存格公式的完整原始碼

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教程中，我們探討如何在 Aspose.Slides for Java 中使用圖表資料單元格公式。我們介紹如何建立 PowerPoint 簡報、新增圖表、設定資料單元格公式、計算公式以及儲存簡報。現在您可以利用這些功能在簡報中建立動態和資料驅動的圖表。

## 常見問題解答

### 如何將圖表新增到特定投影片？

若要將圖表新增至特定投影片，您可以使用 `getSlides().get_Item(slideIndex)` 方法存取所需的幻燈片，然後使用 `addChart` 方法添加圖表。

### 我可以在資料單元格中使用不同類型的公式嗎？

是的，您可以在資料儲存格公式中使用各種類型的公式，包括數學運算、函數和對其他儲存格的參考。

### 如何更改圖表類型？

您可以使用 `setChartType` 方法 `IChart` 對象並指定所需的 `ChartType`。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}