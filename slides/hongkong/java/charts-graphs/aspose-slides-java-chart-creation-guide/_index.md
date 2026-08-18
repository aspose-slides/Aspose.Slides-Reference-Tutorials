---
date: '2026-06-03'
description: 了解如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖。本指南涵蓋 Maven 相依性、圖表建立步驟以及資料處理。
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: 使用 Aspose.Slides 在 Java 中建立叢集柱狀圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 Java 中使用 Aspose.Slides 建立叢集柱狀圖

## 如何在 Java 中建立圖表：簡介

建立動態簡報通常需要透過圖表來視覺化資料。使用 **Aspose.Slides for Java**，您可以輕鬆 **create clustered column chart** 物件，提升清晰度，並對觀眾產生更強的衝擊。本教學將引導您完成設定函式庫、加入叢集柱狀圖、管理系列，以及條件性反轉負值資料點的步驟。

**您將學習**
- 如何設定 Aspose.Slides for Java。
- 在簡報中 **create clustered column chart** 的步驟。
- 管理圖表系列與資料點的技巧。
- 條件性反轉負值資料點以提升可視化的方法。
- 如何安全地儲存簡報。

## 快速問答
- **使用的函式庫是什麼？** Aspose.Slides for Java.  
- **示範的圖表類型是？** Clustered column chart.  
- **我可以反轉負值嗎？** Yes, using `invertIfNegative`.  
- **需要哪個 Java 版本？** JDK 16 or later.  
- **生產環境需要授權嗎？** Yes, a valid Aspose license.

## 什麼是叢集柱狀圖？
叢集柱狀圖是一種視覺化表示方式，將每個類別的多個資料系列並排放置，以便快速比較各群組。它非常適合財務報告、銷售儀表板，以及任何需要一次對比多項指標的情境。

## 為什麼使用 Aspose.Slides 來建立圖表？
Aspose.Slides 讓您能以程式方式產生並完整自訂圖表，省去手動編輯 PowerPoint 的需求。它支援 **70+ 輸入與輸出格式**，且可在不將整個檔案載入記憶體的情況下處理 **最多 10,000 張投影片** 的簡報，確保大型報告的高效能。

## 先決條件
1. **必需的函式庫**  
   - Aspose.Slides for Java (version 25.4 or later).  

2. **環境**  
   - JDK 16 或更新版本。  
   - 用於相依管理的 Maven 或 Gradle。  

3. **知識**  
   - 基本的 Java 程式設計。  
   - 熟悉建置工具 (Maven/Gradle)。  

## 設定 Aspose.Slides for Java
### Maven 安裝
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安裝
Add the following line to your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權
- **免費試用：** 在未取得授權的情況下探索功能。  
- **暫時授權：** 評估期間使用。  
- **完整授權：** 用於正式上線的購買授權。

### 基本初始化
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 如何在投影片中加入叢集柱狀圖？
`Presentation` 是代表 PowerPoint 檔案的核心類別。載入新的 `Presentation`，加入投影片，並呼叫 `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`。此單一呼叫即可在指定座標建立完整功能的叢集柱狀圖。之後您可以存取圖表物件，以修改系列、資料點與視覺樣式。

## 步驟指南
### 步驟 1：建立簡報並加入叢集柱狀圖
`Presentation` 類別代表 PowerPoint 文件，並允許建立投影片。  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### 步驟 2：管理圖表系列
現在我們將清除任何預設系列，新增一個系列，並以正負值填入。  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### 步驟 3：條件性反轉負值資料點
`invertIfNegative` 方法可在圖表系列中啟用負值的反轉。  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## 常見陷阱與技巧
- **忘記釋放 `Presentation` 物件？** 必須在 `finally` 區塊中呼叫 `dispose()` 以釋放原生資源。  
- **負值未顯示為反轉？** 確認在加入資料點之 **後** 呼叫 `invertIfNegative(true)`。  
- **圖表尺寸問題：** 座標 (X, Y) 與尺寸 (width, height) 以點為單位，請調整以符合投影片版面配置。  

## 常見問答
**Q:** 我可以使用相同方法建立其他圖表類型嗎？  
A: 可以，只需將 `ChartType.ClusteredColumn` 替換為任何其他 `ChartType` 列舉值（例如 `Line`、`Pie`）。

**Q:** 開發版需要授權嗎？  
A: 需要暫時或評估授權才能完整使用功能；否則，函式庫會以試用模式運作，並有浮水印限制。

**Q:** 加入圖表後，如何將簡報匯出為 PDF？  
`SaveFormat.Pdf` 指定 PDF 為簡報的輸出格式。完成圖表操作後，使用 `pres.save("output.pdf", SaveFormat.Pdf);`。

**Q:** 能否為單獨的柱狀設定樣式（顏色、邊框）？  
`IChartDataPoint` 代表圖表中的單一資料點，並允許格式設定。每個 `IChartDataPoint` 提供如 `getFillFormat().setFillType(FillType.Solid)` 與 `getLineFormat()` 等選項。

**Q:** 若在簡報儲存後需要更新圖表資料該怎麼辦？  
A: 使用 `new Presentation("file.pptx")` 重新載入簡報，修改圖表資料後再重新儲存。

---

**最後更新：** 2026-06-03  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose

## 相關教學
- [如何在 Java 中使用 Aspose.Slides 建立堆疊柱狀圖 – 完整指南](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [如何在 Java 中使用 Aspose.Slides 建立圖表 – 精通圖表建立與驗證](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [使用 Aspose.Slides 在 Java 中建立與格式化圖表：完整指南](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}