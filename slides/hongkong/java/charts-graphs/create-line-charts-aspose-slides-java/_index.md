---
date: '2026-03-23'
description: 學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立帶有標記的折線圖、加入第二條序列，並處理空值資料。
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 如何使用 Aspose.Slides for Java：建立帶有預設標記的折線圖
url: /zh-hant/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 建立帶預設標記的折線圖

## 簡介
## 快速解答
- **需要什麼函式庫？** Aspose.Slides for Java（建議使用最新版本）  
- **可以加入第二條序列嗎？** 可以 – API 讓您輕鬆新增多條序列。  
- **空值資料點如何處理？** 在儲存格值中使用 `null`；圖表會跳過該點。  
- **需要 Maven 嗎？** Maven 或 Gradle 都可使用；請參閱下方 *aspose slides maven* 章節。  
- **需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權。

## 使用 Aspose.Slides for Java 建立折線圖的方法
以程式方式建立圖表可為您節省數小時的手動格式設定，並確保簡報之間的一致性。無論您是在報告工具中建立 **create powerpoint chart** 功能，或是即時產生投影片組，Aspose.Slides 都能讓您從 Java 程式碼完整掌控。

## 前置條件
1. **Libraries & Dependencies**  
   - Aspose.Slides for Java 函式庫（建議使用 25.4 版）— 這涵蓋 *aspose slides maven* 情境。  
   - Java Development Kit (JDK) 版本 16 或以上。  
2. **Environment Setup**  
   - 支援 Maven 或 Gradle 的 IDE。  
   - 若在試用期外執行程式，需提供有效的 Aspose 授權檔案。  
3. **Knowledge Prerequisites**  
   - 基本的 Java 程式設計。  
   - 熟悉 Maven 或 Gradle 建置檔案。

## 設定 Aspose.Slides for Java
### Maven
Add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Include this in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接下載
或者，您可以從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

**取得授權步驟：**
- 取得免費試用，請前往 [free trial page](https://releases.aspose.com/slides/java/)。
- 取得臨時授權，請前往 [temporary license page](https://purchase.aspose.com/temporary-license/)。
- 透過 [purchase portal](https://purchase.aspose.com/buy) 購買完整授權。

**基本初始化：**
Here's how you can initialize Aspose.Slides in your Java application:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

現在，讓我們開始建立圖表吧！

## 實作指南
### 功能 1：使用預設標記建立圖表
本節示範如何建立 **line chart with markers**，適合在趨勢線上突顯個別資料點。

#### 新增折線圖
To add a line chart with markers:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### 清除序列與類別
To start fresh:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 功能 2：新增序列與類別
新增序列與類別對於填充圖表的有效資料至關重要。

#### 建立新序列
To add a new series named "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### 填充類別與資料點
To add categories and corresponding data points:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### 功能 3：新增第二條序列並填充資料點
新增額外的序列可為您的視覺分析提供更深入的資訊。

#### 建立並填充第二條序列
To add "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### 功能 4：設定圖表圖例
設定圖例可提升圖表可讀性，尤其在您 **add second series** 時。

#### 調整圖例設定
To configure:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### 功能 5：儲存簡報
當圖表完成後，您會想要 **create powerpoint chart** 檔案，以便分享或進一步編輯。

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## 實務應用
1. **商業報告：** 使用帶標記的折線圖來說明每季的財務趨勢。  
2. **資料分析：** 可視化實驗資料，讓每個標記突顯測量點。  
3. **教學教材：** 建立說明流程逐步變化的講義投影片。  
4. **專案管理：** 在時間軸上以明顯標記追蹤里程碑與關鍵日期。  
5. **行銷簡報：** 以清晰的標記符號展示活動績效高峰。  

## 常見問題與解決方案
- **空值資料點導致錯誤：** 傳入 `null` 作為儲存格值（如範例所示）— Aspose 會直接省略該點。  
- **圖表未顯示標記：** 確認使用 `ChartType.LineWithMarkers` 而非 `ChartType.Line`。  
- **圖例覆蓋資料：** 設定 `chart.getLegend().setOverlay(false)` 以使圖例分離。  

## 常見問答
**Q: 我可以在 Web 服務中使用此方法產生圖表嗎？**  
A: 當然可以。此函式庫可在任何 Java 環境執行，包括伺服器端應用程式。

**Q: 開發建置需要授權嗎？**  
A: 免費試用可用於開發與測試。正式環境需購買商業授權。

**Q: Aspose 如何處理大型資料集？**  
A: API 會有效率地串流資料；但請將資料點數量控制在合理範圍，以免產生過大檔案。

**Q: 是否支援其他圖表類型？**  
A: 有 – Aspose.Slides 支援長條圖、圓餅圖、散佈圖等多種圖表類型。

**Q: 我可以自訂標記形狀與顏色嗎？**  
A: 您可透過每個資料點的 `Marker` 屬性來修改標記格式。

## 結論
現在您已了解 **how to use Aspose** 來建立帶預設標記的折線圖、加入第二條序列、處理空值資料，並將結果儲存為 PowerPoint 檔案。這些技巧可讓您自動化報告產出、提升資料敘事，並保持簡報的一致性。  

欲深入了解，請參考 [official documentation](https://docs.aspose.com/slides/java/) 或加入 Stack Overflow 等社群論壇。

---

**最後更新：** 2026-03-23  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}