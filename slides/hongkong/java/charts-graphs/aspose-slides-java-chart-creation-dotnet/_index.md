---
date: '2026-06-03'
description: 了解如何在 .NET 簡報中建立圖表，並使用 Aspose.Slides for Java 將圖表新增至投影片。請依循此一步步的資料視覺化指南。
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: 在 .NET 中使用 Aspose.Slides for Java 建立圖表
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 .NET 中使用 Aspose.Slides for Java 建立圖表

## 介紹
打造引人入勝的簡報通常需要整合圖表等視覺化資料，以提升觀眾的理解與參與度。**如果您想在 .NET 中建立圖表**，Aspose.Slides for Java 提供一套功能強大、語言無關的 API，能在 .NET 應用程式內無縫運作。在本教學中，您將學會如何初始化簡報、加入各種圖表類型、管理圖表資料工作簿，並格式化系列資料——包括處理負值。完成後，您即可以程式方式產生簡報檔案中的圖表，僅需幾行程式碼即可將圖表加入投影片。

## 快速回答
- **主要目標是什麼？** 使用 Aspose.Slides for Java 在 .NET 簡報中建立圖表。  
- **需要哪個版本的函式庫？** Aspose.Slides for Java 25.4 或更新版本。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以使用 Maven 或 Gradle 嗎？** 可以——兩種建置系統皆受支援。  
- **提供哪些圖表類型？** 群組柱狀圖、折線圖、圓餅圖、長條圖、區域圖等多種。

## 如何在 .NET 簡報中使用 Aspose.Slides for Java 建立圖表？
`Presentation` 類別代表 PowerPoint 檔案，提供操作投影片的方法。先載入新的 `Presentation` 物件，呼叫 `slides.addEmptySlide()` 取得投影片，接著使用 `slide.getShapes().addChart()` 在指定座標插入所需的圖表類型。圖表加入後，將資料工作簿填入系列與類別，套用格式（例如負值的顏色），最後將簡報儲存為 .pptx 檔案。這個流程讓您 **在 .NET 中建立圖表**，僅需簡潔的 API 呼叫。

## 什麼是 Aspose.Slides for Java？
Aspose.Slides for Java 是跨平台的 API，讓開發者在不安裝 Microsoft Office 的情況下建立、修改與轉換 PowerPoint 檔案。它支援 **超過 50 種輸入與輸出格式**，且能處理含千張投影片的簡報，同時將記憶體使用量控制在 200 MB 以下。

## 為什麼在 .NET 專案中使用 Aspose.Slides for Java？
Aspose.Slides for Java 在 Java 虛擬機上執行，並可透過原生封裝器從 .NET 呼叫，讓 .NET 開發者取得成熟的圖表引擎、高效能的大資料處理，以及與既有 Java 程式碼的完整相容性，無需重新編寫邏輯。

## 前置條件
在開始使用 Aspose.Slides for Java 建立圖表之前，先確認您具備以下條件：

### 必要的函式庫與版本
- **Aspose.Slides for Java**：版本 25.4 或更新。

### 環境設定需求
- 支援 .NET 應用程式的開發環境。  
- 基本的 Java 程式概念。

### 知識前提
- 熟悉在 .NET 應用程式環境中建立簡報的流程。  
- 了解 Java 相依性管理（Maven/Gradle）。

## 設定 Aspose.Slides for Java
要開始使用 Aspose.Slides，必須將其加入專案相依性。以下說明如何操作：

### Maven
以下 Maven 相依性片段會將 Aspose.Slides for Java 加入您的專案。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 檔案中加入此行，即可從 Maven Central 取得函式庫。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
您也可以從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

#### 取得授權步驟
- **免費試用**：先取得臨時授權以探索功能。  
- **購買授權**：購買授權以獲得無限制的正式環境使用。

#### 基本初始化與設定
`Slides` 初始化需要設定授權並建立 `Presentation` 實例。

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
以下將一步步說明如何實作各項功能。

### 初始化簡報
**概述：**  
建立簡報實例是後續所有操作的基礎。本節示範如何使用 Aspose.Slides 從頭開始建立簡報。

#### 步驟 1：匯入必要的套件
`Presentation` 及相關類別位於 `com.aspose.slides` 命名空間。

```java
import com.aspose.slides.Presentation;
```

#### 步驟 2：建立新的 Presentation 物件
建立 `Presentation` 物件，並以 try‑with‑resources 區塊包住，以確保使用後正確釋放。

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*此作法可在使用完畢後正確釋放簡報物件，避免記憶體泄漏。*

### 在投影片中加入圖表
**概述：**  
在投影片中加入圖表能讓資料視覺化更具說服力與吸引力。

#### 步驟 1：匯入必要的套件
`Chart` 類別代表可放置於投影片上的圖表形狀，且可自訂。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### 步驟 2：初始化簡報並加入圖表
建立投影片後，呼叫 `addChart`，傳入 `ChartType.ClusteredColumn` 以及欲設定的位置與大小。

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

*此範例在第一張投影片的指定座標與尺寸上加入群組柱狀圖。*

### 管理圖表資料工作簿
**概述：**  
有效管理圖表的資料工作簿，可讓您輕鬆操作系列與類別。

#### 步驟 1：匯入必要的套件
`IChartDataWorkbook` 提供對圖表底層類似 Excel 工作簿的存取。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### 步驟 2：存取並清除資料工作簿
從圖表取得工作簿，並清除現有資料以便重新開始。

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

*清除工作簿可確保在新增系列與類別前，資料環境為乾淨狀態。*

### 為圖表新增系列與類別
**概述：**  
本節說明如何透過管理系列與類別，為圖表加入有意義的資料點。

#### 步驟 1：新增系列與類別
使用 `chart.getChartData().getSeries().add()` 與 `chart.getChartData().getCategories().add()` 定義結構。

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

*新增系列與類別可讓資料呈現更有條理。*

### 填入系列資料與格式設定
**概述：**  
將資料點填入圖表並設定外觀，可提升可讀性，特別是負值的顯示。

#### 步驟 1：填入系列資料
將數值寫入工作簿的每個儲存格，並對負數套用紅色填滿。

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

*本段示範如何填入資料並使用顏色格式化，以增強視覺效果。*

## 常見問題與解決方案
- **LicenseNotFoundException** – 請確認授權檔案路徑正確且執行時可存取。  
- **NullPointerException on chart data** – 在新增系列前務必先清除工作簿，以避免遺留資料造成錯誤。  
- **Chart not rendering in .NET** – 請確認使用的是相容 .NET 的 Aspose.Slides JAR，且 Java 執行環境已正確配置於 .NET 專案中。

## 常見問答

**Q: 可以在沒有 GUI 的環境下產生簡報圖表嗎？**  
A: 可以，Aspose.Slides for Java 完全支援無頭模式，可在沒有圖形介面的伺服器上執行。

**Q: 支援哪些 .NET 版本？**  
A: 支援 .NET Framework 4.5+、.NET Core 3.1+、.NET 5 以及 .NET 6。

**Q: 可以加入多少種圖表類型？**  
A: 超過 20 種圖表類型，包括柱狀圖、折線圖、圓餅圖、區域圖與雷達圖等。

**Q: 能否為單一資料點設定樣式？**  
A: 當然可以——您可以透過 `IDataPoint` API 為每個資料點設定填色、邊框與標記。

**Q: 必須手動將 Java 物件轉換成 .NET 類型嗎？**  
A: 不需要，Aspose.Slides for Java 的 .NET 包裝器會自動處理型別轉換。

---

**最後更新：** 2026-06-03  
**測試環境：** Aspose.Slides for Java 25.4  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何在 .NET 簡報中嵌入圖表以提升資料視覺化](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [如何使用 Aspose.Slides for .NET 取得圖表資料來源類型](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [使用 Aspose.Slides .NET 精通圖表系列的建立與操作](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}