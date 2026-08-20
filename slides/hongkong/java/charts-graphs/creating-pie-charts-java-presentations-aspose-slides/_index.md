---
date: '2026-08-01'
description: 了解如何使用 Aspose Slides 授權在 Java 簡報中建立與自訂圓餅圖。依循逐步說明，配置圓餅圖資料並有效新增圖表投影片。
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: 了解如何使用 Aspose Slides 授權在 Java 簡報中建立與自訂圓餅圖。依循逐步說明，配置圓餅圖資料並有效新增圖表投影片。
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: 使用 Aspose Slides 授權在 Java 中建立圓餅圖
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: 使用 Aspose Slides 授權在 Java 中建立圓餅圖
url: /zh-hant/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 簡報中使用 Aspose.Slides 建立圓形圖表

## 簡介

如果您需要製作專業外觀的簡報，**Aspose Slides 授權** 可讓您以程式方式產生與樣式化圖表。  
本指南將教您如何建立圓形圖表、設定其資料，並將其嵌入 Java 簡報中——完全不依賴 Microsoft PowerPoint。我們會逐步說明設定、程式流程與最佳實踐技巧，讓您在數分鐘內交付精緻的視覺報告。

**您將學習：**
- 設定 Aspose.Slides for Java 並使用有效授權
- 建立與自訂圓形圖表的步驟
- 設定圓形圖表資料並新增圖表投影片
- 常見陷阱與效能技巧

讓我們先確認您的環境已就緒。

## 快速解答
- **What does the Aspose Slides license enable?** 完整功能的圖表建立、匯出為 PDF/HTML，並移除浮水印。  
- **Which Java version is required?** 需要哪個 Java 版本？ JDK 16 或更新版本。  
- **Do I need Maven or Gradle?** 需要 Maven 或 Gradle 嗎？ 兩者皆可；此函式庫同時支援兩者。  
- **How many data points can a pie chart hold?** 圓形圖表最多能容納多少資料點？ 最高可容納 10 000 個點，且不會產生記憶體問題。  
- **Can I export the slide as an image?** 我可以將投影片匯出為影像嗎？ 可以——支援 PNG、JPEG、SVG 等多種格式。

## 先決條件

- **Required Libraries:** Aspose.Slides for Java（版本 25.4 或更新）— 此版本支援最新檔案格式與效能最佳化。  
- **Environment Setup:** 已在 IDE 或建置系統中安裝並設定 JDK 16 以上。  
- **Basic Knowledge:** 熟悉 Java、Maven 或 Gradle，以及物件導向程式設計概念。

## 設定 Aspose.Slides for Java

要在 Java 中使用 Aspose.Slides，必須將其加入專案。以下示範最常見的建置工具如何加入相依性：

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Direct Download:** 您也可以從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新 JAR。

### 授權取得

Aspose 提供免費試用版，可解鎖所有功能，但**有效的 Aspose Slides 授權**是正式環境的必要條件，以移除評估浮水印並獲得效能提升。購買選項請參考 [purchase page](https://purchase.aspose.com/buy)。取得授權檔後，於應用程式啟動時載入一次：

`License` 載入並套用您的 Aspose.Slides 授權。  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## 實作指南

### 建立並新增圓形圖表至簡報

#### 概觀
本節說明如何建立圓形圖表、設定資料系列，並將圖表嵌入投影片。您將看到從初始化簡報物件到儲存最終檔案的完整流程。

#### 步驟 1：初始化 Presentation  
`Presentation` 是 Aspose.Slides 的頂層物件，代表記憶體中的 PowerPoint 檔案。建立實例即得到一個可供修改的空白投影片集。

```java
demo.Presentation pres = new demo.Presentation();
```  
此行會建立一個新簡報，之後的所有變更都會套用於此簡報。

#### 步驟 2：將圓形圖表新增至投影片  
`Chart` 類別封裝圖表物件，包括圓形圖表。將圖表加入投影片只需一次方法呼叫，即可指定位置與大小。

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` 與 `yPosition` 設定圖表左上角位置。  
- `width` 與 `height` 定義圖表在投影片上的顯示範圍。

#### 步驟 3：設定圓形圖表資料  
`ChartData` 保存圖表的資料系列。  
**How do I configure pie chart data?**  
使用 `ChartData` 集合新增系列，然後以 `ChartDataPoint` 物件填入數值與類別名稱。此方式可顯示多達 10 000 個切片，同時保留標籤格式。設定完資料後，您還可以自訂顏色、圖例與資料標籤，以符合企業樣式指南。

以下程式碼示範新增兩個類別並顯示其標籤：

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
此片段建立資料系列、插入兩個資料點，並在圖表上啟用類別標籤。

#### 步驟 4：儲存簡報  
最後，將簡報以您選擇的格式（PPTX、PDF 或 PNG）寫入檔案。`save` 方法會遵循已啟用的授權，確保不會出現試用浮水印。

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### 常見問題與解決方案
- **Missing License Error:** 請確認授權檔路徑正確，且在任何 Aspose.Slides 呼叫之前已實例化 `License` 物件。  
- **Empty Chart:** 請確認 `ChartData` 系列至少包含一個 `ChartDataPoint`，空系列會導致圖表區域為空白。  
- **Performance Lag with Large Data Sets:** 使用 `presentation.getSlides().removeAt(index)` 移除未使用的投影片，並在大量處理後呼叫 `System.gc()` 釋放記憶體。

## 實務應用
1. **Business Reports:** 以單一圓形圖表視覺化各區域的市場佔有率或營收分布。  
2. **Academic Presentations:** 以清晰、易於理解的方式呈現調查結果或實驗數據。  
3. **Project Dashboards:** 即時在投影片上顯示任務完成百分比或資源分配情況。

您亦可將 Aspose.Slides 與 JDBC 結合，從資料庫即時取得資料，為每週的主管簡報產生最新圖表。

## 效能考量
處理包含大量高解析度影像或龐大資料集的簡報時：
- 盡快釋放物件，可使用 `try‑with‑resources` 或明確呼叫 `dispose()`。  
- 啟用投影片資源的延遲載入，以降低記憶體使用。  
- 若進行批次處理，盡可能重複使用同一個 `Presentation` 實例，以減少 JVM 開銷。

## 結論
您現在已掌握使用 **Aspose Slides 授權** 在 Java 中建立圓形圖表的完整生產流程。可進一步嘗試長條圖、折線圖或環形圖，以豐富您的簡報內容。接下來，探索 API 的匯出功能，自動產生 PDF 報告或 PNG 圖片。

## 常見問答

**Q: 如何在同一投影片中加入多個圖表？**  
A: 為每個圖表呼叫 `slide.getShapes().addChart()`，並為每個實例提供不同的座標與尺寸。

**Q: 有哪些 Aspose.Slides for Java 的替代方案？**  
A: 常見的替代方案有 Apache POI 與 JFreeChart，但它們缺乏 Aspose 完整的匯出選項與授權模式。

**Q: 我可以使用 Aspose.Slides 將簡報轉換為其他格式嗎？**  
A: 可以——只需一次 `save` 呼叫即可匯出為 PDF、XPS、HTML、PNG、JPEG、SVG 等多種格式。

**Q: 如何為大型開發團隊處理授權？**  
A: 可購買涵蓋多位開發人員與多台伺服器的企業授權；請聯絡 Aspose 銷售以取得批量折扣。

**Q: 如果我的圖表資料經常更新該怎麼辦？**  
A: 可將 Aspose.Slides 與資料來源（例如 SQL 查詢）整合，於執行時重新建立圖表；API 支援動態資料繫結。

## 資源
- **文件:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)  
- **下載:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **購買:** [Buy a License](https://purchase.aspose.com/buy)  
- **免費試用:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)  
- **臨時授權:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支援:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-08-01  
**測試環境：** Aspose.Slides for Java 25.4  
**作者：** Aspose

## 相關教學

- [如何在 Aspose.Slides for Java 中新增與設定圖表](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [在 Java 簡報中使用 Aspose.Slides 建立與自訂圖表](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [如何使用 Aspose.Slides Java 建立與設定簡報：逐步指南](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}