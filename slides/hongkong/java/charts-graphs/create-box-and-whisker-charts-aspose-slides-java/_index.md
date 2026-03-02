---
date: '2026-03-02'
description: 學習如何使用 Aspose.Slides for Java 在 PowerPoint 中建立箱形圖、將圖表加入投影片，以及產生箱鬚圖。
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: 使用 Aspose.Slides for PowerPoint 在 Java 中建立箱形圖
url: /zh-hant/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 在 PowerPoint 中建立箱形圖（Box‑and‑Whisker）圖表

在本指南中，您將使用 Aspose.Slides **建立 box plot java**，然後將圖表直接嵌入 PowerPoint 投影片。製作視覺吸引力的資料簡報在當今資料驅動的世界中至關重要，而圖表是實現此目的的關鍵工具。如果您希望在 PowerPoint 中使用 Java 產生箱形圖（box‑and‑whisker）圖表，Aspose.Slides 函式庫提供了強大的解決方案。本教學將一步步帶您使用 Aspose.Slides for Java 建立與設定這些圖表。

## 您將學習到

- 設定 Aspose.Slides for Java 的開發環境
- 使用 **add chart to slide** 步驟，於 PowerPoint 中以 Java 產生箱形圖（box‑whisker）圖表
- 使用 Aspose.Slides 時最佳化效能的實務建議
- 箱形圖（box‑and‑whisker）的實務應用案例

## 快速解答
- **什麼函式庫可以在 Java 中建立 box plot？** Aspose.Slides for Java.  
- **使用哪種圖表類型？** `ChartType.BoxAndWhisker`.  
- **需要授權嗎？** 免費試用可用於評估；正式環境需購買商業授權。  
- **可以加入多個系列嗎？** 可以 – 為每個資料集重複系列建立區塊。  
- **最終檔案的格式為何？** PowerPoint PPTX (`SaveFormat.Pptx`).  

## 前置條件

要跟隨本教學，請確保您已具備：

- **Java Development Kit (JDK)**：應安裝 JDK 8 或更高版本。  
- **Aspose.Slides for Java Library**：在 Java 中處理 PowerPoint 簡報的必要函式庫。  
- **IDE**：如 IntelliJ IDEA 或 Eclipse 等整合開發環境，用於編寫與執行程式碼。  

## 設定 Aspose.Slides for Java

若要使用 Aspose.Slides，需將其加入為相依性。您可以透過 Maven、Gradle 或直接下載的方式管理。

### Maven

在您的 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

在您的 `build.gradle` 中加入以下內容：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載

或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

#### 取得授權

- **Free Trial**：使用免費試用版探索功能。  
- **Temporary License**：取得臨時授權以供評估。  
- **Purchase**：若需完整功能，建議購買授權。  

在初始化 Aspose.Slides 前，請確保已將函式庫加入 classpath，並依需求設定授權。

## 實作指南

現在讓我們深入逐步程式碼說明。每個程式區塊在程式碼片段前都有說明，讓您清楚了解其功能。

### 什麼是箱形圖（box plot），以及為何在 Java 中使用？

箱形圖（Box‑and‑Whisker chart，亦稱 *box plot*）以緊湊的方式呈現資料分佈——中位數、四分位數與離群值。於 Java 中以程式產生此圖表，可直接將統計洞見嵌入 PowerPoint 投影片，省去手動製作圖表的步驟。

### 為何使用 Aspose.Slides 在投影片中加入圖表？

Aspose.Slides 抽象化了底層 OpenXML 細節，提供流暢的 API 讓您建立、樣式化與匯出圖表。這意味著您可以自動化報告產出、保持品牌一致性，並將圖表整合至更大的 Java 工作流程中。

### 步驟 1：建立或開啟簡報

首先，開啟既有的 PPTX 或建立新的簡報：

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **小技巧：** 若檔案不存在，Aspose.Slides 會為您建立新的空白簡報。

### 步驟 2：在投影片中加入箱形圖（Box‑and‑Whisker）

將圖表放置於所需位置，並以點數指定位置與大小：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### 步驟 3：清除現有資料

在寫入新資料前，先清除任何佔位的類別或系列：

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### 步驟 4：設定類別

加入將顯示於每個箱形下方的類別（X 軸標籤）：

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **注意：** 請調整標籤文字以符合您的資料領域（例如「Q1」、「Product A」）。

### 步驟 5：建立與自訂系列

現在建立系列、設定視覺選項，並寫入數值資料點：

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

您可以將 `int[] data` 陣列替換為從資料庫、CSV 檔或其他來源讀取的值。

### 步驟 6：儲存簡報

將變更寫入新的 PPTX 檔案：

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### 步驟 7：清理資源

請務必釋放 `Presentation` 物件以釋放原生資源：

```java
finally {
    if (pres != null) pres.dispose();
}
```

## 實務應用

箱形圖（Box‑and‑Whisker）在統計分析與資料簡報中極為重要。以下列出幾個典型應用情境：

1. **Financial Analysis** – 以視覺方式呈現各區域的營收分佈。  
2. **Quality Control** – 偵測製造測量中的離群值。  
3. **Academic Research** – 展示實驗結果的變異性。  
4. **Market Research** – 比較不同人口統計下的產品表現。  

將這些圖表整合至 PowerPoint 簡報，可讓利害關係人一眼掌握複雜資料。

## 效能考量

在 Java 中使用 Aspose.Slides 時，請留意以下建議：

- **Memory Management** – 盡快釋放 `Presentation` 物件。  
- **Data Handling** – 僅載入必要資料；避免將龐大資料集直接寫入圖表工作簿。  
- **Lazy Loading** – 若產生大量投影片，建議僅為實際顯示的投影片建立圖表。  

## 常見問題與解決方案

| Issue | Cause | Solution |
|-------|-------|----------|
| **圖表顯示空白** | 資料儲存格未正確填入 | 確認 `wb.getCell` 指向正確的列/欄，且值不為 `null`。 |
| **離群點未顯示** | `setShowOutlierPoints` 設為 `false` | 確保呼叫 `series.setShowOutlierPoints(true)`。 |
| **記憶體泄漏** | 未釋放 Presentation | 始終在 try/finally 中使用，並呼叫 `dispose()`。 |
| **四分位數不正確** | 使用預設的 `Inclusive` 方法 | 改用 `Exclusive`，透過 `setQuartileMethod(QuartileMethodType.Exclusive)`。 |

## 常見問答

**Q1: 什麼是箱形圖（box‑and‑whisker）？**  
箱形圖（亦稱 box plot）根據五個統計摘要（最小值、第一四分位數、中位數、第三四分位數、最大值）以及任何離群值，展示資料的分佈情形。

**Q2: 我可以自訂箱形圖的外觀嗎？**  
可以。Aspose.Slides 允許透過圖表格式化 API 變更顏色、線條樣式、標記形狀，甚至加入資料標籤。

**Q3: 能在同一張圖表中處理多個系列嗎？**  
當然可以。為每個想要視覺化的資料集重複系列建立區塊。

**Q4: 若資料未正確顯示，該如何處理？**  
請確保資料正確寫入工作簿儲存格，且如 `setShowMeanLine` 等可見屬性已啟用。

**Q5: 若遇到問題，該向何處尋求支援？**  
可前往 [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) 取得社群協助，或參考官方文件。

**Q6: Aspose.Slides 支援其他圖表類型嗎？**  
支援，包括折線圖、長條圖、圓餅圖、散點圖、雷達圖等多種圖表類型。

**Q7: 能在無頭（headless）伺服器環境產生圖表嗎？**  
此函式庫可完整於伺服器端執行，無需 UI。

## 資源

- **Documentation**：於 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) 探索詳細 API 參考。  
- **Download**：從 [here](https://releases.aspose.com/slides/java/) 取得 Aspose.Slides 版本。  
- **Purchase**：於 [Aspose Purchase](https://purchase.aspose.com/buy) 購買授權以解鎖全部功能。  
- **Free Trial & Temporary License**：可先使用免費試用或申請臨時授權，請至 [here](https://releases.aspose.com/slides/java/)。

透過本指南，您已具備在 Java 應用程式中程式化產生洞見豐富的箱形圖（box‑and‑whisker）並直接嵌入 PowerPoint 簡報的能力。祝開發順利！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-02  
**測試環境：** Aspose.Slides 25.4 (JDK 16 classifier)  
**作者：** Aspose