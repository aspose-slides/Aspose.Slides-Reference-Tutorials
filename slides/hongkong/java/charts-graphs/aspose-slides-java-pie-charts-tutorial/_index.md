---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 建立和自訂餅圖。本教程涵蓋了從設定到進階自訂的所有內容。"
"title": "使用 Aspose.Slides 在 Java 中建立餅圖綜合指南"
"url": "/zh-hant/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 建立圓餅圖：完整教學課程

## 介紹
創建動態且具有視覺吸引力的簡報對於傳遞有影響力的訊息至關重要。使用 Aspose.Slides for Java，您可以將圓餅圖等複雜圖表無縫整合到投影片中，輕鬆增強資料視覺化。本綜合指南將引導您完成使用 Aspose.Slides Java 建立和自訂餅圖的過程，輕鬆解決常見的簡報難題。

**您將學到什麼：**
- 初始化簡報並新增投影片。
- 在投影片上建立和配置圓餅圖。
- 設定圖表標題、資料標籤和顏色。
- 優化效能並有效管理資源。
- 使用 Maven 或 Gradle 將 Aspose.Slides 整合到 Java 專案中。

首先，確保您擁有所有必要的工具和知識！

## 先決條件
在深入本教學之前，請確保您已準備好以下設定：

### 所需的函式庫、版本和相依性
- **Aspose.Slides for Java**：確保您擁有 25.4 或更高版本。
- **Java 開發工具包 (JDK)**：需要版本 16 或更高版本。

### 環境設定要求
- 安裝並配置了 Java 的開發環境。
- 整合開發環境 (IDE)，如 IntelliJ IDEA、Eclipse 或 NetBeans。

### 知識前提
- 對 Java 程式設計有基本的了解。
- 熟悉 Maven 或 Gradle 的依賴管理。

## 設定 Aspose.Slides for Java
要開始在 Java 專案中使用 Aspose.Slides，您需要將該程式庫新增為依賴項。以下是使用不同的建置工具來實現此目的的方法：

**Maven**
將此程式碼片段新增至您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載**
如果您不想使用建置工具，請從下載最新版本 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 許可證取得步驟
- **免費試用**：從免費試用開始探索 Aspose.Slides 功能。
- **臨時執照**：取得臨時許可證，以便不受限制地延長使用時間。
- **購買**：如果您需要長期訪問，請考慮購買。

**基本初始化和設定**
要開始使用 Aspose.Slides，請透過建立一個新的演示物件來初始化您的專案：
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 實施指南
現在讓我們將新增和自訂餅圖的流程分解為易於管理的步驟。

### 初始化簡報和投影片
首先設定一個新的簡報並存取第一張投影片。這是您創建圖表的畫布：
```java
import com.aspose.slides.*;

// 建立一個新的演示實例。
Presentation presentation = new Presentation();
// 存取簡報中的第一張投影片。
islide slides = presentation.getSlides().get_Item(0);
```

### 將圓餅圖加入投影片
使用預設資料集將餅圖插入指定位置：
```java
import com.aspose.slides.*;

// 在位置 (100, 100) 處新增一個圓餅圖，大小為 (400, 400)。
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 設定圖表標題
透過設定和居中標題來自訂您的圖表：
```java
import com.aspose.slides.*;

// 為圓餅圖新增標題。
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 配置系列的資料標籤
確保數據標籤清晰地顯示值：
```java
import com.aspose.slides.*;

// 顯示第一個系列的資料值。
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 準備圖表資料工作表
透過清除現有系列和類別來設定圖表的資料工作表：
```java
import com.aspose.slides.*;

// 準備圖表資料工作簿。
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 將類別新增至圖表
定義餅圖的類別：
```java
import com.aspose.slides.*;

// 新增類別。
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 新增系列並填充數據點
創建一個系列並用數據點填充它：
```java
import com.aspose.slides.*;

// 新增系列並設定其名稱。
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 自訂系列顏色和邊框
透過設定顏色和自訂邊框來增強視覺吸引力：
```java
import com.aspose.slides.*;

// 為系列扇區設定不同的顏色。
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// 對具有不同顏色和樣式的其他資料點重複此操作。
```

### 配置自訂資料標籤
微調每個數據點的標籤：
```java
import com.aspose.slides.*;

// 配置自訂標籤。
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// 啟用標籤的引線。
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### 設定旋轉角度並儲存簡報
透過設定旋轉角度並儲存簡報來完成圓餅圖：
```java
import com.aspose.slides.*;

// 設定旋轉角度。
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// 將簡報儲存到文件。
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 結論
在本教學中，您學習如何使用 Aspose.Slides for Java 建立和自訂圓餅圖。透過遵循這些步驟，您可以使用視覺上吸引人的資料視覺化來增強您的簡報。如果您有任何疑問或需要進一步的協助，請隨時與我們聯繫。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}