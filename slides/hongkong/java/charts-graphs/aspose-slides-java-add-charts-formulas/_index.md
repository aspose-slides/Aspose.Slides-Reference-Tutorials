---
date: '2026-08-21'
description: 了解如何使用 Aspose.Slides for Java 建立 PowerPoint 圖表、打造動態 clustered column
  charts，並在自動化簡報中計算 chart formulas。
keywords:
- create powerpoint chart java
- Aspose.Slides Java
- dynamic PowerPoint charts
lastmod: '2026-08-21'
og_description: 使用 Aspose.Slides for Java 建立 PowerPoint 圖表（Java）。打造動態 clustered column
  charts，套用公式，並高效自動化簡報。
og_image_alt: Screenshot of a Java-generated PowerPoint chart using Aspose.Slides
og_title: 使用 Aspose.Slides 建立 PowerPoint 圖表（Java） – 快速指南
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create PowerPoint chart java using Aspose.Slides for Java,
    build dynamic clustered column charts, and calculate chart formulas in automated
    presentations.
  headline: How to create PowerPoint chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create PowerPoint chart java using Aspose.Slides for Java,
    build dynamic clustered column charts, and calculate chart formulas in automated
    presentations.
  name: How to create PowerPoint chart in Java with Aspose.Slides
  steps:
  - name: initialize the presentation
    text: The `Presentation` class represents a PowerPoint file in memory, allowing
      you to add slides, shapes, and charts.
  - name: access the first slide
    text: The `ISlide` interface represents an individual slide within a presentation.
  - name: add a clustered column chart
    text: The `IChart` interface defines chart objects that can be added to a slide.
      **Parameters explained** - `ChartType` – specifies the type of chart (here,
      a clustered column chart). - Coordinates (`x`, `y`) – position on the slide.
      - Width and height – dimensions of the chart.
  - name: access the chart data workbook
    text: The `IWorkbook` object stores the chart's underlying data table.
  - name: setting formulas (calculate chart formulas)
    text: '**Formula in cell B2** **R1C1‑style formula in cell C2** These formulas
      let the chart update automatically whenever the underlying data changes.'
  - name: calculate all formulas
    text: The `calculateFormulas()` method evaluates all formulas in the workbook.
  - name: save your presentation
    text: The `save` method writes the presentation to a file. Make sure to replace
      `YOUR_OUTPUT_DIRECTORY` with an actual path where you want to store the file.
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for compatibility and performance reasons.
    question: What is the minimum JDK version required for Aspose.Slides?
  - answer: Yes, but with limitations on functionality. Acquire a temporary or full
      license for unrestricted use.
    question: Can I use Aspose.Slides without a license?
  - answer: Use try‑finally blocks to ensure resources are released, as shown in the
      basic initialization example.
    question: How do I handle exceptions when using Aspose.Slides?
  - answer: Absolutely—create and position each chart individually within the slide’s
      bounds.
    question: Can I add multiple charts to the same slide?
  - answer: Yes—directly manipulate the chart data workbook and recalculate formulas.
    question: Is it possible to update chart data without regenerating the entire
      presentation?
  type: FAQPage
tags:
- create powerpoint chart
- Aspose.Slides
- Java presentation automation
title: 如何使用 Aspose.Slides 在 Java 中建立 PowerPoint 圖表
url: /zh-hant/java/charts-graphs/aspose-slides-java-add-charts-formulas/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 精通 Aspose.Slides Java：在 PowerPoint 簡報中新增圖表與公式

## 介紹

在本指南中，您將學習如何使用 Aspose.Slides for Java **create powerpoint chart java**，自動產生動態群組柱狀圖，並套用計算公式——全部不需開啟 PowerPoint 介面。當需要快速傳達複雜資料時，製作引人入勝的簡報至關重要，而程式化的圖表建立可讓您即時將最新資料嵌入投影片中。

**您將學習**
- 設定 Aspose.Slides for Java
- 建立 PowerPoint 簡報並插入圖表
- 使用公式存取與修改圖表資料
- 計算圖表公式並儲存簡報

讓我們先檢視先決條件！

## 快速解答
- **主要目標是什麼？** 使用 Aspose.Slides for Java 自動建立 PowerPoint 圖表。  
- **示範的圖表類型為何？** 群組柱狀圖。  
- **公式可以計算嗎？** 可以——使用 `calculateFormulas()` 來評估動態 PowerPoint 圖表。  
- **建議使用哪種建置工具？** 用於 Aspose Slides 整合的 Maven（或 Gradle）。  
- **需要授權嗎？** 免費試用可用於測試；完整授權可移除評估限制。

## 什麼是使用 Aspose.Slides “在 PowerPoint 中新增圖表”？

Aspose.Slides for Java 讓您能以程式方式產生與修改 PowerPoint 檔案，包括插入圖表，且無需開啟 PowerPoint 介面。此功能可直接從 Java 程式碼自動化報告與資料驅動的投影片。您可以定義圖表類型、設定資料範圍，並套用公式，非常適合財務、銷售與分析簡報。

## 為何使用群組柱狀圖？

群組柱狀圖可讓您將多個資料系列並排比較，使趨勢與差異即時顯現。每張圖表最多支援 20 個系列，並以高解析度圖形呈現列印品質的投影片。由於每個系列依類別分組，利害關係人能一眼看出各區域、產品或時間段的績效差距。

## 如何使用 Aspose.Slides for Java 建立 PowerPoint 圖表

若要使用 Aspose.Slides for Java 建立 PowerPoint 圖表，您需先設定函式庫，接著初始化簡報、加入投影片、插入群組柱狀圖、填入資料工作簿、套用所需公式、重新計算，最後儲存檔案。此工作流程可確保圖表在產生簡報前反映最新的資料與公式。

### 先決條件

- **Aspose.Slides for Java 函式庫** – 版本 25.4 或更新，支援 **50+ 圖表類型**，且可在不將整個檔案載入記憶體的情況下處理含 **500+ 投影片** 的簡報。  
- **Java Development Kit (JDK)** – 必須在系統上安裝並設定 JDK 16 或更高版本。  
- **開發環境** – IntelliJ IDEA、Eclipse 或任何相容 Java 的 IDE。  

具備 Java 類別、方法與例外處理的基本概念是必要的。若您對這些主題尚未熟悉，建議先閱讀 Java 入門教學。

#### 設定 Aspose.Slides for Java

#### Maven 相依性（aspose slides 的 maven）

將以下相依性加入您的 `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle 相依性

若使用 Gradle，請在 `build.gradle` 中加入以下內容：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接下載

或者，從 [Aspose Releases](https://releases.aspose.com/slides/java/) 下載最新的 Aspose.Slides for Java。

#### 取得授權
- **免費試用** – 先使用免費試用版探索功能。  
- **臨時授權** – 取得臨時授權以延長測試時間 [temporary license request](https://purchase.aspose.com/temporary-license/)。  
- **購買** – 若您認為此工具有價值，請考慮購買完整授權。

### 基本初始化

設定完成後，初始化您的 Aspose.Slides 環境：

```java
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## 實作指南

本節分為多個步驟，協助您清楚了解每個部分。

### 步驟 1：初始化簡報

`Presentation` 類別代表記憶體中的 PowerPoint 檔案，允許您新增投影片、圖形與圖表。

```java
Presentation presentation = new Presentation();
```

### 步驟 2：存取第一張投影片

`ISlide` 介面代表簡報中的單一投影片。  

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

### 步驟 3：新增群組柱狀圖

`IChart` 介面定義可加入投影片的圖表物件。  

```java
IChart chart = slide.getShapes().addChart(
    ChartType.ClusteredColumn, 
    150, 150, 
    500, 300
);
```
**參數說明**
- `ChartType` – 指定圖表類型（此處為群組柱狀圖）。  
- 座標 (`x`, `y`) – 投影片上的位置。  
- 寬度與高度 – 圖表的尺寸。

### 步驟 4：存取圖表資料工作簿

`IWorkbook` 物件儲存圖表的底層資料表。

```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```

### 步驟 5：設定公式（計算圖表公式）

**B2 儲存格的公式**  

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

**C2 儲存格的 R1C1 風格公式**  

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

這些公式可讓圖表在底層資料變更時自動更新。

### 步驟 6：計算所有公式

`calculateFormulas()` 方法會評估工作簿中的所有公式。

```java
workbook.calculateFormulas();
```

### 步驟 7：儲存簡報

`save` 方法將簡報寫入檔案。

```java
String outpptxFile = "YOUR_OUTPUT_DIRECTORY" + File.separator + "ChartDataCell_Formulas_out.pptx";
presentation.save(outpptxFile, SaveFormat.Pptx);
```

請確保將 `YOUR_OUTPUT_DIRECTORY` 替換為您欲儲存檔案的實際路徑。

## 實務應用

- **財務報告** – 自動化月度或季度的資產負債表與損益表圖表。  
- **教育** – 產生以資料為基礎的投影片，用於教學統計或科學結果。  
- **商業分析** – 將即時 KPI 儀表板嵌入簡報，隨來源資料變更自動更新。  

將 Aspose.Slides 整合至現有工作流程，可簡化簡報製作，尤其在處理需要頻繁更新的大型資料集時。

## 效能考量

透過以下方式優化效能：
- 及時釋放 `Presentation` 物件以釋放原生資源。  
- 若需次秒級處理時間，請限制單張投影片上的圖表複雜度。  
- 使用批次操作一次新增或更新多個圖表，可在大型簡報上減少高達 30 % 的開銷。  

遵循這些最佳實踐，可確保即使在資源受限的環境中也能順暢運作。

## 結論

現在，您應已具備使用 Aspose.Slides for Java **create PowerPoint chart java**、建立動態簡報以及運用計算圖表公式的能力。這個強大的函式庫可節省時間並提升資料視覺化的品質。透過深入閱讀 [Aspose 文件說明](https://reference.aspose.com/slides/java/) 探索更多功能，並考慮使用其他 Aspose.Slides 功能擴充您的專案。

### 後續步驟

- 嘗試不同的圖表類型與版面配置。  
- 將 Aspose.Slides 功能整合至更大型的 Java 應用程式。  
- 探索 Aspose 的其他函式庫，以提升跨格式的文件處理。

## 常見問題

**Q: Aspose.Slides 所需的最低 JDK 版本為何？**  
A: 為了相容性與效能，建議使用 JDK 16 或更高版本。

**Q: 可以在沒有授權的情況下使用 Aspose.Slides 嗎？**  
A: 可以，但功能會受限。取得臨時或完整授權即可無限制使用。

**Q: 使用 Aspose.Slides 時如何處理例外？**  
A: 如基本初始化範例所示，使用 try‑finally 區塊確保資源釋放。

**Q: 可以在同一張投影片上加入多個圖表嗎？**  
A: 當然可以——在投影片範圍內分別建立並定位每個圖表。

**Q: 是否能在不重新產生整個簡報的情況下更新圖表資料？**  
A: 可以——直接操作圖表資料工作簿並重新計算公式。

透過以下連結探索更多資源：
- [Aspose 文件說明](https://reference.aspose.com/slides/java/)
- [下載 Aspose.Slides](https://releases.aspose.com/slides/java/)
- [購買授權](https://purchase.aspose.com/buy)
- [免費試用](https://releases.aspose.com/slides/java/)
- [臨時授權申請](https://purchase.aspose.com/temporary-license/)
- [支援論壇](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-08-21  
**測試環境：** Aspose.Slides 25.4 (JDK 16)  
**作者：** Aspose  

{{< blocks/products/pf/backtop-button >}}

## 相關教學

- [aspose slides maven 相依性：使用 Aspose.Slides for Java 在簡報中新增與設定圖表](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [使用 Aspose.Slides 的 Java 圖表建立指南](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [使用 Aspose.Slides 的 Java 建立 PowerPoint 圖表](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}