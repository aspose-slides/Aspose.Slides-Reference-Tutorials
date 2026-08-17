---
date: '2026-05-29'
description: 了解如何使用 Aspose.Slides Maven 建立圓餅圖、將 Java 圓餅圖新增至投影片，並自訂圖表資料。提供 Maven 設定與實務範例的逐步指南。
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: 建立 Aspose 圓餅圖 – 使用 Maven 為簡報新增圖表
url: /zh-hant/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides Java 為簡報新增圓餅圖

## 介紹
在本指南中，您將 **create pie chart aspose** 使用 Aspose.Slides Maven，並了解如何將其嵌入 PowerPoint 投影片。製作視覺吸引力的簡報對於有效傳遞資訊至關重要，尤其是當資料視覺化扮演關鍵角色時。如果您想透過 **aspose slides maven** 自動化此流程，您來對地方了。我們將逐步說明如何在投影片中加入圖表——特別是圓餅圖——並針對實務情境進行客製化。

### 您將學習
- 如何在 Java 中初始化簡報物件。  
- 在簡報的第一張投影片上 **add a pie chart java**（新增圓餅圖）的步驟。  
- 存取圖表資料工作簿並列出其中的工作表。  

讓我們深入了解如何利用 Aspose.Slides Java 以動態圖表提升您的簡報！

## 快速解答
- **哪個函式庫透過 Maven 加入圖表？** aspose slides maven  
- **示範的是哪種圖表類型？** Pie chart (add chart to slide)  
- **最低需要的 Java 版本？** JDK 16 or later  
- **測試是否需要授權？** A free trial works; production needs a license  
- **在哪裡可以找到 Maven 相依性？** In the setup section below  

## 什麼是 Aspose Slides Maven？
Aspose.Slides for Java 是功能強大的 API，讓開發人員能以程式方式建立、修改與轉換 PowerPoint 檔案。Maven 套件（`aspose-slides`）簡化相依性管理，使您能專注於建構與客製化投影片——例如加入圓餅圖——而不必處理低階檔案操作。

## 為何使用 Aspose.Slides Maven 在投影片中加入圖表？
使用 Aspose.Slides Maven 能直接從 Java 程式碼產生圖表，免除手動編輯 PowerPoint。它提供完整的程式化控制，涵蓋圖表類型、資料來源與樣式，確保品牌一致性與資料精確性。Maven 套件亦會自動處理所有必要的相依性，簡化建置流程，並可無縫整合至 CI/CD 管線。

## 前置條件
- **Aspose.Slides for Java** 版本 25.4 或更新（Maven/Gradle）。  
- 已安裝 JDK 16 以上。  
- 具備 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知識，並熟悉 Maven 或 Gradle。

## 設定 Aspose.Slides for Java
首先，透過 Maven 或 Gradle 將 Aspose.Slides 加入您的專案。

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
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

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，您也可以直接從 Aspose 官方網站[下載最新版本](https://releases.aspose.com/slides/java/)。

### 取得授權
Aspose.Slides for Java 提供免費試用與暫時授權供測試使用。若需無限制的正式環境，請透過[購買頁面](https://purchase.aspose.com/buy)取得授權。

## 實作指南
以下我們將解決方案分為兩個功能：加入圓餅圖以及存取其資料工作簿。

### 功能 1：建立簡報並加入圖表
#### 概觀
此部分說明如何建立新簡報並 **add a pie chart** 到第一張投影片。

#### 如何建立 pie chart aspose？
載入 `Presentation` 類別，加入類型為 `ChartType.Pie` 的圖表，然後儲存檔案。整個操作僅需三個 API 呼叫，對於一般 10 張投影片的簡報，執行時間不到一秒，非常適合自動化報表產生。

#### 步驟說明

**步驟 1：初始化新的 Presentation 物件**  
`Presentation` 類別是 Aspose.Slides 的頂層物件，代表記憶體中的 PowerPoint 檔案。  
```java
Presentation pres = new Presentation();
```
*建立將容納所有投影片的 `Presentation` 實例。*

**步驟 2：加入圓餅圖**  
`ChartType.Pie` 告訴 Aspose 繪製圓餅圖。  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*在座標 (50, 50) 處放置寬 400、高 500 的圓餅圖。*

**步驟 3：釋放資源**  
呼叫 `dispose()` 釋放原生資源，防止記憶體洩漏。  
```java
if (pres != null) pres.dispose();
```
*釋放原生資源；完成後務必呼叫 `dispose()`。*

### 功能 2：存取圖表資料工作簿與工作表
#### 概觀
學習如何取得儲存圖表資料的底層工作簿，並遍歷其工作表。

#### 如何存取圖表資料工作簿？
從圖表取得 `IChartDataWorkbook`，再遍歷其 `Worksheets` 集合。此工作簿模擬 Excel 檔案，允許以程式方式讀取、修改或新增資料系列，圖表在執行期間重新整理時會即時反映變更，無需重新啟動。

#### 步驟說明

**步驟 1：（重用）初始化新的 Presentation 物件**  
*同功能 1 的步驟 1。*

**步驟 2：（重用）加入圓餅圖**  
*同功能 1 的步驟 2。*

**步驟 3：取得圖表資料工作簿**  
`IChartDataWorkbook` 是提供對圖表內部類 Excel 工作簿讀寫存取的介面。  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*取得與圖表關聯的 `IChartDataWorkbook`。*

**步驟 4：遍歷工作表**  
`Worksheet` 物件代表工作簿內的個別工作表。  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*列印每個工作表的名稱，以驗證資料結構。*

**步驟 5：釋放資源**  
*同功能 1 的步驟 3。*

## 實務應用
- **資料報告：** 自動產生包含最新指標的投影片套件，以支援商業智慧。  
- **學術簡報：** 可視化研究結果，免除手動製作圖表。  
- **行銷素材：** 即時展示產品表現或調查結果。

## 效能考量
- Aspose.Slides 能處理 **50+ 種輸入與輸出格式**，且可在不將整個檔案載入記憶體的情況下處理數百頁的簡報。  
- 請保持投影片與圖表數量在合理範圍；每個圖表皆會佔用原生記憶體。  
- 務必即時呼叫 `dispose()` 釋放資源。  
- 優化工作簿資料處理——避免將龐大資料集載入單一圖表。

## 結論
我們已說明 **aspose slides maven** 如何讓您以程式方式 **add chart to slide**，以及如何操作圖表的資料工作簿。透過這些基礎，您可以自動化任何需要精緻 PowerPoint 輸出的報告工作流程。

### 後續步驟
- 探索圖表樣式選項（顏色、圖例、資料標籤）。  
- 連接外部資料來源（CSV、資料庫）以動態填充圖表。  
- 在同一簡報中結合多種圖表類型，打造更豐富的敘事。

## 常見問題

**Q: 如何安裝 Aspose.Slides for Java？**  
A: 使用上方示範的 Maven 或 Gradle 相依性，或從發行頁面下載程式庫。

**Q: Aspose.Slides 的系統需求是什麼？**  
A: JDK 16 或更新版本；只要平台支援 Java，即可執行此程式庫。

**Q: 除了圓餅圖，我可以加入其他圖表類型嗎？**  
A: 可以，Aspose.Slides 支援長條圖、折線圖、散佈圖、雷達圖等超過 20 種圖表類型。

**Q: 如何有效處理大型簡報？**  
A: 及時釋放物件，限制高解析度影像，並重複使用圖表範本以降低記憶體使用量。

**Q: 哪裡可以找到 Aspose.Slides 功能的更多細節？**  
A: 前往 [Aspose documentation](https://reference.aspose.com/slides/java/) 取得完整 API 參考。

**Q: 商業使用是否需要授權？**  
A: 正式環境必須使用有效授權；可使用免費試用版進行評估。

**Q: Maven 套件是否包含所有圖表功能？**  
A: 是的，`aspose-slides` Maven 套件內含完整的圖表引擎。

## 資源
- 文件說明：[Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- 下載：[Latest Releases](https://releases.aspose.com/slides/java/)
- 購買與試用：[Purchase Page](https://purchase.aspose.com/buy)
- 免費試用：[Trial Downloads](https://releases.aspose.com/slides/java/)
- 暫時授權：[Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- 支援論壇：[Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## 相關教學

- [如何在 Java 使用 Aspose.Slides 自訂圓餅圖顏色 – 完整指南](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [在 Java 使用 Aspose.Slides 建立「圓餅中的圓餅」圖表 – 全面指南](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表加入動畫 – 步驟說明](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}