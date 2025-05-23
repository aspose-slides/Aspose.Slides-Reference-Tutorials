---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides for Java 在 .NET 演示文稿中创建和自定义图表。按照本分步指南，增强演示文稿的数据可视化效果。"
"title": "Aspose.Slides for Java&#58; 在.NET演示文稿中创建图表"
"url": "/zh/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 在 .NET 演示文稿中创建图表
## 介绍
创建引人入胜的演示文稿通常需要集成图表等可视化数据，以增强观众的理解和参与度。如果您是一位开发人员，希望使用 Aspose.Slides for Java 为 .NET 演示文稿添加动态、可自定义的图表，那么本教程将为您量身定制。我们将深入讲解如何初始化演示文稿、添加各种图表类型、管理图表数据以及有效地格式化系列数据。
**您将学到什么：**
- 如何在您的 .NET 环境中设置和使用 Aspose.Slides for Java。
- 使用 Aspose.Slides 初始化新的演示文稿。
- 在幻灯片中添加和自定义图表。
- 管理图表数据工作簿。
- 格式化系列数据，尤其是处理负值。
过渡到先决条件部分将确保您已做好轻松跟进的准备。
## 先决条件
在深入使用 Aspose.Slides for Java 创建图表之前，让我们先概述一下您的需求：
### 所需的库和版本
确保您具有以下依赖项：
- **Aspose.Slides for Java**：版本 25.4 或更高版本。
### 环境设置要求
- 支持.NET应用程序的开发环境。
- 对 Java 编程概念有基本的了解。
### 知识前提
- 熟悉在 .NET 应用程序环境中创建演示文稿。
- 了解 Java 依赖项及其管理（Maven/Gradle）。
## 设置 Aspose.Slides for Java
要开始使用 Aspose.Slides，您需要将其作为依赖项添加到您的项目中。具体操作如下：
### Maven
将以下依赖项添加到您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
将其包含在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接下载
或者，您可以从 [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).
#### 许可证获取步骤
- **免费试用**：从临时许可证开始探索功能。
- **购买**：考虑购买许可证以供广泛使用。
#### 基本初始化和设置
以下是在代码中初始化 Aspose.Slides 的方法：
```java
import com.aspose.slides.Presentation;
// 初始化新的 Presentation 对象
Presentation pres = new Presentation();
try {
    // 你的逻辑在这里...
} finally {
    if (pres != null) pres.dispose();
}
```
此设置可确保资源管理得到有效处理。
## 实施指南
我们将指导您逐步实现这些功能。
### 初始化演示文稿
**概述：**
创建演示文稿实例为所有后续操作奠定了基础。此功能演示了如何使用 Aspose.Slides 从头开始。
#### 步骤1：导入必要的包
```java
import com.aspose.slides.Presentation;
```
#### 步骤 2：创建新的演示对象
以下是操作方法：
```java
Presentation pres = new Presentation();
try {
    // 您的代码逻辑在这里...
} finally {
    if (pres != null) pres.dispose(); // 确保资源被释放
}
```
*这确保了展示对象在使用后被正确处置，从而防止内存泄漏。*
### 将图表添加到幻灯片
**概述：**
在幻灯片中添加图表可以使数据可视化更有效、更吸引人。
#### 步骤1：导入必要的包
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```
#### 步骤2：初始化演示文稿并添加图表
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // 图表定制的附加逻辑...
} finally {
    if (pres != null) pres.dispose();
}
```
*在这里，我们在第一张幻灯片中按指定的坐标和尺寸添加了一个簇状柱形图。*
### 管理图表数据工作簿
**概述：**
有效地管理图表的数据工作簿使您能够无缝地操作系列和类别。
#### 步骤1：导入必要的包
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### 第 2 步：访问和清除数据工作簿
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 清除现有数据
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // 您的自定义逻辑在这里...
} finally {
    if (pres != null) pres.dispose();
}
```
*在添加新系列和类别时，清除工作簿对于从头开始至关重要。*
### 向图表添加系列和类别
**概述：**
此功能显示如何通过管理系列和类别添加有意义的数据点。
#### 步骤 1：添加系列和类别
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 清除现有系列和类别
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // 添加新系列和类别
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // 进一步定制逻辑...
} finally {
    if (pres != null) pres.dispose();
}
```
*添加系列和类别可以使数据呈现更有条理。*
### 填充系列数据和格式化
**概述：**
用数据点填充图表并格式化外观以增强可读性，尤其是在处理负值时。
#### 步骤 1：填充系列数据
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 添加系列和类别（重复使用以前的逻辑）
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // 负值的格式系列
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // 保存演示文稿
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*本节演示如何填充数据并应用颜色格式以实现更好的可视化。*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}