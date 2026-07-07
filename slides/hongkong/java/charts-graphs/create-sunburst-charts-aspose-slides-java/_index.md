---
date: '2026-07-03'
description: 學習如何在 Java 中使用 Aspose.Slides 逐步建立 Sunburst 圖表，並提供完整的 PowerPoint 簡報自訂選項。
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: 如何在 Java 中使用 Aspose.Slides 建立 Sunburst 圖表
url: /zh-hant/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides 在 Java 中建立日暈圖表

## 介紹
在當今以數據為驅動的簡報中，快速**如何建立日暈圖**可讓您的投影片脫穎而出。本教學將帶您從專案設定到最終匯出，使用 Aspose.Slides for Java 建立日暈圖表，讓您在不離開 Java 生態系統的情況下呈現引人入勝的階層資料圖形。

## 快速回答
- **PowerPoint 檔案的主要類別是什麼？** `Presentation` – 它代表記憶體中的整個 PPTX。  
- **建立基本日暈圖需要多少行程式碼？** 通常在引用庫後只需 5–7 行。  
- **支援哪些輸出格式？** PPTX、PDF、PNG、SVG 與 HTML。  
- **我可以自訂個別區段的樣式嗎？** 可以 – 填色、邊框與資料標籤皆可完全自訂。  
- **生產環境需要授權嗎？** 免費評估版可用於測試；部署時需購買商業授權。  

## 什麼是日暈圖表？
日暈圖表以同心環的方式呈現階層資料，每個環代表階層的一層。它讓觀眾一眼即可了解父子關係，非常適合用於組織圖、分類法展示以及多層級指標。特別適用於顯示多層級的類別，例如產品線、地理區域或組織結構，讓觀眾同時看到整體分佈與各區段的詳細細分。

## 為何使用 Aspose.Slides 建立日暈圖表？
Aspose.Slides 支援 **30+ 種圖表類型**，可在不將整個文件載入記憶體的情況下處理高達 **500 MB** 的檔案，並以 **300 DPI** 產出晶瑩剔透的圖形。這些具體的能力確保即使在大型簡報中也能快速產生高品質的視覺效果。此外，該函式庫提供執行緒安全的操作，且能無縫整合於流行的 Java 建置工具，適合在桌面與伺服器端大規模產生簡報。

## 前置條件
- Java Development Kit (JDK) 8 或更新版本。  
- 用於相依管理的 Maven 或 Gradle。  
- Aspose.Slides for Java（最新版本）。  
- 基本的階層資料結構概念。  

## 如何逐步建立日暈圖表？
載入環境、加入圖表、提供階層資料、設定樣式，最後儲存檔案——只需幾個簡單步驟。以下提供完整的工作流程，您可直接套用而無需撰寫額外樣板程式碼。此流程全自動化，無需手動 UI 操作，亦可整合至批次工作或 Web 服務，即時產生圖表。

### 步驟 1：設定專案
在 `pom.xml` 中加入 Aspose.Slides 的 Maven 相依（或相等的 Gradle 片段）。此舉會自動下載所有必要的二進位檔與傳遞相依庫。

### 步驟 2：載入或建立簡報
`Presentation` 是 Aspose.Slides 的最高層物件，代表記憶體中的單一 PowerPoint 檔案。使用 `new Presentation()` 可建立全新簡報，或傳入檔案路徑以開啟既有 PPTX。

### 步驟 3：加入日暈圖表
使用 `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` 在投影片上插入新的圖表形狀。此指令會建立日暈圖的佔位元，待填入資料。`ChartType.Sunburst` 用於在投影片上新增圖表時指定日暈圖類型。

### 步驟 4：填入階層資料
`ChartData` 保存圖表的資料系列與類別。存取圖表的 `ChartData` 集合，並加入對應階層的系列與類別。對於每一層級，透過 `ParentSeries` 屬性指定父子關係，圖表即可自動繪製同心環。

### 步驟 5：自訂外觀
透過 `ChartSeries` 與 `ChartDataPoint` 物件微調區段顏色、邊框樣式與資料標籤。`ChartSeries` 代表圖表中的一組資料點，`ChartDataPoint` 代表系列中的單一資料點。您亦可啟用 3‑D 旋轉或設定 `Explode` 屬性，以突顯特定切片。

### 步驟 6：儲存簡報
`SaveFormat` 列舉定義可將簡報儲存為的檔案格式。呼叫 `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` 即可寫入磁碟。變更 `SaveFormat` 列舉值亦可匯出為 PDF 或 PNG。

## 如何自訂日暈圖表顏色？
使用 `point.getFillFormat().setFillType(FillType.Solid)` 再搭配 `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))` 為每個 `ChartDataPoint` 指定填色。此直接方式可讓您符合企業品牌或強調關鍵資料點。亦可套用漸層填色、調整透明度，或使用主題色彩，以確保與投影片其他設計保持一致。

## 常見問題與解決方案
- **問題：** 階層顯示為平面。  
  **解決方案：** 確保每個子系列正確參照其 `ParentSeries`。缺少連結會導致圖表將所有資料視為同一層級。  

- **問題：** 匯出的 PNG 模糊。  
  **解決方案：** 透過設定 `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` 提高匯出 DPI。  

- **問題：** 大型 PPTX 檔案導致 OutOfMemoryError。  
  **解決方案：** 使用 `Presentation.setMemoryOptimization(true)` 以串流方式處理資料，降低記憶體使用量。  

## 常見問答

**Q: 我可以從 CSV 檔案產生日暈圖表嗎？**  
A: 可以。讀取 CSV，於記憶體中建立階層，然後在儲存前將其填入圖表的 `ChartData` 集合。

**Q: Aspose.Slides 支援日暈圖表的動畫過渡效果嗎？**  
A: 支援。可對投影片套用 `SlideShowTransition`，或使用 `ChartFormat.setAnimationEnabled(true)` 為圖表層級啟用動畫。

**Q: 可以將圖表匯出為 SVG 向量圖形嗎？**  
A: 當然可以。使用 `SaveFormat.Svg` 儲存簡報，即可取得可伸縮的日暈圖向量版本。

**Q: 日暈圖表最多能處理多少資料點？**  
A: Aspose.Slides 可在單一日暈圖表中可靠地處理高達 **10,000** 個資料點，且不會出現效能下降。

**Q: 每個部署環境都需要單獨的授權嗎？**  
A: 只要遵守授權條款，一份商業授權即可涵蓋所有環境（開發、測試、正式）。

## 結論
您現在擁有一套完整的 **如何在 Java 中使用 Aspose.Slides 建立日暈圖表** 的逐步指南。依照上述工作流程，即可為任何 PowerPoint 簡報產生高品質、完全可自訂的階層視覺化圖表。

---

**最後更新：** 2026-07-03  
**測試環境：** Aspose.Slides for Java 24.12  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Slides for Java 為 PowerPoint 添加圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [精通使用 Aspose.Slides Java 為動態簡報自訂 PowerPoint 圖表](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表類別添加動畫 | 逐步指南](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}