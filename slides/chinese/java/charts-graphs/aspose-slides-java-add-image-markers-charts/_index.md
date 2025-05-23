---
"date": "2025-04-17"
"description": "了解如何在 Aspose.Slides for Java 中通过添加自定义图像标记来增强您的图表。通过视觉上独特的演示文稿提升参与度。"
"title": "掌握 Aspose.Slides Java —— 向图表添加图像标记"
"url": "/zh/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握 Aspose.Slides Java：向图表添加图像标记

## 介绍
创建视觉吸引力强的演示文稿是有效沟通的关键，而图表是简洁传达复杂数据的强大工具。标准图表标记有时无法突出您的数据。使用 Aspose.Slides for Java，您可以通过添加自定义图像作为标记来增强图表，使其更具吸引力和信息量。

在本教程中，我们将探索如何使用 Java 中的 Aspose.Slides 库将图像标记集成到图表中。掌握这些技巧后，您将能够创建以独特的视觉元素吸引眼球的演示文稿。

**您将学到什么：**
- 如何设置 Aspose.Slides for Java
- 创建基本的演示文稿和图表
- 向图表数据点添加图像标记
- 配置标记设置以实现最佳可视化

准备好提升你的排行榜了吗？开始之前，我们先来了解一下先决条件！

### 先决条件
要遵循本教程，您需要：
1. **Aspose.Slides for Java 库**：通过 Maven 或 Gradle 依赖项获取它，或者直接从 Aspose 下载。
2. **Java 开发环境**：确保您的机器上安装了 JDK 16。
3. **基本的 Java 编程知识**：熟悉 Java 语法和概念将会很有帮助。

## 设置 Aspose.Slides for Java
在深入研究代码之前，让我们先用必要的库来设置我们的开发环境。

### Maven 安装
将以下依赖项添加到您的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安装
将其包含在您的 `build.gradle` 文件：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
或者，从下载最新版本 [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).

#### 许可证获取步骤
- **免费试用**：从临时许可证开始探索 Aspose.Slides 功能。
- **临时执照**：通过获取临时许可证来访问高级功能。
- **购买**：为了长期使用，请考虑购买完整许可证。

### 基本初始化和设置
初始化 `Presentation` 对象来开始创建幻灯片：

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // 添加幻灯片和图表的代码放在这里。
    }
}
```

## 实施指南
现在，让我们分解向图表系列添加图像标记的过程。

### 使用图表创建新的演示文稿
首先，我们需要一张幻灯片来添加我们的图表：

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // 初始化Presentation对象
        Presentation presentation = new Presentation();

        // 从集合中获取第一张幻灯片
        ISlide slide = presentation.getSlides().get_Item(0);

        // 向幻灯片添加带有标记的默认折线图
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### 访问和配置图表数据
接下来，我们将访问图表的数据工作表来管理系列：

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

        // 清除现有系列并添加新系列
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### 向图表数据点添加图像标记
现在到了令人兴奋的部分——添加图像作为标记：

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

        // 加载并添加图像作为标记
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // 添加带有图像的数据点作为标记
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

### 配置图表系列标记并保存演示文稿
最后，让我们调整标记大小以获得更好的可见性并保存我们的演示文稿：

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

        // 加载并添加图像作为标记（例如使用占位符路径）
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

## 结论
通过本指南，您学习了如何在 Aspose.Slides for Java 中通过添加自定义图像标记来增强图表效果。这种方法可以显著提升演示文稿的吸引力和清晰度。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}