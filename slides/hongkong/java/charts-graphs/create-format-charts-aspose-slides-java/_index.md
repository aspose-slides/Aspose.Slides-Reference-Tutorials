---
date: '2026-03-07'
description: 學習如何使用 Aspose.Slides 在 Java 中建立折線圖、添加圖表標題、加入格線、格式化圖表標籤，並儲存專業簡報。
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: 如何使用 Aspose.Slides 在 Java 中建立折線圖 – 完整指南
url: /zh-hant/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides 在 Java 中建立折線圖

## 使用 Aspose.Slides 在 Java 中建立折線圖

### 簡介
製作視覺吸引的簡報對於有效溝通至關重要。無論您是商業專業人士還是教育工作者，通常都需要 **create line chart** 視覺效果，既要資訊豐富，又要美觀。在本教學中，我們將示範如何使用 **Aspose.Slides for Java** 產生折線圖、加入圖表標題、加入格線、格式化圖表標籤，並將結果儲存為 PowerPoint 檔案。

#### 快速解答
- **哪個函式庫最適合在 Java 中建立圖表？** Aspose.Slides for Java
- **本指南聚焦於哪種圖表類型？** Line chart with markers
- **執行範例是否需要授權？** A free temporary license works for evaluation
- **我可以使用哪種 IDE？** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans
- **圖表元素如何格式化？** Using fluent API calls for titles, axes, grid lines, legends, and backgrounds

### 什麼是折線圖以及為何使用 Aspose.Slides？
折線圖以直線連接資料點，適合顯示隨時間變化的趨勢。Aspose.Slides 讓您能以程式方式建立並完整自訂這些圖表，免除手動編輯 PowerPoint 的需求。

### 先決條件
- **Java Development Kit (JDK) 8+** 已安裝
- **IDE**（IntelliJ IDEA、Eclipse、NetBeans 等）
- **Aspose.Slides for Java** 函式庫（透過 Maven 或 Gradle 新增）

#### 所需函式庫與相依性
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

或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新的 JAR。

#### 授權取得
- 取得 [免費試用授權](https://purchase.aspose.com/temporary-license/) 以進行測試。
- 從 [Aspose 官方網站](https://purchase.aspose.com/buy) 購買完整授權以供正式使用。

### 設定 Aspose.Slides for Java
1. **Add the dependency** 如上所示，新增至您的專案。
2. **Apply the license**（若已有授權）於建立任何簡報物件之前套用。

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## 逐步實作

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
*此舉重要原因:* 確保資料夾存在可避免在稍後儲存簡報時拋出 `FileNotFoundException`。

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
*說明:* 這會建立一張新的投影片，並在指定座標放置一個 **line chart with markers**。

### 步驟 3：加入圖表標題（add chart title）
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
*提示:* 使用粗體、灰色的標題可讓圖表立即辨識。

### 步驟 4：格式化座標軸並加入格線（add grid lines）
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
*此舉重要原因:* 清晰的格線與旋轉的標籤可提升可讀性，特別是在資料點密集時。

### 步驟 5：自訂圖例（add chart title – already covered, but legend is part of overall formatting）
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### 步驟 6：設定背景顏色（format chart labels – part of overall visual styling）
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
*結果:* 您現在已擁有一個 PowerPoint 檔案（`FormattedChart_out.pptx`），其中包含完整格式化的折線圖。

## 實務應用
- **Business Reports:** 展示季度績效的趨勢線。
- **Educational Slides:** 於講座中視覺化科學資料。
- **Project Proposals:** 突顯里程碑與預測。
- **Marketing Analysis:** 呈現活動 ROI 趨勢。
- **Dashboard Integration:** 將即時資料匯出至 PowerPoint，供利害關係人會議使用。

## 效能考量
- **Memory Management:** 確保對 `Presentation` 物件呼叫 `dispose()`，即時釋放原生資源。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **未套用授權** | 在建立任何 `Presentation` 物件之前，先載入試用或完整授權。 |
| **圖表顯示空白** | 確認投影片確實包含資料系列；如有需要請新增系列。 |
| **檔案未儲存** | 確保輸出目錄已存在（使用「create directory java」步驟）。 |
| **顏色未套用** | 使用 `java.awt.Color` 或 `PresetColor` 中的 `Color` 常數。 |

## 常見問答

**Q: 我可以建立除折線圖之外的其他圖表類型嗎？**  
A: 可以，Aspose.Slides 支援長條圖、圓餅圖、散佈圖以及其他多種圖表類型。

**Q: 如何為折線圖加入多個資料系列？**  
A: 使用 `chart.getChartData().getSeries().add(...)` 在格式化之前插入額外的系列。

**Q: 能否將圖表匯出為影像？**  
A: 完全可以。呼叫 `chart.getChartData().getChartDataWorkbook().save(...)` 或將投影片渲染為影像格式。

**Q: 開發是否需要付費授權？**  
A: 評估階段可使用免費的臨時授權；正式上線則需購買商業授權。

**Q: 支援哪些 Java 版本？**  
A: 此函式庫支援 JDK 8 至 JDK 22（使用相應的 classifier，例如 `jdk16`）。

---

**最後更新：** 2026-03-07  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}