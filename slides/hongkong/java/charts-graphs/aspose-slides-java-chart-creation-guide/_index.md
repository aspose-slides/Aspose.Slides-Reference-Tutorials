---
date: '2026-02-12'
description: 學習如何使用 Aspose.Slides for Java 建立圖表及管理圖表。本教學示範如何建立叢集柱狀圖、處理資料系列，並自訂視覺化效果。
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 如何使用 Aspose.Slides 在 Java 中建立圖表：完整指南
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose.Slides 建立圖表

## 在 Java 中建立圖表：簡介
建立動態簡報通常需要透過圖表來視覺化資料。使用 **Aspose.Slides for Java**，您可以輕鬆 **how to create chart** 物件，提升清晰度，並對觀眾產生更強的衝擊。本教學將帶您設定函式庫、加入 **create clustered column chart**、管理系列，並條件性地反轉負值資料點。

**您將學習到**
- 如何設定 Aspose.Slides for Java。
- 在簡報中加入 **create clustered column chart** 的步驟。
- 管理圖表系列與資料點的技巧。
- 為了更佳視覺效果，條件性反轉負值資料點的方法。
- 如何安全地儲存簡報。

### 快速答覆
- **使用的函式庫是什麼？** Aspose.Slides for Java。
- **示範的圖表類型為何？** Clustered column chart。
- **我可以反轉負值嗎？** 可以，使用 `invertIfNegative`。
- **需要哪個版本的 Java？** JDK 16 或更新版本。
- **正式環境需要授權嗎？** 需要，有效的 Aspose 授權。

## 什麼是 Clustered Column Chart？
Clustered column chart 會在每個類別中並排顯示多個資料系列，讓您輕鬆比較各群組的數值。它非常適合財務報表、銷售儀表板，以及任何需要對比多項指標的情境。

## 為何使用 Aspose.Slides 來建立圖表？
- **Full control**：在不依賴 PowerPoint UI 的情況下，完整掌控圖表外觀。
- **Programmatic generation**：支援自動化報表流程的程式化產生。
- **Cross‑platform**：確保程式碼可在任何相容 Java 的系統上執行。
- **Rich API**：提供細緻的客製化功能（顏色、資料標籤、反轉等）。

## 先備條件
1. **必要函式庫**
   - Aspose.Slides for Java（版本 25.4 或更新）。

2. **環境**
   - JDK 16 或更新版本。
   - Maven 或 Gradle 用於相依管理。

3. **知識**
   - 基本的 Java 程式設計。
   - 熟悉建置工具（Maven/Gradle）。

## 設定 Aspose.Slides for Java
### Maven 安裝
在您的 `pom.xml` 檔案中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安裝
在您的 `build.gradle` 檔案中加入以下行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權
- **免費試用：** 無需授權即可體驗功能。
- **暫時授權：** 評估期間使用。
- **完整授權：** 用於正式部署的購買授權。

### 基本初始化
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 逐步指南

### 步驟 1：建立簡報並加入 Clustered Column Chart
在此步驟中，我們 **how to create chart** 物件，並在第一張投影片上放置 **create clustered column chart**。

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
接下來，我們會清除預設系列，新增一個系列，並填入正負值。

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
預設情況下，Aspose.Slides 不會反轉負值。我們將僅對需要的資料點啟用反轉。

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

### 常見問題與技巧
- **忘記釋放 `Presentation` 物件？** 必須在 `finally` 區塊中呼叫 `dispose()`，以釋放原生資源。
- **負值未顯示為反轉？** 確認在加入資料點之後呼叫 `invertIfNegative(true)` **之後**。
- **圖表尺寸問題：** 座標 (X, Y) 與尺寸 (width, height) 以點為單位，請依投影片版面調整。

## 常見問答

**Q: 我可以用相同方式建立其他圖表類型嗎？**  
A: 可以，只要將 `ChartType.ClusteredColumn` 替換為其他 `ChartType` 列舉值（例如 `Line`、`Pie`）。

**Q: 開發版需要授權嗎？**  
A: 需要暫時或評估授權才能使用全部功能；否則函式庫會以試用模式運作，並有浮水印限制。

**Q: 加入圖表後，如何將簡報匯出為 PDF？**  
A: 在完成圖表操作後，使用 `pres.save("output.pdf", SaveFormat.Pdf);`。

**Q: 能否為個別柱狀設定樣式（顏色、邊框）？**  
A: 可以，每個 `IChartDataPoint` 都提供格式設定選項，例如 `getFillFormat().setFillType(FillType.Solid)` 與 `getLineFormat()`。

**Q: 若簡報已儲存，仍需更新圖表資料該怎麼做？**  
A: 使用 `new Presentation("file.pptx")` 重新載入簡報，修改圖表資料後再重新儲存。

---  
**最後更新：** 2026-02-12  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}