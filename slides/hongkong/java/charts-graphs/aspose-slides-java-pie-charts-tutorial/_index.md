---
date: '2026-02-19'
description: 學習如何在 Java 中使用 Aspose.Slides 建立圓餅圖，並自訂圓餅圖顏色、加入圖表系列、操作圖表資料工作表，以及設定旋轉角度。
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 使用 Aspose.Slides 在 Java 中自訂圓餅圖顏色 – 完整指南
url: /zh-hant/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

Translate table.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 建立圓餅圖：完整教學

## 介紹
建立動態且具視覺吸引力的簡報對於傳遞有衝擊力的資訊至關重要。使用 Aspose.Slides for Java，您可以輕鬆在投影片中整合複雜的圖表（如圓餅圖），**自訂圓餅圖顏色**，並毫不費力地提升資料可視化效果。本完整指南將一步步帶您使用 Aspose.Slides Java 建立與自訂圓餅圖，輕鬆解決常見的簡報挑戰。

**您將學會：**
- 初始化簡報並新增投影片。
- 在投影片上建立與設定圓餅圖。
- 設定圖表標題、資料標籤，並**自訂圓餅圖顏色**。
- 最佳化效能與有效管理資源。
- 透過 Maven 或 Gradle 將 Aspose.Slides 整合至 Java 專案。

讓我們先確保您已具備所有必要的工具與知識，然後開始吧！

## 快速答覆
- **建立簡報的主要類別是什麼？** `Presentation`（來自 `com.aspose.slides`）。
- **哪個方法可將圓餅圖加入投影片？** `addChart(ChartType.Pie, …)`。
- **如何為每個切片啟用不同顏色？** 在系列群組上設定 `setColorVaried(true)`。
- **可以旋轉圓餅圖嗎？** 可以，使用圖表物件的 `setRotationAngle(double)`。
- **商業環境需要授權嗎？** 商業部署必須使用 Aspose.Slides 授權。

## 什麼是「自訂圓餅圖顏色」？
自訂圓餅圖顏色是指為圓餅圖的每個切片指派不同的填色，以提升可讀性與視覺衝擊力。於 Aspose.Slides 中，您只需啟用多色模式，然後為各資料點設定實心填色即可。

## 為什麼使用 Aspose.Slides for Java 來建立圓餅圖？
- **完整控制** 圖表外觀，無需 Microsoft Office。
- **跨平台** 相容性——支援 Windows、Linux 與 macOS。
- **功能豐富的 API**，可進行資料繫結、樣式設定，並匯出為 PPTX、PDF 或影像。
- **授權彈性**——可先使用免費試用版，之後視需求升級取得完整功能。

## 前置條件
在開始本教學前，請確保已完成以下設定：

### 必要的函式庫、版本與相依性
- **Aspose.Slides for Java**：版本 25.4 或更新。
- **Java Development Kit (JDK)**：版本 16 以上。

### 環境設定需求
- 已安裝並配置 Java 的開發環境。
- 使用 IntelliJ IDEA、Eclipse 或 NetBeans 等整合開發環境 (IDE)。

### 知識前置條件
- 基本的 Java 程式設計概念。
- 熟悉 Maven 或 Gradle 之相依性管理。

## 設定 Aspose.Slides for Java
要在 Java 專案中使用 Aspose.Slides，必須將函式庫加入相依性。以下示範不同建置工具的加入方式：

**Maven**  
將以下片段加入 `pom.xml` 檔案：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
在 `build.gradle` 檔案中加入：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載**  
若不使用建置工具，可從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權的步驟
- **免費試用**：先取得免費試用版以探索功能。  
- **暫時授權**：取得暫時授權以延長無限制使用時間。  
- **購買**：若需長期使用，請考慮購買正式授權。

**基本初始化與設定**  
以下程式碼示範如何建立新的簡報物件以開始使用 Aspose.Slides：
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 實作指南
接下來，我們將把加入與自訂圓餅圖的流程拆解為可管理的步驟。

### 初始化簡報與投影片
先建立新簡報並取得第一張投影片，作為圖表的畫布：
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### 在投影片加入圓餅圖
在指定位置插入圓餅圖，使用預設資料集：
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 設定圖表標題
自訂圖表標題並置中顯示：
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 為系列設定資料標籤
確保資料標籤顯示數值，以提升清晰度：
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 準備圖表資料工作表
先清除既有的系列與類別，為圖表資料工作表做初始化：
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 為圖表加入類別
為圓餅圖定義類別：
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 新增系列並填入資料點
建立系列並填入資料點——此步驟即**加入圖表系列**：
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 自訂系列顏色與邊框
設定顏色與邊框以提升視覺效果——這正是**自訂圓餅圖顏色**的核心：
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
微調每個資料點的標籤：
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
最後透過**設定旋轉角度**完成圓餅圖，並將檔案儲存：
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **切片全部呈現相同顏色** | 未呼叫 `setColorVaried(true)` | 確認已在系列群組上啟用多色模式。 |
| **資料標籤未顯示** | `showValue` 旗標未開啟 | 在相應的標籤格式上呼叫 `setShowValue(true)`。 |
| **旋轉無效** | 使用較舊的 Aspose.Slides 版本 | 升級至 25.4 或更新版本。 |
| **執行時出現授權例外** | 未載入或授權檔案無效 | 在建立 `Presentation` 前先載入授權：`License license = new License(); license.setLicense("Aspose.Slides.lic");` |

## 常見問答

**Q: 如何取得 Aspose.Slides 的 Java 授權？**  
A: 可於 Aspose 官方網站申請免費試用，之後購買正式授權。於執行時依上述「常見問題」表格載入授權。

**Q: 可以在較舊的 JDK 版本使用此程式碼嗎？**  
A: API 需要 JDK 16 以上，較舊版本不受支援。

**Q: 能否將圖表匯出為影像而非 PPTX？**  
A: 可以，於渲染後呼叫 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`。

**Q: 若要在圓餅圖中加入多個系列該怎麼辦？**  
A: 圓餅圖通常僅顯示單一系列；若需多系列建議改用環形圖 (doughnut chart)。  

**Q: 此函式庫能在 Linux 伺服器上運行嗎？**  
A: 完全可以——Aspose.Slides for Java 為跨平台套件，只要安裝相容的 JDK，即可在任何作業系統執行。

---

**最後更新日期：** 2026-02-19  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}