---
date: '2026-06-13'
description: 了解如何將 Excel 加入 PowerPoint，並透過建立動態餅圖，使用 Aspose.Slides for Java 從 Excel
  產生 PowerPoint。
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 將 Excel 加入 PowerPoint：使用 Aspose.Slides for Java 的動態餅圖簡報
url: /zh-hant/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 將 Excel 加入 PowerPoint：使用 Aspose.Slides for Java 的動態簡報與圓餅圖

在當今資料驅動的環境中，**將 Excel 加入 PowerPoint** 必須快速且可靠，讓觀眾能以視覺化方式看到數字。本教學將帶您一步步從 Excel 產生 PowerPoint、使用 Java 建立圓餅圖，並設定圖表資料範圍——全部透過 Aspose.Slides for Java 完成。完成後，您將擁有一個即時從 Excel 活頁簿抓取資料的可直接使用的簡報。

## 快速回答
- **哪個程式庫在 Java 中建立圖表？** Aspose.Slides for Java。  
- **可以直接將 Excel 資料拉入 PowerPoint 圖表嗎？** 可以——使用 Aspose.Cells 讀取活頁簿並將資料提供給圖表。  
- **示範的圖表類型是什麼？** 圓餅圖。  
- **如何設定圖表的資料範圍？** 呼叫 `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`。  
- **此方法的主要好處是什麼？** 自動化「將 Excel 加入 PowerPoint」的工作流程，省去手動複製貼上的步驟。

## 什麼是 **將 Excel 加入 PowerPoint**？
將 Excel 加入 PowerPoint 意指以程式方式匯入試算表資料，並在投影片中以圖表形式呈現。這讓您能保留原始 Excel 格式的資料，同時在簡報中展示精緻的圖表，確保活頁簿的任何更新都會即時反映在簡報裡。

## 為什麼要使用 Aspose.Slides for Java 從 Excel 產生 PowerPoint？
使用 Aspose.Slides for Java 從 Excel 產生 PowerPoint，可在數秒內建立投影片套件，直接從活頁簿抓取資料，免除手動複製貼上。此程式庫支援超過 50 種輸入與輸出格式，能在不將整個檔案載入記憶體的情況下處理上百頁的活頁簿，並提供完整的程式化控制，讓您自訂圖表樣式、顏色與資料範圍。

## 如何使用 Aspose.Slides for Java 從 Excel 產生 PowerPoint？
先使用 Aspose.Cells 載入 Excel 活頁簿，建立新的 `Presentation`，在投影片上加入圓餅圖形狀，然後將圖表綁定至活頁簿的資料範圍。只需幾行 Java 程式碼，即可產生反映最新試算表數值的完整 `.pptx` 檔案。

## 如何使用 Aspose.Slides 將 Excel 匯入 PowerPoint？
匯入流程是先將 Excel 檔案讀入 `Workbook` 物件，將活頁簿轉換為位元組陣列，然後將該位元組陣列傳遞給圖表的資料來源。圖表會自動讀取指定的範圍，使視覺效果與試算表保持同步。

## 如何在 Aspose.Slides for Java 中設定圖表資料範圍？
使用 `chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` 方法，即可將圖表指向包含類別與數值的確切儲存格。這一呼叫同時定義資料來源與版面配置，免除手動建立系列的步驟。

## 前置條件

開始之前，請確保您已具備：

- **Java Development Kit (JDK) 1.8+** 已安裝。  
- **Aspose.Slides for Java** 與 **Aspose.Cells for Java** 程式庫（Maven、Gradle，或直接下載 JAR）。  
- 包含欲視覺化資料的 Excel 活頁簿 (`book1.xlsx`)。  
- 有效的 Aspose 授權（免費試用版可用於評估）。

### 必要程式庫
您需要 Aspose.Slides 與 Aspose.Cells。請使用以下其中一種相依管理工具：

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

或直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載 JAR。

### 授權取得
- **免費試用：** 前往 [Aspose 下載頁面](https://releases.aspose.com/slides/java/) 取得。  
- **臨時授權：** 若需在無評估限制的情況下測試，請至 [Aspose 臨時授權頁面](https://purchase.aspose.com/temporary-license/) 申請。  
- **購買授權：** 若在正式環境使用 Aspose 產品，請購買完整授權。

## 設定 Aspose.Slides for Java

將 Aspose.Slides 相依加入專案（參考上方 Maven/Gradle 片段），若未使用建置工具，請將 JAR 放入 classpath。

### 基本初始化與設定
匯入代表 PowerPoint 檔案的核心類別：  
```java
import com.aspose.slides.Presentation;
```  

## 實作指南

以下提供逐步說明，涵蓋 **建立 Java 圓餅圖**、**設定圖表資料範圍** 與 **將 Excel 加入 PowerPoint** 的完整流程。

### 建立並加入圖表至簡報

**概觀：** 初始化新簡報、取得第一張投影片，並插入圓餅圖。

#### 步驟 1：初始化 Presentation  
```java
Presentation pres = new Presentation();
```  
- **目的：** 在記憶體中建立空的 PowerPoint 檔案。

#### 步驟 2：存取第一張投影片  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **說明：** 取得系統自動建立的第一張投影片。

#### 步驟 3：在投影片加入圓餅圖  
`IChart` 物件代表投影片上的圖表形狀。  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **參數：** 位置 (`x`, `y`) 與大小 (`width`, `height`)。  
- **目的：** 在投影片上放置圓餅圖形狀。

### 從檔案載入活頁簿

**概觀：** 載入保存圖表資料的 Excel 活頁簿。

#### 步驟 1：定義文件目錄  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- 請將此路徑設定為放置 `book1.xlsx` 的資料夾。

#### 步驟 2：開啟活頁簿  
`Workbook` 類別來自 Aspose.Cells，用於將 Excel 檔案載入記憶體。  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **目的：** 讀取 Excel 檔案至記憶體。

### 將活頁簿儲存至 ByteArrayOutputStream

**概觀：** 將活頁簿轉換為位元組陣列，以供 Aspose.Slides 使用。

#### 步驟 1：建立 ByteArrayOutputStream  
`ByteArrayOutputStream` 提供二進位資料的記憶體緩衝區。  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **目的：** 為暫存提供記憶體串流。

#### 步驟 2：將活頁簿儲存至串流  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **說明：** 將活頁簿寫入為 XLSX 位元組串流。

### 將活頁簿資料寫入圖表

**概觀：** 將 Excel 位元組陣列作為圖表的資料來源。

#### 步驟 1：將資料餵入圖表  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **目的：** 讓圖表連結至 Excel 資料。

### 設定圖表資料範圍並配置系列

**概觀：** 定義圖表讀取的儲存格範圍，並調整視覺樣式。

#### 步驟 1：定義資料範圍  
`setRange` 方法指定用於圖表的 Excel 儲存格。  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **說明：** 將圖表指向 *Sheet2* 上的精確範圍。

#### 步驟 2：配置系列屬性  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **目的：** 為圓餅圖的每一切片啟用不同顏色。

### 將簡報儲存至檔案

**概觀：** 將完成的簡報寫入磁碟。

#### 步驟 1：定義輸出路徑  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- 請選擇欲存放最終 PowerPoint 檔案的資料夾。

#### 步驟 2：儲存簡報  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **說明：** 將簡報寫入為 `.pptx` 檔案。

## 實務應用

1. **商業報告：** 只需一個指令即可將每月銷售試算表轉換為精美投影片。  
2. **教學工具：** 在課堂簡報中展示統計分布，免除手動製作圖表的時間。  
3. **儀表板整合：** 自動產生以 Excel 活頁簿為資料來源的投影片式儀表板。

## 效能考量

- **記憶體管理：** 使用 try‑with‑resources 或在 `finally` 區塊中關閉串流，以避免記憶體泄漏。  
- **大型資料集：** 可分塊處理資料，或在取得所需值後呼叫 `Workbook.getWorksheets().clear()` 釋放資源。  
- **延遲載入：** 僅在需要填充圖表時才載入活頁簿，避免在應用程式啟動時即載入。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **圖表未顯示資料** | 確認範圍字串完全符合工作表名稱與儲存格地址（例如 `Sheet2!$A$1:$B$3`）。 |
| **OutOfMemoryError** | 使用 `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` 以確保即時釋放串流。 |
| **授權未套用** | 在實例化任何 Aspose 類別之前先載入授權：`License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## 常見問答

**Q: 可以在沒有授權的情況下使用 Aspose.Slides 嗎？**  
A: 可以，但評估模式會加上浮水印並限制部分功能。正式環境建議取得臨時或完整授權。

**Q: 如何處理 Aspose.Slides 中的大型簡報？**  
A: 採用有效的資源管理，將簡報拆分為較小的部分，並及時釋放不再使用的物件。

**Q: Aspose.Slides 可以匯出哪些檔案格式？**  
A: 支援 PPTX、PDF、XPS、ODP、HTML，以及 PNG、JPEG、BMP 等影像格式。

**Q: 能否更新既有的 PowerPoint 檔案，而不是建立新檔？**  
A: 完全可以。使用 `new Presentation("existing.pptx")` 載入既有檔案，修改投影片或圖表後再儲存。

**Q: 程式庫是否支援為個別圓餅切片設定自訂顏色？**  
A: 支援——取得系列後，可使用 `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` 並指定 `Color`。

## 資源
- **文件說明：** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)  
- **下載：** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)  
- **購買授權：** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **免費試用：** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)  
- **臨時授權：** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**最後更新：** 2026-06-13  
**測試環境：** Aspose.Slides 25.4 for Java (JDK 16) 與 Aspose.Cells 25.4  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.Slides for Java 更新 PowerPoint 圖表資料範圍](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)  
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中加入圓餅圖](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)  
- [使用 Aspose.Slides for Java 為 PowerPoint 加入圖表的逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}