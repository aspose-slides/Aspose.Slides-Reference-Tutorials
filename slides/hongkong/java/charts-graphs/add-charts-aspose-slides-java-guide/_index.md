---
date: '2026-06-03'
description: 了解如何使用 aspose slides maven 相依性添加圖表、配置資料標籤，並在 Java 演示文稿中產生動態圖表。
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: aspose slides maven 相依性：使用 Aspose.Slides for Java 在演示文稿中添加與配置圖表
url: /zh-hant/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency：在簡報中使用 Aspose.Slides for Java 添加與設定圖表

## 介紹
**aspose slides maven dependency** 讓 Java 開發人員能夠以程式方式建立、修改及豐富 PowerPoint 檔案，完全不需要開啟 PowerPoint 本身。 在許多商業與學術情境中，手動插入圖表既耗時又容易出錯。本教學將一步步示範如何加入氣泡圖、將資料標籤綁定至工作表儲存格，並儲存結果——全程透過 **aspose slides maven dependency** 以乾淨、可重複的方式完成。

**您將學習**
- 使用 aspose slides maven dependency 新增圖表的方法
- 使用 Maven 或 Gradle 設定 Java 專案
- 載入現有簡報並插入氣泡圖
- 使用儲存格參照設定資料標籤（新增資料標籤圖表）
- 儲存更新後的檔案以供日後分發
- 真實案例，例如動態圖表產生與建立簡報圖表工作流程

## 快速解答
- **哪個 Maven 套件提供圖表功能？** `com.aspose:aspose-slides:25.4`（或最新版）  
- **我可以將資料標籤綁定至 Excel 風格的儲存格嗎？** 可以——使用 `ChartDataLabel` 搭配 `setDataLabelFormat` 以及儲存格參照。  
- **生產環境是否需要授權？** 完整授權會移除評估水印並解鎖所有功能。  
- **此功能能在 Java 11+ 上運作嗎？** 當然可以；此函式庫相容於 Java 8 至 Java 21。  
- **支援多少種圖表類型？** 超過 70 種不同的圖表類型，包含氣泡圖、雷達圖與股票圖等。

## 什麼是 aspose slides maven dependency？
**aspose slides maven dependency** 是一個相容於 Maven 的套件，提供完整的 API 以在 Java 中建立與編輯 PowerPoint（PPTX、PPT、ODP）檔案。只要在 `pom.xml` 或 `build.gradle` 中加入此相依，即可取得超過 70 種圖表類型、150+ 投影片版面配置，並能在未安裝 Office 的環境下操作形狀、動畫與中繼資料。

## 為何在圖表自動化中使用 aspose slides maven dependency？
Aspose.Slides 能在標準伺服器硬體上於一秒內處理上千張投影片的簡報，支援 **70+ 圖表類型**，且可渲染至 **10,000 張投影片** 而不需將整個檔案載入記憶體。這些可量化的效能使其成為企業級動態圖表產生的理想選擇，因為效能與擴充性是不可妥協的需求。

## 前置條件
- **Java Development Kit (JDK)** 8 或更新（建議使用 Java 11+）。  
- **Maven** 3.6+ **或** **Gradle** 6+。  
- **Aspose.Slides for Java** 函式庫（即 aspose slides maven dependency，版本 25.4 或更新）。  
- 具備 Java 集合與檔案 I/O 的基本知識。  
- 若計畫在試用期後執行程式，需提供評估或正式授權檔案（`license.json`）。

## 如何使用 Aspose.Slides 在投影片中加入圖表？
載入目標簡報、在指定投影片上建立新圖表形狀，並指定圖表類型（本例為氣泡圖）。只要引用函式庫，即可在 **三行程式碼** 內完成整個操作，讓快速原型開發與正式生產流程皆得以簡化。

### 步驟 1：加入 aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
這些程式碼片段直接從 Maven Central 取得完整的 Aspose.Slides API（含圖表支援）。

### 步驟 2：載入簡報並插入氣泡圖
**實作：**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 步驟 3：設定圖表的資料系列與標籤
**實作：**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 步驟 4：儲存已修改的簡報
**實作：**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## 如何使用儲存格參照設定資料標籤？
資料標籤可以綁定至外部儲存格值，類似 Excel 的「連結至儲存格」功能。此方式可避免硬編碼值，並實現 **動態圖表產生**——當底層資料變更時，標籤內容會自動更新。透過將每個標籤連結至特定工作簿儲存格，可確保來源資料的任何變動即時反映於簡報，減少維護工作並降低資訊過時的風險。

### 直接答案
Call `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` and pass a `DataLabelFormat` that references a cell address such as `"Sheet1!A2"`. Aspose.Slides resolves the reference at runtime, inserting the cell’s current value into the chart label.

### 步驟說明
1. 確認要標記的系列。  
2. 取得每個資料點的 `IDataLabel` 物件。  
3. 使用 `setDataLabelFormat`，並以 `CellReference` 設定 `DataLabelFormat`。  
4. （可選）自訂字型、顏色與顯示選項。

## 如何儲存已修改的簡報？
儲存只需呼叫單一方法，即可將記憶體中的 `Presentation` 物件寫入檔案路徑或輸出串流。您亦可透過傳入相應的 `SaveFormat` 列舉，選擇輸出格式（PPTX、PDF、ODP）。此操作會直接將結果串流至磁碟，且在 `Presentation` 實例關閉或超出範圍時自動釋放所有原生資源，確保即使是大型簡報亦能保持低記憶體使用量。

### 直接答案
Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`; the library streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope.

## 實務應用
1. **商業報告：** 從資料庫匯出自動產生季報銷售圖表。  
2. **學術講座：** 將即時研究資料拉入每堂課的投影片。  
3. **業務簡報：** 即時建立客製化績效儀表板。  
4. **專案管理：** 使用動態資料標籤視覺化甘特式時間軸。  
5. **行銷分析：** 將活動 KPI 嵌入簡報，隨新指標到達即自動更新。

## 效能考量
- **記憶體管理：** 使用 try‑with‑resources 或明確呼叫 `presentation.dispose()` 以即時釋放原生記憶體。  
- **大型資料集：** 處理超過 10,000 個資料點時，透過 `ChartDataWorkbook` 填充圖表資料，以避免將整個資料集載入 Java 物件。  
- **執行緒安全性：** 每個執行緒應使用各自的 `Presentation` 實例；API 在共享物件上並非執行緒安全。

## 常見問題與解決方案
- **問題：** 「找不到授權檔案。」  
  **解決方案：** 將 `license.json` 放置於 classpath，並在使用任何 API 前呼叫 `License license = new License(); license.setLicense("license.json");`。  
- **問題：** 儲存後圖表顯示為空白。  
  **解決方案：** 確認圖表的資料工作簿已隨簡報一起儲存（`presentation.getCharts().setDataWorkbook(chartWorkbook);`）。  
- **問題：** 資料標籤顯示 “#REF!” 錯誤。  
  **解決方案：** 檢查儲存格參照字串是否與正確的工作表名稱與位址相符，且確保已將參照的工作簿附加至圖表。

## 常見問答

**Q: 我可以加入除氣泡圖之外的其他圖表類型嗎？**  
A: 可以，`ChartType` 列舉包含折線圖、長條圖、圓餅圖、雷達圖、股票圖等超過 70 種其他類型。

**Q: aspose slides maven dependency 能與 OpenJDK 搭配使用嗎？**  
A: 當然可以；它完全相容於 OpenJDK 8‑21，且可在所有主要作業系統上執行。

**Q: 我要如何從現有的 Excel 檔案嵌入圖表？**  
A: 使用 `WorkbookFactory.create(new FileInputStream("data.xlsx"))` 載入 Excel 工作簿，然後在設定儲存格參照前，將圖表的 `ChartDataWorkbook` 綁定至該工作簿。

**Q: 每張投影片的圖表數量有限制嗎？**  
A: 實際上沒有——Aspose.Slides 能在每張投影片上處理數十個圖表，唯一限制是可用記憶體。

**Q: 最終簡報可以匯出為哪些格式？**  
A: 支援 PPTX、PPT、ODP、PDF、XPS、HTML，甚至 PNG、JPEG 等影像格式。

## 資源
- [Aspose.Slides for Java 版本發布](https://releases.aspose.com/slides/java/) – download the latest library binaries.  
- [Aspose.Slides 文件](https://reference.aspose.com/slides/java/) – comprehensive API reference and guides.  
- [下載 Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – direct download page for the Maven/Gradle packages.  
- [購買授權](https://purchase.aspose.com/buy) – obtain a full commercial license.  
- [免費試用](https://releases.aspose.com/slides/java/) – start with a trial to evaluate features.  
- [臨時授權](https://purchase.aspose.com/temporary-license/) – request a temporary key for extended evaluation.  
- [Aspose 支援論壇](https://forum.aspose.com/c/slides/11) – get help from the community and Aspose engineers.

## 結論
您現在已擁有使用 **aspose slides maven dependency** 在 Java 簡報中新增、設定與保存圖表的完整端對端指南。依照上述步驟，您可以自動化圖表建立、將資料標籤綁定至即時儲存格值，並大規模產生專業級簡報。請嘗試其他圖表類型、探索動畫 API，並將此工作流程整合至您的報表管線，以獲得最大效益。

---  
**最後更新：** 2026-06-03  
**測試環境：** Aspose.Slides for Java 25.4  
**作者：** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## 相關教學

- [如何使用 Aspose.Slides Java 建立與設定簡報：逐步指南](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [使用 Aspose.Slides Maven 建立 PPTX Java – 自動化指南](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [如何在 Java 中使用 Aspose.Slides 建立圖表：完整指南](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}