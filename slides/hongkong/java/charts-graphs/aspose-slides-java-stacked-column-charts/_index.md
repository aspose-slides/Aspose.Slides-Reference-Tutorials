---
date: '2026-01-24'
description: 學習如何使用 Aspose.Slides for Java 建立圖表，包括百分比堆疊柱狀圖設定、坐標軸格式化以及資料標籤自訂。
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: 如何使用 Aspose.Slides Java 建立圖表：堆疊柱形圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通 Java Aspose.Slides 堆疊柱狀圖：完整指南

## 介紹

透過 Aspose.Slides for Java 的強大功能，為您的簡報加入深入的資料對。

我們將一步步說明環境設定柱起來既精緻又專業。

現在就開始打造能吸引觀眾目光的簡報吧。

## 快速答覆
- **主要使用的函式庫是什麼？** Aspose.Slides for Java
- **哪個 Maven 套件可加入此函式庫？** `com.aspose:aspose-slides`（請參考 *aspose slides maven* 章節）
- **柱狀圖？** 在呼叫 `addChart` 時？** 可以 – 設定 `verticalAxis.setNumberFormat於同一根柱子中，讓您在比較總量的同時，也能看到各組成部分的貢獻度。**百分比堆疊柱狀圖** 會將每根柱子正規化為 100 %，非常適合展示各類別之間的比例關係。

## 為什麼選擇 Aspose.Slides for Java？
- **不需安裝 Office** – 可在任何伺服器上產生 PPTX 檔案。  
- **功能完整的圖表 API** – 支援所有圖表類型，包括百分比堆疊柱狀圖。  
- **跨平台相容** – 可在 Windows、Linux 與 macOS 上執行。  
- **簡易的 Maven/Gradle 整合** – 請參考下方 *aspose slides maven* 片段。

## 前置需求
- **Java Development Kit (JDK)：** 8 版或以上。  
- **IDE：** IntelliJ IDEA、Eclipse，或任何支援 Java 的編輯器。  
- **建置工具（可選）：** Maven 或 Gradle，用於管理相依性。  
- **基本的 Java 知識** – 需要熟悉類別、方法與集合等概念。

## 設定 Aspose.Slides for Java
要開始使用，必須在專案中加入 Aspose.Slides 函式庫。

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

**直接下載:**  
亦可從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新 JAR。

### 取得授權
您可以先使用免費試用版體驗 Aspose.Slides 功能。若要移除評估限制，請考慮取得臨時或正式授權。

- **免費試用:** 可使用有限功能，無需立即付費。  
- **臨時授權:** 可透過 [Aspose 官方網站](https://purchase.aspose.com/temporary-license/) 申請。  
- **正式購買:** 前往購買頁面取得完整授權。

### 基本初始化
以下示範如何在 Java 應用程式中初始化 Aspose.Slides：  
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

## 如何建立圖表：逐步指南

### 建立簡報並新增投影片
**概觀:** 先建立一個簡單的簡報與第一張投影片，作為後續操作的基礎。

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
```java
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### 在投影片中加入百分比堆疊柱狀圖
**概觀:** 為投影片加入 **百分比堆疊柱狀圖**，以便輕鬆比較資料。

#### 步驟 1：初始化並取得投影片  
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

### 自訂圖表座標軸的數字格式
**概觀:** 為圖表的垂直座標軸設定自訂的數字格式，提高可讀性。

#### 步驟 1：加入並取得圖表  
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

### 為圖表加入系列與資料點
**概觀:** 為圖表 **加入系列資料**，使其內容豐富且具視覺吸引力。

#### 步驟 1：初始化 Presentation 與圖表  
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

#### 步驟 2：加入資料系列  
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### 設定系列填色
**概觀:** 透過設定每個系列的填色，提升圖表的美觀度。

#### 步驟 1：初始化並取得圖表  
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
**概觀:** 透過 **格式化圖表資料標籤**，讀且可自訂。

#### 步驟 1：取得圖表系列與資料點  
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

## 常見使用情境
- **季度銷售儀表板** – 以疊狀圖是否需要付費授權？**  
A: 免費試用版可建立圖換圖表類型嗎？**  
A: 可以，先移除Type` 新增圖表即可。

**Q: 如何將簡報匯出為 PDF？**  
A: 完成投影片編輯後，使用 `presentation.save("output.pdf", SaveFormat.Pdf);` 即可。

**Q: API 是否相容於 Java 11 以上版本？**  
A: 完全相容。函式庫支援 JDK 8 至 JDK 21，只需選擇對應的 classifier（例如 `jdk16`）。

**Q: 若需要加入超過三個系列該要重複加入系列的程式區塊，並為每個新系列調整工作表的儲存格參照即可。

## 結論
透過本指南，您已掌握 **如何使用 Aspose.Slides for Java 建立圖表**，從 Maven/Gradle 相依性設定，到自訂百分比堆疊柱狀圖的座標軸、系列顏色與資料標籤。請嘗試不同的資料集、套用自家品牌色彩，並將這些投影片整合至自動化報表流程中。

---

**最後更新日期：** 2026-01-24  
**測試環境：** Aspose.Slides 25.4（jdk16 classifier）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}