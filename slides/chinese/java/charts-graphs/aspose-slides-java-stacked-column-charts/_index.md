---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides for Java 创建专业的演示文稿。本指南涵盖了如何设置环境、添加堆叠柱形图以及如何自定义柱形图以提高清晰度。"
"title": "使用 Aspose.Slides 掌握 Java 中的堆叠柱形图——综合指南"
"url": "/zh/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 掌握 Java 中的堆叠柱形图：综合指南

## 介绍

结合 Aspose.Slides for Java 的强大功能，将富有洞察力的数据可视化效果融入您的演示文稿，提升您的演示文稿质量。无论您是准备业务报告还是展示项目统计数据，使用堆叠柱状图创建专业外观的幻灯片都非常简单。

在本教程中，我们将探索如何使用 Aspose.Slides for Java 创建动态演示文稿并添加美观的堆叠柱形图。学习完本指南后，您将掌握以下技能：
- 设置您的环境以使用 Aspose.Slides
- 从头开始创建演示文稿
- 添加和自定义百分比堆积柱形图
- 格式化图表轴和数据标签以提高清晰度

让我们深入研究如何创建吸引观众的演示文稿。

## 先决条件
在开始之前，请确保您具备以下条件：
- **Java 开发工具包 (JDK)：** 版本 8 或更高版本。
- **集成开发环境（IDE）：** 任何集成开发环境，如 IntelliJ IDEA 或 Eclipse。
- **Maven/Gradle：** 用于管理依赖项（可选但推荐）。
- **Java基础知识：** 熟悉 Java 编程概念。

## 设置 Aspose.Slides for Java
首先，您需要在项目中包含 Aspose.Slides 库。具体操作如下：

**Maven：**
将此依赖项添加到您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**
将其包含在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载：**
或者，从下载最新的 JAR [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).

### 许可证获取
您可以立即免费试用，探索 Aspose.Slides 的功能。如需移除评估限制，请考虑获取临时许可证或购买许可证。
- **免费试用：** 无需立即付费即可访问有限的功能。
- **临时执照：** 请求方式 [Aspose 的网站](https://purchase。aspose.com/temporary-license/).
- **购买：** 请访问购买页面以获得完全访问权限。

### 基本初始化
以下是在 Java 应用程序中初始化 Aspose.Slides 的方法：
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // 创建 Presentation 类的实例
        Presentation presentation = new Presentation();
        
        // 对展示对象执行操作
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## 实施指南

### 创建演示文稿并添加幻灯片
**概述：**
首先创建一个包含初始幻灯片的简单演示文稿。这是进一步增强的基础。

#### 步骤1：初始化演示对象
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // 创建新的演示实例
        Presentation presentation = new Presentation();
        
        // 参考第一张幻灯片（自动创建）
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 第 2 步：保存演示文稿
```java
// 将演示文稿保存到文件
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### 将百分比堆积柱形图添加到幻灯片
**概述：**
通过添加百分比堆积柱形图来增强您的幻灯片，以便于轻松比较数据。

#### 步骤 1：初始化并访问幻灯片
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // 下一步继续添加图表
    }
}
```

#### 步骤 2：将图表添加到幻灯片
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### 自定义图表轴数字格式
**概述：**
自定义图表垂直轴的数字格式以增强可读性。

#### 步骤 1：添加并访问图表
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

#### 步骤 2：设置自定义数字格式
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### 向图表添加系列和数据点
**概述：**
用数据系列填充您的图表，使其信息丰富且具有视觉吸引力。

#### 步骤 1：初始化演示文稿和图表
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

#### 步骤 2：添加数据系列
```java
// 清除现有系列并添加新系列
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// 根据需要添加更多数据点
```

### 格式化系列填充颜色
**概述：**
通过格式化每个系列的填充颜色来增强图表的美感。

#### 步骤 1：初始化并访问图表
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

#### 步骤 2：设置填充颜色
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// 对其他系列使用不同颜色重复此操作
```

### 格式化数据标签
**概述：**
通过自定义格式使数据标签更具可读性。

#### 步骤 1：访问图表系列和数据点
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

#### 第 2 步：自定义数据标签
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

## 结论
通过本指南，您已学习如何设置 Aspose.Slides for Java 并创建包含百分比堆叠柱形图的动态演示文稿。您可以根据自己的需求调整颜色和标签，进一步自定义图表。

编码愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}