---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 建立和管理圖表。本指南涵蓋簇狀長條圖、資料系列管理等內容。"
"title": "使用 Aspose.Slides 掌握 Java 中的圖表建立綜合指南"
"url": "/zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 掌握 Java 圖表創建

## 如何使用 Aspose.Slides for Java 建立和管理圖表

### 介紹
建立動態簡報通常涉及透過圖表視覺化資料。和 **Aspose.Slides for Java**，您可以輕鬆創建和管理各種圖表類型，增強清晰度和影響力。本教學將指導您建立空白簡報、新增聚集長條圖、管理系列和自訂資料點反轉 - 所有這些都使用 Aspose.Slides for Java。

**您將學到什麼：**
- 如何為 Java 設定 Aspose.Slides。
- 在簡報中建立聚集長條圖的步驟。
- 有效管理圖表系列和數據點的技術。
- 為了更好地進行視覺化，有條件地反轉負資料點的方法。
- 如何安全地保存簡報。

在開始之前，讓我們先深入了解先決條件。

## 先決條件
在開始之前，請確保您已具備以下條件：

1. **所需庫：**
   - Aspose.Slides for Java（版本 25.4 或更高版本）。

2. **環境設定要求：**
   - 相容的 JDK 版本（例如 JDK 16）。
   - 如果您喜歡依賴管理，請安裝 Maven 或 Gradle。

3. **知識前提：**
   - 對 Java 程式設計有基本的了解。
   - 熟悉處理開發環境中的依賴關係。

## 設定 Aspose.Slides for Java
若要開始使用 Aspose.Slides，請依照下列步驟操作：

**Maven安裝：**
將以下相依性新增至您的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 安裝：**
將以下行新增到您的 `build.gradle`：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載：**
或者，從下載最新版本 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 許可證獲取
- **免費試用：** 您可以先免費試用，探索其功能。
- **臨時執照：** 在評估期間取得臨時許可證以獲得完全存取權。
- **購買：** 如果您發現它適合您的長期需求，請考慮購買。

### 基本初始化
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// 您的程式碼在這裡...
pres.dispose(); // 完成後務必處置演示對象。
```

## 實施指南
現在，讓我們將每個功能分解為易於管理的步驟。

### 使用簇狀長條圖建立簡報
#### 概述
本節介紹如何建立空白簡報並在投影片上的特定座標處新增簇狀長條圖。

**步驟：**
1. **初始化演示物件：**
   - 建立新實例 `Presentation`。
2. **添加簇狀長條圖：**
   - 使用 `getSlides().get_Item(0).getShapes().addChart()` 新增圖表。
   - 指定位置、尺寸和類型。

**程式碼範例：**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // 在 (50, 50) 處加入一個簇狀長條圖，寬度為 600，高度為 400。
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### 管理圖表系列
#### 概述
了解如何清除現有系列並新增具有自訂資料點的新系列。

**步驟：**
1. **清除現有系列：**
   - 使用 `series.clear()` 刪除任何預先存在的資料。
2. **新增系列：**
   - 使用新增系列 `series。add()`.
3. **插入資料點：**
   - 利用 `getDataPoints().addDataPointForBarSeries()` 用於添加值，包括負值。

**程式碼範例：**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // 清除現有系列並新增系列。
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // 新增具有不同值（正值和負值）的資料點。
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

### 根據條件反轉序列資料點
#### 概述
透過有條件地反轉負數據點來自訂其視覺化。

**步驟：**
1. **設定預設反轉行為：**
   - 使用 `setInvertIfNegative(false)` 確定整體反轉行為。
2. **有條件地反轉特定資料點：**
   - 申請 `setInvertIfNegative(true)` 如果為負數，則在特定資料點上。

**程式碼範例：**
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
    
    // 新增具有不同值（正值和負值）的資料點。
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
    
    // 設定預設反轉行為
    series.get_Item(0).invertIfNegative(false);
    
    // 有條件地反轉特定資料點
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### 結論
在本教程中，您學習如何設定 Aspose.Slides for Java 並建立聚集長條圖。您還探索如何管理資料系列以及如何自訂負資料點的視覺化。有了這些技能，您現在可以自信地在 Java 應用程式中建立動態圖表。

**後續步驟：**
- 嘗試使用 Aspose.Slides for Java 中可用的不同圖表類型。
- 探索其他自訂選項以增強您的簡報。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}