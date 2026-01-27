---
date: '2026-01-09'
description: 探索如何使用 Aspose Slides Maven 在投影片中加入圖表，並在 Java 簡報中自訂圓餅圖。一步一步的設定、程式碼與實務範例。
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: aspose slides maven - 在簡報中加入圓餅圖
url: /zh-hant/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides Java 在簡報中加入圓餅圖

## 介紹
製作視覺吸引力的簡報對於有效傳遞資訊至關重要，尤其在資料視覺化扮演關鍵角色時。如果你想使用 **aspose slides maven** 來自動化此流程，你來對地方了。在本教學中，你將學會如何 **add chart to slide** — 特別是圓餅圖 — 使用 Aspose.Slides for Java，並了解如何在實務情境中自訂它。

### 你將學到
- 如何在 Java 中初始化 Presentation 物件。  
- 在簡報的第一張投影片上 **add a pie chart java** 的步驟。  
- 存取圖表資料工作簿並列出其中的工作表。  

現在就來看看如何利用 Aspose.Slides Java 為你的簡報加入動態圖表吧！

## 快速答覆
- **哪個函式庫可透過 Maven 加入圖表？** aspose slides maven  
- **示範的圖表類型是？** 圓餅圖 (add chart to slide)  
- **最低需要的 Java 版本？** JDK 16 或更新版本  
- **測試需要授權嗎？** 免費試用即可；正式上線需購買授權  
- **Maven 依賴在哪裡可以找到？** 請參考下方設定章節  

## 什麼是 Aspose Slides Maven？
Aspose.Slides for Java 是一套功能強大的 API，讓開發者能以程式方式建立、修改與轉換 PowerPoint 檔案。Maven 套件 (`aspose-slides`) 簡化了相依管理，讓你專注於建構與自訂投影片——例如加入圓餅圖——而不必處理底層檔案操作。

## 為什麼使用 Aspose.Slides Maven 來在投影片加入圖表？
- **自動化：** 自動產生報表與儀表板。  
- **精確控制：** 完全掌握圖表類型、資料與樣式。  
- **跨平台：** 可在任何相容 Java 的環境執行。  

## 前置條件
- **Aspose.Slides for Java** 版本 25.4 或更新（Maven/Gradle）。  
- 已安裝 JDK 16 以上。  
- 任一 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知識，並熟悉 Maven 或 Gradle。

## 設定 Aspose.Slides for Java
首先，透過 Maven 或 Gradle 將 Aspose.Slides 加入專案。

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

或者，你也可以直接從 Aspose 官方網站 [下載最新版本](https://releases.aspose.com/slides/java/)。

### 取得授權
Aspose.Slides for Java 提供免費試用與臨時授權供測試使用。若要在正式環境無限制使用，請透過 [購買頁面](https://purchase.aspose.com/buy) 取得授權。

## 實作指南
以下我們將解決方案分為兩個功能：加入圓餅圖以及存取其資料工作簿。

### 功能 1：建立簡報並加入圖表
#### 概觀
本節說明如何建立新簡報並 **add a pie chart** 到第一張投影片。

#### 步驟說明

**步驟 1：初始化新的 Presentation 物件**  
```java
Presentation pres = new Presentation();
```
*建立將容納所有投影片的 `Presentation` 實例。*

**步驟 2：加入圓餅圖**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*在座標 (50, 50) 處放置寬 400、高 500 的圓餅圖。`ChartType.Pie` 列舉告訴 Aspose 繪製圓餅圖。*

**步驟 3：釋放資源**  
```java
if (pres != null) pres.dispose();
```
*釋放原生資源；完成後務必呼叫 `dispose()`。*

### 功能 2：存取圖表資料工作簿與工作表
#### 概觀
學習如何取得儲存圖表資料的底層工作簿，並遍歷其工作表。

#### 步驟說明

**步驟 1：（重用）初始化新的 Presentation 物件**  
*同功能 1 的步驟 1。*

**步驟 2：（重用）加入圓餅圖**  
*同功能 1 的步驟 2。*

**步驟 3：取得圖表資料工作簿**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*取得與圖表關聯的 `IChartDataWorkbook`。*

**步驟 4：遍歷工作表**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*列印每個工作表的名稱，以驗證資料結構。*

**步驟 5：釋放資源**  
*同功能 1 的步驟 3。*

## 實務應用
- **資料報告：** 自動產生含即時指標的投影片套件，支援商業智慧。  
- **學術簡報：** 無需手動製作圖表，即可視覺化研究成果。  
- **行銷素材：** 即時展示產品績效或調查結果。  

## 效能考量
- 保持投影片與圖表數量在合理範圍；每個都會佔用記憶體。  
- 必須呼叫 `dispose()` 以釋放原生資源。  
- 優化工作簿資料處理——避免將龐大資料集一次載入單一圖表。

## 結論
我們已說明 **aspose slides maven** 如何以程式方式 **add chart to slide**，以及如何操作圖表的資料工作簿。掌握這些基礎，你即可自動化任何需要精美 PowerPoint 輸出的報告工作流程。

### 後續步驟
- 探索圖表樣式選項（顏色、圖例、資料標籤）。  
- 連接外部資料來源（CSV、資料庫）以動態填充圖表。  
- 在同一簡報中結合多種圖表類型，提升敘事豐富度。

## 常見問題

**Q: 如何安裝 Aspose.Slides for Java？**  
A: 使用上方的 Maven 或 Gradle 相依，或從發行頁面下載程式庫。

**Q: Aspose.Slides 的系統需求是什麼？**  
A: JDK 16 或更新；此函式庫與平台無關。

**Q: 除了圓餅圖，我可以加入其他圖表類型嗎？**  
A: 可以，Aspose.Slides 支援長條圖、折線圖、散佈圖等多種圖表。

**Q: 如何有效處理大型簡報？**  
A: 及時釋放物件，限制高解析度影像數量，盡量重用圖表範本。

**Q: 在哪裡可以找到 Aspose.Slides 功能的更多細節？**  
A: 前往 [Aspose 文件](https://reference.aspose.com/slides/java/) 查看完整 API 參考。

**Q: 商業使用是否需要授權？**  
A: 正式環境必須使用有效授權；可使用免費試用版進行評估。

**Q: Maven 套件是否包含所有圖表功能？**  
A: 是的，`aspose-slides` Maven 套件內含完整的圖表引擎。

## 資源
- 文件： [Aspose.Slides Java API 參考](https://reference.aspose.com/slides/java/)
- 下載： [最新發行版](https://releases.aspose.com/slides/java/)
- 購買與試用： [購買頁面](https://purchase.aspose.com/buy)
- 免費試用： [試用下載](https://releases.aspose.com/slides/java/)
- 臨時授權： [申請臨時授權](https://purchase.aspose.com/temporary-license/)
- 支援論壇： [Aspose 社群論壇](https://forum.aspose.com/c/slides/11)

---  

**最後更新：** 2026-01-09  
**測試環境：** Aspose.Slides 25.4 for Java (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
