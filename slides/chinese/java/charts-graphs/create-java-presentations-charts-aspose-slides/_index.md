---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides 在 Java 中创建和配置带有图表的动态演示文稿。掌握如何高效地添加、自定义和保存演示文稿。"
"title": "使用 Aspose.Slides for Java 创建带有图表的 Java 演示文稿"
"url": "/zh/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 创建和配置带有图表的演示文稿

## 介绍

在当今快节奏的商业环境中，创建能够有效传达数据的动态演示文稿至关重要。无论您是在准备财务报告还是展示项目指标，添加图表都能显著提升演示文稿的影响力。本教程将指导您使用 Aspose.Slides for Java（一个功能强大的、旨在以编程方式处理演示文稿的库）创建和配置包含 3D 堆叠柱形图的演示文稿。

**您将学到什么：**
- 如何创建新的演示文稿
- 在幻灯片中添加和配置图表
- 自定义图表数据和外观
- 有效保存您的演示文稿

准备好掌握如何使用 Java 创建视觉上引人入胜的演示文稿了吗？让我们开始吧！

## 先决条件

在深入学习本教程之前，请确保您已满足以下先决条件：

- **库和依赖项**：必须安装 Aspose.Slides for Java。
- **环境设置**：在 Java 环境中工作（建议使用 JDK 16 或更高版本）。
- **知识库**：熟悉基本的 Java 编程概念将会很有帮助。

## 设置 Aspose.Slides for Java

### 安装

要将 Aspose.Slides 集成到您的项目中，请按照以下步骤操作：

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载**：或者，从下载最新版本 [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).

### 许可证获取
- **免费试用**：从免费试用开始探索功能。
- **临时执照**：获取临时许可证以进行延长测试。
- **购买**：获得商业使用的完整许可。

安装后，通过创建 `Presentation` 类。这为向演示文稿中添加图表和其他元素奠定了基础。

## 实施指南

### 创建并配置带有图表的演示文稿

#### 概述
使用 Aspose.Slides 从零开始创建演示文稿非常简单。在本节中，我们将在演示文稿的第一张幻灯片中添加一个 3D 堆积柱形图。

**步骤：**

1. **初始化演示对象**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // 初始化新的 Presentation 对象
           Presentation presentation = new Presentation();
           
           // 访问演示文稿中的第一张幻灯片
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // 在幻灯片的 (0,0) 位置添加一个 3D 堆积柱形图
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **解释参数**：
   - `ChartType.StackedColumn3D`：指定图表类型。
   - 位置和大小 `(0, 0, 500, 500)`：确定图表在幻灯片上出现的位置。

### 配置图表数据

#### 概述
为了使您的图表更有意义，请配置其数据系列和类别。本节演示如何向图表添加特定的数据点。

**步骤：**

1. **访问图表的数据工作簿**

   ```java
   public static void configureChartData(IChart chart) {
       // 设置包含图表数据的工作表的索引
       int defaultWorksheetIndex = 0;
       
       // 访问图表的数据工作簿
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // 添加两个带有名称的系列
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // 添加三个类别
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### 设置图表的 Rotation3D 属性

#### 概述
使用 3D 旋转属性增强图表的视觉吸引力。此自定义功能允许您调整视角和深度。

**步骤：**

1. **配置 3D 旋转**

   ```java
   public static void setRotation3D(IChart chart) {
       // 启用直角轴并配置 X、Y 方向的旋转和深度百分比
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **解释参数**：
   - `setRightAngleAxes(true)`：确保轴垂直。
   - 旋转值：调整 3D 视图的角度和深度。

### 在图表中填充系列数据

#### 概述
在图表中填充数据点对于分析至关重要。在这里，我们将向图表中的序列添加特定值。

**步骤：**

1. **添加数据点**

   ```java
   public static void populateSeriesData(IChart chart) {
       // 访问第二个图表系列
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // 为具有指定值的条形系列添加数据点
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### 调整图表中的系列重叠

#### 概述
微调图表的外观可以提高可读性。本节介绍如何调整重叠属性以实现更好的数据可视化。

**步骤：**

1. **设置系列重叠**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // 从图表中获取第二个系列并将其重叠设置为 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### 保存演示文稿

#### 概述
配置演示文稿后，请将其以所需格式保存到磁盘。此步骤可确保所有更改均已保存。

**步骤：**

1. **保存演示文稿**

   ```java
   public static void savePresentation(Presentation presentation) {
       // 将修改后的演示文稿保存到文件
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## 结论

现在您已经学习了如何使用 Aspose.Slides for Java 创建和配置带有图表的演示文稿。本指南涵盖了初始化演示文稿、添加 3D 堆积柱形图、配置数据系列和类别、设置旋转属性、填充系列数据、调整系列重叠以及保存最终演示文稿。

有关更多高级功能和自定义选项，请参阅 [Aspose.Slides for Java 文档](https://docs。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}