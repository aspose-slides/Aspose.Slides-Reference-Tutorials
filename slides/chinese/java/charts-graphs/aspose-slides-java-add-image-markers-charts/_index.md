---
date: '2026-01-11'
description: 学习如何使用 Aspose Slides for Java，向图表添加图像标记，并配置 Aspose Slides Maven 依赖以实现自定义图表视觉效果。
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 如何使用 Aspose Slides Java - 向图表添加图像标记
url: /zh/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose Slides Java：向图表添加图像标记

## 简介
创建视觉上吸引人的演示文稿是有效沟通的关键，图表是简洁传达复杂数据的强大工具。当您思考 **how to use Aspose** 让图表脱颖而出时，自定义图像标记就是答案。标准标记可能显得通用，但使用 Aspose.Slides for Java，您可以将它们替换为任意图片——使每个数据点瞬间可辨。

在本教程中，我们将完整演示向折线图添加图像标记的全过程，包括设置 **Aspose Slides Maven dependency**、加载图像并将其应用于数据点。结束时，您将熟悉 **how to add markers**、如何 **add images to chart** 系列，并拥有可直接运行的代码示例。

**您将学习**
- 如何设置 Aspose.Slides for Java（包括 Maven/Gradle）
- 创建基本的演示文稿和图表
- 向图表数据点添加图像标记
- 配置标记大小和样式以获得最佳可视化

准备提升您的图表了吗？让我们在开始之前先了解前提条件！

### 快速解答
- **What is the primary purpose?** 添加自定义图像标记到图表数据点。  
- **Which library is required?** Aspose.Slides for Java（Maven/Gradle）。  
- **Do I need a license?** 临时许可证可用于评估；生产环境需要完整许可证。  
- **Which Java version is supported?** JDK 16 或更高。  
- **Can I use any image format?** 可以——PNG、JPEG、BMP 等，只要文件可访问。

### 前提条件
要跟随本教程，您需要：
1. **Aspose.Slides for Java Library** – 通过 Maven、Gradle 或直接下载获取。  
2. **Java 开发环境** – 已安装 JDK 16 或更高版本。  
3. **基本的 Java 编程知识** – 熟悉 Java 语法和概念会有所帮助。

## 什么是 Aspose Slides Maven 依赖？
Maven 依赖会为您的 Java 版本拉取正确的二进制文件。将其添加到 `pom.xml` 可确保库在编译时和运行时可用。


### Maven 安装

将以下依赖项添加到您的 `pom.xml` 文件中：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安装
将以下代码添加到您的 `build.gradle` 文件中：


```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新发布版本。

#### 获取许可证的步骤
- **Free Trial** – 使用临时许可证开始探索功能。  
- **Temporary License** – 在测试期间解锁高级功能。  
- **Purchase** – 为商业项目获取完整许可证。

## 基本初始化和设置
首先，创建一个“Presentation”对象。该对象代表整个 PowerPoint 文件，并将用于存放我们的图表。

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
下面是向图表添加图像标记的逐步演示。每个代码块都有说明，帮助您了解每行代码的 **原因**。

### 步骤 1：创建带图表的新演示文稿
我们在第一张幻灯片中添加了一个带有默认标记的折线图。

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
我们清除所有默认序列并添加我们自己的序列，为自定义数据点准备工作表。

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

### 步骤 3：向图表数据点添加图像标记  
这里我们演示如何使用图片添加标记。请将占位符路径替换为图片的实际位置。

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
我们调整标记样式以提高可见性，并写入最终的 PPTX 文件。

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

## 常见问题与故障排除
- **FileNotFoundException** – 验证图像路径（`YOUR_DOCUMENT_DIRECTORY/...`）是否正确且文件存在。  
- **LicenseException** – 确保在生产环境调用任何 API 前已设置有效的 Aspose 许可证。  
- **Marker Not Visible** – 增加 `setMarkerSize` 或使用更高分辨率的图像以获得更清晰的显示。

## 常见问题

**问：我可以使用 PNG 图像而不是 JPEG 作为标记吗？**  
**答：** 可以，任何 Aspose.Slides 支持的图像格式（PNG、JPEG、BMP、GIF）都可用作标记。

**问：Maven/Gradle 包需要许可证吗？**  
**答：** 开发和测试阶段临时许可证即可；商业发布需要完整许可证。

**问：能否在同一系列的每个数据点使用不同的图像？**  
**答：** 完全可以。在 `AddImageMarkers` 示例中我们在两张图片之间交替，但您可以为每个点加载唯一的图像。

**问：`aspose slides maven dependency` 对项目大小有什么影响？**  
**答：** Maven 包仅包含所选 JDK 版本所需的二进制文件，保持占用合理。如果对体积有顾虑，也可以使用 **no‑dependencies** 版本。

**问：支持哪些 Java 版本？**  
**答：** Aspose.Slides for Java 支持 JDK 8 到 JDK 21。示例使用 JDK 16，您可以相应调整 classifier。

## 结论
通过本指南，您现在了解了 **how to use Aspose** 为图表添加自定义图像标记，如何配置 **Aspose Slides Maven dependency**，以及如何 **add images to chart** 系列，以获得精致、专业的外观。尝试不同的图标、尺寸和图表类型，创建真正脱颖而出的演示文稿。

---

**最后更新：** 2026-01-11  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}