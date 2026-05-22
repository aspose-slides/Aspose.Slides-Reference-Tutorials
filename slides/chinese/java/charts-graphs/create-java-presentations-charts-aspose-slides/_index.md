---
date: '2026-03-20'
description: 了解如何使用 Aspose.Slides 在 Java 演示文稿中添加图表，并快速生成演示文稿图表文件。
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: 如何使用 Aspose.Slides 在 Java 演示文稿中添加图表
url: /zh/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 向演示文稿添加图表

## 介绍

在当今节奏快速的商业环境中，创建能够有效传达数据的动态演示文稿至关重要。无论您是在准备财务报告、营销演示还是项目状态更新，**了解如何添加图表**到幻灯片都能显著提升观众的参与度。在本教程中，您将一步步学习如何添加 3D 堆积柱形图、配置其数据并保存最终文件——全部使用 Aspose.Slides for Java。

### 快速回答
- **主要库是什么？** Aspose.Slides for Java  
- **演示的图表类型是什么？** 3D Stacked Column  
- **我可以使用编程方式生成演示文稿图表文件吗？** 是的，使用下面展示的 API 方法  
- **推荐使用哪个 Java 版本？** JDK 16 或更高  
- **生产环境需要许可证吗？** 商业使用需要有效的 Aspose.Slides 许可证  

## 在 Aspose.Slides 中“如何添加图表”是什么？

Aspose.Slides for Java 提供了一套丰富的对象，允许您在无需 Microsoft Office 的情况下创建、编辑和导出 PowerPoint 文件。添加图表只需创建一个 `Presentation` 对象，插入图表形状，并通过内置工作簿向其提供数据。

## 为什么在 Java 演示文稿中添加图表？

- **视觉冲击力：** 图表将原始数字转换为一目了然的可视化。  
- **自动化：** 实时生成报告——适用于定时邮件摘要或仪表板。  
- **一致性：** 在所有生成的演示文稿中使用相同的样式和品牌。  
- **可移植性：** 只需一次方法调用即可导出为 PPTX、PDF 或图像。  

## 前置条件

- **库和依赖项：** 必须安装 Aspose.Slides for Java。  
- **环境设置：** 在 Java 环境中工作（建议使用 JDK 16 或更高）。  
- **知识基础：** 熟悉基本的 Java 编程概念会有所帮助。  

## 设置 Aspose.Slides for Java

### 安装

要将 Aspose.Slides 集成到您的项目中，请按照以下任一方式操作。

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

**Direct Download**：另外，您可以从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

### 许可证获取
- **免费试用：** 开始免费试用以探索功能。  
- **临时许可证：** 获取临时许可证以进行更长时间的测试。  
- **购买：** 获取完整许可证用于商业使用。

安装完成后，您即可实例化 `Presentation` 类，它是所有图表相关操作的入口。

## 实现指南

### 使用 3D 堆积柱形图向演示文稿添加图表

#### 概述
使用 Aspose.Slides 从头创建演示文稿非常简便。本节将在演示文稿的第一张幻灯片中添加一个 3D 堆积柱形图。

**步骤：**

1. **初始化 Presentation 对象**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
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

2. **解释参数**  
   - `ChartType.StackedColumn3D`：指定图表类型。  
   - 位置和大小 `(0, 0, 500, 500)`：决定图表在幻灯片上的显示位置。

### 配置图表数据

#### 概述
为了让图表有意义，需要配置其数据系列和类别。本节演示如何向图表添加特定的数据点。

**步骤：**

1. **访问图表的数据工作簿**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### 为图表设置 Rotation3D 属性

#### 概述
通过 3D 旋转属性提升图表的视觉效果。此自定义可让您调整视角和深度。

**步骤：**

1. **配置 3D 旋转**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **解释参数**  
   - `setRightAngleAxes(true)`：确保坐标轴垂直。  
   - 旋转值：调整 3D 视图的角度和深度。

### 在图表中填充系列数据

#### 概述
为图表填充数据点是分析的关键。本节将在图表的一个系列中添加具体数值。

**步骤：**

1. **添加数据点**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
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
微调图表外观可以提升可读性。本节介绍如何调整重叠属性以获得更好的数据可视化。

**步骤：**

1. **设置系列重叠**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### 保存演示文稿

#### 概述
配置完演示文稿后，将其保存到磁盘的所需格式。此步骤确保所有更改被保留。

**步骤：**

1. **保存演示文稿**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **图表显示平面** | 未设置 3D 旋转 | 调用 `setRotation3D` 并使用适当的 X/Y 值。 |
| **数据未显示** | 工作簿单元格未关联 | 确保 `fact.getCell` 引用正确的行/列索引。 |
| **文件未保存** | 路径不正确或缺少权限 | 验证 `outputFilePath` 可写且文件夹存在。 |

## 常见问题

**问：我可以生成除 PPTX 之外的演示文稿图表文件格式吗？**  
答：是的，Aspose.Slides 通过 `SaveFormat` 枚举支持 PDF、ODP 和图像格式。

**问：在开发阶段运行代码是否需要许可证？**  
答：临时或评估许可证可用于开发，但生产部署需要完整许可证。

**问：可以在同一幻灯片上添加多个图表吗？**  
答：当然。可多次调用 `slide.getShapes().addChart`，并使用不同的位置或大小。

**问：如何更改图表的配色方案？**  
答：使用 `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` 并设置 `SolidFillColor`。

**问：我可以将图表绑定到外部数据源（如数据库）吗？**  
答：可以。使用 JDBC 检索数据，然后在保存之前以编程方式填充工作簿单元格。

## 结论

您现在已经学习了**如何向 Java 演示文稿添加图表**、配置其数据、定制 3D 旋转、调整系列重叠并保存最终文件。这些知识使您能够实现报告自动化、保持品牌一致性，并在无需手动操作的情况下交付数据驱动的演示文稿。欲了解更深入的自定义——例如图例、坐标轴样式或主题应用——请查阅官方文档的全部功能。

如需更高级的功能和自定义选项，请参考 [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/)。  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose