---
date: '2026-09-12'
description: 了解如何在 PowerPoint 中使用 Aspose.Slides for Java 建立叢集柱狀圖、擷取其資料範圍，並有效地匯出圖表影像。
keywords:
- create clustered column chart
- update powerpoint chart data
- export powerpoint chart image
- create pie chart java
- create powerpoint presentation java
- author: Aspose
  dateModified: '2026-09-12'
  description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  headline: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  type: TechArticle
- description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  name: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  steps:
  - name: Create the Presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: Add a Clustered Column Chart
    text: 'Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters Explained**:
      - `ChartType.ClusteredColumn`: Defines the type of chart. - `(10, 10)`: X and
      Y coordinates for positioning the chart on the slide. - `(400, 300)`: Width
      and height of the chart.'
  - name: Retrieve the Data Range
    text: 'Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving Data**: This method gives you a snapshot of your chart''s
      data, useful for debugging or display purposes.'
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
lastmod: '2026-09-12'
og_description: 了解如何在 PowerPoint 中使用 Aspose.Slides for Java 建立叢集柱狀圖、擷取其資料範圍，並有效地匯出圖表影像。支援更新
  PowerPoint 圖表資料及匯出圖表影像。
og_image_alt: 'Developer guide: create clustered column chart in PowerPoint using
  Aspose.Slides for Java'
og_title: 如何使用 Aspose.Slides for Java 建立叢集柱狀圖
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  headline: How to create clustered column chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  name: How to create clustered column chart with Aspose.Slides for Java
  steps:
  - name: create the presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: add a clustered column chart
    text: Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters explained**
      - `ChartType.ClusteredColumn` – selects the clustered column visual. - `(10,
      10)` – X and Y coordinates (points) for the chart’s top‑left corner.
  - name: add a clustered column chart
    text: Firstly, add a clustered column chart as described previously.
  - name: retrieve the data range
    text: Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving data** – this method gives you a snapshot of your chart's
      data, useful for debugging or display purposes.
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides Java
- PowerPoint chart generation
- Java presentation automation
- chart data retrieval
title: 如何使用 Aspose.Slides for Java 建立叢集柱狀圖
url: /zh-hant/java/charts-graphs/create-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PowerPoint 中使用 Aspose.Slides for Java 建立叢集柱狀圖

在 PowerPoint 檔案中建立叢集柱狀圖過去需要繁瑣的 XML 操作或完整的 Office 安裝。使用 **Aspose.Slides for Java**，您可以以程式方式產生圖表、調整其資料，並在數秒內匯出視覺效果。本教學將帶您一步步建立簡報、插入叢集柱狀圖，並讀取其底層資料範圍，以便稍後驗證或記錄。欲了解更多資訊，請造訪 [Aspose 網站](https://releases.aspose.com/slides/java/)。

## 快速解答
- **哪個函式庫可在 Java 中建立 PowerPoint 圖表？** Aspose.Slides for Java.  
- **範例使用哪種圖表類型？** A clustered column chart.  
- **執行範例是否需要授權？** 免費試用可用於評估；正式環境需購買商業授權。  
- **建立圖表後能否取得圖表資料？** 可以 – 呼叫 `getChartData().getRange()` 於圖表物件。  
- **支援哪個 Java 版本？** JDK 16 及更新版本。  

## Aspose.Slides for Java 是什麼？

`Aspose.Slides for Java` 是一個 **stand‑alone API**，讓您能在沒有 Microsoft Office 的情況下建立、編輯與轉譯 PowerPoint 檔案。它支援 **50+ 輸入與輸出格式**，且能處理 **數百張投影片且記憶體使用低於 200 MB** 的簡報。

## 為何使用 Aspose.Slides for Java 產生圖表？

Aspose.Slides 處理 **50+ 圖表類型**，在一般伺服器硬體上以 **最高 30 fps** 速度渲染，且可 **不將整個檔案載入記憶體** 即操作簡報。這使其非常適合需要每日產生數千張圖表且保持 CPU 與記憶體佔用低的自動化報表管線。

## 前置條件

在開始之前，請確保您已具備：

- **Java Development Kit (JDK)** 16 或更新版本已安裝。  
- IDE，例如 **IntelliJ IDEA** 或 **Eclipse**。  
- **Maven** 或 **Gradle** 用於相依性管理。  

### 必要的函式庫與相依性

使用以下任一程式碼片段將 Aspose.Slides 加入您的專案。

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，從 [Aspose.Slides for Java 版本發佈頁面](https://releases.aspose.com/slides/java/) 下載最新的 JAR。

### 取得授權

先使用免費試用版或申請臨時授權以解鎖全部功能。正式環境請從 [Aspose 授權購買頁面](https://purchase.aspose.com/buy) 購買授權。

## 設定 Aspose.Slides for Java

`Presentation` 類別是建立與操作 PowerPoint 檔案的主要入口點。加入相依性後，於程式碼中初始化 API。

1. **加入相依性**，使用上述的 Maven 或 Gradle。  
2. **建立 `Presentation` 實例** – 此物件將保存您的投影片與圖表。  

```java
Presentation pres = new Presentation();
```  

3. **釋放 Presentation**，完成後以釋放原生資源。  

```java
if (pres != null) pres.dispose();
```  

## 如何在 Java 中建立含叢集柱狀圖的 PowerPoint 簡報？

載入新的 `Presentation`，新增投影片，並以單一流暢的呼叫插入叢集柱狀圖。`Presentation` 物件在記憶體中代表整個 PowerPoint 檔案，而 `addChart` 方法則在指定的投影片上建立圖表形狀。以下為核心步驟，程式碼行數不超過十行。

### 步驟 1：建立簡報  

`Presentation` 類別是 Aspose.Slides 的最高層級物件，代表記憶體中的 PowerPoint 檔案。  

```java
Presentation pres = new Presentation();
```  

### 步驟 2：加入叢集柱狀圖  

使用 `addChart` 方法將圖表插入簡報。指定其類型、位置（x 與 y 座標）以及大小。  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

- **參數說明**  
  - `ChartType.ClusteredColumn` – 選擇叢集柱狀圖類型。  
  - `(10, 10)` – 圖表左上角的 X 與 Y 座標（點）。  
  - `(400, 300)` – 圖表的寬度與高度（點）。  

## 如何使用 Aspose.Slides for Java 取得 PowerPoint 簡報中圖表的資料範圍？

在圖表物件上呼叫 `getChartData().getRange()`；它會立即回傳類似 `"Sheet1!A1:B5"` 的字串，對應支援圖表的 Excel 風格範圍。此方法提供資料來源的簡潔文字表示，無需載入完整工作簿，適合用於記錄、除錯或自動化管線中的快速驗證。

### 步驟 1：加入叢集柱狀圖  

首先，依前述方式加入叢集柱狀圖。  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

### 步驟 2：取得資料範圍  

使用 `getChartData().getRange()` 取得資料範圍的字串表示。  

```java
String result = chart.getChartData().getRange();
// Output omitted for clarity
```  

- **取得資料** – 此方法提供圖表資料的快照，適用於除錯或顯示用途。  

## 實務應用

1. **商業報告** – 產生 KPI 儀表板，當來源資料變更時自動更新。  
2. **資料驅動的簡報** – 建立投影片套件，反映最新的銷售或庫存數據，無需手動編輯。  
3. **教育工具** – 為教學、測驗或互動教科書製作動態圖表。  

## 效能考量

- **及時釋放物件** – 在 `finally` 區塊中呼叫 `presentation.dispose()` 以釋放原生記憶體。  
- **避免載入完整文件** – 處理超過 200 MB 的簡報時使用串流 API。  
- **僅取得所需範圍** – `getChartData().getRange()` 可避免載入整個圖表資料集，降低 CPU 使用率。  

## 常見問題與解決方案

- **簡報當機** – 總是將檔案 I/O 包在 `try‑catch` 區塊，並確保在 `finally` 子句中執行 `dispose()`。  
- **圖表尺寸不正確** – 確認 X、Y、寬度與高度值均在投影片 960 × 720 點的畫布範圍內。  
- **授權錯誤** – 在建立任何 `Presentation` 物件之前載入授權檔案：`License license = new License(); license.setLicense("Aspose.Slides.lic");`。  

## 常見問答

**Q: 如何安裝 Aspose.Slides for Java？**  
A: 使用 Maven、Gradle，或從 [Aspose.Slides for Java 版本發佈頁面](https://releases.aspose.com/slides/java/) 下載 JAR。

**Q: 我可以建立其他類型的圖表嗎？**  
A: 可以，Aspose.Slides 支援超過 50 種圖表類型，包括長條圖、折線圖、圓餅圖與雷達圖。

**Q: 若簡報在處理過程中當機該怎麼辦？**  
A: 確保正確釋放資源，並將程式碼包在 try‑catch 區塊以處理 `IOException` 與 `Exception`。

**Q: 使用 Aspose.Slides 是否需要付費授權？**  
A: 有提供免費試用版。若需持續使用，請考慮購買授權或申請臨時授權。

**Q: 若遇到問題該如何取得支援？**  
A: 前往 [Aspose 支援論壇](https://forum.aspose.com/c/slides/11) 取得社群與 Aspose 專家的協助。

## 資源
- **文件**: [Aspose.Slides 文件說明](https://reference.aspose.com/slides/java/)  
- **下載**: [Aspose.Slides 下載頁面](https://releases.aspose.com/slides/java/)  
- **購買**: [購買 Aspose.Slides](https://purchase.aspose.com/buy)  
- **免費試用**: [取得免費試用版](https://releases.aspose.com/slides/java/)  
- **臨時授權**: [申請臨時授權](https://purchase.aspose.com/temporary-license/)

祝您使用 Aspose.Slides for Java 繪製圖表愉快！

---

**最後更新：** 2026-09-12  
**測試環境：** Aspose.Slides for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

## 相關教學

- [精通 Aspose.Slides Java 的 PowerPoint 操作：簡報功能完整指南](/slides/java/presentation-operations/aspose-slides-java-manipulate-pptx-presentations/)
- [精通 Aspose.Slides Java 的 PowerPoint 投影片自動化：批次處理完整指南](/slides/java/batch-processing/automate-powerpoint-slides-aspose-slides-java/)
- [使用 Aspose.Slides 在 Java 中建立環形圖：完整指南](/slides/java/charts-graphs/create-sunburst-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}