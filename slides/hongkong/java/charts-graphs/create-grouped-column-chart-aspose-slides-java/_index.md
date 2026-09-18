---
date: '2026-09-17'
description: 了解如何在 PowerPoint 簡報中添加叢集柱狀圖、客製化 PowerPoint 圖表，以及使用 Aspose.Slides for
  Java 插入資料系列圖表。
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中添加叢集柱狀圖，包括插入資料系列、客製化分組以及將檔案儲存為
  PPTX 的步驟。
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: 在 PowerPoint 中使用 Aspose.Slides 添加叢集柱狀圖
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: 如何在 PowerPoint 中使用 Aspose.Slides for Java 添加叢集柱狀圖
url: /zh-hant/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PowerPoint 中使用 Aspose.Slides for Java 添加群組柱狀圖

## 介紹

當您需要在 PowerPoint 簡報中 **添加群組柱狀圖** 時，清晰的視覺效果可以將原始數據轉化為即時易懂的故事。手動在 PowerPoint 中完成此操作可能非常耗時，尤其是需要以程式方式產生大量投影片時。**Aspose.Slides for Java** 消除這些阻礙——只需幾行程式碼即可建立、客製化 PowerPoint 圖表，並插入資料系列圖表。

在本教學中您將學習如何：

- 使用 Aspose.Slides for Java 初始化新的 PowerPoint 簡報。  
- **將圖表加入投影片** 並將其設定為群組柱狀圖。  
- **建立分組柱狀圖**，透過為類別定義分組層級。  
- **插入資料系列圖表**，使您的資料正確顯示。  
- 將完成的簡報儲存為 PPTX 檔案。

## 快速答案
- **主要類別是什麼？** `Presentation` 來自 `com.aspose.slides`。  
- **使用的圖表類型是？** `ChartType.ClusteredColumn`。  
- **測試是否需要授權？** 免費試用可用，但授權可移除評估限制。  
- **支援的 Java 版本是？** JDK 16 或更新版本（範例使用 JDK 16）。  
- **如何執行範例？** 加入 Maven/Gradle 相依性，編譯並執行 `main` 方法。

## 什麼是「添加群組柱狀圖」？

群組柱狀圖會在每個類別中並排顯示多個資料系列，讓您在單一視覺中比較不同群組的數值。它非常適合用於季銷售、調查結果，或任何需要在同一類別內對比多個資料集的情境。

## 為何使用 Aspose.Slides 添加群組柱狀圖？

您可以自動產生數十張投影片，客製化每個視覺元素，且可在任何支援 Java 的作業系統上執行程式碼——無需安裝 Microsoft Office。Aspose.Slides 支援 **50 多種圖表類型**，且能在不將整個檔案載入記憶體的情況下處理 **最多 500 張投影片** 的簡報，適合大型報告管線。

## 前置條件

- **Aspose.Slides for Java** 函式庫（建議使用最新版本）。  
- JDK 16 或更新版本。  
- Maven 或 Gradle 建置工具（或手動加入 JAR）。  
- 用於執行 Java 程式碼的 IDE 或文字編輯器。

## 設定 Aspose.Slides for Java

使用以下任一建置腳本將函式庫加入您的專案。

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

或者，您也可以直接從 [Aspose.Slides for Java 版本發佈](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權

在部署至正式環境前，請取得授權：

- **免費試用** – 無需購買即可探索所有功能。  
- **臨時授權** – 在短期內評估擴充功能。  
- **完整授權** – 解鎖無限制使用。可從 [Aspose 購買頁面](https://purchase.aspose.com/buy) 取得。

## 如何在 PowerPoint 中使用 Aspose.Slides for Java 添加群組柱狀圖？

載入新的 `Presentation`，新增投影片，插入類型為 `ChartType.ClusteredColumn` 的 `Chart`，以類別與系列填充其內部工作簿，最後將檔案儲存為 PPTX。此流程僅需少量 API 呼叫即可建立完整功能的分組柱狀圖。

### 初始化簡報

`Presentation` 是代表記憶體中 PowerPoint 檔案的類別，允許您以程式方式新增投影片、圖形與圖表。

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 將圖表加入投影片

`ChartType.ClusteredColumn` 告訴 Aspose.Slides 產生分組柱狀圖。

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### 準備圖表資料工作簿

圖表將資料存於內部工作簿。清除工作簿可為自訂資料提供乾淨的起點。

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### 新增具分組層級的類別

對類別進行分組即可產生分組柱狀圖效果。每個類別可屬於一個邏輯群組，該群組會顯示於座標軸標籤中。

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### 為圖表新增資料系列

`Series` 物件代表圖表中的單一柱狀。新增多個系列會在每個類別中產生並排的柱狀。

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### 儲存含圖表的簡報

儲存 `Presentation` 會寫入標準 PPTX 檔案，可在任何 PowerPoint 檢視器中開啟。

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 實務應用

- **商業報告** – 比較各區域的季營收。  
- **學術研究** – 顯示依測試條件分組的實驗結果。  
- **專案管理** – 在單一投影片上視覺化多個團隊的任務完成率。

## 效能考量

- **記憶體管理** – 使用後釋放大型工作簿。  
- **批次操作** – 避免在緊密迴圈中更新圖表；先收集資料，再一次性套用。  
- **內建最佳化** – Aspose.Slides 提供如 `Presentation.optimize()` 等方法，針對大型檔案可將記憶體佔用降低至 **30 %**。

## 常見陷阱與技巧

- **陷阱：** 忘記清除現有的系列/類別可能導致資料重複。  
  **技巧：** 在填入新資料前務必呼叫 `clear()`。  
- **陷阱：** 使用錯誤的儲存格位址（例如 `"c2"` 而非 `"C2"`）。  
  **技巧：** 儲存格參照不區分大小寫，但為了可讀性請保持一致。  
- **技巧：** 使用 `setGroupingItem` 建立有意義的群組標籤；它們會自動顯示於圖表圖例中。

## 常見問答

**Q1: 如何為圖表新增多個系列？**  
A1: 反覆呼叫 `ch.getChartData().getSeries().add()`，為每個系列提供唯一名稱與資料點。

**Q2: Aspose.Slides 圖表常見的問題是什麼？**  
A2: 問題通常源於資料範圍不匹配或缺少工作簿儲存格。請確認每個類別與資料點都有對應的儲存格。

**Q3: 我可以在其他程式語言中使用 Aspose.Slides 嗎？**  
A3: 可以，Aspose 提供 .NET、C++、Python 等等等效函式庫。

**Q4: 如何更新簡報中已存在的圖表？**  
A4: 載入簡報，透過 `slide.getShapes().get_Item(index)` 找到圖表，然後依需求修改其系列或格式。

**Q5: Aspose.Slides 的圖表類型有什麼限制嗎？**  
A5: 此函式庫支援超過 **50 種圖表類型**，且持續新增；請隨時查閱最新文件以取得最新列表。

## 資源

- **文件：** [Aspose.Slides 參考文件](https://reference.aspose.com/slides/java/)  
- **下載：** [最新發佈版](https://releases.aspose.com/slides/java/)  
- **購買：** [購買 Aspose.Slides](https://purchase.aspose.com/buy)  
- **免費試用：** [開始免費試用](https://releases.aspose.com/slides/java/)  
- **臨時授權：** [申請臨時授權](https://purchase.aspose.com/temporary-license/)  
- **支援論壇：** [Aspose 支援](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-09-17  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose

## 相關教學

- [在 Java 中使用 Aspose.Slides 建立圖表指南](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [如何使用 Aspose.Slides for Java 為 PowerPoint 添加圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表添加動畫 – 逐步指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}