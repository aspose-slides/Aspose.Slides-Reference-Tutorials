---
date: '2026-08-21'
description: 學習如何使用 Aspose.Slides 建立 box plot java、將圖表加入投影片，並在 PowerPoint 中產生 box‑and‑whisker
  chart。適合 Java 開發人員。
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: 學習如何使用 Aspose.Slides 建立 box plot java、將圖表加入投影片，並在 PowerPoint 中產生 box‑and‑whisker
  chart。完美適合 Java 開發人員。
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: 如何使用 Aspose.Slides for PowerPoint 建立 box plot java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: 如何使用 Aspose.Slides for PowerPoint 建立 box plot java
url: /zh-hant/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Slides for PowerPoint 建立箱形圖

在本指南中，您將使用 Aspose.Slides **在 Java 中建立箱形圖**，然後將圖表直接嵌入 PowerPoint 投影片。以程式方式產生箱形圖（box‑and‑whisker）可讓您在不離開 Java 程式碼的情況下，將原始統計資料轉換為清晰的視覺洞見。若需要自動化 PowerPoint 報告，Aspose.Slides for Java 提供可靠且高效能的 API。

## 您將學習

- 為 Aspose.Slides for Java 設定環境
- 使用 Java **將圖表新增至投影片** 並在 PowerPoint 中產生箱形圖的步驟
- 使用 Aspose.Slides 時最佳化效能的實務建議
- 箱形圖的實務應用案例

## 快速解答
- **什麼函式庫可以在 Java 中建立箱形圖？** Aspose.Slides for Java。  
- **使用哪種圖表類型？** `ChartType.BoxAndWhisker`。  
- **需要授權嗎？** 免費試用可用於評估；正式環境需購買商業授權。  
- **可以加入多個系列嗎？** 可以 – 為每個資料集重複系列建立區塊。  
- **最終檔案的格式為何？** PowerPoint PPTX (`SaveFormat.Pptx`)。  

## 什麼是箱形圖，為何在 Java 中使用？

箱形圖（亦稱 *box plot*）以緊湊的方式呈現資料分佈——中位數、四分位數與離群值。於 Java 中以程式方式產生此圖表，可直接將統計洞見嵌入 PowerPoint 簡報，免除手動製作圖表的步驟。它特別適合比較多個類別的分佈，例如各班級的測驗成績或各區域的銷售數字。透過在 Java 中產生圖表，您能將其整合至自動化報告流程，確保簡報始終反映最新資料。

## 為何使用 Aspose.Slides 在投影片中加入圖表？

Aspose.Slides 抽象化了低階的 OpenXML 細節，提供流暢的 API 來建立、樣式化與匯出圖表。這意味著您可以自動化報告產生、維持一致的品牌形象，並將圖表整合至更大的 Java 工作流程。此函式庫亦支援顏色、字型、標記等樣式選項，讓您符合企業品牌需求。此外，它能處理資料繫結與圖表重新整理等複雜工作，無需 Microsoft Office。

## 如何在 Java 中使用 Aspose.Slides 新增圖表投影片？

載入或建立 `Presentation`，插入類型為 `BoxAndWhisker` 的 `Chart`，填入資料，最後儲存檔案——全部只需幾行 Java 程式碼。API 會處理版面配置、縮放與渲染，您不必自行操作 XML。亦可程式化設定圖表標題與座標軸標籤，為觀眾提供說明。

## 前置條件

- **Java Development Kit (JDK)**：JDK 8 或以上。  
- **Aspose.Slides for Java Library**：用於 PowerPoint 操作的必要套件。  
- **IDE**：IntelliJ IDEA、Eclipse 或任何相容 Java 的編輯器。

## 設定 Aspose.Slides for Java

將此函式庫以 Maven、Gradle 或手動方式加入相依性。

### Maven

在 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

在 `build.gradle` 中加入：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載

或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

#### 取得授權

- **Free trial** – 免費試用，探索功能。  
- **Temporary license** – 用於短期評估。  
- **Purchase** – 購買授權以解鎖正式環境的完整功能。

要初始化 Aspose.Slides，請確保 JAR 已加入 classpath，並依文件說明設定授權檔案。

## 實作指南

以下為逐步說明。每個程式碼區塊皆在前面說明其功能，讓您清楚了解其作用。

### `Presentation` 類別是什麼？

`Presentation` 類別是 Aspose.Slides 中的核心物件，代表記憶體中的整個 PowerPoint 檔案。它提供存取投影片、圖表、圖形及其他投影片元素的功能，讓您能以程式方式建立、修改與儲存簡報。使用此類別，您可以新增投影片、插入圖片，並透過簡單的 API 呼叫調整投影片順序。

### 步驟 1：建立或開啟簡報

首先，開啟現有的 PPTX 檔或建立新檔：

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **小技巧：** 若檔案不存在，Aspose.Slides 會自動建立新的空白簡報。

### 步驟 2：在投影片中加入箱形圖

透過指定位置與大小（以點為單位）將圖表放置在所需位置：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### 步驟 3：清除現有資料

在填入新資料前，先清除任何佔位的類別或系列：

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### 步驟 4：設定類別

新增每個箱形下方的類別（X 軸標籤）：

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **備註：** 調整標籤文字以符合您的資料領域（例如 “Q1”、 “Product A”）。

### 步驟 5：建立並自訂系列

現在建立系列，設定視覺選項，並填入數值資料點：

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

將變更保存為新的 PPTX 檔案：

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### 步驟 7：清理資源

務必釋放 `Presentation` 物件以釋放原生資源：

```java
finally {
    if (pres != null) pres.dispose();
}
```

## 實務應用

箱形圖在統計分析與資料呈現上極為重要。以下是幾個典型應用情境：

1. **財務分析** – 可視化各區域的營收分佈。  
2. **品質管制** – 發現製造測量中的離群值。  
3. **學術研究** – 顯示實驗結果的變異性。  
4. **市場調查** – 比較不同人口統計下的產品表現。

將這些圖表直接嵌入 PowerPoint 簡報，可讓利害關係人一目了然地掌握複雜資料。

## 效能考量

Aspose.Slides 能處理包含 **500+ 投影片** 與 **100 000+ 資料點** 的圖表，同時在一般伺服器上將記憶體使用量控制在 200 MB 以下。為了維持在此範圍內：

- **記憶體管理** – 及時釋放 `Presentation` 物件。  
- **資料處理** – 僅載入必要的資料；避免將龐大資料集直接寫入圖表工作表。  
- **延遲載入** – 產生大量投影片時，僅為實際顯示的投影片建立圖表。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **圖表顯示空白** | 資料儲存格未正確填入 | 確認 `wb.getCell` 指向正確的列/欄，且值不為 `null`。 |
| **離群值未顯示** | `setShowOutlierPoints` 設為 `false` | 確保已呼叫 `series.setShowOutlierPoints(true)`。 |
| **記憶體洩漏** | 未釋放 Presentation | 始終在 `try/finally` 中使用，並呼叫 `dispose()`。 |
| **四分位數不正確** | 使用預設的 `Inclusive` 方法 | 改用 `Exclusive`，透過 `setQuartileMethod(QuartileMethodType.Exclusive)`。 |

## 常見問答

**Q1: 什麼是箱形圖？**  
箱形圖（亦稱 box plot）根據五項統計摘要（最小值、第一四分位數、中位數、第三四分位數、最大值）以及任何離群值，展示資料的分佈。

**Q2: 我可以自訂箱形圖的外觀嗎？**  
可以。Aspose.Slides 允許透過圖表格式化 API 變更顏色、線條樣式、標記形狀，並加入資料標籤。

**Q3: 能在同一圖表中處理多個系列嗎？**  
當然可以。為每個想要視覺化的資料集重複系列建立區塊。

**Q4: 如何解決資料未正確顯示的問題？**  
確保資料正確寫入工作表儲存格，且如 `setShowMeanLine` 等可見屬性已啟用。

**Q5: 若遇到問題，該向哪裡尋求支援？**  
可前往 [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) 取得社群協助，或參考官方文件。

**Q6: Aspose.Slides 支援其他圖表類型嗎？**  
是的，支援超過 50 種圖表類型，包括折線圖、長條圖、圓餅圖、散點圖、雷達圖與漏斗圖等，讓您可選擇最適合的視覺呈現。

**Q7: 能在無頭（headless）伺服器環境產生圖表嗎？**  
此函式庫完全支援伺服器端使用，無需 UI 或 Microsoft Office 安裝。

## 資源

- **Documentation**：於 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) 探索詳細的 API 參考。  
- **Download**：前往 Aspose.Slides 下載頁面 [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)。  
- **Purchase**：購買授權以解鎖完整功能 [Aspose Purchase](https://purchase.aspose.com/buy)。  
- **Free trial & temporary license**：以免費試用開始或申請臨時授權 [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)。

遵循本指南後，您即可在 Java 應用程式中以程式方式產生具洞見的箱形圖，並直接嵌入 PowerPoint 簡報。祝開發順利！

---

**最後更新：** 2026-08-21  
**測試環境：** Aspose.Slides 25.4 (JDK 16 classifier)  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Slides for Java 在 PowerPoint 中新增圖表：一步步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [使用 Aspose.Slides 在 Java 中建立 PowerPoint 圖表](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表加入動畫 – 步驟指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}