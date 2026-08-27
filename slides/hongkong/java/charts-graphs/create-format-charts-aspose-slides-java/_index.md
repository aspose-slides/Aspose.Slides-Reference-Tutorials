---
date: '2026-08-27'
description: 了解如何在 Java 中使用 Aspose.Slides 為圖表新增格線、格式化坐標軸與標題，並匯出精緻的 PowerPoint 折線圖。
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: 了解如何在 Java 中使用 Aspose.Slides 為圖表新增格線、格式化坐標軸與標題，並匯出精緻的 PowerPoint 折線圖。
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: 如何使用 Aspose.Slides for Java 為圖表新增格線
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: 如何使用 Aspose.Slides for Java 為圖表新增格線
url: /zh-hant/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Slides for Java 中為圖表添加格線

## 介紹
如果您需要以程式方式在 PowerPoint 簡報中**添加格線圖表**，Aspose.Slides for Java 為您提供乾淨且功能完整的 API。無論您是在準備季度業務回顧、學術講座，或是以資料驅動的銷售簡報，都可以產生折線圖、客製化每個視覺元素，並在數秒內儲存結果——完全不需手動開啟 PowerPoint。

## 快速回答
- **什麼函式庫在 Java 中建立圖表？** Aspose.Slides for Java.
- **本指南涵蓋哪種圖表類型？** 帶有標記與格線的折線圖。
- **執行範例是否需要授權？** 免費暫時授權可用於評估；商業授權則需於正式環境使用。
- **可以使用哪種 IDE？** 任何 Java IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。
- **圖表元素如何格式化？** 使用流暢的 API 呼叫設定標題、座標軸、格線、圖例與背景顏色。

## 如何在 Java 中使用 Aspose.Slides 添加格線圖表
載入新的 `Presentation`，插入投影片，新增折線圖，然後在垂直座標軸啟用主要格線——全部程式碼不超過十行。此直接範例展示所需的完整步驟，讓您可以直接複製貼上，即時看到完整格式化的圖表。

### 定義錨點
`Presentation` 是 Aspose.Slides 的核心類別，代表記憶體中的 PowerPoint 檔案；所有投影片層級的操作皆從此物件開始。

## 什麼是折線圖，為何使用 Aspose.Slides？
折線圖以直線連接一系列資料點，讓時間趨勢即時可見。Aspose.Slides 支援**超過 50 種圖表類型**，且每個系列可處理**高達 10,000 個資料點**而不會明顯變慢，為大型資料集提供企業級效能。

### 定義錨點
`Chart` 是 Aspose.Slides 中所有圖表的頂層物件；它儲存系列、類別與格式資訊。

## 前置條件
- **Java Development Kit (JDK) 8+** 已安裝。
- **IDE**（IntelliJ IDEA、Eclipse、NetBeans 等）。
- **Aspose.Slides for Java** 函式庫已透過 Maven 或 Gradle 加入（請參閱下方 *aspose.slides maven 依賴* 章節）。

### Maven 依賴 (aspose.slides maven 依賴)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 依賴
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新的 JAR。

## 取得授權 (套用 aspose 授權)
- 從 [free trial license](https://purchase.aspose.com/temporary-license/) 頁面取得**免費試用授權**以進行測試。
- 從 [Aspose's official site](https://purchase.aspose.com/buy) 購買完整授權，以供正式環境部署。

## 設定 Aspose.Slides for Java
1. 將上述的 Maven 或 Gradle 依賴加入您的專案。
2. 在建立任何 `Presentation` 物件之前**載入**授權檔，以解鎖全部功能。

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## 步驟實作

### 步驟 1：建立輸出目錄（create directory java）
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*為什麼這很重要:* 確保資料夾存在可避免在稍後儲存簡報時拋出 `FileNotFoundException`。

### 步驟 2：新增投影片並插入折線圖
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*說明:* 這會建立一個全新的投影片，並在指定座標放置**帶標記的折線圖**。

### 步驟 3：新增圖表標題（add chart title）
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*提示:* 使用粗體、灰色的標題可讓圖表立即易於辨識。

### 步驟 4：格式化座標軸並添加格線（add grid lines）
#### 垂直座標軸格式化
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*為什麼這很重要:* 清晰的格線與旋轉的標籤可提升可讀性，特別是在資料點密集時。

#### 水平座標軸格式化
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### 步驟 5：自訂圖例（add chart legend）
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### 步驟 6：設定背景顏色（format chart labels）
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### 步驟 7：儲存簡報
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*結果:* 您現在擁有一個包含完整格式化折線圖的 PowerPoint 檔案 (`FormattedChart_out.pptx`)。

## 實務應用（generate line chart powerpoint）
- **商業報告：** 使用清晰的格線顯示季度營收趨勢。
- **學術講座：** 可視化多次實驗的資料。
- **專案提案：** 突顯里程碑進度與預測曲線。
- **行銷分析：** 將活動 ROI 趨勢與競爭者資料並排呈現。
- **儀表板整合：** 將即時分析匯出至 PowerPoint，供利害關係人會議使用。

## 效能考量
- **記憶體管理：** 儲存後呼叫 `presentation.dispose()` 以即時釋放原生資源。
- **大型資料集：** Aspose.Slides 透過串流處理含數千點的圖表，於一般伺服器上將記憶體使用量維持在 100 MB 以下。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **授權未套用** | 在實例化任何 `Presentation` 物件之前**載入**試用或完整授權。 |
| **圖表顯示空白** | 確認投影片至少包含一個資料系列；如有需要，可透過 `chart.getChartData().getSeries().add(...)` 新增系列。 |
| **檔案未儲存** | 確保輸出目錄已存在（見步驟 1）。 |
| **顏色未套用** | 使用 `java.awt.Color` 常數或 `PresetColor` 列舉，以確保顏色正確呈現。 |

## 常見問答

**Q: 我可以建立除折線圖外的其他圖表類型嗎？**  
A: 是的，Aspose.Slides 支援長條圖、圓餅圖、散點圖、雷達圖，以及超過 50 種其他圖表類型。

**Q: 如何為折線圖新增多個資料系列？**  
A: 使用 `chart.getChartData().getSeries().add(...)` 在套用格式之前插入額外的系列。

**Q: 可以將圖表匯出為影像嗎？**  
A: 當然可以。使用 `presentation.save("slide.png", SaveFormat.Png)` 將投影片渲染為 PNG、JPEG 或 SVG。

**Q: 開發階段需要付費授權嗎？**  
A: 免費暫時授權足以進行評估；正式使用則需商業授權。

**Q: 支援哪些 Java 版本？**  
A: 此函式庫支援 JDK 8 至 JDK 22；在加入 Maven/Gradle 依賴時，請選擇相應的 classifier（例如 `jdk16`）。

---

**最後更新：** 2026-08-27  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## 相關教學

- [aspose slides maven 依賴：使用 Aspose.Slides for Java 在簡報中新增與設定圖表](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中新增圖表：一步步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [建立與自訂圖表趨勢線 Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}