---
date: '2026-02-06'
description: 學習如何在 .NET 中使用 Aspose.Slides for Java 初始化 Aspose Slides 簡報並自訂叢集柱狀圖。跟隨此一步一步的指南，提升資料視覺化效果。
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 使用 Aspose Slides 初始化簡報：.NET 圖表
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 .NET 簡報中使用 Aspose.Slides for Java 建立圖表

## Introduction
在本教學中，您將 **初始化 presentation Aspose Slides**，並學習如何將動態、可自訂的圖表嵌入到 .NET 簡報中。視覺化資料（例如群組柱狀圖）能讓觀眾即時掌握趨勢，而 Aspose.Slides for Java 即使在 .NET 環境下也能提供完整的程式化控制。我們將逐步說明如何設定函式庫、建立新簡報、加入圖表、填入資料，以及套用格式化技巧（如負值著色）。

**您將學會**
- 如何在 .NET 專案中設定 Aspose.Slides for Java。  
- 如何 **初始化 presentation Aspose Slides** 並加入圖表。  
- 如何 **自訂群組柱狀圖** 的系列與類別。  
- 管理圖表的資料工作簿並套用條件格式化。  

### Quick Answers
- **第一步是什麼？** 初始化 `Presentation` 物件。  
- **範例中使用哪種圖表類型？** `ClusteredColumn`。  
- **可以將負值以不同方式格式化嗎？** 可以，使用條件填色。  
- **測試時需要授權嗎？** 免費試用授權即可用於開發。  
- **需要哪個 Maven 套件？** `com.aspose:aspose-slides:25.4`，分類器為 `jdk16`。  

## What is “initialize presentation Aspose Slides”?
初始化簡報會在記憶體中建立一個 PPTX 檔案，您可以在儲存之前對其進行各種操作。Aspose.Slides 抽象化了檔案格式，讓您能在不處理底層 OPC 結構的情況下新增投影片、圖形與圖表。

## Why customize a clustered column chart?
群組柱狀圖非常適合在不同類別間比較多個資料系列。自訂顏色、資料點與標籤可讓您突顯關鍵洞見——例如將負值標示為紅色、正值標示為綠色——使簡報更具說服力。

## Prerequisites
- **Aspose.Slides for Java** ≥ 25.4  
- .NET 開發環境（建議使用 Visual Studio、.NET 6 以上）  
- 基本的 Java 知識（您將撰寫在 JVM 上執行、並透過 JNI 或橋接層由 .NET 呼叫的 Java 程式）  

### Required Libraries and Versions
- **Aspose.Slides for Java**：版本 25.4 或更新。

### Environment Setup Requirements
- 相容 .NET 的 Java 執行環境（例如 AdoptOpenJDK 16）。  
- 用於相依管理的 Maven 或 Gradle。

### Knowledge Prerequisites
- 熟悉在 .NET 環境下建立簡報的流程。  
- 了解 Java 專案設定（Maven/Gradle）。

## Setting Up Aspose.Slides for Java
使用您偏好的建置工具將函式庫加入專案。

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

### Direct Download
您也可以從官方發行頁面下載最新的 JAR 檔案： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

#### License Acquisition Steps
- **Free Trial** – 產生臨時授權檔供開發使用。  
- **Purchase** – 取得正式授權以部署於正式環境。

#### Basic Initialization and Setup
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
`try/finally` 區塊確保本機資源會被釋放，避免記憶體洩漏。

## How to initialize presentation Aspose Slides
以下將說明建立全新簡報並為插入圖表做準備的具體步驟。

### Initializing Presentation
**Overview:**  
建立簡報實例是後續所有操作的基礎。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
```

#### Step 2: Create a New Presentation Object
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*此步驟確保簡報物件在使用完畢後能正確釋放，避免記憶體洩漏。*

## How to customize clustered column chart
簡報已就緒，接下來加入並客製化群組柱狀圖。

### Adding Chart to Slide
**Overview:**  
加入圖表可讓資料在投影片上栩栩如生。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Step 2: Initialize Presentation and Add Chart
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
*此範例在第一張投影片的指定座標與尺寸處加入群組柱狀圖。*

### Managing Chart Data Workbook
**Overview:**  
有效管理圖表的資料工作簿，可讓您順暢操作系列與類別。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Step 2: Access and Clear Data Workbook
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
*清除工作簿是為了在新增系列與類別前，確保有一個乾淨的起點。*

### Adding Series and Categories to Chart
**Overview:**  
本步驟示範如何透過管理系列與類別來加入有意義的資料點。

#### Step 1: Add Series and Categories
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
*加入系列與類別可使資料呈現更有條理。*

### Populating Series Data and Formatting
**Overview:**  
將資料點填入圖表，並調整外觀以提升可讀性，特別是負值的顯示。

#### Step 1: Populate Series Data
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
*本節示範如何填入資料並套用顏色格式，以提升視覺效果。*

## Common Issues and Solutions
- **Memory leaks** – 請務必如範例所示將 `Presentation` 物件包在 `try/finally` 區塊中，以保證釋放。  
- **Incorrect cell coordinates** – 記得列與欄是從零開始編號，索引錯誤會導致 `NullPointerException`。  
- **License not found** – 請將授權檔放在應用程式的工作目錄，或使用 `License.setLicense("Aspose.Slides.Java.lic")` 明確設定路徑。

## Frequently Asked Questions

**Q: 我可以在 .NET Core 中使用此方法嗎？**  
A: 可以。Aspose.Slides for Java 可在任何 JVM 上執行，您可透過 IKVM 或 JNI 等橋接方式從 .NET Core 呼叫 Java 程式碼。

**Q: 開發階段需要付費授權嗎？**  
A: 免費試用授權足以支援開發與測試。正式上線則需購買授權。

**Q: 如何在建立後變更圖表類型？**  
A: 您可以呼叫 `chart.getChartData().setChartType(ChartType.Pie)` 來切換為其他圖表類型。

**Q: 能否以程式方式加入資料標籤？**  
A: 能。使用 `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` 即可在圖表上顯示數值。

**Q: 簡報可以儲存為哪些格式？**  
A: Aspose.Slides 支援 PPTX、PPT、PDF、XPS，以及 PNG、JPEG 等多種影像格式。

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}