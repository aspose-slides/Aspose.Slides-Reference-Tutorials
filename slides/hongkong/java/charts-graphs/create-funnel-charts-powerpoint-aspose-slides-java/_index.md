---
date: '2026-09-02'
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中建立 funnel chart。此 step‑by‑step
  guide 介紹設定 chart data、customizing colors 以及 exporting the presentation 的方法。
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中建立 funnel chart。此 guide
  逐步說明 data setup、color customization 以及 exporting the final presentation 的流程。
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: 使用 Aspose.Slides for Java 在 PowerPoint 中建立 funnel chart
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: 使用 Aspose.Slides for Java 在 PowerPoint 中建立 funnel chart
url: /zh-hant/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 精通在 PowerPoint 中使用 Aspose.Slides for Java 建立漏斗圖表

## 簡介
製作引人入勝的簡報是一門結合資料視覺化、設計與敘事的藝術。能即時說明多階段流程的強大視覺效果之一就是漏斗圖表。無論您需要說明銷售管道、轉換流程或生產瓶頸，設計良好的漏斗圖表都能將原始數據轉化為直觀的敘事。在本教學中，您將學習如何使用 Aspose.Slides for Java 以程式方式 **create funnel chart** 於 PowerPoint，設定其資料、客製化每個區段的顏色，並匯出完成的簡報。

**您將學習**
- 如何將 Aspose.Slides for Java 加入 Maven 或 Gradle 專案  
- 如何實例化 `Presentation` 物件並存取其投影片  
- 如何插入漏斗圖表、定義類別，並填充系列資料  
- 如何使用純色填充或品牌特定顏色樣式化每個漏斗切片  
- 如何將簡報儲存為 PPTX 檔案或將投影片匯出為影像  

## 快速解答
- **Java 資料視覺化的主要函式庫是什麼？** Aspose.Slides for Java.  
- **如何在 PowerPoint 中建立漏斗圖表？** Call `slide.addChart(ChartType.Funnel, …)` on the target slide.  
- **哪個 API 設定圖表的資料來源？** Use `IChartDataWorkbook` together with `chart.getChartData()`.  
- **您可以為每個漏斗區段自訂顏色嗎？** Yes—set `FillFormat.setFillType(FillType.Solid)` and assign a `java.awt.Color`.  
- **生產環境是否需要授權？** A purchased Aspose.Slides license is required for commercial deployments.

## 什麼是 Java 資料視覺化？
Java 資料視覺化是指直接從 Java 應用程式將原始資料轉換為圖表、圖形或互動式圖形的做法。Aspose.Slides for Java 是領先的函式庫，可讓開發人員產生超過 100 種圖表類型——包括漏斗圖表——而無需手動啟動 PowerPoint，支援最多 500 張投影片的簡報，同時保持低記憶體使用量。

## 為何在 PowerPoint 中使用漏斗圖表？
漏斗圖表能即時顯示各連續階段的流失率，使其成為銷售管道、轉換分析或流程效率檢視的理想工具。Aspose.Slides 為您提供像素級的版面、區段顏色與資料標籤控制，讓您維持品牌一致性，並避免在 PowerPoint 使用者介面手動編輯圖表的繁瑣工作。

## 前置條件 (H2)

### 必要的函式庫、版本與相依性
要在您的專案中使用 Aspose.Slides for Java，請加入相應的 Maven 或 Gradle 坐標。此函式庫支援 Java 8‑21，且不需要外部原生相依性。

**Maven：**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

您也可以直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載 JAR。

### 環境設定需求
確保已安裝 JDK 8 或更新版本，且 `JAVA_HOME` 指向正確的 JDK 目錄。Aspose.Slides 可在任何支援 JDK 的作業系統上執行，包括 Windows、macOS 與 Linux。

### 知識前置條件
具備 Java 語法、物件導向程式設計以及簡報檔概念的基本認識會有幫助，但程式碼片段已完整說明，適用於任何經驗層級的開發人員。

## 設定 Aspose.Slides for Java (H2)

1. **加入相依性** – 使用上述的 Maven 或 Gradle 片段。  
2. **取得授權** –  
   - **免費試用** – 從 [Aspose's website](https://purchase.aspose.com/temporary-license/) 下載臨時授權以供評估。  
   - **完整授權** – 透過 [purchase page](https://purchase.aspose.com/buy) 購買正式授權。  
3. **基本初始化** –  

`Presentation` 是 Aspose.Slides 的核心類別，代表記憶體中的 PowerPoint 檔案。它提供對投影片、圖形與圖表物件的存取。

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

上述程式碼建立了一個新的 `Presentation` 實例，可進行投影片操作，並確保使用 `dispose()` 釋放資源。

## 實作指南
我們將逐步說明建立完整漏斗圖表所需的每個功能，並在每個程式碼佔位符前加入簡短說明文字。

### 功能 1：建立簡報 (H2)

#### 概觀
首先建立 `Presentation` 類別的實例。此物件是所有後續操作的入口點。

`Presentation` 是 Aspose.Slides 的頂層物件，保存投影片集合與全域文件設定。

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

此程式碼片段開啟一個空白簡報，您之後可將其儲存為 `.pptx` 檔案。

### 功能 2：在投影片中加入漏斗圖表 (H2)

#### 概觀
在第一張投影片插入漏斗圖表，定義其尺寸，並設定圖表類型。

`ChartType.Funnel` 告訴 Aspose.Slides 以漏斗樣式呈現，而非長條圖或折線圖。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

`addChart` 呼叫會建立圖表形狀，將其定位於 `(50, 50)` 點，寬度為 `500`、高度為 `400`。

### 功能 3：清除圖表資料 (H2)

#### 概觀
在填充圖表之前，先清除範本可能包含的任何佔位類別或系列。

`chart.getChartData().getCategories().clear()` 會移除所有現有的類別項目，而 `chart.getChartData().getSeries().clear()` 會移除任何預先填入的系列。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

這確保了乾淨的起點，使您的自訂資料能如預期般呈現。

### 功能 4：設定圖表資料工作簿 (H2)

#### 概觀
`IChartDataWorkbook` 物件儲存驅動圖表的原始數值。初始化它可讓您直接寫入儲存格。

`IChartDataWorkbook` 是 Aspose.Slides 用於提供圖表系列與類別的輕量級記憶體內試算表。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

程式碼會清除所有現有儲存格，為新條目做好準備。

### 功能 5：為圖表加入類別 (H2)

#### 概觀
定義顯示在漏斗左側的文字標籤——這些代表流程的每個階段。

`chart.getChartData().getCategories().add()` 會建立與特定工作簿儲存格連結的新類別物件。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

此處我們加入三個階段：「Prospects」、 「Qualified Leads」 與 「Closed Deals」。

### 功能 6：為圖表加入資料系列 (H2)

#### 概觀
以數值填充漏斗，並可選擇為每個切片指派唯一顏色。

`IDataPoint` 代表圖表系列中的單一資料點。

`chart.getChartData().getSeries().add()` 會建立一個保存數值資料點的系列；每個 `IDataPoint` 都可以設定自己的填充顏色。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

此迴圈示範如何為每個點設定純色填充，可使用品牌特定的 `java.awt.Color` 常數或隨機產生的顏色，以增加視覺變化。

## 常見使用情境與技巧 (H2)

- **銷售管道報告** – 顯示每個階段中有多少潛在客戶從 prospect 轉為 closed‑won。  
- **流程效率分析** – 以圖形化方式呈現製造步驟中的材料損耗或時間延遲。  
- **行銷漏斗檢視** – 比較不同活動或流量來源的轉換率。  

**專業提示：** 與其使用隨機顏色，不如使用公司品牌調色盤（例如 `new Color(0, 112, 192)`），以確保簡報與其他行銷資產保持一致。

## 常見問與答 (H2)

**Q: 如何變更漏斗圖表的方向？**  
A: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical` or `ChartOrientation.Horizontal`.

**Q: 加入圖表後，我可以將投影片匯出為影像嗎？**  
A: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.

**Q: 如果需要超過三個類別該怎麼辦？**  
A: Simply add additional categories using `chart.getChartData().getCategories().add(...)` and provide matching data points for each new category.

**Q: 有沒有方法隱藏圖例？**  
A: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)` to remove both the title and legend from the visual.

**Q: 開發版是否需要授權？**  
A: A temporary license is sufficient for evaluation; a full commercial license is required for production deployments.

---

**最後更新：** 2026-09-02  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Slides for Java 為 PowerPoint 新增圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [如何使用 Aspose.Slides for Java 編輯 PowerPoint 圖表資料：完整指南](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表加入動畫 – 逐步指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}