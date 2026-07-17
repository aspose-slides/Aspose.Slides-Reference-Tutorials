---
date: '2026-07-17'
description: 了解如何使用 Aspose.Slides for Java 旋轉圓餅圖、客製化圓餅圖顏色，並將投影片匯出為 PDF——完整的資料視覺化指南。
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: 使用 Aspose.Slides for Java 旋轉圓餅圖並自訂圓餅圖顏色。了解如何將投影片匯出為 PDF 以及操作圖表資料工作表。
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: 在 Java 中旋轉圓餅圖並自訂顏色 – Aspose.Slides 指南
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: 如何在 Java 中使用 Aspose.Slides 旋轉圓餅圖並自訂顏色
url: /zh-hant/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 建立圓餅圖：完整教學

## 介紹
在本教學中，您將學會 **旋轉圓餅圖** 元素、為每個切片自訂顏色，並將最終投影片匯出為 PDF——全部使用 Aspose.Slides for Java。無論您是在打造銷售儀表板、財務報告，或任何資料驅動的簡報，掌握這些技巧都能讓您在不依賴 Microsoft Office 的情況下，呈現清晰且吸睛的視覺效果。讓我們先準備好工具，然後深入實作。

## 快速回答
- **什麼類別可開啟新簡報？** `Presentation` 來自 `com.aspose.slides`。
- **哪個 API 呼叫會新增圓餅圖？** `slide.addChart(ChartType.Pie, …)`。
- **如何為每個切片設定獨特顏色？** 呼叫 `series.setColorVaried(true)`，並為每個資料點設定實心填色。
- **哪個方法可旋轉圖表？** `chart.setRotationAngle(double)` – 使用 0 到 360 度的角度。
- **投影片能匯出為 PDF 嗎？** 可以，呼叫 `presentation.save("output.pdf", SaveFormat.Pdf)`。

## 什麼是「自訂圓餅圖顏色」？
自訂圓餅圖顏色是指為圓餅圖的每一切片指派不同的填色，以提升可讀性與視覺衝擊力。於 Aspose.Slides 中，您只需啟用多樣顏色，然後為各資料點設定實心填色，即可讓每個資料區段在簡報中清晰突顯。

## 為什麼使用 Aspose.Slides for Java 來建立圓餅圖？
Aspose.Slides 支援 **150+ 圖表類型**，且能在一般伺服器上於 **5 秒內** 渲染 300 頁簡報，且不需安裝 Microsoft Office。此函式庫可在 Windows、Linux 與 macOS 上執行，為任何基於 Java 的資料視覺化專案提供跨平台彈性。

## 前置條件
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 或更新版本
- IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE
- 基本的 Java 知識，並熟悉 Maven 或 Gradle

## 設定 Aspose.Slides for Java
將函式庫加入您的建置設定。

**Maven**  
將以下片段加入您的 `pom.xml` 檔案：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
在您的 `build.gradle` 檔案中加入以下內容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
如果您偏好手動方式，請從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新的 JAR。

### 取得授權步驟
- **免費試用** – 無償探索全部功能。  
- **臨時授權** – 在短期內延長試用限制。  
- **購買** – 取得永久授權以供正式使用。

**基本初始化與設定**  
`Presentation` 類別代表記憶體中的 PowerPoint 檔案，並提供操作投影片的方法。  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 實作指南
以下提供逐步說明，從建立投影片到旋轉最終圓餅圖皆涵蓋其中。

### 初始化 Presentation 與投影片
建立新的 `Presentation` 實例，並取得第一張投影片作為圖表畫布。  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### 新增圓餅圖至投影片
`addChart` 會在指定座標位置於投影片上新增指定類型的圖表形狀。  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 設定圖表標題
`setTitle` 為圖表指派文字標題，並將其置中。  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 為系列設定資料標籤
`setShowValue(true)` 會在系列的每個資料點上顯示數值標籤。  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 準備圖表資料工作表
`ChartDataWorkbook` 儲存供圖表系列與類別使用的底層資料表。  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 為圖表新增類別
`addCategory` 為圖表的資料系列建立新的類別標籤。  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 新增系列並填入資料點
`addSeries` 建立資料系列，`addDataPointForBarSeries` 為每個類別插入數值。  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 自訂系列顏色與邊框
`setColorVaried(true)` 會啟用每切片的顏色，`setFillFormat` 為每個資料點指派實心填色。  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### 設定自訂資料標籤
`setDataLabelFormat` 可自訂標籤的外觀、位置與字型，以提升圖表註解的清晰度。  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### 設定旋轉角度並儲存簡報
`setRotationAngle` 會旋轉整個圓餅圖，`save` 則將簡報寫入檔案。  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 如何旋轉圓餅圖？
載入圖表物件，呼叫 `chart.setRotationAngle(45.0)`（或任意角度值），然後儲存簡報。旋轉圓餅圖會改變起始角度，讓您在不改變資料的前提下強調特定區段。此單一方法呼叫適用於 Aspose.Slides 中的任何 `Chart` 實例。您亦可結合多樣切片顏色，以突顯最重要的資料點。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|-------|-----|
| **所有切片顏色相同** | `setColorVaried(true)` 未呼叫 | 確保在系列群組上啟用多樣顏色。 |
| **資料標籤未顯示** | `showValue` 標誌被停用 | 在標籤格式上呼叫 `setShowValue(true)`。 |
| **旋轉無效** | 使用較舊的 Aspose.Slides 版本 | 升級至 25.4 版或更新版本。 |
| **執行時授權例外** | 缺少或無效的授權檔案 | 在建立 `Presentation` 前載入授權：`License license = new License(); license.setLicense("Aspose.Slides.lic");` |

## 常見問答

**Q: 如何取得 Aspose.Slides 的 Java 授權？**  
A: 從 Aspose 官方網站申請免費試用，之後購買永久授權。於執行時如同上表所示載入授權檔案。

**Q: 我可以在較舊的 JDK 版本上使用此程式碼嗎？**  
A: 此 API 需要 JDK 16 或以上，較舊版本不受支援。

**Q: 是否可以將圖表匯出為影像而非 PPTX？**  
A: 可以——渲染完成後，呼叫 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`。

**Q: 如果圓餅圖需要多於一個系列該怎麼辦？**  
A: 圓餅圖設計僅支援單一資料系列；若需多系列，建議改用環形圖（doughnut chart）。

**Q: Aspose.Slides 能在 Linux 伺服器上執行嗎？**  
A: 當然可以——Aspose.Slides for Java 與作業系統無關，只要有相容的 JDK 即可在任何平台上運行。

**最後更新：** 2026-07-17  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.Slides 在 Java 簡報中建立圓餅圖：完整指南](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [精通 Java 圓餅圖使用 Aspose.Slides：完整指南](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [在 Java 中使用 Aspose.Slides 旋轉圖表文字：完整指南](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}