---
"date": "2025-04-17"
"description": "了解如何透過新增自訂圖像標記來增強 Aspose.Slides for Java 中的圖表。透過視覺上獨特的演示來提高參與度。"
"title": "掌握 Aspose.Slides Java&#58;向圖表添加圖像標記"
"url": "/zh-hant/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握 Aspose.Slides Java：為圖表添加圖像標記

## 介紹
創建具有視覺吸引力的簡報是有效溝通的關鍵，而圖表是簡潔地傳達複雜數據的強大工具。標準圖表標記有時無法使您的數據脫穎而出。使用 Aspose.Slides for Java，您可以透過新增自訂圖像作為標記來增強圖表，使其更具吸引力和資訊量。

在本教程中，我們將探討如何使用 Java 中的 Aspose.Slides 庫將圖像標記整合到圖表中。透過掌握這些技巧，您將能夠創建以其獨特的視覺元素吸引註意力的簡報。

**您將學到什麼：**
- 如何設定 Aspose.Slides for Java
- 建立基本的簡報和圖表
- 在圖表資料點中新增圖像標記
- 配置標記設定以實現最佳視覺化

準備好提升你的排行榜了嗎？在開始之前，讓我們先來了解先決條件！

### 先決條件
要遵循本教程，您需要：
1. **Aspose.Slides for Java 函式庫**：透過 Maven 或 Gradle 依賴項取得它，或直接從 Aspose 下載。
2. **Java 開發環境**：請確保您的機器上安裝了 JDK 16。
3. **基本的 Java 程式設計知識**：熟悉 Java 語法和概念將會很有幫助。

## 設定 Aspose.Slides for Java
在深入研究程式碼之前，讓我們先用必要的函式庫來設定我們的開發環境。

### Maven 安裝
將以下相依性新增至您的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安裝
將其包含在您的 `build.gradle` 文件：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
或者，從下載最新版本 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

#### 許可證取得步驟
- **免費試用**：從臨時許可證開始探索 Aspose.Slides 功能。
- **臨時執照**：透過取得臨時許可證來存取進階功能。
- **購買**：為了長期使用，請考慮購買完整許可證。

### 基本初始化和設定
初始化 `Presentation` 物件來開始建立投影片：

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // 新增投影片和圖表的程式碼放在這裡。
    }
}
```

## 實施指南
現在，讓我們分解為圖表系列添加圖像標記的過程。

### 使用圖表建立新的簡報
首先，我們需要一張投影片來加入我們的圖表：

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // 初始化Presentation對象
        Presentation presentation = new Presentation();

        // 從集合中取得第一張投影片
        ISlide slide = presentation.getSlides().get_Item(0);

        // 在投影片中新增帶有標記的預設折線圖
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### 存取和配置圖表數據
接下來，我們將存取圖表的資料工作表來管理系列：

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

        // 清除現有系列並新增系列
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### 在圖表資料點中新增圖像標記
現在到了令人興奮的部分——添加圖像作為標記：

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

        // 加載並添加圖像作為標記
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // 添加帶有圖像的數據點作為標記
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

### 配置圖表系列標記並儲存簡報
最後，讓我們調整標記大小以獲得更好的可見性並保存我們的簡報：

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

        // 載入並新增圖像作為標記（例如使用佔位路徑）
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## 結論
透過遵循本指南，您已經學會如何透過新增自訂圖像標記來增強 Aspose.Slides for Java 中的圖表。這種方法可以顯著提高簡報的吸引力和清晰度。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}