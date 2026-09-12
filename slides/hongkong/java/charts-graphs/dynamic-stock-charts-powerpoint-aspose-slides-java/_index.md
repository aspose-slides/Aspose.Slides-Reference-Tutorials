---
date: '2026-09-12'
description: 了解如何使用 Maven Aspose Slides 在 PowerPoint 中以 Java 新增與自訂動態股票圖表。內容包括設定、新增資料系列、設定線條格式以及儲存。
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides 教學示範如何使用 Java 在 PowerPoint 中建立與自訂動態股票圖表，涵蓋資料系列、線條格式設定與儲存。
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: Maven Aspose Slides 指南：在 PowerPoint 中建立動態股票圖表
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: Maven Aspose Slides：使用 Java 在 PowerPoint 中建立動態股票圖表
url: /zh-hant/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides：使用 Java 在 PowerPoint 中建立動態股票圖表

## 介紹

**Maven Aspose Slides** 讓您能以程式方式從 Java 產生高階的 PowerPoint 簡報。在本教學中，您將學會如何建立動態股票圖表、加入與格式化資料系列、客製化圖表線條，最後儲存檔案。無論您是為財務分析師準備季報，或是開發自動化投影片的程式設計師，以下步驟都提供完整、可投入生產環境的解決方案。

**您將學習**
- 如何使用 Maven 設定 Aspose.Slides for Java  
- 如何新增股票圖表並清除預設資料  
- 如何 **新增資料系列圖表** 與 **格式化圖表線條**  
- 如何 **客製化圖表 Java** 專屬的視覺元素  
- 如何儲存更新後的簡報

準備好把原始數字轉換成吸睛的股票視覺效果了嗎？讓我們開始吧！

## 快速解答
- **需要哪個 Maven 套件？** `aspose-slides` 版本 25.4（或更新）。  
- **可以在任何作業系統上執行嗎？** 可以 – 此函式庫純 Java，支援 Windows、macOS 與 Linux。  
- **開發時需要授權嗎？** 測試可使用免費暫時授權；正式上線需購買完整授權。  
- **支援哪些圖表類型？** 超過 70 種內建圖表類型，包含股票、折線與長條圖。  
- **可以處理多大的簡報？** Aspose.Slides 能在不將整個檔案載入記憶體的情況下處理 500 張以上投影片的檔案。

## 什麼是 Maven Aspose Slides？

`Aspose.Slides for Java` 是一套 Java API，讓您在不安裝 Microsoft Office 的情況下建立、操作與轉換 PowerPoint 檔案。Maven 整合簡化了相依管理，您只需從 Maven Central 直接取得函式庫。

## 為何在股票圖表中使用 Maven Aspose Slides？

Aspose.Slides 支援 **70+ 圖表類型**，且能在一般伺服器硬體上於一秒內渲染上百頁簡報。其 **high‑low line** 與 **up/down bar** 功能提供對金融視覺化的精確控制，遠超 PowerPoint UI 所能提供的功能。

## 前置條件

- **Java Development Kit (JDK)** – 版本 11 或以上。  
- **IDE** – IntelliJ IDEA、Eclipse，或您慣用的任何編輯器。  
- **Aspose.Slides for Java** – 版本 25.4（撰寫本文時的最新版本）。  

### 設定 Aspose.Slides for Java

#### Maven
將 Aspose.Slides 整合至 Maven 專案，請在 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Gradle 使用者請在 `build.gradle` 中加入：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接下載
亦可從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新 JAR。

**License acquisition** – 先使用免費試用或申請暫時授權。商業使用則需購買完整授權。

如需詳細 API 參考，請見 [Aspose.Slides documentation](https://docs.aspose.com/slides/java/)。

## 如何一步步建立動態股票圖表

載入簡報、加入股票圖表、清除預設資料，然後注入自訂的系列與類別。核心問題的直接答案如下：

> 使用 `new Presentation("template.pptx")` 載入既有 PPTX，加入 `ChartType.Stock` 類型的 `Chart`，清除其預設系列與類別，接著以自訂的資料點與格式選項填入。最後呼叫 `presentation.save("output.pptx", SaveFormat.Pptx)`。

### 初始化簡報
#### 概覽
先載入既有的 PowerPoint 檔案，以便直接在原檔上進行修改。

#### 步驟說明
1. **匯入函式庫** – `Presentation` 類別是所有投影片操作的入口點。  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **載入簡報檔案** – 提供您的範本 PPTX 路徑。  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 向投影片新增股票圖表
#### 概覽
在簡報的第一張投影片上插入股票圖表。

`Chart` 類別代表可加入投影片的圖表形狀。

#### 直接答案
呼叫 `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` 即可新增股票圖表，並立即取得可操作的圖表物件。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 清除圖表中現有的資料系列與類別
#### 概覽
移除任何預先填入的系列或類別，以便從乾淨的資料集開始。

`ChartData` 物件保存圖表的系列與類別。

#### 直接答案
使用 `chart.getChartData().getSeries().clear()` 與 `chart.getChartData().getCategories().clear()` 先清除預設內容，再加入自訂資料。

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 為圖表資料新增類別
#### 概覽
定義 X 軸的類別（例如日期），用以分組股票數值。

`ChartCategory` 代表圖表的 X 軸標籤。

#### 直接答案
使用 `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` 為每個標籤建立新 `ChartCategory`，依月份或期間重複此步驟。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 為圖表新增資料系列
#### 概覽
加入四個必要的系列：Open、High、Low、Close。

`ChartSeries` 保存特定系列的資料點集合。

#### 直接答案
對每個系列，呼叫 `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`，將系列註冊至圖表的資料工作簿。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 為系列新增資料點
#### 概覽
為每個系列填入代表股票價格的數值。

`DataPoint` 代表系列中的單一數值。

#### 直接答案
遍歷您的資料集合，使用 `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)`（或相應系列類型的方法）插入每個資料點。

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 格式化高低線與上/下條
#### 概覽
調整 high‑low 連接線與上/下條的視覺樣式。

`Marker` 定義資料點的視覺符號。

#### 直接答案
設定 `chart.getChartData().getSeries().get(0).getMarker().setSize(10)`，並透過 `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` 來控制線條粗細與顏色。

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### 顯示上/下條
使用圖表的 `setShowUpDownBars(true)` 方法即可顯示上/下條。

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### 自訂高低線上的資料標籤
#### 概覽
在 high‑low 線上直接顯示數值，方便快速參考。

`DataLabel` 控制附加於資料點的標籤外觀。

#### 直接答案
透過 `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` 開啟資料標籤，並依需求調整樣式。

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### 設定上/下條填色
#### 概覽
將上漲條設為綠色填色，下跌條設為紅色填色，以直觀呈現市場走勢。

`UpDownBars` 物件提供上下條的格式設定介面。

#### 直接答案
使用 `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` 並將實心顏色設為 `Color.GREEN`；下條則以 `Color.RED` 方式設定。

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### 儲存 PowerPoint 檔案
#### 概覽
將變更寫入新的 PPTX 檔案。

`save` 方法會以指定格式將簡報寫入磁碟。

#### 直接答案
呼叫 `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – 這會將修改後的簡報以標準 PowerPoint 格式寫入磁碟。

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## 常見問題與疑難排解

- **圖表未顯示** – 確認圖表的 X/Y 座標與尺寸在投影片範圍內。  
- **資料點遺失** – 核對資料工作簿的儲存格索引是否與您欲填入的系列/列相符。  
- **授權例外** – 暫時試用授權在 30 天後失效；生產環境請換上永久授權。  
- **大型檔案效能下降** – 若一次處理上千張投影片，可使用 `Presentation.setCacheSize(0)` 停用快取。

## 常見問答

**Q: 可以在 Web 應用程式中使用這段程式碼嗎？**  
A: 可以。此函式庫純 Java，能在任何 servlet 容器或 Spring Boot 服務中執行。

**Q: Aspose.Slides 支援除 Stock 之外的其他圖表類型嗎？**  
A: 當然支援。它提供超過 70 種圖表類型，包括折線圖、長條圖、圓餅圖與雷達圖等。

**Q: 如何以程式方式為圖表加入標題？**  
A: 使用 `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`，然後依需求格式化標題。

**Q: 每個系列的資料點數量有上限嗎？**  
A: 實務上可以加入數萬筆資料點；記憶體使用量會線性成長，函式庫會以串流方式處理以降低佔用。

**Q: 最新版的 Maven 坐標應該使用什麼？**  
A: 最新版本始終可於 Maven Central 取得，坐標為 `com.aspose:aspose-slides:25.4`（或更新）。

---

**最後更新：** 2026-09-12  
**測試環境：** Aspose.Slides for Java 25.4  
**作者：** Aspose

## 相關教學

- [aspose slides maven dependency：使用 Aspose.Slides for Java 在簡報中新增與設定圖表](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create PowerPoint Chart Java – 使用 Aspose.Slides 儲存含圖表的簡報](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Create Format Powerpoint Charts Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}