---
date: '2026-05-23'
description: 了解如何使用 Aspose.Slides for Java 為 PowerPoint 添加圖表、調整圖表軸標籤，以及在 Java 中新增圓餅圖——完整設定、程式碼說明與效能技巧。
keywords:
- add chart to powerpoint
- adjust chart axis labels
- add pie chart java
schemas:
- author: Aspose
  dateModified: '2026-05-23'
  description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  headline: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  type: TechArticle
- description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  name: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  steps:
  - name: Create or Load a Presentation
    text: '`Presentation` is the top‑level class that represents a PowerPoint file
      in memory. > **Pro tip:** Always call `presentation.dispose()` after you finish
      to free native resources.'
  - name: Get the Target Slide
    text: '`ISlide` represents a single slide within a presentation. The first slide
      can be accessed via the `getSlides().get_Item(0)` method. This returns an `ISlide`
      object that acts as a container for shapes, including charts.'
  - name: Add a Clustered Column Chart
    text: '`ChartType` is an enumeration that lists all supported chart kinds. `ChartType.ClusteredColumn`
      creates a classic column chart. You can replace it with any other enum value,
      such as `ChartType.Pie` to add a pie chart.'
  - name: Adjust Chart Axis Labels
    text: '`CategoryAxis` controls the horizontal labels of a chart. The **category
      axis** controls horizontal labels. Setting the label offset improves readability
      when labels are long or rotated. > **Why adjust axis labels?** Proper spacing
      prevents overlapping text, especially on mobile‑sized presentations.'
  - name: Save the Presentation
    text: Define an output path and write the file in PPTX format. Aspose.Slides also
      supports saving to PDF, ODP, and HTML if needed.
  type: HowTo
- questions:
  - answer: Yes – load the file with `new Presentation("existing.pptx")`, modify the
      slides, and save it back.
    question: Can I add charts to an existing PowerPoint file?
  - answer: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)`
      to switch types instantly.
    question: How do I change a chart’s type after it’s been added?
  - answer: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even
      command‑line builds.
    question: Is Aspose.Slides compatible with all major Java IDEs?
  - answer: Using a negative offset or forgetting to enable `setAutomaticScale(true)`
      can cause labels to disappear or overlap.
    question: What are typical pitfalls when configuring axis labels?
  - answer: Limit the number of data points per chart, reuse `Presentation` objects
      where possible, and enable the `setCacheSize` option for large images.
    question: How can I improve rendering speed for massive slide decks?
  type: FAQPage
title: 如何使用 Aspose.Slides for Java 為 PowerPoint 添加圖表：逐步指南
url: /zh-hant/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 為 PowerPoint 添加圖表：一步一步指南

## 介紹
如果您需要以程式方式 **add chart to PowerPoint**，Aspose.Slides for Java 為您提供一種乾淨、免授權的方式，直接將長條圖、折線圖、圓餅圖或任何 150 多種圖表類型嵌入 PPTX 檔案。本教學將逐步示範如何建立簡報、插入圖表、調整座標軸標籤，並儲存結果——全部使用您可以直接複製貼上的簡潔 Java 程式碼。

**您將學會**
- 如何建立並初始化 `Presentation`。
- 如何加入不同類型的圖表，包括在 Java 中的圓餅圖。
- 如何 **adjust chart axis labels** 以獲得最佳可讀性。
- 如何將最終檔案儲存至磁碟。

在開始之前，請確保您的環境符合以下先決條件。

## 快速解答
- **Can I add a chart to an existing PPTX?** 是 – 使用 `new Presentation("path.pptx")` 載入檔案並進行修改。  
- **Which chart types are supported?** 超過 150 種，從群組柱狀圖到 3D 圓餅圖皆支援。  
- **Do I need a license for development?** 免費試用版可使用所有功能；永久授權可移除評估限制。  
- **How do I change the axis label distance?** 設定 `chart.getAxes().getCategoryAxis().setLabelOffset(value)`。  
- **Is Aspose.Slides Java compatible with Maven and Gradle?** 當然支援 – 兩種建置工具皆可使用。

## 「add chart to PowerPoint」是什麼？
*「Add chart to PowerPoint」* 指的是使用 API 以程式方式將視覺化資料系列插入投影片，而非在使用者介面手動設計。此技術可實現自動化報告產生、動態資料更新以及批次處理簡報，且不需在伺服器上安裝 Microsoft Office，十分適合企業級工作流程。

## 為什麼使用 Aspose.Slides for Java？
Aspose.Slides 能在不將整個檔案載入記憶體的情況下處理包含 **最高 10,000 張投影片** 與 **數百 MB** 的簡報，提供 **最高 40 % 更快的渲染速度**，相較於許多競爭對手。它亦支援 **150 多種圖表類型**、**50 多種影像格式**，以及 **完整的 PPTX/ODP 相容性**，成為自動化投影片產生最具彈性的函式庫。

## 先決條件
- **Java Development Kit (JDK)** 8 或更新版本。  
- **Aspose.Slides for Java** – 透過 Maven、Gradle 或直接下載方式加入。  
- 具備基本的 Java 知識，並使用如 IntelliJ IDEA 或 Eclipse 等 IDE。

### 設定 Aspose.Slides for Java

#### Maven 相依性
在您的 `pom.xml` 中加入以下內容：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle 相依性
在您的 `build.gradle` 檔案中加入以下內容：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接下載
或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

開始使用 Aspose.Slides 前，請取得授權：
- **Free Trial** – 完整功能，無時間限制。  
- **Temporary License** – 可透過 [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/) 申請。  
- **Purchase** – 從 [Aspose's purchase page](https://purchase.aspose.com/buy) 取得永久授權。

透過建立 `Presentation` 實例來初始化函式庫。

## 如何使用 Aspose.Slides for Java 為 PowerPoint 添加圖表？

載入或建立 `Presentation` 物件，取得投影片，使用 `addChart` 並指定所需的 `ChartType`，填入資料，最後呼叫 `save`。整個流程只需幾行 Java 程式碼，且可在任何執行 JRE 的平台上運作。

### 步驟 1：建立或載入簡報
`Presentation` 是代表記憶體中 PowerPoint 檔案的頂層類別。

```java
import com.aspose.slides.Presentation;

// Instantiate the Presentation class
tPresentation presentation = new Presentation();

// Dispose of the object once operations are complete
if (presentation != null) presentation.dispose();
```

> **Pro tip:** 完成後務必呼叫 `presentation.dispose()` 釋放原生資源。

### 步驟 2：取得目標投影片
`ISlide` 代表簡報中的單一投影片。  
第一張投影片可透過 `getSlides().get_Item(0)` 方法取得。此方法回傳一個 `ISlide` 物件，作為形狀（包括圖表）的容器。

```java
import com.aspose.slides.ISlide;

ISlide sld = presentation.getSlides().get_Item(0);
```

### 步驟 3：加入群組柱狀圖
`ChartType` 為列舉型別，列出所有支援的圖表類型。  
`ChartType.ClusteredColumn` 會建立傳統的柱狀圖。您可以改用其他列舉值，例如 `ChartType.Pie` 以加入圓餅圖。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = sld.getShapes().addChart(
    ChartType.ClusteredColumn, 20, 20, 500, 300);
```

### 步驟 4：調整圖表座標軸標籤
`CategoryAxis` 控制圖表的水平標籤。  
**類別座標軸** 控制水平標籤。設定標籤偏移量可在標籤過長或旋轉時提升可讀性。

```java
chart.getAxes().getHorizontalAxis().setLabelOffset(500);
```

> **Why adjust axis labels?** 適當的間距可防止文字重疊，尤其在行動裝置尺寸的簡報中更為重要。

### 步驟 5：儲存簡報
定義輸出路徑，並以 PPTX 格式寫入檔案。若有需要，Aspose.Slides 亦支援儲存為 PDF、ODP 與 HTML。

```java
import com.aspose.slides.SaveFormat;

String outputPath = "YOUR_OUTPUT_DIRECTORY/SetCategoryAxisLabelDistance_out.pptx";
```

```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## 如何在 Java 中使用 Aspose.Slides 加入圓餅圖？

使用 `ChartType.Pie` 建立新圖表，為單一系列填入數值，並可選擇啟用突出切片以強調重點。圓餅圖會自動繼承投影片的主題，但您仍可完整自訂顏色、圖例與資料標籤。亦可設定起始角度與突出偏移量，以突顯特定切片。

> **Direct answer (40‑70 words):**  
建立 `Presentation`，取得投影片，呼叫 `slide.getShapes().addChart(ChartType.Pie, x, y, width, height)`，接著使用 `chart.getChartData().getSeries().add(...)` 填入數值。最後呼叫 `presentation.save("pieChart.pptx", SaveFormat.Pptx)`。此程式碼在不到十行內即可建立完整功能的圓餅圖。

## 實務應用
Aspose.Slides for Java 在自動化報告流程中表現卓越：

- **Business Reports** – 即時產生季報財務圖表。  
- **Academic Presentations** – 將 CSV 研究資料轉換為精緻圖表。  
- **Marketing Decks** – 每日自動更新銷售漏斗視覺，免手動編輯。

## 效能考量
處理大型簡報時：

- 將圖表資料陣列維持在 10,000 點以下，以避免記憶體激增。  
- 及時呼叫 `presentation.dispose()`。  
- 使用批次處理（在迴圈中建立 `Presentation` 物件）以有效利用 JVM 的垃圾回收機制。

## 常見問題與解決方案
- **Memory Leak** – 若遺忘呼叫 `dispose()` 會導致原生記憶體累積。  
- **Incorrect Axis Scaling** – 請確認已設定 `chart.getAxes().getValueAxis().setAutomaticScale(true)`。  
- **License Not Found** – 請將授權檔案放置於 classpath，或以程式碼 `License license = new License(); license.setLicense("Aspose.Slides.Java.lic");` 設定。

## 常見問答

**Q: Can I add charts to an existing PowerPoint file?**  
A: 是 – 使用 `new Presentation("existing.pptx")` 載入檔案，修改投影片後再儲存回去。

**Q: How do I change a chart’s type after it’s been added?**  
A: 取得 `Chart` 物件，並設定 `chart.getChartData().setChartType(ChartType.Pie)` 即可立即切換類型。

**Q: Is Aspose.Slides compatible with all major Java IDEs?**  
A: 當然支援 – 可在 IntelliJ IDEA、Eclipse、NetBeans 以及命令列建置中使用。

**Q: What are typical pitfalls when configuring axis labels?**  
A: 使用負值偏移或忘記啟用 `setAutomaticScale(true)` 可能導致標籤消失或重疊。

**Q: How can I improve rendering speed for massive slide decks?**  
A: 限制每個圖表的資料點數量，盡可能重複使用 `Presentation` 物件，並為大型影像啟用 `setCacheSize` 選項。

## 資源
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/slides/java/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-05-23  
**測試環境：** Aspose.Slides for Java 24.11  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [How to Rotate Chart Axis Titles in PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}