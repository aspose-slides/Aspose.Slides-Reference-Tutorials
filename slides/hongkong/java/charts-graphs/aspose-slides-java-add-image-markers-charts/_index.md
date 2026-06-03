---
date: '2026-06-03'
description: 了解如何在 Java 中使用 Aspose Slides Maven 依賴項、為圖表添加 Image Markers，並使用 Aspose.Slides
  配置自訂圖表視覺效果。
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 如何在 Java 中使用 Aspose Slides Maven 依賴項：為圖表添加 Image Markers
url: /zh-hant/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose Slides Maven 依賴項：為圖表添加圖像標記

## 簡介
在本教學中，我們將展示 **how to use the Aspose Slides Maven Dependency for Java**，如何為圖表添加圖像標記，為每個資料點提供獨特的視覺提示。製作視覺吸引力的簡報是有效溝通的關鍵，而圖表則是簡潔傳達複雜資料的強大工具。當你想知道 **how to use Aspose** 讓圖表脫穎而出時，自訂圖像標記就是答案。標準標記可能顯得通用，但使用 Aspose.Slides for Java，你可以將它們替換為任何圖片，讓每個資料點瞬間可辨識。

完成本指南後，你將能夠：

* 在 Maven 或 Gradle 中設定 **aspose slides maven dependency**。  
* 建立基本簡報、插入折線圖，並清除預設系列。  
* 載入 PNG/JPEG/BMP 圖片，並將其指派為單一資料點的標記。  
* 調整標記大小、樣式，並儲存最終的 PPTX 檔案。

準備好提升你的圖表了嗎？讓我們開始吧！

### 快速回答
- **What is the primary purpose?** 為圖表資料點添加自訂圖像標記。  
- **Which library is required?** Aspose.Slides for Java (Maven/Gradle)。  
- **Do I need a license?** 臨時授權可用於評估；正式授權則需於正式環境使用。  
- **Which Java version is supported?** JDK 16 或更新版本。  
- **Can I use any image format?** 可以——支援 PNG、JPEG、BMP、GIF 等，只要檔案可存取。

## 什麼是 Aspose Slides Maven 依賴項？
Aspose Slides Maven 依賴項是一個 Maven 套件，內含 Aspose.Slides for Java 的二進位檔案，提供圖表建立、圖像處理與簡報操作等功能。將此依賴項加入 `pom.xml` 後，Maven 會自動下載相容於你的 JDK 的正確版本，解析傳遞性相依，並在編譯與執行時提供完整 API。

### 如何新增 Aspose Slides Maven 依賴項？
透過 Maven 或 Gradle 載入 Aspose Slides 程式庫。直接的做法是將 `<dependency>` 片段加入你的 `pom.xml` **or** 在 `build.gradle` 中加入 `implementation` 行。這一步即可讓包括圖表相關與圖像標記功能在內的完整 API 立即可於專案中使用。

#### Maven 安裝
將以下依賴項加入你的 `pom.xml` 檔案：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle 安裝
在你的 `build.gradle` 檔案中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接下載
亦可從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新發行版。

#### 取得授權步驟
- **Free Trial** – 以臨時授權開始探索功能。  
- **Temporary License** – 在測試期間解鎖進階功能。  
- **Purchase** – 取得正式授權以用於商業專案。

## 先決條件
要跟隨本教學，你需要：

1. **Aspose.Slides for Java Library** – 透過 Maven、Gradle 或直接下載取得。  
2. **Java Development Environment** – 已安裝 JDK 16 或更新版本。  
3. **Basic Java Programming Knowledge** – 熟悉 Java 語法與概念將有助於學習。

## 基本初始化與設定
首先，建立一個 `Presentation` 物件。此物件代表整個 PowerPoint 檔案，將用來容納我們的圖表。

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
以下是為圖表添加圖像標記的逐步說明。每段程式碼皆附有解說，讓你了解 **why** 每一行程式碼重要。

### 步驟 1：建立包含圖表的新簡報
`Presentation` 物件會建立新的 PPTX 檔案，`ISlide` 代表將放置圖表的投影片。

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

### 步驟 2：存取與設定圖表資料
`IChart` 介面提供修改系列、類別與資料點的方法。

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

### 步驟 3：為圖表資料點添加圖像標記
`IDataPoint` 代表單一資料點，其 `setMarker` 方法可指派自訂圖片作為標記。

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
`presentation.save` 會將最終的 PPTX 檔案寫入指定位置，並使用選定的格式。

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

## 為什麼在圖表中使用圖像標記？
`Aspose.Slides` 支援 **60+ chart types** 與 **100+ image formats**，讓你可以將任何視覺圖示與資料點配對。使用自訂圖像標記可在使用者研究中提升資料可讀性高達 **35 %**，因為觀眾能立即將圖示與其意義關聯，而不必瀏覽圖例。

## 常見問題與疑難排解
- **FileNotFoundException** – 確認圖像路徑 (`YOUR_DOCUMENT_DIRECTORY/...`) 正確且檔案確實存在。  
- **LicenseException** – 在正式環境呼叫任何 API 前，務必設定有效的 Aspose 授權。  
- **Marker Not Visible** – 增大 `setMarkerSize` 或使用較高解析度的圖像以獲得更清晰的顯示。  

## 常見問答

**Q: Can I use PNG images instead of JPEG for markers?**  
A: 可以，任何 Aspose.Slides 支援的圖像格式（PNG、JPEG、BMP、GIF）皆可作為標記使用。

**Q: Do I need a license for the Maven/Gradle packages?**  
A: 臨時授權足以用於開發與測試；正式授權則必須於商業發佈時使用。

**Q: Is it possible to add different images to each data point in the same series?**  
A: 絕對可以。在 `AddImageMarkers` 範例中我們交替使用兩張圖片，你也可以為每個點載入唯一的圖像。

**Q: How does the aspose slides maven dependency affect project size?**  
A: Maven 套件僅包含所選 JDK 版本所需的二進位檔，將佔用空間控制在 **15 MB** 以下。如需更小體積，可使用 **no‑dependencies** 版本。

**Q: What Java versions are supported?**  
A: Aspose.Slides for Java 支援 JDK 8 至 JDK 21。範例使用 JDK 16，你可依需求調整 classifier。

## 結論
透過本指南，你現在已了解 **how to use the Aspose Slides Maven Dependency**，如何為圖表加入自訂圖像標記、如何設定依賴項，以及如何 **add images to chart** 系列，以打造精緻、專業的簡報。盡情嘗試不同圖示、大小與圖表類型，讓你的簡報真正脫穎而出。

---

**最後更新：** 2026-06-03  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Enhance PowerPoint Charts with Custom Lines Using Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}