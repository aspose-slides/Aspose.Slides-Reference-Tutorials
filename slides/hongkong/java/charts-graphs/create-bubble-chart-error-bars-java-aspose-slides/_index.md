---
date: '2026-03-04'
description: 學習如何在 Aspose.Slides for Java 中為氣泡圖加入自訂誤差棒。本指南涵蓋圖表的建立、為每個資料點設定誤差棒，以及儲存簡報。
keywords:
- Bubble Chart Java
- Custom Error Bars Aspose.Slides
- Java Data Visualization
title: 如何在 Java 中使用 Aspose.Slides 為氣泡圖添加自訂誤差棒
url: /zh-hant/java/charts-graphs/create-bubble-chart-error-bars-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose.Slides 為氣泡圖新增自訂誤差棒

建立清晰、以資料為驅動的簡報通常需要超越一般圖表。學會 **如何為氣泡圖新增自訂誤差棒**，即可讓觀眾了解每個資料點的變異性與信心水準。在本教學中，你將看到如何設定 Java 專案以使用 Aspose.Slides、將氣泡圖加入投影片、為每個點配置誤差棒，最後將結果儲存為 PowerPoint 檔案。

## 快速解答
- **需要哪個函式庫？** Aspose.Slides for Java（最新版本）。  
- **哪種圖表類型支援自訂誤差棒？** 氣泡圖 (`ChartType.Bubble`)。  
- **誤差棒可以針對每個資料點設定嗎？** 可以 – 使用 `ErrorBarsCustomValues` 來設定 X/Y 的正負值。  
- **需要授權嗎？** 免費試用版可用於測試；正式授權可移除評估限制。  
- **實作大約需要多久？** 基本範例約 10‑15 分鐘即可完成。

## 前置條件

在開始之前，請確保你已具備以下環境：

- **Java Development Kit (JDK)：** 8 版或以上。  
- **Aspose.Slides for Java：** 將函式庫加入專案（請參考下方 Maven/Gradle 範例）。  
- **IDE：** IntelliJ IDEA、Eclipse、NetBeans，或任何你慣用的編輯器。

### 必要函式庫與相依性

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

你也可以從官方發行頁面下載最新 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

### 授權取得

- 先使用免費試用版探索全部功能。  
- 申請臨時授權以進行無限制測試。  
- 購買正式執行授權以供正式上線使用。

## 設定 Aspose.Slides for Java

將函式庫加入 classpath 後，即可初始化 Presentation 物件。以下程式碼會建立一個乾淨的畫布供圖表使用。

```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## 實作指南

### 功能 1：將圖表加入投影片並建立氣泡圖

**為什麼要將圖表加入投影片？**  
直接把圖表嵌入投影片，可讓視覺內容與周圍文字或圖片保持同一上下文，提升簡報的整體連貫性。

#### 步驟 1：匯入必要類別
```java
import com.aspose.slides.*;
```

#### 步驟 2：在第一張投影片加入氣泡圖
```java
// Access the first slide
ISlide slide = presentation.getSlides().get_Item(0);

// Create a bubble chart on the slide
IChart chart = slide.getShapes().addChart(
    ChartType.Bubble, 50, 50, 400, 300, true);
```
- `ChartType.Bubble` 告訴 Aspose 我們要建立氣泡圖。  
- 座標 `(50, 50)` 與尺寸 `(400, 300)` 讓圖表在投影片上有適當的位置與大小。

### 功能 2：設定誤差棒

誤差棒為觀眾提供每個點可靠性的視覺提示。我們會將其顯示出來，並使用自訂值。

#### 步驟 3：取得第一個系列
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### 步驟 4：啟用並設定自訂誤差棒
```java
// Accessing error bar formats
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();

// Making error bars visible
errBarX.setVisible(true);
errBarY.setVisible(true);

// Setting custom value types for more detailed control
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

### 功能 3：為資料點設定誤差棒（每點誤差棒）

現在為每個氣泡指派獨特的誤差幅度，示範 **每點誤差棒** 的設定方式。

#### 步驟 5：設定資料點集合
```java
IChartDataPointCollection points = series.getDataPoints();

// Configuring custom values for error bars
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Loop through each data point
for (int i = 0; i < points.size(); i++) {
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```
*使用自訂值可精確定義每個氣泡的誤差範圍，這在科學或金融分析中尤為重要。*

### 功能 4：儲存簡報

```java
String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";

// Saving the presentation
presentation.save(YOUR_DOCUMENT_DIRECTORY + "/ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

## 實務應用

在許多真實情境中，為氣泡圖加入自訂誤差棒相當有價值：

1. **科學研究：** 顯示每項實驗結果的測量不確定度。  
2. **商業分析：** 可視化銷售或市場佔有率的預測範圍。  
3. **教育教學：** 示範統計概念，如信賴區間。

## 效能考量

- 盡快釋放 `Presentation` 物件以釋放原生資源。  
- 若大量產生圖表，請限制資料點數量；過大的資料集會增加渲染時間。  
- 在建立多張投影片時重複使用圖表物件，可減少額外開銷。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **ErrorBarsCustomValues 回傳 `null`** | 系列尚未有資料點。 | 先加入資料點，或確保在設定誤差棒之前系列已填充資料。 |
| **圖表在投影片上不可見** | 圖表尺寸超出投影片範圍。 | 調整 X/Y 座標及寬高，使其符合投影片尺寸。 |
| **授權例外** | 使用試用版卻未提供有效授權。 | 在儲存投影片前套用臨時或正式授權。 |

## 常見問答

**Q: 什麼是 Aspose.Slides for Java？**  
A: 它是一套功能強大的 API，讓你在不安裝 Microsoft Office 的情況下，以程式方式建立、修改與轉換 PowerPoint 檔案。

**Q: 我可以在沒有授權的情況下使用 Aspose.Slides 嗎？**  
A: 可以，免費試用版適用於開發與測試，但會加上評估水印並限制部分功能。

**Q: 如何更新至最新版本的 Aspose.Slides？**  
A: 前往官方 [Aspose releases page](https://releases.aspose.com/slides/java/) 檢查最新版本，並相應更新你的 Maven/Gradle 相依性。

**Q: 為什麼要在氣泡圖中加入自訂誤差棒？**  
A: 誤差棒能傳達每個資料點的變異或信心水準，將簡單的散佈圖轉變為更豐富、資訊量更大的視覺敘事。

**Q: 我可以為其他圖表類型自訂誤差棒嗎？**  
A: 當然可以。Aspose.Slides 支援線圖、長條圖、柱狀圖以及許多其他圖表類型的誤差棒設定。

---

**最後更新：** 2026-03-04  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}