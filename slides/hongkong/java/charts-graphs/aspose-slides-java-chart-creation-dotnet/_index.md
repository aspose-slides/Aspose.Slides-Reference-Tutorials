---
date: '2026-01-14'
description: 學習如何使用 Aspose.Slides for Java 在 .NET 簡報中加入叢集柱狀圖並將圖表插入投影片。請參考此一步一步的教學，內含完整程式碼範例。
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 將群組柱狀圖新增至 .NET 投影片 Aspose.Slides Java
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 .NET 簡報中使用 Aspose.Slides for Java 建立圖表
## 簡介
製作引人入勝的簡報通常需要整合圖表等視覺化資料呈現，以提升觀眾的理解與參與度。若您是開發人員，想在 .NET 簡報中使用 Aspose.Slides for Java 加入動態、可自訂的圖表，本教學正為您而設。我們將深入探討如何初始化簡報、加入各類圖表、管理圖表資料，並有效地格式化系列資料。

**您將學會：**
- 如何在 .NET 環境中設定與使用 Aspose.Slides for Java。
- 使用 Aspose.Slides 初始化新簡報。
- 在投影片中加入與自訂圖表。
- 管理圖表資料工作簿。
- 格式化系列資料，特別是負值的處理方式。

接下來進入前置條件章節，確保您已做好全部準備，輕鬆跟隨操作。

## 快速回答
- **主要目標是什麼？** 在 .NET 投影片中加入叢集柱狀圖。
- **需要哪個函式庫？** Aspose.Slides for Java（v25.4 以上）。
- **可以在 .NET 專案中使用嗎？** 可以 ─ 透過 Java‑to‑.NET 橋接即可使用 Java 函式庫。
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。
- **實作大約需要多久？** 基本圖表約 10‑15 分鐘即可完成。

## 什麼是叢集柱狀圖？
叢集柱狀圖會在每個類別下將多個資料系列並排顯示，方便比較不同群組之間的數值。此類視覺效果非常適合商業儀表板、績效報告，以及任何需要對多項指標進行對比的情境。

## 為什麼要使用 Aspose.Slides for Java 在投影片中加入圖表？
使用 Aspose.Slides，您可以在未安裝 Microsoft PowerPoint 的環境下產生、修改與儲存簡報。它提供完整的圖表類型、資料與樣式控制，讓您能直接從 .NET 應用程式自動化產生報告。

## 前置條件
在開始使用 Aspose.Slides for Java 建立圖表之前，先確認您具備以下條件：

### 必要的函式庫與版本
- **Aspose.Slides for Java**：版本 25.4 或更新版本。

### 環境設定需求
- 支援 .NET 應用程式的開發環境。
- 具備基本的 Java 程式概念。

### 知識前提
- 熟悉在 .NET 應用程式中建立簡報的流程。
- 了解 Java 相依性管理（Maven / Gradle）。

## 設定 Aspose.Slides for Java
要開始使用 Aspose.Slides，必須將其加入專案相依性。以下說明不同的加入方式：

### Maven
在 `pom.xml` 中加入以下相依性：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 中加入以下內容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
您亦可從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

#### 授權取得步驟
- **免費試用**：先取得臨時授權以探索功能。
- **購買授權**：若需大量使用，建議購買正式授權。

#### 基本初始化與設定
以下示範如何在程式碼中初始化 Aspose.Slides：
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
此設定可確保資源管理得當。

## 實作指南
以下將逐步說明實作流程。

### 初始化簡報
**概述：**  
建立簡報實例是後續所有操作的基礎。本節示範如何使用 Aspose.Slides 從頭開始建立簡報。

#### 步驟 1：匯入必要的套件
```java
import com.aspose.slides.Presentation;
```

#### 步驟 2：建立新簡報物件
操作方式如下：
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*此步驟確保簡報物件在使用完畢後能正確釋放，避免記憶體洩漏。*

### 在投影片中加入圖表
**概述：**  
在投影片加入圖表可提升資料可視化的效果與吸引力。

#### 步驟 1：匯入必要的套件
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### 步驟 2：初始化簡報並加入圖表
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*此範例在第一張投影片的指定座標與尺寸處加入叢集柱狀圖。*

### 管理圖表資料工作簿
**概述：**  
有效管理圖表的資料工作簿，可讓您輕鬆操作系列與類別。

#### 步驟 1：匯入必要的套件
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### 步驟 2：存取並清除資料工作簿
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*清除工作簿可確保在新增系列與類別前有一個乾淨的起點。*

### 新增系列與類別至圖表
**概述：**  
本功能示範如何透過管理系列與類別，為圖表加入有意義的資料點。

#### 步驟 1：新增系列與類別
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*加入系列與類別有助於資料的條理化呈現。*

### 填入系列資料並格式化
**概述：**  
將資料點填入圖表並調整外觀，可提升可讀性，特別是在處理負值時。

#### 步驟 1：填入系列資料
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*本段說明如何填入資料並套用顏色格式，以增強視覺效果。*

## 常見問題與解決方案
- **記憶體洩漏**：務必在 `finally` 區塊中呼叫 `Presentation` 物件的 `dispose()`。
- **圖表類型錯誤**：若需叢集柱狀圖，請使用 `ChartType.ClusteredColumn`；其他類型會產生不同的視覺結果。
- **負值顏色未套用**：請確認 `IDataPoint` 的值已正確轉型為 `Number` 後再進行比較。

## 常見問答

**Q: 可以在純 .NET 專案中使用 Aspose.Slides for Java 而不安裝 Java 嗎？**  
A: 可以。此函式庫透過 Java‑to‑.NET 橋接，允許您在 .NET 語言中呼叫 Java API。

**Q: 免費試用版支援圖表建立嗎？**  
A: 試用版提供完整的圖表功能，但產生的檔案會帶有小型評估水印。

**Q: 哪些 .NET 版本相容？**  
A: 任何能與 Java 16+ 互操作的 .NET 版本皆可，包括 .NET Framework 4.6+、.NET Core 3.1+ 以及 .NET 5/6/7。

**Q: 如何處理包含大量圖表的巨型簡報？**  
A: 盡可能重複使用同一個 `IChartDataWorkbook` 實例，並在使用完每個 `Presentation` 後即時釋放以節省記憶體。

**Q: 能否將圖表匯出為影像？**  
A: 能。使用 `chart.getImage()` 或 `chart.exportChartImage()` 方法即可取得 PNG/JPEG 形式的圖表影像。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-14  
**測試環境：** Aspose.Slides for Java 25.4  
**作者：** Aspose  

---