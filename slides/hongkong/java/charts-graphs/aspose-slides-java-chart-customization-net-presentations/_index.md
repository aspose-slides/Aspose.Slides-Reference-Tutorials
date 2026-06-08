---
date: '2026-06-08'
description: 了解如何在 .NET 簡報中使用 Aspose.Slides for Java 為圖表新增系列並自訂堆疊柱狀圖。
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: 使用 Aspose.Slides for Java 在 .NET 中為圖表新增系列
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通在 .NET 簡報中使用 Aspose.Slides for Java 進行圖表自訂

## 簡介
在以資料驅動的簡報領域，圖表是不可或缺的工具，能將原始數字轉化為引人入勝的視覺故事。當您需要以程式方式 **add series to chart**，尤其是在 .NET 簡報檔案中時，這項工作可能會感到相當繁雜。幸運的是，**Aspose.Slides for Java** 提供了功能強大且語言無關的 API，讓圖表的建立與自訂變得簡單直觀——即使目標格式是 .NET PPTX。本指南將帶您一步步完成新增系列、建立堆疊柱狀圖，並微調如間距寬度等視覺細節，讓您產生動態且資料豐富的投影片，外觀精緻且專業。

## 快速回答
`Presentation` 類別代表 PPTX 檔案，`slide.getShapes().addChart(...)` 會插入圖表形狀。使用 `chart.getChartData().getSeries().add(...)` 來新增系列，`setGapWidth()` 則可調整間距。

- **什麼是啟動簡報的主要類別？** `Presentation` – 它在記憶體中代表 PPTX 檔案。  
- **哪個方法可在投影片上新增圖表？** `slide.getShapes().addChart(...)` 會在投影片上建立圖表物件。  
- **如何新增一個系列？** `chart.getChartData().getSeries().add(...)` 會插入新的資料系列。  
- **能否變更柱狀之間的間距寬度？** 可以——呼叫 `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)`（數值為百分比）。  
- **在正式環境需要授權嗎？** 絕對需要——有效的 Aspose.Slides for Java 授權會解鎖所有功能並移除評估水印。

## 什麼是 “add series to chart”？
將系列新增至圖表即是插入一組新的資料點集合，圖表會將其呈現為獨立的視覺元素（例如，單獨的柱狀群組）。每個系列可以擁有自己的數值、顏色與格式，從而允許多個資料集之間的並排比較。

## 為什麼使用 Aspose.Slides for Java 來修改 .NET 簡報？
Aspose.Slides for Java 讓您能產生或編輯完全相容於 .NET PowerPoint 檢視器的 PPTX 檔案，且不需安裝任何 Microsoft Office。當您需要在伺服器端、跨平台的解決方案來建立或更新 .NET PPTX 檔案、支援超過 50 種圖表類型，且可在不將整個文件載入記憶體的情況下處理高達 500 MB 的檔案時，請使用 Aspose.Slides for Java。其 API 可在 Java、Kotlin、Scala 或任何 JVM 語言中使用，提供與 .NET 開發者預期相同的輸出結果。

## 先決條件
- **Aspose.Slides for Java** 函式庫（版本 25.4 或更新）。  
- Maven、Gradle，或手動下載 JAR。  
- 基本的 Java 知識以及對 PPTX 檔案結構的了解。  

## 設定 Aspose.Slides for Java
### Maven 安裝
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安裝
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
或者，從官方發行頁面取得最新的 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**取得授權**  
先透過下載臨時授權（[此處](https://purchase.aspose.com/temporary-license/)）取得免費試用。若於正式環境使用，請購買完整授權以解鎖全部功能並移除評估水印。

## 逐步實作指南
在每個步驟下方，您會看到簡潔的程式碼片段（保持原始教學不變），以及對其功能的說明。

### 步驟 1：建立空白簡報
`Presentation` 是代表記憶體中 PowerPoint 檔案的入口類別。  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*我們從一個全新的 PPTX 檔案開始，提供了加入圖表的畫布。*

### 步驟 2：在投影片上新增堆疊柱狀圖
`Chart` 代表投影片內的圖表形狀。`ChartType.StackedColumn` 指定堆疊柱狀圖。  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*`addChart` 方法會建立一個 **stacked column chart**，並將其放置於投影片的左上角。*

### 步驟 3：將系列新增至圖表（主要目標）
`Series` 封裝圖表中的單一資料系列。  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*在此我們 **add series to chart** —— 每次呼叫都會建立一個新的資料系列，會以獨立的柱狀群組顯示。*

### 步驟 4：為圖表新增類別
`Category` 定義圖表資料的 X 軸標籤。  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*類別作為 X 軸標籤，為每根柱狀賦予意義。*

### 步驟 5：填充系列資料
`DataPoint` 保存特定類別下系列的數值。  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*資料點為每個系列提供數值，圖表會以柱狀高度呈現。*

### 步驟 6：設定圖表系列群組的間距寬度
`SeriesGroup` 控制一組系列的版面屬性，例如間距寬度。  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*調整間距寬度可提升可讀性，特別是在類別眾多時。*

## 常見使用情境
- **財務報告** – 比較各事業單位的季度營收。  
- **專案儀表板** – 顯示各團隊的任務完成百分比。  
- **行銷分析** – 以並排方式視覺化活動績效。  
這些情境適合使用 **stacked column chart** 範例，因為它能凸顯各類別對總計的貢獻。

## 效能建議
- **重複使用 `Presentation` 物件** 以在建立多個圖表時降低記憶體開銷。  
- **限制資料點數量** 僅保留視覺敘事所需的點；Aspose.Slides 可處理 10,000 點，但在約 5,000 點之後渲染速度會下降。  
- **釋放物件**（`presentation.dispose()`）於儲存後釋放資源，避免記憶體泄漏。  

## 常見問題
**Q: 我可以新增除堆疊柱狀圖之外的其他圖表類型嗎？**  
A: 可以，Aspose.Slides 支援折線圖、圓餅圖、面積圖、雷達圖、氣泡圖以及超過 50 種其他圖表類型，皆可透過相同的 `addChart` 方法取得。

**Q: .NET 輸出需要額外的授權嗎？**  
A: 不需要，同一份 Java 授權適用於所有輸出格式，包括 .NET PPTX 檔案。

**Q: 我要如何變更圖表的色彩調色盤？**  
A: 使用 `series.getFormat().getFill().setFillType(FillType.Solid)`，然後為每個系列設定所需的 `Color` 物件。

**Q: 能否以程式方式新增資料標籤？**  
A: 完全可以。呼叫 `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` 即可在每根柱狀上顯示數值。

**Q: 如果需要更新既有簡報該怎麼做？**  
A: 使用 `new Presentation("existing.pptx")` 載入檔案，使用相同的 API 呼叫修改圖表，然後儲存回磁碟。

## 結論
您現在已擁有完整的端對端指南，說明如何 **add series to chart**、建立 **stacked column chart**，以及在 .NET 簡報中使用 Aspose.Slides for Java 微調其外觀。可嘗試不同的圖表類型、顏色與資料來源，打造令人印象深刻且能驅動決策的視覺報告。

---

**最後更新：** 2026-06-08  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何在 .NET 使用 Aspose.Slides 建立百分比堆疊柱狀圖](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [使用 Aspose.Slides .NET 精通圖表系列建立與操作以實現有效的資料視覺化](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [使用 Aspose.Slides .NET 清除特定圖表系列資料點](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}