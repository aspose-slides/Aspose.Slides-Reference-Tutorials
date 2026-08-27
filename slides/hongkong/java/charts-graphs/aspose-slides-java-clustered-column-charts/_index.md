---
date: '2026-08-27'
description: 了解如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖、加入圖表、設定自動系列顏色，並將簡報儲存為 PPTX。
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: 了解如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖、加入圖表、設定自動系列顏色，並將簡報儲存為 PPTX——提供清晰的逐步說明。
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: 在 Java 中使用 Aspose.Slides 建立叢集柱狀圖
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: 如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖

## 介紹
以程式方式建立叢集柱狀圖可為您節省數小時的手動格式設定，並確保多個簡報之間的一致性。在本教學中，您將學習 **如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖**、**如何加入圖表**、**如何設定顏色**，以及 **如何將簡報儲存為 PPTX**。我們將從安裝函式庫到自訂系列填色與儲存檔案全部說明，讓您能在任何 PowerPoint 簡報中嵌入豐富的資料視覺化。

## 快速回答
- **什麼是處理簡報的主要類別？** `Presentation` 來自 `com.aspose.slides` 套件。  
- **如何加入叢集柱狀圖？** 呼叫 `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`。  
- **系列顏色可以自動設定嗎？** 可以——在每個系列上啟用 `setAutomaticSeriesColor(true)`。  
- **應使用哪種格式儲存檔案？** `SaveFormat.Pptx` 會產生標準的 PowerPoint 檔案。  
- **生產環境是否需要授權？** 試用版可用於開發；商業使用則需正式授權。

## 什麼是叢集柱狀圖？
叢集柱狀圖會在每個類別中將多個資料系列並排顯示，讓您能輕鬆比較各群組的數值。Aspose.Slides 內建支援此圖表類型，並允許您以程式方式控制每個視覺層面。

## 為什麼要使用 Aspose.Slides 建立叢集柱狀圖？
Aspose.Slides 能處理 **超過 50 種輸入與輸出格式**，且可在不將整個檔案載入記憶體的情況下處理 **數百張投影片**。此效能讓您能在伺服器端環境中以最小資源消耗產生大型簡報。

## 前置條件
- **Java Development Kit** 16 或更新版本。  
- **Maven** 或 **Gradle** 用於相依性管理。  
- 具備 Java 語法與物件導向概念的基本認識。  

### 必要的函式庫與相依性
您需要 Aspose.Slides for Java 函式庫（版本 25.4 或更新）。此函式庫完全相容於 JDK 16，並提供豐富的圖表操作 API。

### 環境設定需求
您的 IDE（IntelliJ IDEA、Eclipse、VS Code）必須設定為編譯 Java 16 程式碼，並能解析 Maven/Gradle 相依性。

### 知識前置條件
了解 PowerPoint 投影片結構與基本圖表術語（系列、類別、資料點）將有助於您更快掌握範例。

## 設定 Aspose.Slides for Java
使用以下任一方式將函式庫整合至您的專案中。

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

**直接下載** – 從官方發行頁面取得 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### 取得授權步驟
- **免費試用** – 在 Aspose 網站註冊以取得臨時授權檔案。  
- **臨時授權** – 申請 30 天授權以用於較大的測試套件。  
- **正式授權** – 購買以獲得無限制的生產使用。

**基本初始化與設定**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## 如何加入叢集柱狀圖？
`Presentation` 代表記憶體中的 PowerPoint 檔案。

**直接答案：**  
建立一個 `Presentation` 物件（代表記憶體中的 PowerPoint 檔案），取得第一張投影片，然後呼叫 `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`。此單一呼叫會插入完整功能的叢集柱狀圖，準備好填入資料，並將其放置於投影片上指定的座標。

### 功能 1：建立叢集柱狀圖
`Presentation` 類別代表記憶體中的 PowerPoint 檔案，並提供存取投影片、圖形與圖表物件的功能。

**步驟 1：初始化簡報**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**步驟 2：加入叢集柱狀圖**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**步驟 3：清理資源**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## 如何設定圖表的顏色？
`Series` 代表圖表中資料點的集合。

**直接答案：**  
圖表建立後，透過 `chart.getChartData()` 取得圖表資料，並遍歷每個 `Series` 物件。對每個系列，於其父系列上呼叫 `setAutomaticSeriesColor(true)`。Aspose.Slides 會自動從調色盤為每個系列指派不同且對比度高的顏色，確保視覺清晰，無需手動選色。

### 功能 2：設定自動系列填色
`IChart` 是代表圖表形狀的介面；它提供 `getChartData()` 以操作系列。

**步驟 1：存取圖表並遍歷系列**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**步驟 2：資源管理**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## 如何將簡報儲存為 PPTX？
`save` 會將簡報寫入指定格式的檔案。

**直接答案：**  
指定輸出檔案路徑，例如 `"output/ClusteredColumnChart.pptx"`，然後呼叫 `presentation.save(outputPath, SaveFormat.Pptx)`。`save` 方法會將整個投影片組（包括所有圖形、圖表與資源）序列化為標準 PPTX 檔案，可於 PowerPoint 2010 及之後版本，或大多數線上檢視器開啟。

### 功能 3：將簡報儲存至磁碟
使用 `SaveFormat.Pptx` 儲存會產生與 PowerPoint 2010 及之後版本，以及大多數線上檢視器相容的檔案。

**步驟 1：定義輸出路徑**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**步驟 2：儲存簡報**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## 實務應用
- **財務報告** – 比較各產品線的季度營收。  
- **行銷分析** – 以區域呈現活動績效。  
- **專案管理** – 顯示衝刺速度或團隊間的資源分配。  

## 效能考量
- 及時釋放 `Presentation` 物件以釋放原生資源。  
- 在儲存前使用 `presentation.getSlides().removeUnusedResources()` 以減少檔案大小。  
- 使用輕量集合（例如 `ArrayList<Double>`）填充圖表系列，以降低記憶體使用量。  

## 結論
您現在已了解如何使用 Aspose.Slides for Java **建立叢集柱狀圖**、自動 **設定顏色**，以及 **將簡報儲存為 PPTX**。這些步驟讓您能以程式方式產生資料驅動的投影片，省去重複的手動工作，並確保整個組織的視覺一致性。

**後續步驟：**  
探索進階客製化，例如資料標籤、座標軸格式設定，以及從資料庫或 CSV 檔案動態綁定資料，以進一步豐富您的簡報。

## 常見問題
**Q: 我可以在 Web 應用程式中使用此程式碼嗎？**  
A: 可以——Aspose.Slides 為平台無關，能在任何基於 Java 的伺服器環境（包括 Spring Boot 與 Jakarta EE）中運作。

**Q: 此函式庫支援其他圖表類型嗎？**  
A: 當然支援。`ChartType` 列舉包含 Pie、Bar、Line、Area、Radar 等多種圖表。

**Q: 如果輸出資料夾不存在該怎麼辦？**  
A: 請先建立目錄，或使用 `Files.createDirectories(Paths.get(folder))` 以避免 `FileNotFoundException`。

**Q: 如何處理大型資料集（數千個資料點）？**  
A: 使用串流 API 或批次插入方式填充系列，並考慮停用圖表動畫以提升渲染速度。

**Q: 我可以在哪裡找到更多程式碼範例？**  
A: 前往官方文件與範例倉庫：[Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)。

## 資源
- **文件：** [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **參考：** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **下載：** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **購買：** [Buy a License](https://purchase.aspose.com/buy)  
- **免費試用：** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **臨時授權：** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **支援：** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-08-27  
**測試環境：** Aspose.Slides 25.4 (JDK 16)  
**作者：** Aspose

## 相關教學

- [建立 PowerPoint 圖表 Java – 使用 Aspose.Slides 儲存含圖表的簡報](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [aspose slides maven 相依性：使用 Aspose.Slides for Java 在簡報中加入與設定圖表](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表加入動畫 – 步驟指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}