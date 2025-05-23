---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 建立動態散點圖。使用可自訂的圖表功能增強您的簡報。"
"title": "使用 Aspose.Slides 在 Java 中建立和自訂散點圖"
"url": "/zh-hant/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 中建立和自訂散點圖

透過使用 Java 和 Aspose.Slides 新增動態散點圖來增強您的簡報。本綜合教學將引導您輕鬆設定目錄、初始化簡報、建立散點圖、管理圖表資料、自訂系列類型和標記以及儲存您的工作。

**您將學到什麼：**
- 設定用於儲存演示檔案的目錄
- 使用 Aspose.Slides 初始化和操作簡報
- 在投影片上建立散點圖
- 管理並向圖表系列添加數據
- 自訂圖表系列類型和標記
- 儲存已修改的簡報

首先，請確保您具備必要的先決條件。

## 先決條件

要遵循本教程，請確保您已具備：
- **Aspose.Slides for Java**：需要 25.4 或更高版本。
- **Java 開發工具包 (JDK)**：需要 JDK 8 或更高版本。
- 具備 Java 程式設計基礎並熟悉 Maven 或 Gradle 建置工具。

## 設定 Aspose.Slides for Java

在開始編碼之前，請使用以下方法之一將 Aspose.Slides 整合到您的專案中：

### Maven
將此依賴項包含在您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
將此行新增至您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，從下載最新的 Aspose.Slides for Java [Aspose 版本](https://releases。aspose.com/slides/java/).

#### 許可證獲取
- **免費試用**：從 30 天免費試用開始探索功能。
- **臨時執照**：取得臨時許可證以進行延長測試。
- **購買**：購買許可證以獲得完全訪問和支援。

現在，透過新增必要的匯入來初始化 Java 應用程式中的 Aspose.Slides，如下所示。

## 實施指南

### 目錄設定
首先，確保我們的目錄存在以儲存演示文件。此步驟可防止文件保存期間發生錯誤。

#### 如果目錄不存在則建立
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // 建立目錄
    new File(dataDir).mkdirs();
}
```
此程式碼片段檢查指定的目錄，如果不存在則建立它。它使用 `File.exists()` 驗證存在和 `File.mkdirs()` 建立目錄。

### 演示初始化

接下來，初始化您將新增散點圖的示範物件。

#### 初始化您的簡報
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
這裡， `new Presentation()` 建立一個空白簡報。我們進入第一張投影片並直接進行操作。

### 圖表創建
接下來在我們初始化的投影片上建立散點圖。

#### 將散點圖加入投影片
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
此程式碼片段在第一張投影片中新增了帶有平滑線條的散佈圖。這些參數定義圖表的位置和大小。

### 圖表資料管理
現在讓我們透過清除任何現有系列並新增新系列來管理我們的圖表資料。

#### 管理圖表系列
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// 在圖表中新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
此部分清除現有資料並為散佈圖新增兩個新系列。

### 散點圖系列的數據點添加
為了可視化我們的數據，我們在散點圖中的每個系列中添加點。

#### 新增數據點
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
我們使用 `addDataPointForScatterSeries()` 將資料點附加到我們的第一個系列。參數定義 X 和 Y 值。

### 系列類型和標記修改
透過改變每個系列中標記的類型和樣式來客製化圖表的外觀。

#### 客製化系列
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// 修改第二個系列
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
這些變化調整了系列類型以使用直線和標記。我們還設定了標記大小和符號以便進行視覺區分。

### 簡報儲存
最後，儲存所做的所有修改的簡報。

#### 儲存您的簡報
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
使用 `SaveFormat.Pptx` 指定用於儲存文件的 PowerPoint 格式。此步驟對於保存所有變更至關重要。

## 實際應用
以下是一些實際用例：
1. **財務分析**：使用散佈圖顯示股票隨時間的變化趨勢。
2. **科學研究**：代表需要分析的實驗數據點。
3. **專案管理**：可視化資源分配和進度指標。

將 Aspose.Slides 整合到您的系統中，您可以自動產生報告，從而提高生產力和準確性。

## 性能考慮
為了獲得最佳性能：
- 透過儲存後處理簡報來管理記憶體使用量。
- 對大型資料集使用高效率的資料結構。
- 盡量減少循環內的資源密集型操作。

最佳實務確保即使複雜的圖表操作也能順利執行。

## 結論
在本教程中，您學習如何設定目錄、初始化 Aspose.Slides 簡報、建立和自訂散點圖、管理系列資料、修改標記以及儲存您的工作。為了進一步探索 Aspose.Slides 的功能，請考慮深入了解動畫和幻燈片過渡等更高級的功能。

**後續步驟**：嘗試不同的圖表類型或將這些技術整合到更大的 Java 專案中。

## 常問問題

### 如何更改標記的顏色？
若要變更標記顏色，請使用 `series.getMarker().getFillFormat().setFillColor(ColorObject)`， 在哪裡 `ColorObject` 是您想要的顏色。

### 我可以為散點圖添加兩個以上的系列嗎？
是的，您可以透過重複新增系列和資料點的過程來新增所需數量的系列。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}