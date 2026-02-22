---
date: '2026-02-22'
description: 學習如何在 Java 中使用 Aspose.Slides 建立堆疊柱形圖。本教學涵蓋 Aspose.Slides 的 Maven 依賴、加入百分比堆疊圖、格式化圖表資料標籤，以及將簡報儲存為
  PPTX。
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: 如何在 Java 中使用 Aspose.Slides 建立堆疊柱狀圖 – 完整指南
url: /zh-hant/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 使用 Aspose.Slides 建立堆疊直條圖 – 完整指南

## 簡介

提升你的簡報品質，透過 Aspose.Slides for Java 的強大功能加入深入的資料視覺化。在本指南中，你將 **建立堆疊直條圖** 投影片，呈現出專業的外觀，無論是製作商業報告或展示專案統計資料。完成本教學後，你將能夠：

- 使用 Aspose Slides Maven 依賴設定環境
- 從零開始建立簡報
- **加入百分比堆疊圖** 並自訂外觀
- **格式化圖表資料標籤** 與 **變更垂直座標軸格式**
- **以單行程式碼儲存為 PPTX** 檔案

讓我們一步步操作，立即開始打造引人入勝的簡報。

## 快速解答
- **需要什麼函式庫？** `aspose-slides` Maven/Gradle 依賴（請參閱以下「aspose slides maven dependency」）  
- **使用哪種圖表類型？** `ChartType.PercentsStackedColumn` 用於百分比堆疊直條圖  
- **如何變更座標軸的數字格式？** 使用 `IAxis.setNumberFormat()` 並停用與來源的連結  
- **我可以自訂資料標籤嗎？** 可以 – 迭代 `IChartDataPoint` 物件並設定自訂的 `ITextFrame`  
- **如何儲存檔案？** 呼叫 `presentation.save("output.pptx", SaveFormat.Pptx)`

## 什麼是堆疊直條圖？
堆疊直條圖會將多個資料系列以垂直柱狀方式堆疊在一起。使用 **百分比堆疊** 變體時，每根柱狀圖的總和恆為 100 %，方便比較各類別的比例貢獻。

## 為什麼要使用 Aspose.Slides for Java？
Aspose.Slides 提供純 Java API，無需安裝 Microsoft Office 即可在任何平台上運作。它對圖表物件提供精細的控制，支援多種格式，並允許以程式方式產生簡報——非常適合自動化報告或伺服器端文件產生。

## 先決條件
- **Java Development Kit (JDK)：** 8 或以上  
- **IDE：** IntelliJ IDEA、Eclipse 或任何相容 Java 的編輯器  
- **建置工具：** Maven 或 Gradle（非必須但建議使用）  
- **基本的 Java 知識** – 你應該對類別與方法相當熟悉  

## 設定 Aspose.Slides for Java
首先，將 Aspose.Slides 函式庫加入你的專案。

### Aspose Slides Maven 依賴
在你的 `pom.xml` 中加入以下內容（這就是你需要的 **aspose slides maven dependency**）：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 替代方案
如果你偏好使用 Gradle，請在 `build.gradle` 中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新的 JAR。

### 取得授權
你可以先使用免費試用版來探索 Aspose.Slides 功能。若要移除評估限制，請考慮取得臨時或正式授權。

- **免費試用：** 可使用有限功能，且無需立即付費。  
- **臨時授權：** 可透過 [Aspose 的網站](https://purchase.aspose.com/temporary-license/) 申請。  
- **正式購買：** 前往購買頁面取得完整功能。

### 基本初始化
以下是一段最小範例，示範如何建立 `Presentation` 物件：

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
**概觀：**  
首先，我們會建立一個空白簡報，並確認投影片已存在。

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

### 在投影片中加入百分比堆疊直條圖
**概觀：**  
現在我們將在第一張投影片上放置一個 **percentage stacked chart**。

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

### 自訂圖表座標軸數字格式
**概觀：**  
為了提升可讀性，我們將 **變更垂直座標軸格式** 為百分比。

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

### 為圖表加入系列與資料點
**概觀：**  
我們將使用範例資料系列填充圖表。

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
**概觀：**  
為每個系列指定不同顏色，使圖表更易閱讀。

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
**概觀：**  
現在我們將 **格式化圖表資料標籤**，使其顯示自訂文字。

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
- **圖表顯示為空白：** 請確認在儲存前已加入至少一個資料系列與資料點。  
- **座標軸數字未顯示百分比：** 記得設定 `verticalAxis.setNumberFormatLinkedToSource(false)`；否則自訂格式會被忽略。  
- **授權評估訊息：** 在建立 `Presentation` 物件前套用有效的授權檔案，以隱藏評估橫幅。

## 常見問答

**Q：我可以在 Java 11 或更新的版本使用此程式碼嗎？**  
A：可以。此函式庫支援 JDK 8 以上；只要使用相應的 classifier（例如 `jdk16` 用於 JDK 16 或更高）。

**Q：如何將圖表匯出為影像而非 PPTX？**  
A：在將圖表加入投影片後，使用 `chart.getImage().save("chart.png", ImageFormat.Png);`。

**Q：能否為堆疊直條圖加入圖例？**  
A：當然可以。呼叫 `chart.getChartTitle().addTextFrameForOverriding("My Chart");`，並依需求設定 `chart.getLegend()`。

**Q：如果需要在產生簡報後更新資料該怎麼辦？**  
A：你可以修改 `ChartDataWorkbook` 的儲存格，然後呼叫 `chart.refresh();` 以反映變更。

**Q：Aspose.Slides 能在 Linux 伺服器上執行嗎？**  
A：可以。此函式庫為純 Java，可在任何具相容 JRE 的作業系統上運行。

## 結論
透過本指南，你已學會如何使用 Aspose.Slides for Java **建立堆疊直條圖** 簡報，從環境設定到精細的視覺樣式。可嘗試不同的資料集、顏色與標籤格式，讓你的報告真正脫穎而出。

---

**最後更新：** 2026-02-22  
**測試環境：** Aspose.Slides 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}