---
date: '2026-07-27'
description: 了解如何使用 Aspose.Slides 建立 Java 環形圖 – 快速指南，教您設定函式庫、加入可自訂的環形圖、調整孔徑大小，並儲存簡報。
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: 了解如何使用 Aspose.Slides 建立 Java 環形圖 – 快速指南，教您設定函式庫、加入可自訂的環形圖、調整孔徑大小，並儲存簡報。
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: 使用 Aspose.Slides 逐步建立 Java 環形圖
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: 使用 Aspose.Slides 逐步建立 Java 環形圖
url: /zh-hant/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Presentations 在 Java 中建立環形圖

## 介紹
建立視覺吸引力的簡報對於有效傳遞資訊至關重要。**Create doughnut chart java** 是在需要以現代外觀說明比例資料時的常見需求。在本教學中，您將學習如何設定 Aspose.Slides for Java、建立環形圖、客製化其孔徑大小與顏色，最後儲存簡報檔案。完成後，您將擁有一個可重複使用的模式，能夠直接嵌入任何自動產生 PowerPoint 投影片的 Java 專案中。

**您將學到：**
- 設定 Aspose.Slides for Java
- 在簡報中建立與設定環形圖
- 調整圖表美觀，例如孔徑大小
- 將簡報與新圖表一起儲存

讓我們先設定環境！

## 快速解答
- **哪個函式庫可以建立 doughnut chart java？** Aspose.Slides for Java.
- **建立基本環形圖需要多少行程式碼？** 大約 8–10 行（在建立 Presentation 之後）。
- **我可以調整孔徑大小嗎？** 可以，`setHoleSize(double)` 方法接受 0 % 到 100 % 的值。
- **支援哪些輸出格式？** PPTX、PDF、XPS、PNG、JPEG 以及其他多種格式（總計超過 50 種）。
- **生產環境需要授權嗎？** 需要商業授權才能無限制使用；免費試用版可用於評估。

## 什麼是 Aspose.Slides for Java？
**Aspose.Slides for Java** 是一套完整管理的 API，讓開發人員能在不依賴 Microsoft Office 的情況下建立、修改、轉換與呈現 PowerPoint 檔案。它支援超過 50 種檔案格式，且即使面對含有數千張投影片的簡報，也能保持低記憶體使用量。

## 為什麼在簡報中使用環形圖？
環形圖可顯示部分與整體的關係，同時在中心留下空間放置標籤或圖片。Aspose.Slides 在一般 2.5 GHz 伺服器上可每分鐘渲染高達 **500 張投影片** 的環形圖，且能在不將整個檔案載入記憶體的情況下處理 **數百頁的簡報**，因此非常適合大型報表解決方案。

## 前置條件
開始之前，請確保已滿足以下前置條件：

### 必要的函式庫與版本
若要使用 Aspose.Slides for Java，請透過 Maven、Gradle 或直接下載的方式將其加入專案。

#### 環境設定需求
- 可正常運作的 Java Development Kit（JDK），建議使用 8 版或以上。
- 整合開發環境（IDE），如 IntelliJ IDEA 或 Eclipse。

### 知識前置條件
熟悉 Java 與基本程式概念會很有幫助。具備 Maven 或 Gradle 的基礎知識能讓設定流程更順暢。

## 設定 Aspose.Slides for Java
將 Aspose.Slides 整合至專案中有多種方式：

**Maven：**  
將以下相依性加入 `pom.xml` 檔案：  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**  
在 `build.gradle` 檔案中加入以下內容：  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載：**  
或者，從 [Aspose.Slides for Java 版本](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權
- **免費試用：** 先下載試用版以探索 Aspose.Slides 功能。  
- **臨時授權：** 取得臨時授權以獲得無限制的擴充功能。  
- **購買授權：** 若需持續使用，必須購買授權。

設定好函式庫與環境後，讓我們繼續實作環形圖。

## 如何在 Java 中建立環形圖？
載入新的 `Presentation` 物件，於投影片中加入環形圖、設定孔徑大小，並儲存檔案——只需幾個簡單的 API 呼叫。此方法讓您完整掌控圖表資料、外觀與匯出格式，且不需在伺服器上安裝 Microsoft PowerPoint。

### 初始化 Presentation 物件
`Presentation` 類別是 Aspose.Slides 的最高層級物件，代表記憶體中的 PowerPoint 檔案。  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
此步驟會建立一個空白簡報，您可以在其中加入投影片、圖形與圖表。

### 在投影片中加入環形圖
`ISlide` 為單一投影片的介面；您可以取得第一張投影片或新增一張。  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
`addChart` 方法會建立環形圖；參數定義其在投影片上的位置 (X, Y) 與大小 (寬度, 高度)。

### 設定環形圖孔徑大小
`Chart` 提供 `setHoleSize(double)` 以控制內部半徑，比例為圖表半徑的百分比。  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
將孔徑大小設定為 90 % 會使圖表看起來幾乎是完整的圓形，適合想強調外圍區段時使用。

### 儲存簡報
`presentation.save(String, SaveFormat)` 會將檔案以指定格式寫入磁碟。  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
此範例將結果儲存為 `DoughnutHoleSize_out.pptx`，您也可以選擇 PDF、PNG 或其他 50 多種支援的格式。

### 清理資源
呼叫 `presentation.dispose()` 會釋放原生資源，防止記憶體洩漏，對長時間執行的伺服器應用程式尤為重要。  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```

## 實務應用
環形圖用途廣泛，以下是一些適用情境：
1. **預算分配：** 顯示預算在各部門之間的分配情況。  
2. **調查結果：** 以視覺方式呈現多選題的回覆。  
3. **網站流量來源：** 顯示來自不同渠道（自然搜尋、付費、推薦等）的流量比例。

## 效能考量
使用 Aspose.Slides 時，請考慮以下效能最佳化建議：
- 在完成後立即釋放 `Presentation` 物件，以釋放原生記憶體。  
- 對於大型資料集，使用串流（`FileInputStream`、`ByteArrayOutputStream`）以避免將整個檔案載入記憶體。  
- 在迴圈中產生多張投影片時，重複使用圖表物件以減少物件建立的開銷。

## 常見問題與解決方案
- **儲存時錯誤：** 請確認輸出目錄已存在且應用程式具有寫入權限。  
- **圖表資料遺失：** 請在呼叫 `setHoleSize` 前確保已填充圖表的 `ChartData` 集合。  
- **記憶體激增：** 對於包含數千張投影片的簡報，請將 `Presentation.setSlideSize` 設為較小尺寸，並及時釋放中間投影片。

## 常見問答

**Q: 我可以調整環形圖各區段的顏色嗎？**  
A: 可以。使用 `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`，然後指定所需的 RGB 顏色。

**Q: 我該如何為圖表加入資料標籤？**  
A: 呼叫 `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` 即可在每個區段內顯示數值。

**Q: 能否將圖表儲存為 PPTX 以外的格式？**  
A: 當然可以。Aspose.Slides 支援 PDF、XPS、PNG、JPEG、TIFF 以及其他多種格式——總計超過 50 種。

**Q: 若在載入大型簡報時遇到例外情況，該怎麼辦？**  
A: 使用接受串流的 `Presentation` 建構子，並啟用 `loadOptions.setLoadFormat(LoadFormat.Pptx)` 以串流方式讀取檔案，降低記憶體使用量。

**Q: 我可以使用即時資料來源自動更新圖表嗎？**  
A: 可以。從資料庫或 REST API 取得資料，更新 `ChartData` 集合，然後在儲存簡報前呼叫 `chart.refresh()`。

## 資源
- **文件說明：** 在 [Aspose.Slides for Java](https://reference.aspose.com/slides/java/) 探索詳細的 API 參考。  
- **下載：** 從 [Aspose.Slides 版本](https://releases.aspose.com/slides/java/) 取得最新函式庫版本。  
- **購買：** 前往 [Aspose 購買](https://purchase.aspose.com/buy) 取得完整授權。  
- **免費試用：** 在下載頁面提供的免費試用版體驗 Aspose.Slides。  
- **臨時授權：** 取得臨時授權以進行無限制的延伸測試。  
- **支援：** 如有問題，請前往 [Aspose 論壇](https://forum.aspose.com/c/slides/11) 尋求協助。

---

**最後更新：** 2026-07-27  
**測試環境：** Aspose.Slides for Java 24.12  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Slides for Java 在 PowerPoint 中加入圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [如何使用 Aspose.Slides 在 Java 中建立圖表：完整指南](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}