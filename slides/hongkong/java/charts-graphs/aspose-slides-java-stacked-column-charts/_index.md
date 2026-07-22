---
date: '2026-07-22'
description: 了解 Aspose Slides Maven Dependency，於 Java 中建立堆疊柱狀圖、加入資料標籤、變更垂直軸數字格式，並將結果匯出為
  PPTX 檔案。
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency 可讓您在 Java 中建立堆疊柱狀圖、客製化資料標籤、調整垂直軸格式，並以簡潔、可投入生產的程式碼儲存為
  PPTX。
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: Aspose Slides Maven Dependency：Java 中的堆疊柱狀圖
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: Aspose Slides Maven Dependency：Java 中的堆疊柱狀圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven 依賴項：Java 堆疊柱狀圖

## 介紹

透過結合深入的資料視覺化，利用 **Aspose.Slides for Java** 的強大功能，提升您的簡報品質。本指南將教您 **建立堆疊柱狀圖**，讓您的簡報看起來更專業，無論是編寫商業報告或展示專案統計資料。完成本教學後，您將能夠：

- 設定環境，使用 **Aspose Slides Maven 依賴項**
- 從頭建立簡報
- **加入百分比堆疊圖** 並自訂外觀
- **格式化圖表資料標籤** 以及 **變更垂直軸的數字格式**
- **以單行程式碼將簡報儲存為 PPTX**

## 快速答覆
- **需要哪個函式庫？** 加入 `aspose-slides` Maven/Gradle 依賴項（請參閱下方「Aspose Slides Maven 依賴項」）。  
- **哪種圖表類型會產生堆疊視圖？** 使用 `ChartType.PercentsStackedColumn` 以建立百分比堆疊柱狀圖。  
- **如何變更軸的數字格式？** 呼叫 `IAxis.setNumberFormat()` 並設定 `setNumberFormatLinkedToSource(false)`。  
- **我可以自訂資料標籤嗎？** 可以——遍歷每個 `IChartDataPoint` 並指派自訂的 `ITextFrame`。  
- **如何儲存檔案？** 呼叫 `presentation.save("output.pptx", SaveFormat.Pptx)`。

## 什麼是堆疊柱狀圖？
堆疊柱狀圖會在每個類別欄位中垂直堆疊多個資料系列，**百分比堆疊** 變體會將每個欄位正規化為 100 %，以便輕鬆比較比例。此格式讓觀眾能快速評估各組件在不同類別中的貢獻比例，使趨勢與相對大小一目了然。

## 為什麼使用 Aspose.Slides for Java？
Aspose.Slides for Java 讓您 **無需 Microsoft Office** 即可產生、編輯與轉換 PowerPoint 檔案，並支援 **超過 50 種輸出格式**，可在 Windows、Linux 與 macOS 上執行。此函式庫完全在 JRE 上運行，適合伺服器端自動化與高吞吐量報告，同時提供對圖表物件、投影片版面與文件屬性的精細控制，是企業級簡報產生的理想選擇。

## 前置條件
- **Java Development Kit (JDK)：** 8 或以上  
- **IDE：** IntelliJ IDEA、Eclipse 或任何相容 Java 的編輯器  
- **建置工具：** Maven 或 Gradle（可選，但建議使用）  
- **基本的 Java 知識**——您應該熟悉類別與方法  

## 設定 Aspose.Slides for Java
要開始使用，先將 Aspose.Slides 函式庫加入您的專案。

### Aspose Slides Maven 依賴項
將以下內容加入您的 `pom.xml`（這就是您需要的 **aspose slides maven dependency**）：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 替代方案
如果您偏好使用 Gradle，請在 `build.gradle` 中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
亦可從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新的 JAR。

### 取得授權
您可以先使用免費試用版探索 Aspose.Slides 功能。若要移除評估限制，請考慮取得臨時或正式授權。

- **免費試用：** 可使用有限功能，且無需立即付費。  
- **臨時授權：** 可透過 [Aspose 的網站](https://purchase.aspose.com/temporary-license/) 申請。  
- **購買授權：** 前往購買頁面取得完整功能。

### 基本初始化
`Presentation` 是 Aspose.Slides 的核心類別，代表記憶體中的 PowerPoint 檔案。以下最小範例示範如何建立 `Presentation` 物件：

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## 實作指南

### 建立簡報並新增投影片
**概述：**  
首先，我們將建立一個空白簡報，並確認投影片已存在。

#### 步驟 1：初始化 Presentation 物件
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 步驟 2：儲存簡報
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### 向投影片加入百分比堆疊柱狀圖
**概述：**  
現在我們將 **百分比堆疊圖** 放置於第一張投影片上。

`ChartType.PercentsStackedColumn` 指定了百分比堆疊柱狀圖類型。

#### 步驟 1：初始化並存取投影片
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### 步驟 2：將圖表加入投影片
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### 自訂圖表軸的數字格式
**概述：**  
為了提升可讀性，我們將 **變更垂直軸格式** 以顯示百分比。

`IAxis` 為代表圖表軸的介面，可用於格式與比例的調整。

#### 步驟 1：新增並存取圖表
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### 步驟 2：設定自訂數字格式
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### 向圖表加入系列與資料點
**概述：**  
我們將使用範例資料系列填充圖表。

#### 步驟 1：初始化簡報與圖表
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 步驟 2：新增資料系列
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### 格式化系列填色
**概述：**  
為每個系列設定不同顏色，使圖表更易於閱讀。

#### 步驟 1：初始化並存取圖表
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### 步驟 2：設定填色
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### 格式化資料標籤
**概述：**  
現在我們將 **格式化圖表資料標籤**，使其顯示自訂文字。

`IChartDataPoint` 代表圖表系列中的單一資料點，`ITextFrame` 則保存標籤文字。

#### 步驟 1：存取圖表系列與資料點
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 步驟 2：自訂資料標籤
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## 常見問題與解決方案
- **圖表顯示空白：** 請確認已加入至少一個資料系列與資料點後再儲存。  
- **軸的數字未顯示百分比：** 記得設定 `verticalAxis.setNumberFormatLinkedToSource(false)`，否則自訂格式會被忽略。  
- **授權評估訊息：** 在建立 `Presentation` 物件前先套用有效的授權檔，以移除評估橫幅。

## 常見問答

**Q: 我可以在 Java 11 或更新的版本使用此程式碼嗎？**  
A: 可以。函式庫支援 JDK 8 以上；只需使用相應的 classifier（例如 `jdk16` 代表 JDK 16 或更高）。

**Q: 如何將圖表匯出為影像而非 PPTX？**  
A: 在將圖表加入投影片後，使用 `chart.getImage().save("chart.png", ImageFormat.Png);`。

**Q: 能否為堆疊柱狀圖加入圖例？**  
A: 當然可以。呼叫 `chart.getChartTitle().addTextFrameForOverriding("My Chart");` 並依需求設定 `chart.getLegend()`。

**Q: 若簡報產生後需要更新資料，該怎麼做？**  
A: 您可以修改 `ChartDataWorkbook` 的儲存格，然後呼叫 `chart.refresh();` 以套用變更。

**Q: Aspose.Slides 能在 Linux 伺服器上執行嗎？**  
A: 能。此函式庫純 Java，能在任何安裝相容 JRE 的作業系統上執行。

## 結論
透過本指南，您已學會如何使用 **Aspose Slides Maven 依賴項** 在 Java 中 **建立堆疊柱狀圖**，從環境設定到精細的視覺樣式調整。可自行嘗試不同的資料集、顏色與標籤格式，讓您的報告更具吸引力。

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [How to create clustered column chart in Java with Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [How to Set Number Formats in Chart Data Points Using Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}