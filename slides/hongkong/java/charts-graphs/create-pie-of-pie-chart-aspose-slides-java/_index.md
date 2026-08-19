---
date: '2026-07-17'
description: 了解如何透過使用 Aspose.Slides for Java 建立餅圖子圖，將圖表加入 PowerPoint。內容包括環境設定、程式碼、客製化以及儲存為
  PPTX。
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: 使用 Aspose.Slides for Java 在 PowerPoint 中加入圖表。本指南說明如何在數分鐘內建立、客製化並儲存餅圖子圖為
  PPTX。
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: 在 PowerPoint 中加入圖表 – 使用 Java 建立餅圖子圖
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: 在 PowerPoint 中加入圖表 – 使用 Aspose.Slides for Java 建立餅圖子圖
url: /zh-hant/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 PowerPoint 中加入圖表 – 使用 Aspose.Slides for Java 建立餅圖中的餅圖

## 圖表與圖形

### 簡介

在現代以資料為驅動的簡報中，**在 PowerPoint 中加入圖表** 通常是將原始數字轉換為視覺洞見的最快方式。普通的餅圖適用於少量類別，但當有幾個切片非常小時，會變得難以閱讀。*Pie of Pie* 圖表透過將這些小切片抽取到次要餅圖中，保持主圖表簡潔，同時讓細節易於存取。

在本教學中，你將學會如何 **在 PowerPoint 中加入圖表**，方法是使用 Aspose.Slides for Java 建立 Pie of Pie 圖表。我們會逐步說明環境設定、圖表建立、標籤客製化、切割位置調整，最後將簡報儲存為 PPTX 檔案。完成後，你即可在任何投影片中嵌入高階圖表。

## 快速解答
在 Aspose.Slides 中，`Presentation` 代表 PPTX 檔案，`ChartType.PieOfPie` 選取 Pie of Pie 圖表，`setShowValue(true)` 會在標籤上顯示數值，`save` 則寫入檔案。

- **操作 PowerPoint 的主要類別是什麼？** `Presentation` – 它在記憶體中代表整個 PPTX 檔案。  
- **哪種圖表類型會為小切片建立次要餅圖？** `ChartType.PieOfPie`。  
- **如何在每個切片上顯示數值？** 設定 `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`。  
- **可以直接將檔案儲存為 PPTX 嗎？** 可以 – 呼叫 `presentation.save("output.pptx", SaveFormat.Pptx)`。  
- **開發時需要授權嗎？** 免費 30 天試用可用於測試；永久授權可移除評估水印。

## 什麼是 Pie of Pie 圖表？

**Pie of Pie 圖表** 是一種兩層餅圖視覺化，會將一個或多個小切片隔離到獨立且連結的次要餅圖中，讓它們更易於閱讀。Aspose.Slides 內建支援此圖表類型，讓你可以控制切割大小、位置與標籤格式。

## 為什麼要使用 Aspose.Slides 在 PowerPoint 中加入圖表？

Aspose.Slides 能在未安裝 Microsoft Office 的環境下產生、編輯與轉譯 PowerPoint 檔案。它支援 **50+ 輸入與輸出格式**，在一般伺服器硬體上可在一秒內處理 **最多 500 張投影片** 的簡報，並提供 **完整 API 控制** 以調整圖表樣式、資料標籤與版面配置——非常適合自動化報表流程。

## 先決條件

- 已安裝 **Java Development Kit (JDK) 16+**。  
- IDE，例如 **IntelliJ IDEA**、**Eclipse** 或 **NetBeans**。  
- 用於相依性管理的 Maven 或 Gradle（請參閱以下章節）。  
- 基本的 Java 知識與專案建置經驗。

## 設定 Aspose.Slides for Java

### 安裝資訊

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

**直接下載：**您可以從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權步驟
- **免費試用：**先使用 30 天試用版探索所有功能。  
- **暫時授權：**申請臨時金鑰以延長評估期間。  
- **購買：**取得永久授權以在正式環境中使用，並移除評估水印。

### 基本初始化與設定
`Presentation` 是建立 PowerPoint 檔案的主要物件，`Chart` 代表投影片中的圖表形狀。

```java
Presentation presentation = new Presentation();
```  

此程式碼會建立一個空的簡報，供後續加入投影片與圖表使用。

## 實作指南

### 如何使用 Aspose.Slides for Java 在 PowerPoint 中加入圖表？

載入新的 `Presentation`，新增投影片，然後插入類型為 `PieOfPie` 的 `Chart`。API 呼叫鏈相當簡潔：建立圖表、填入系列資料、調整標籤可見性、設定次要餅圖大小，最後儲存。整個流程通常不超過 20 行程式碼，非常適合自動化報表產生。

### 建立「Pie of Pie」圖表

#### 概覽
我們將在第一張投影片上建立 Pie of Pie 圖表，將最小的切片分離出來，並為每個區段顯示其數值。

#### 步驟 1：建立 Presentation 類別的實例
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
此程式碼初始化了容納所有後續投影片與圖表的容器。

#### 步驟 2：在第一張投影片上加入「Pie of Pie」圖表
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
此處指定 `ChartType.PieOfPie`，並在投影片畫布上定義圖表的位置 (X, Y) 與大小 (寬度, 高度)。

#### 步驟 3：設定資料標籤以顯示系列的數值
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
啟用 `showValue` 後，每個切片會顯示其數值，這對快速資料解讀相當重要。

#### 步驟 4：設定次要餅圖大小與依百分比分割
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
這些選項讓你決定次要餅圖佔用的比例，以及依百分比門檻將哪些切片移至次要餅圖。

#### 步驟 5：將簡報儲存為 PPTX 格式
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **專業提示：**使用絕對路徑或 Java 的 `Paths.get()` 可避免平台特定的分隔符問題。

## 常見問題與解決方案

`License` 類別會載入授權檔案以移除評估限制。

- **缺少授權警告：**若圖表上出現「Evaluation Only」訊息，請確保透過 `License license = new License(); license.setLicense("Aspose.Slides.lic");` 正確套用授權檔案。  
- **切片分割不正確：**確認 `splitBy` 屬性已設定為 `SplitBy.Percentage`，且 `secondPieSize` 為 0~100 之間的數值。  
- **資料未顯示：**確認圖表的系列至少包含一個資料點，否則圖表會呈現空白。

## 常見問答

`IChart` 代表可加入投影片的圖表物件。

**Q：我可以在同一個簡報中產生多個圖表嗎？**  
A：可以，為每張投影片或每個位置實例化新的 `IChart`，API 允許在檔案中加入無限制的圖表物件。

`SaveFormat.Pdf` 指定 PDF 輸出格式。

**Q：Aspose.Slides 也支援儲存為 PDF 嗎？**  
A：當然支援 – 呼叫 `presentation.save("output.pdf", SaveFormat.Pdf)` 即可將相同的投影片套件匯出為 PDF。

`IPortion` 代表餅圖中單一切片。

**Q：Pie of Pie 圖表最多能處理多少筆資料點？**  
A：此函式庫每個系列最多支援 **10,000** 筆資料點，僅受可用記憶體限制。

**Q：能否自訂個別切片的顏色？**  
A：可以，透過 `chart.getChartData().getSeries().get_Item(0).getPortions()` 取得每個 `IPortion`，再使用 `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))` 設定顏色。

**Q：如何將產生的 PPTX 嵌入到 Web 應用程式中？**  
A：儲存檔案後，使用 `HttpServletResponse` 並設定 `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`，即可直接將檔案串流傳送給客戶端。

## 結論

你現在已掌握一套完整、可投入生產環境的 **在 PowerPoint 中加入圖表** 方法，透過 Aspose.Slides for Java 建立 Pie of Pie 圖表。可自行嘗試不同的切割門檻、標籤格式與配色方案，以符合品牌指引。接下來，探索其他圖表類型（如堆疊長條圖或雷達圖），進一步豐富你的自動化投影片套件。

---

**最後更新：** 2026-07-17  
**測試環境：** Aspose.Slides for Java 24.12  
**作者：** Aspose

## 相關教學

- [建立動態圖表 Java – PowerPoint 圖表教學 for Aspose.Slides](/slides/java/charts-graphs/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中加入餅圖](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [使用 Aspose.Slides for Java 在 PowerPoint 中加入圖表：一步步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}