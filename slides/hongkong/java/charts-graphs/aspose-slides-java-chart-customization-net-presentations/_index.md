---
date: '2026-01-17'
description: 學習如何在 .NET 簡報中使用 Aspose.Slides for Java 添加系列至圖表並自訂堆疊柱狀圖。
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: 在 .NET 中使用 Aspose.Slides for Java 為圖表添加系列
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通 .NET 簡報中的圖表自訂 – 使用 Aspose.Slides for Java

## 介紹
在以資料為驅動的簡報領域，圖表是將原始數字轉化為引人入勝視覺故事的不可或缺工具。當你需要以程式方式 **add series to chart**，尤其是在 .NET 簡報檔案內操作時，往往會感到挑戰重重。幸好 **Aspose.Slides for Java** 提供了功能強大、語言無關的 API，讓圖表的建立與自訂變得簡單，即使最終目標是 .NET PPTX。

在本教學中，你將學會如何 **add series to chart**、如何 **add chart**（堆疊柱狀圖類型），以及如何微調間距等視覺屬性。完成後，你就能產生動態、資料豐富且外觀精緻的投影片。

**學習目標**
- 使用 Aspose.Slides 建立空白簡報  
- **add stacked column chart** 至投影片  
- **add series to chart** 並定義類別  
- 填入資料點並調整視覺設定  

讓我們先準備開發環境。

## 快速答疑
- **建立簡報的主要類別是什麼？** `Presentation`  
- **哪個方法可將圖表加入投影片？** `slide.getShapes().addChart(...)`  
- **如何新增系列？** `chart.getChartData().getSeries().add(...)`  
- **可以調整柱狀之間的間距嗎？** 可以，使用系列群組的 `setGapWidth()` 方法  
- **正式環境需要授權嗎？** 需要，有效的 Aspose.Slides for Java 授權是必須的  

## 何謂 “add series to chart”？
將系列加入圖表即是插入一組新的資料集合，圖表會將其呈現為獨立的視覺元素（例如新的一根柱、線條或切片）。每個系列可擁有自己的數值、顏色與格式，讓你能夠在同一圖表中並排比較多筆資料集。

## 為什麼使用 Aspose.Slides for Java 來修改 .NET 簡報？
- **跨平台**：一次編寫 Java 程式碼，即可針對 .NET 應用使用的 PPTX 檔案。  
- **無需 COM 或 Office 依賴**：可在伺服器、CI/CD 流程與容器中執行。  
- **完整圖表 API**：支援超過 50 種圖表類型，包含堆疊柱狀圖。  

## 前置條件
1. **Aspose.Slides for Java** 套件（版本 25.4 以上）。  
2. Maven 或 Gradle 建置工具，或手動下載 JAR。  
3. 基本的 Java 知識與 PPTX 結構概念。  

## 設定 Aspose.Slides for Java
### Maven 安裝
在 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安裝
在 `build.gradle` 檔案中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
或是從官方發行頁面取得最新 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**取得授權**  
先下載臨時授權以試用，網址在 [here](https://purchase.aspose.com/temporary-license/)。正式環境請購買完整授權以解鎖全部功能。

## 步驟式實作指南
以下每一步皆附有簡潔程式碼片段（與原教學相同），並說明其功能。

### 步驟 1：建立空白簡報
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*我們從一個全新的 PPTX 檔案開始，提供加入圖表的畫布。*

### 步驟 2：在投影片上加入堆疊柱狀圖
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*`addChart` 方法會 **add stacked column chart**，並將其放置於投影片左上角。*

### 步驟 3：向圖表加入系列（主要目標）
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*此處 **add series to chart** – 每次呼叫都會建立一個新資料系列，呈現在圖表中為獨立的柱狀群組。*

### 步驟 4：為圖表加入類別
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*類別即 X 軸標籤，為每根柱子提供意義。*

### 步驟 5：填入系列資料
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
*資料點為每個系列提供數值，圖表會依此繪製柱高。*

### 步驟 6：設定圖表系列群組的間距寬度
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*調整間距寬度可提升可讀性，特別是在類別眾多時。*

## 常見使用情境
- **財務報表** – 比較各事業部的季營收。  
- **專案儀表板** – 顯示各團隊的任務完成百分比。  
- **行銷分析** – 以並排方式呈現不同活動的成效。  

## 效能小技巧
- **重複使用 `Presentation` 物件** 以產生多個圖表，降低記憶體開銷。  
- **僅保留必要的資料點**，避免過度繪製影響效能。  
- **完成後釋放資源**（`presentation.dispose()`）以釋放記憶體。  

## 常見問答
**Q: 除了堆疊柱狀圖，我可以加入其他圖表類型嗎？**  
A: 可以，Aspose.Slides 支援折線圖、圓餅圖、面積圖等多種圖表。

**Q: .NET 輸出需要額外授權嗎？**  
A: 不需要，同一份 Java 授權即可支援所有輸出格式，包括 .NET PPTX。

**Q: 如何變更圖表的配色方案？**  
A: 使用 `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)`，再設定想要的 `Color`。

**Q: 能否以程式方式加入資料標籤？**  
A: 完全可以。呼叫 `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` 即可顯示數值。

**Q: 若要更新既有簡報該怎麼做？**  
A: 使用 `new Presentation("existing.pptx")` 載入檔案，修改圖表後再存回去。

## 結語
現在你已掌握 **add series to chart**、建立 **stacked column chart**，以及在 .NET 簡報中使用 Aspose.Slides for Java 微調圖表外觀的完整流程。可自行嘗試不同圖表類型、配色與資料來源，打造令人印象深刻的視覺報告，贏得利害關係人的青睞。

---

**最後更新：** 2026-01-17  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
