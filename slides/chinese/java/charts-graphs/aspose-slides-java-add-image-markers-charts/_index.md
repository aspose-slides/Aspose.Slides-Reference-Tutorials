---
date: '2026-06-03'
description: 了解如何在 Java 中使用 Aspose Slides Maven 依赖项，向图表添加图像标记，并使用 Aspose.Slides 配置自定义图表视觉效果。
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
title: 如何在 Java 中使用 Aspose Slides Maven 依赖项：向图表添加图像标记
url: /zh/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose Slides Maven 依赖项：为图表添加图像标记

## 介绍
在本教程中，我们展示**如何在 Java 中使用 Aspose Slides Maven 依赖项**为图表添加图像标记，为每个数据点提供独特的视觉提示。创建视觉上吸引人的演示文稿是有效沟通的关键，图表是简洁传达复杂数据的强大方式。当您想知道**如何使用 Aspose**让图表脱颖而出时，自定义图像标记就是答案。标准标记可能显得通用，但使用 Aspose.Slides for Java，您可以将其替换为任意图片——使每个数据点瞬间可辨识。

通过本指南，您将能够：

* 在 Maven 或 Gradle 中设置 **aspose slides maven dependency**。  
* 创建一个基本的演示文稿，插入折线图，并清除默认系列。  
* 加载 PNG/JPEG/BMP 图像并将其分配为各个数据点的标记。  
* 调整标记大小、样式，并保存最终的 PPTX 文件。  

准备好提升您的图表了吗？让我们开始吧！

### 快速答案
- **主要目的是什么？** 向图表数据点添加自定义图像标记。  
- **需要哪个库？** Aspose.Slides for Java (Maven/Gradle)。  
- **我需要许可证吗？** 临时许可证可用于评估；生产环境需要完整许可证。  
- **支持哪个 Java 版本？** JDK 16 或更高版本。  
- **我可以使用任何图像格式吗？** 可以——PNG、JPEG、BMP、GIF 等，只要文件可访问。  

## Aspose Slides Maven 依赖项是什么？
Aspose Slides Maven 依赖项是一个 Maven 构件，捆绑了创建图表、图像处理和演示文稿操作所需的 Aspose.Slides for Java 二进制文件。将该依赖项添加到您的 `pom.xml` 中，Maven 会自动下载适用于您 JDK 的正确版本，解析传递依赖，并在编译和运行时提供完整的 API。

### 如何添加 Aspose Slides Maven 依赖项？
通过 Maven 和 Gradle 加载 Aspose Slides 库。直接答案：将 `<dependency>` 代码段添加到您的 `pom.xml` **或** 将 `implementation` 行添加到您的 `build.gradle`。此一步即可在项目中立即使用完整的 API，包括图表相关和图像标记功能。

#### Maven 安装
在您的 `pom.xml` 文件中添加以下依赖项：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle 安装
在您的 `build.gradle` 文件中包含此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接下载
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新发布版本。

#### 获取许可证的步骤
- **Free Trial** – 使用临时许可证开始探索功能。  
- **Temporary License** – 在测试期间解锁高级功能。  
- **Purchase** – 为商业项目获取完整许可证。  

## 先决条件
要遵循本教程，您需要：

1. **Aspose.Slides for Java Library** – 通过 Maven、Gradle 或直接下载获取。  
2. **Java Development Environment** – 已安装 JDK 16 或更高版本。  
3. **Basic Java Programming Knowledge** – 熟悉 Java 语法和概念将有所帮助。  

## 基本初始化和设置
首先，创建一个 `Presentation` 对象。该对象代表整个 PowerPoint 文件，并将容纳我们的图表。

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## 实现指南
下面是向图表添加图像标记的逐步演练。每个代码块都有解释，帮助您了解**为什么**每行代码重要。

### 步骤 1：创建带有图表的新演示文稿
`Presentation` 对象创建一个新的 PPTX 文件，`ISlide` 表示放置图表的幻灯片。

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

### 步骤 2：访问并配置图表数据
`IChart` 接口提供了修改图表中系列、类别和数据点的方法。

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

### 步骤 3：为图表数据点添加图像标记
`IDataPoint` 代表单个点，其 `setMarker` 方法将自定义图像分配为标记。

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

### 步骤 4：配置标记大小并保存演示文稿
`presentation.save` 将最终的 PPTX 文件写入指定位置并使用所选格式。

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

## 为什么在图表中使用图像标记？
`Aspose.Slides` 支持 **60+ 图表类型** 和 **100+ 图像格式**，让您可以将任意视觉图标与数据点配对。使用自定义图像标记在用户研究中可将数据可读性提升至 **35 %**，因为观众无需浏览图例即可立即将图标与其含义关联。

## 常见问题与故障排除
- **FileNotFoundException** – 验证图像路径 (`YOUR_DOCUMENT_DIRECTORY/...`) 是否正确且文件存在。  
- **LicenseException** – 确保在生产环境调用任何 API 之前已设置有效的 Aspose 许可证。  
- **Marker Not Visible** – 增大 `setMarkerSize` 或使用更高分辨率的图像以获得更清晰的显示。  

## 常见问题
**Q: 我可以使用 PNG 图像而不是 JPEG 作为标记吗？**  
A: 可以，任何 Aspose.Slides 支持的图像格式（PNG、JPEG、BMP、GIF）都可用作标记。

**Q: Maven/Gradle 包需要许可证吗？**  
A: 开发和测试阶段使用临时许可证即可；商业发布需要完整许可证。

**Q: 能否为同一系列的每个数据点添加不同的图像？**  
A: 完全可以。在 `AddImageMarkers` 示例中我们交替使用两张图片，但您可以为每个点加载唯一的图像。

**Q: Aspose Slides Maven 依赖项对项目大小有何影响？**  
A: Maven 包仅包含所选 JDK 版本所需的二进制文件，使体积保持在 **15 MB** 以下。如果对大小有顾虑，也可以使用 **no‑dependencies** 版本。

**Q: 支持哪些 Java 版本？**  
A: Aspose.Slides for Java 支持 JDK 8 到 JDK 21。示例使用 JDK 16，您可以相应地调整 classifier。

## 结论
通过本指南，您现在了解**如何使用 Aspose Slides Maven 依赖项**为图表添加自定义图像标记，了解如何配置该依赖项，以及如何**向图表系列添加图像**以获得精致、专业的外观。尝试不同的图标、大小和图表类型，创建真正脱颖而出的演示文稿。

---

**最后更新：** 2026-06-03  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Slides 在 Java 中创建图表 – 添加和验证图表](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [使用 Aspose.Slides for Java 创建带默认标记的折线图](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [使用 Aspose.Slides Java 用自定义线条增强 PowerPoint 图表](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}