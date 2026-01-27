---
date: '2026-01-11'
description: 學習如何使用 Aspose Slides for Java、在圖表中加入圖像標記，並設定 Aspose Slides 的 Maven 依賴，以實現自訂圖表視覺效果。
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 如何使用 Aspose Slides Java - 在圖表中添加圖片標記
url: /zh-hant/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose Slides Java：為圖表添加圖像標記

## 簡介
製作視覺吸引的簡報是有效溝通的關鍵，而圖表則是簡潔傳達複雜資料的強大工具。當你想知道 **how to use Aspose** 讓圖表脫穎而出時，自訂圖像標記就是答案。標準標記可能顯得普通，但使用 Aspose.Slides for Java，你可以將它們替換為任何圖片——讓每個資料點即刻辨識。

在本教學中，我們將完整示範如何在折線圖中加入圖像標記，從設定 **Aspose Slides Maven dependency**、載入圖片到套用至資料點。完成後，你將熟悉 **how to add markers**、如何 **add images to chart** 系列，並擁有可直接執行的程式碼範例。

**你將學會**
- 如何設定 Aspose.Slides for Java（含 Maven/Gradle）
- 建立基本的簡報與圖表
- 為圖表資料點加入圖像標記
- 調整標記大小與樣式以獲得最佳視覺效果

準備好提升圖表品質了嗎？先來看看先決條件吧！

### 快速答覆
- **主要目的為何？** 為圖表資料點加入自訂圖像標記。  
- **需要哪個函式庫？** Aspose.Slides for Java（Maven/Gradle）。  
- **需要授權嗎？** 評估可使用臨時授權，正式上線需購買正式授權。  
- **支援哪個 Java 版本？** JDK 16 或更新版本。  
- **可以使用任何圖像格式嗎？** 可以，PNG、JPEG、BMP 等皆可，只要檔案可存取。

### 先決條件
要跟隨本教學，你需要：
1. **Aspose.Slides for Java 函式庫** – 透過 Maven、Gradle 或直接下載取得。  
2. **Java 開發環境** – 已安裝 JDK 16 以上。  
3. **基本的 Java 程式設計知識** – 熟悉 Java 語法與概念會更順利。

## 什麼是 Aspose Slides Maven Dependency？
Maven 依賴會為你的 Java 版本下載正確的二進位檔。將它加入 `pom.xml` 後，函式庫即可在編譯與執行時使用。

### Maven 安裝
在 `pom.xml` 檔案中加入以下依賴：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安裝
在 `build.gradle` 檔案中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
亦可從 [Aspose.Slides for Java 版本](https://releases.aspose.com/slides/java/) 下載最新發行版。

#### 取得授權步驟
- **免費試用** – 先使用臨時授權探索功能。  
- **臨時授權** – 測試期間解鎖進階功能。  
- **購買正式授權** – 商業專案必須取得正式授權。

## 基本初始化與設定
首先，建立一個 `Presentation` 物件。此物件代表整個 PowerPoint 檔案，亦會容納我們的圖表。

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## 實作指南
以下提供逐步說明，教你如何為圖表加入圖像標記。每段程式碼皆附有說明，讓你了解 **為何** 這麼寫。

### 步驟 1：建立含圖表的新簡報
我們在第一張投影片加入一個預設標記的折線圖。

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### 步驟 2：存取並設定圖表資料
先清除預設系列，然後自行新增系列，為自訂資料點做準備。

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### 步驟 3：為圖表資料點加入圖像標記  
以下示範 **how to add markers** 使用圖片。請將佔位路徑替換成實際圖檔所在位置。

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### 步驟 4：設定標記大小並儲存簡報  
調整標記樣式以提升可見度，最後寫出 PPTX 檔案。

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## 常見問題與除錯
- **FileNotFoundException** – 請確認圖像路徑 (`YOUR_DOCUMENT_DIRECTORY/...`) 正確且檔案確實存在。  
- **LicenseException** – 在正式環境呼叫任何 API 前，務必先設定有效的 Aspose 授權。  
- **標記未顯示** – 增大 `setMarkerSize` 或使用較高解析度的圖像以獲得更清晰的顯示。

## FAQ

**Q: 可以使用 PNG 圖片取代 JPEG 作為標記嗎？**  
A: 可以，任何 Aspose.Slides 支援的圖像格式（PNG、JPEG、BMP、GIF）皆可作為標記。

**Q: Maven/Gradle 套件需要授權嗎？**  
A: 開發與測試階段使用臨時授權即可，商業發佈則必須購買正式授權。

**Q: 能否在同一系列的不同資料點使用不同圖像？**  
A: 完全可以。在 `AddImageMarkers` 範例中我們交替使用兩張圖片，你也可以為每個點載入唯一圖像。

**Q: `aspose slides maven dependency` 會影響專案大小嗎？**  
A: Maven 套件僅包含選定 JDK 版本所需的二進位檔，保持相對合理的體積。如需更小體積，可改用 **no‑dependencies** 版本。

**Q: 支援哪些 Java 版本？**  
A: Aspose.Slides for Java 支援 JDK 8 至 JDK 21。範例使用 JDK 16，你可依需求調整 classifier。

## 結論
透過本指南，你已掌握 **how to use Aspose** 為圖表加入自訂圖像標記、設定 **Aspose Slides Maven dependency**，以及 **add images to chart** 系列的完整流程，讓簡報更具專業與視覺衝擊。可自行嘗試不同圖示、大小與圖表類型，打造真正脫穎而出的簡報。

---

**最後更新：** 2026-01-11  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}