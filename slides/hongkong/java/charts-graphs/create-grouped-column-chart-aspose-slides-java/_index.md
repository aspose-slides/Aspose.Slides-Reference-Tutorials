---
date: '2026-03-20'
description: 學習如何在 PowerPoint 簡報中加入叢集柱狀圖、客製化 PowerPoint 圖表，並使用 Aspose.Slides for Java
  插入資料系列圖表。
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: 如何在 PowerPoint 中使用 Aspose.Slides for Java 添加叢集柱狀圖
url: /zh-hant/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint 中使用 Aspose.Slides for Java 添加叢集柱狀圖

## 簡介

當您需要 **新增叢集柱狀圖** 到 PowerPoint 簡報時，清晰的視覺效果可以將原始數字轉化為即時可理解的故事。手動在 PowerPoint 中完成此操作往往耗時，尤其是需要以程式方式產生大量投影片時。**Aspose.Slides for Java** 消除了這些阻礙——只需幾行程式碼，即可建立、客製化 PowerPoint 圖表，並插入資料系列圖表。

在本教學中，您將學習如何：
- 使用 Aspose.Slides for Java 初始化新的 PowerPoint 簡報。
- **將圖表新增至投影片** 並將其設定為叢集柱狀圖。
- **建立分組柱狀圖**，透過為類別定義分組層級。
- **插入資料系列圖表**，使您的資料正確顯示。
- 將完成的簡報儲存為 PPTX 檔案。

在深入程式碼之前，先確保您已備妥所有必需的項目。

## 快速答覆
- **主要類別是什麼？** `Presentation` 來自 `com.aspose.slides`。
- **使用哪種圖表類型？** `ChartType.ClusteredColumn`。
- **測試是否需要授權？** 免費試用可使用，但授權可移除評估限制。
- **支援哪個 Java 版本？** JDK 16 或更新版本（範例使用 JDK 16）。
- **如何執行範例？** 加入 Maven/Gradle 相依性，編譯並執行 `main` 方法。

## 什麼是「新增叢集柱狀圖」？

*叢集柱狀圖*（亦稱為分組柱狀圖）會在每個類別中並排顯示多個資料系列，讓您輕鬆比較各組之間的數值。在 PowerPoint 中，此圖表類型非常適合用於季節性銷售、調查結果，或任何需要在同一類別內對比多組資料的情境。

## 為什麼使用 Aspose.Slides 來新增叢集柱狀圖？

- **完整自動化** – 無需手動即可產生數十張投影片。
- **細緻的自訂** – 控制顏色、標籤、分組層級等。
- **跨平台** – 可在任何支援 Java 的作業系統上執行。
- **不需安裝 Office** – 可在伺服器或 CI 流程中產生 PPTX 檔案。

## 先決條件

- **Aspose.Slides for Java** 函式庫（建議使用最新版本）。
- JDK 16 或更新版本。
- Maven 或 Gradle 建置工具（亦可手動加入 JAR）。
- 用於執行 Java 程式碼的 IDE 或文字編輯器。

## 設定 Aspose.Slides for Java

將函式庫加入您的專案，使用以下任一建置腳本。

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

或者，您也可以直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權

在部署至正式環境前，請取得授權：

- **免費試用** – 無需購買即可探索所有功能。
- **臨時授權** – 短期內評估擴充功能。
- **正式授權** – 解鎖無限制使用。請至 [Aspose's purchase page](https://purchase.aspose.com/buy) 取得。

## 實作指南

我們將逐步說明每個步驟，並說明 **如何新增圖表** 以及 **自訂 PowerPoint 圖表**。

### 初始化簡報

首先，建立新的 `Presentation` 物件並取得預設投影片。

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 將圖表新增至投影片

現在，我們使用 `ClusteredColumn` 類型 **將圖表新增至投影片**，並清除任何預設資料。

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### 準備圖表資料工作簿

圖表將資料儲存在內部工作簿中。我們先清除它以重新開始。

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### 加入具分組層級的類別

對類別進行分組可產生 **分組柱狀圖** 效果。每個類別可屬於一個邏輯群組。

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### 為圖表加入資料系列

此處我們 **插入資料系列圖表** 條目，將以獨立柱狀顯示。

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### 儲存含圖表的簡報

最後，將 PPTX 檔寫入磁碟。

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 實務應用

- **商業報告** – 比較各區域的季度營收。
- **學術研究** – 顯示依測試條件分組的實驗結果。
- **專案管理** – 在單一投影片上呈現多個團隊的任務完成率。

## 效能考量

- **記憶體管理** – 使用後釋放大型工作簿。
- **批次操作** – 避免在緊密迴圈中更新圖表；先收集資料，再一次套用。
- **內建最佳化** – Aspose.Slides 提供如 `Presentation.optimize()` 等方法，以處理大型檔案。

## 常見陷阱與技巧

- **陷阱：** 忘記清除既有的系列/類別會導致資料重複。  
  **技巧：** 在填入新資料前，務必呼叫 `clear()`。

- **陷阱：** 使用錯誤的儲存格位址（例如 `"c2"` 而非 `"C2"`）。  
  **技巧：** 儲存格參照不區分大小寫，但為了可讀性請保持一致。

- **技巧：** 使用 `setGroupingItem` 建立有意義的分組標籤；它們會自動顯示於圖例中。

## 常見問與答

**Q1：如何為圖表新增多個系列？**  
A1：重複呼叫 `ch.getChartData().getSeries().add()`，為每個系列提供唯一名稱與資料點。

**Q2：Aspose.Slides 圖表常見的問題是什麼？**  
A2：問題通常來自資料範圍不匹配或工作簿儲存格缺失。請確認每個類別與資料點都有對應的儲存格。

**Q3：我可以在其他程式語言中使用 Aspose.Slides 嗎？**  
A3：可以，Aspose 提供 .NET、C++、Python 等等等效函式庫。

**Q4：如何更新簡報中已存在的圖表？**  
A4：載入簡報後，透過 `slide.getShapes().get_Item(index)` 取得圖表，然後依需求修改其系列或格式。

**Q5：Aspose.Slides 的圖表類型有什麼限制？**  
A5：函式庫支援廣泛的圖表類型，但請隨時參考最新文件，以了解新加入或已棄用的類型。

## 資源

- **文件**：[Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **下載**：[Latest Releases](https://releases.aspose.com/slides/java/)
- **購買**：[Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **免費試用**：[Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **臨時授權**：[Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **支援論壇**：[Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-20  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose