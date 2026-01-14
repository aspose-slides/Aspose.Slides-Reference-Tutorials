---
date: '2026-01-14'
description: 學習如何在 Java 中使用 Aspose.Slides 建立群組柱狀圖。一步一步的指南，涵蓋空白簡報、將圖表加入簡報以及管理資料系列。
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握在 Java 中使用 Aspose.Slides 建立圖表

## 使用 Aspose.Slides for Java 建立與管理圖表的方式

### 介紹
建立動態簡報通常需要透過圖表來視覺化資料。使用 **Aspose.Slides for Java**，您可以輕鬆 **建立叢集柱狀圖** 並管理各種圖表類型，提升清晰度與衝擊力。本教學將指導您如何建立空白簡報、加入叢集柱狀圖、管理系列，以及自訂資料點的反轉——全部使用 Aspose.Slides for Java。

**您將學習：**
- 如何設定 Aspose.Slides for Java。
- 步驟說明 **建立空白簡報** 並將圖表加入簡報。
- 有效管理圖表系列與資料點的技巧。
- 依條件反轉負值資料點以提升視覺效果的方法。
- 如何安全地儲存簡報。

在開始之前，讓我們先了解前置條件。

## 快速解答
- **開始時的主要類別是什麼？** `Presentation` 來自 `com.aspose.slides`。
- **哪種圖表類型會建立叢集柱狀圖？** `ChartType.ClusteredColumn`。
- **如何將圖表加入投影片？** 在投影片的 shape 集合上使用 `addChart()`。
- **可以反轉負值嗎？** 可以，對資料點使用 `invertIfNegative(true)`。
- **需要哪個版本？** Aspose.Slides for Java 25.4 或更新版本。

## 什麼是叢集柱狀圖？
叢集柱狀圖會在每個類別中將多個資料系列並排顯示，非常適合比較各組之間的數值。Aspose.Slides 讓您能以程式方式產生此圖表，無需開啟 PowerPoint。

## 為何使用 Aspose.Slides for Java 在簡報中加入圖表？
- **完整控制** 圖表資料、外觀與版面配置。
- **不需安裝 Office** 即可在伺服器上使用。
- **支援所有主要圖表類型**，包含叢集柱狀圖。
- **輕鬆整合** Maven/Gradle 建置流程。

## 前置條件
在開始之前，請確保您具備以下條件：

1. **必要的函式庫：**
   - Aspose.Slides for Java（版本 25.4 或更新）。

2. **環境設定需求：**
   - 相容的 JDK 版本（例如 JDK 16）。
   - 若偏好套件管理，請安裝 Maven 或 Gradle。

3. **知識前提：**
   - 基本的 Java 程式設計概念。
   - 熟悉在開發環境中處理相依性。

## 設定 Aspose.Slides for Java
要開始使用 Aspose.Slides，請依照以下步驟：

**Maven 安裝：**  
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 安裝：**  
Add the following line to your `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載：**  
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### 取得授權
- **免費試用：** 您可以先使用免費試用版來探索功能。  
- **臨時授權：** 在評估期間取得臨時授權以獲得完整存取權。  
- **購買：** 若符合長期需求，請考慮購買授權。

### 基本初始化
以下為建立新簡報實例所需的最小程式碼：

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 實作指南
現在，讓我們將每個功能拆解成可管理的步驟。

### 建立含叢集柱狀圖的簡報
#### 概觀
本節說明如何 **建立空白簡報**、加入 **叢集柱狀圖**，並將其放置於第一張投影片上。

**步驟：**
1. **初始化 Presentation 物件** – 建立新的 `Presentation`。
2. **加入叢集柱狀圖** – 使用適當的類型與尺寸呼叫 `addChart()`。

**Code Example:**
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

### 管理圖表系列
#### 概觀
了解如何清除預設系列、加入新系列，並以正負值填入資料。

**步驟：**
1. **清除現有系列** – 移除任何預先填入的資料。
2. **加入新系列** – 使用工作簿儲存格作為系列名稱。
3. **插入資料點** – 加入值（含負值），以示範之後的反轉。

**Code Example:**
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

### 根據條件反轉系列資料點
#### 概觀
預設情況下，Aspose.Slides 可能會反轉負值。您可以全域或針對單一資料點控制此行為。

**步驟：**
1. **設定全域反轉** – 為整個系列停用自動反轉。
2. **套用條件反轉** – 僅對特定負值點啟用反轉。

**Code Example:**
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

### 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| 圖表顯示空白 | 確保投影片索引 (`0`) 存在，且圖表尺寸在投影片範圍內。 |
| 負值未被反轉 | 確認系列已設定 `invertIfNegative(false)`，且特定資料點設定 `invertIfNegative(true)`。 |
| 授權例外 | 在建立 `Presentation` 物件前套用有效的 Aspose 授權。 |

## 常見問答

**Q: 我可以加入除叢集柱狀圖之外的其他圖表類型嗎？**  
A: 可以，Aspose.Slides 支援折線圖、圓餅圖、長條圖、面積圖等多種圖表類型。

**Q: 開發時需要授權嗎？**  
A: 免費試用可用於評估，但正式上線需購買商業授權。

**Q: 如何將圖表匯出為影像？**  
A: 在渲染後使用 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`。

**Q: 可以自訂圖表樣式（顏色、字型）嗎？**  
A: 當然可以。每個 `IChartSeries` 與 `IChartDataPoint` 都提供樣式屬性。

**Q: 若要將圖表加入現有的 PPTX 檔案該怎麼做？**  
A: 使用 `new Presentation("existing.pptx")` 載入檔案，然後將圖表加入目標投影片。

## 結論
在本教學中，您學會了如何在 Java 中 **建立叢集柱狀圖**、管理系列，並使用 Aspose.Slides 依條件反轉負值資料點。掌握這些技巧後，您即可以程式方式建立引人入勝、以資料為驅動的簡報。

**下一步：**
- 嘗試 Aspose.Slides for Java 提供的其他圖表類型。  
- 深入探索進階樣式選項，如自訂顏色、資料標籤與座標軸格式。  
- 將圖表產生整合至您的報告或分析流程中。

---

**最後更新：** 2026-01-14  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}