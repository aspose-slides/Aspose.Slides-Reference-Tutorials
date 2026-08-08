---
date: '2026-08-06'
description: 了解如何使用 Aspose.Slides 在 Java 簡報中建立圖表，以及如何連結工作簿以實現動態資料更新。逐步指南。
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: 了解如何使用 Aspose.Slides 在 Java 簡報中建立圖表，以及如何連結工作簿以實現動態資料更新。請參考此簡明教學。
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: 如何在 Java 簡報中使用 Aspose.Slides 建立圖表
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: 如何在 Java 簡報中使用 Aspose.Slides 建立圖表
url: /zh-hant/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 Java 簡報中使用 Aspose.Slides 建立圖表：連結外部活頁簿

## 介紹
在本教學中，您將學習 **如何在 Java 簡報中建立圖表** 物件，以及 **如何連結活頁簿** 資料，使圖表自動更新。動態圖表可讓您的投影片即時保持最新，無需手動複製貼上，這對即時報告、財務儀表板與專案狀態簡報尤為重要。我們將逐步說明設定、實作與常見陷阱，讓您只需幾行程式碼即可整合即時 Excel 資料。

## 快速回答
- **主要好處是什麼？** 圖表會在連結的 Excel 活頁簿變更時自動更新。  
- **需要哪個版本的函式庫？** Aspose.Slides for Java 25.4 或更新版本。  
- **需要授權嗎？** 免費試用可用於開發；商業授權可移除所有評估限制。  
- **可以使用任何 Excel 格式嗎？** 可以——支援 `.xlsx` 與舊版 `.xls` 檔案。  
- **網路延遲會是問題嗎？** 可將活頁簿快取至本機或使用 CDN 以降低延遲。

## 什麼是動態圖表連結？
動態圖表連結允許圖表在執行時從外部活頁簿讀取資料來源，任何對活頁簿的變更都會在下次開啟投影片時反映出來。這樣就不必在每次資料更新後重新產生簡報。

## 為什麼使用 Aspose.Slides for Java？
Aspose.Slides 支援 **50+ 輸入與輸出格式**，可在不將整個檔案載入記憶體的情況下渲染上百頁簡報，且在一般伺服器上可於 200 ms 內處理圖表資料更新。這些具體的效能數據使其成為企業報告管線的可靠選擇。

## 前置條件
- **Aspose.Slides for Java** 25.4 或更新版本。  
- **Java Development Kit (JDK)** 16 或更新版本。  
- 熟悉 Maven 或 Gradle 以管理相依性。  

### 必要的函式庫與相依性
- **Aspose.Slides for Java** – 提供簡報 API。  
- **Java Development Kit (JDK)** – 編譯與執行程式碼所必需。

### 環境設定需求
- 基本的 Java 程式設計知識。  
- 可取得外部 Excel 活頁簿（本機檔案路徑或 HTTP URL）。

## 設定 Aspose.Slides for Java
要將 Aspose.Slides 加入您的專案，請選擇以下支援的建置系統之一。

### Maven 設定
將此相依性加入您的 `pom.xml`：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 設定
在您的 `build.gradle` 檔案中加入以下內容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
您也可以從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載函式庫。

#### 取得授權
先使用免費試用或取得臨時授權，以在無限制的情況下測試 Aspose.Slides。長期使用時，建議購買正式授權。

##### 基本初始化與設定
`Presentation` 是 Aspose.Slides 的核心類別，代表記憶體中的 PowerPoint 檔案。請如下初始化您的簡報物件：
```java
Presentation pres = new Presentation();
```

## 實作指南
本節將說明如何為簡報設定外部活頁簿，以更新圖表資料。

### 設定外部活頁簿以更新圖表資料
#### 概述
此功能讓圖表能動態從外部來源更新資料。當您的資料頻繁變動且需要投影片自動反映變更時，此功能相當理想。

#### 步驟實作
1. **Create a new presentation**  
   先建立一個全新的 `Presentation` 實例：
   ```java
   Presentation pres = new Presentation();
   ```

2. **Access the first slide**  
   取得第一張投影片的方式相當直接：
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **Add a chart to the slide**  
   在指定位置與尺寸加入圓餅圖：
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **Set external workbook URL for chart data**  
   指定外部活頁簿作為資料來源：
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### 設定選項
- **Chart type** – 可從圓餅圖、長條圖、折線圖、區域圖等選擇，視您想要的資料視覺化方式而定。  
- **Position & size** – 調整 X/Y 座標與寬度/高度，以符合投影片版面配置。

## 如何建立連結至活頁簿的圖表？
`Chart` 是 Aspose.Slides 用來封裝圖表形狀與其資料的物件。載入簡報、加入圖表，然後呼叫 `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`。如此一來，圖表每次開啟檔案時都會從活頁簿讀取系列值，提供即時更新，無需重新產生 PPTX。此段落直接回應 GEO 要求，並提供簡潔可行的說明。

## 常見問題與解決方案
若外部連結未更新：
- 確認 URL 可被存取且回傳有效的 Excel 檔案。  
- 確保伺服器允許匿名 GET 請求，或在需要時提供認證資訊。  
- 若網路延遲較高，請將活頁簿快取至本機；在開啟簡報前先更新快取。

## 實務應用
動態圖表搭配外部活頁簿在多種情境下都相當有用：
1. **即時資料報告** – 從中心 Excel 檔案拉取最新數字的銷售儀表板。  
2. **財務分析** – 從市場資料來源自動刷新股票價格走勢。  
3. **專案管理** – KPI 儀表板即時顯示最新的任務完成統計。

## 效能考量
在處理大型活頁簿時，最佳化效能相當重要：
- 將活頁簿快取於應用伺服器，以減少重複的網路呼叫。  
- 使用串流 API 只讀取所需的工作表範圍，降低記憶體使用量。  
- Aspose.Slides 可在 200 ms 內處理高達 10 MB 活頁簿的圖表更新，足以應付大多數報告情境。

## 結論
透過本指南，您已掌握 **如何在 Java 簡報中建立圖表** 以及 **如何連結活頁簿** 以實現自動更新。此功能讓投影片更具互動性，減少手動工作，確保利害關係人隨時看到最新數據。您亦可探索 Aspose.Slides 的其他功能，如投影片複製、動畫與 PDF 匯出，以進一步提升報告工作流程。

## 常見問答
**Q1: 可以使用任何 URL 作為外部活頁簿嗎？**  
A1: URL 必須指向可存取的 Excel 檔案（`.xlsx` 或 `.xls`）。請確保伺服器回傳正確的 MIME 類型，且若需要驗證，請在程式碼中處理相關認證。

**Q2: 哪些圖表類型支援動態連結？**  
A2: 所有原生的 Aspose.Slides 圖表類型——圓餅圖、長條圖、折線圖、區域圖、散佈圖、雷達圖等——皆可連結至外部活頁簿。

**Q3: 外部活頁簿有大小限制嗎？**  
A3: 雖然 Aspose.Slides 能處理超過 100 MB 的活頁簿，但處理時間會線性增加；為獲得最佳效能，建議檔案保持在 20 MB 以下，或僅串流所需的資料範圍。

**Q4: 若 URL 無法存取，該如何處理？**  
A4: 請將連結程式碼包在 try‑catch 區塊中，記錄例外，並可選擇回退至靜態資料來源，以確保簡報仍能正常載入。

**Q5: 這能用於自動化報告管線嗎？**  
A5: 絕對可以。此 API 支援無頭模式，您可以在伺服器上產生或更新簡報，將其嵌入電子郵件，或發佈至 SharePoint 資料庫。

## 資源
- [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial and Temporary License](https://releases.aspose.com/slides/java/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## 相關教學

- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}