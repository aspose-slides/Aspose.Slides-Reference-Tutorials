---
date: '2026-07-27'
description: 如何使用 Aspose.Slides for Java 自訂圖表。學習建立 PowerPoint 圖表、樣式化 scatter series，並有效儲存
  presentations。
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: 如何使用 Aspose.Slides for Java 自訂圖表。本指南說明如何建立 PowerPoint 圖表、樣式化 scatter
  points，並匯出 presentations。
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 如何自訂圖表：Scatter Chart Aspose in Java
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 如何自訂圖表：Scatter Chart Aspose in Java
url: /zh-hant/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 Java 中自訂 Aspose 散點圖表

在本教學中，您將學習 **如何自訂圖表** — 以散點圖為例 — 使用功能強大的 Aspose.Slides for Java 函式庫。我們將逐步說明專案設定、建立散點圖、調整系列類型與標記，最後儲存簡報。完成後，您即可以程式方式產生專業外觀的散點圖，並依據品牌或報告需求調整每一項視覺細節。

## 快速解答
- **需要的函式庫是什麼？** Aspose.Slides for Java (v25.4+)。  
- **支援哪個 Java 版本？** JDK 8 或以上。  
- **可以變更標記形狀嗎？** 可以 – 使用 `MarkerStyleType` 來選擇星形、圓形等。  
- **如何儲存檔案？** 呼叫 `pres.save("output.pptx", SaveFormat.Pptx)`。  
- **是否需要授權？** 免費試用可用於開發；正式環境需購買商業授權。

## 如何使用 Aspose.Slides 在 Java 中自訂圖表？
`Presentation` 是 Aspose.Slides 中代表整個 PowerPoint 檔案於記憶體中的類別。載入新的 `Presentation`，在第一張投影片上加入散點圖，設定系列與標記樣式，最後呼叫 `save`。這個簡單流程只需幾行 Java 程式碼即可建立完整樣式的圖表，隨時可嵌入任何 PowerPoint 簡報。

## 什麼是「customize scatter chart aspose」？
使用 Aspose 進行散點圖自訂，指的是以程式方式定義圖表的資料、外觀與行為——從座標點到標記符號皆可設定，而不需手動開啟 PowerPoint。此方式非常適合自動化報告、資料驅動的簡報，或任何需要可重複產生高品質視覺化的情境。

## 為什麼要使用 Aspose.Slides 自訂散點圖表？
- **完整控制** – 透過 Java 程式碼修改系列類型、標記樣式、顏色等。  
- **自動化** – 即時產生數十張圖表，用於儀表板或批次報告。  
- **跨平台** – 可在任何支援 Java 的作業系統上執行，無需安裝 Office。  
- **效能** – 輕量級 API 可處理 **150+ 圖表類型**，且能在不將整個檔案載入記憶體的情況下處理數百頁的簡報。

## 前置條件

- **Aspose.Slides for Java**（v25.4 或更新版本）。  
- **Java Development Kit (JDK)** 8 以上已安裝。  
- 使用 Maven 或 Gradle 進行相依性管理（或手動下載 JAR）。  
- 具備基本的 Java 知識，並熟悉您選擇的建置工具。

## 設定 Aspose.Slides for Java

使用以下任一方式將函式庫整合至您的專案。

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

或從 [Aspose Releases](https://releases.aspose.com/slides/java/) 取得最新版本。

#### 取得授權
- **免費試用** – 30 天評估。  
- **臨時授權** – 延長測試期間。  
- **正式授權** – 生產環境使用並享有高級支援。

## 步驟指南：自訂 Aspose 散點圖表

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
*為什麼重要：* 確保輸出資料夾已存在，可避免在稍後儲存 PPTX 時拋出 `FileNotFoundException`。

### 2️⃣ 建立新簡報並取得第一張投影片
`Presentation` 代表 PowerPoint 文件，提供存取投影片與圖形的功能。`Presentation` 類別在記憶體中表示整個 PowerPoint 檔案。

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ 新增平滑線散點圖
`ChartType.ScatterWithSmoothLines` 會建立一種散點圖，將資料點以平滑線連接。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ 清除預設系列並加入自訂系列
`IChartSeries` 代表圖表中的資料系列。

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

### 5️⃣ 為第一個系列填入資料點
`addDataPointForScatterSeries` 為散點系列加入單一 X‑Y 點。

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ 自訂系列類型與標記外觀
`Marker` 控制圖表系列中每個資料點的視覺符號。

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

### 7️⃣ 儲存簡報
`save` 將簡報寫入指定格式的檔案。

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 自訂散點圖表的常見使用情境
- **金融儀表板** – 繪製股價與成交量的關係。  
- **科學研究** – 顯示帶有誤差標記的實驗測量值。  
- **專案管理** – 比較各任務的計畫與實際工時。

## 效能小技巧
- 儲存後呼叫 `pres.dispose()` 釋放本機記憶體。  
- 對於大型資料集，先填充工作簿再綁定系列，可避免重複的 UI 重繪。  
- 在加入多個系列時，重複使用同一個 `IChartDataWorkbook` 實例，以降低記憶體使用量。

## 常見問與答

**問：如何變更標記的顏色？**  
A: 使用 `series.getMarker().getFillFormat().setFillColor(Color)`，其中 `Color` 為 `java.awt.Color` 例項，例如 `Color.RED`。

**問：可以在散點圖中加入超過兩個系列嗎？**  
A: 可以。對每個額外的系列呼叫 `chart.getChartData().getSeries().add(...)`，並相應地填入資料點。

**問：能為每個系列設定自訂圖例嗎？**  
A: 當然可以。建立系列後，呼叫 `series.getLegend().setText("Your Legend Text")` 以覆寫預設名稱。

**問：如何將圖表匯出為影像而非 PPTX？**  
A: 在設定圖表後呼叫 `chart.getImage().save("chart.png", ImageFormat.Png)`，即可產生獨立的 PNG 檔案。

**問：如果需要為散點加入動畫該怎麼做？**  
A: Aspose.Slides 支援動畫效果。使用 `chart.getTimeline().getMainSequence().addEffect(...)` 可為圖表或個別系列加入進入或強調動畫。

---

**最後更新：** 2026-07-27  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Slides 在 Java 中建立與自訂 PowerPoint 圖表](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中建立氣泡圖（教學）](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [使用 Aspose.Slides for Java 建立與自訂帶趨勢線的圖表](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}