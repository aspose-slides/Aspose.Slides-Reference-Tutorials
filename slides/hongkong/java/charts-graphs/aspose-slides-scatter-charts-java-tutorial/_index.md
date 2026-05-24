---
date: '2026-02-24'
description: 學習如何使用 Aspose.Slides for Java 自訂散點圖。此指南將帶領您完成在簡報中建立、樣式設定與儲存動態散點圖的步驟。
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: 在 Java 中自訂 Aspose 散點圖
url: /zh-hant/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 自訂散點圖 Aspose（Java 版）

在本教學中，您將學習如何使用功能強大的 Aspose.Slides for Java 函式庫 **自訂散點圖 aspose**。我們將逐步說明如何設定專案、建立散點圖、調整系列類型與標記，最後儲存簡報。完成後，您即可以程式方式產生專業外觀的散點圖，並依品牌或報告需求調整每一個視覺細節。

## 快速解答
- **需要哪個函式庫？** Aspose.Slides for Java（v25.4 以上）。  
- **支援哪個 Java 版本？** JDK 8 或更高。  
- **可以變更標記形狀嗎？** 可以 – 使用 `MarkerStyleType` 來選擇星形、圓形等。  
- **如何儲存檔案？** 呼叫 `pres.save("output.pptx", SaveFormat.Pptx)`。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。

## 什麼是「customize scatter chart aspose」？
使用 Aspose 進行散點圖自訂，指的是以程式方式定義圖表的資料、外觀與行為——從座標點到標記符號，都不需手動開啟 PowerPoint。此方式非常適合自動化報表、資料驅動的簡報，或任何需要可重複產出高品質視覺化的情境。

## 為什麼要使用 Aspose.Slides 來自訂散點圖？
- **完整控制** – 透過 Java 程式碼修改系列類型、標記樣式、顏色等。  
- **自動化** – 可即時產生大量圖表，適用於儀表板或批次報告。  
- **跨平台** – 在任何支援 Java 的作業系統上執行，無需安裝 Office。  
- **效能佳** – 輕量級 API 能有效處理大量資料。

## 前置條件

請先確保您已具備：

- **Aspose.Slides for Java**（v25.4 或更新版本）。  
- **Java Development Kit (JDK)** 8 以上。  
- Maven 或 Gradle 以管理相依性（亦可手動下載 JAR）。  
- 基本的 Java 知識與您慣用的建置工具。

## 設定 Aspose.Slides for Java

將函式庫整合至專案，以下任一方式皆可。

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或從 [Aspose 版本發佈](https://releases.aspose.com/slides/java/) 下載最新版本。

#### 授權取得
- **免費試用** – 30 天評估。  
- **臨時授權** – 延長測試期間。  
- **正式授權** – 生產環境使用並享有高級支援。

## 步驟教學：自訂散點圖 Aspose

### 1️⃣ 為簡報檔案準備資料夾
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*為什麼需要這一步驟：* 確保輸出資料夾已存在，可避免在稍後儲存 PPTX 時拋出 `FileNotFoundException`。

### 2️⃣ 建立新簡報並取得第一張投影片
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
全新的 `Presentation` 提供乾淨的畫布；第一張投影片將放置圖表。

### 3️⃣ 新增平滑線散點圖
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` 會產生平滑線散點圖，適合呈現趨勢走勢。

### 4️⃣ 清除預設系列並加入自訂系列
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
移除預設系列後，您即可完全掌控要顯示的資料。

### 5️⃣ 為第一個系列填入資料點
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` 需要 X 軸儲存格與 Y 軸儲存格，逐點建立散點圖。

### 6️⃣ 自訂系列類型與標記外觀
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
此處我們 **customize the scatter chart aspose**，將線條改為直線、放大標記，並選擇不同符號（星形 vs 圓形）以提升可讀性。

### 7️⃣ 儲存簡報
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
以 `Pptx` 格式儲存可保留所有圖表自訂設定，並方便分享或後續編輯。

## 常見自訂散點圖的使用情境
- **財務儀表板** – 繪製股價與成交量的關係。  
- **科學研究** – 顯示實驗測量值與誤差標記。  
- **專案管理** – 比較計畫工時與實際工時的差異。  

## 效能最佳化建議
- 儲存後呼叫 `pres.dispose()` 釋放本機資源。  
- 大量資料時，先填充工作簿再綁定系列，可減少重複 UI 刷新。  
- 若需加入多個系列，請重複使用同一個 `IChartDataWorkbook` 實例。

## 常見問答

### 如何變更標記的顏色？
使用 `series.getMarker().getFillFormat().setFillColor(Color)`，其中 `Color` 為 `java.awt.Color` 例項（如 `Color.RED`）。

### 可以在散點圖中加入超過兩個系列嗎？
當然可以。對每個額外系列重複呼叫 `chart.getChartData().getSeries().add(...)`，並依序填入資料點。

### 能否為每個系列設定自訂圖例文字？
可以。建立系列後，呼叫 `series.getLegend().setText("Your Legend Text")` 以覆寫預設名稱。

### 如何將圖表匯出為影像而非 PPTX？
在配置完圖表後，呼叫 `chart.getImage().save("chart.png", ImageFormat.Png)`，即可取得獨立的 PNG 檔案。

### 若要為散點加入動畫效果該怎麼做？
Aspose.Slides 支援動畫。使用 `chart.getTimeline().getMainSequence().addEffect(...)` 為圖表或單一系列加入進場或強調動畫。

---

**最後更新日期：** 2026-02-24  
**測試環境：** Aspose.Slides for Java 25.4（jdk16 classifier）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}