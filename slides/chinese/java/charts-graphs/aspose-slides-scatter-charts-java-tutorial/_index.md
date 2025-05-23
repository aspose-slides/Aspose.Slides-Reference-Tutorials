---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides for Java 创建动态散点图。使用可自定义的图表功能增强您的演示文稿。"
"title": "使用 Aspose.Slides 在 Java 中创建和自定义散点图"
"url": "/zh/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 中创建和自定义散点图

使用 Java 和 Aspose.Slides 添加动态散点图，增强您的演示文稿效果。本教程将指导您轻松设置目录、初始化演示文稿、创建散点图、管理图表数据、自定义序列类型和标记以及保存工作。

**您将学到什么：**
- 设置用于存储演示文件的目录
- 使用 Aspose.Slides 初始化和操作演示文稿
- 在幻灯片上创建散点图
- 管理和向图表系列添加数据
- 自定义图表系列类型和标记
- 保存已修改的演示文稿

首先，请确保您具备必要的先决条件。

## 先决条件

要遵循本教程，请确保您已具备：
- **Aspose.Slides for Java**：需要 25.4 或更高版本。
- **Java 开发工具包 (JDK)**：需要 JDK 8 或更高版本。
- 具备 Java 编程基础知识并熟悉 Maven 或 Gradle 构建工具。

## 设置 Aspose.Slides for Java

在开始编码之前，请使用以下方法之一将 Aspose.Slides 集成到您的项目中：

### Maven
将此依赖项包含在您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
将此行添加到您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，从下载最新的 Aspose.Slides for Java [Aspose 版本](https://releases。aspose.com/slides/java/).

#### 许可证获取
- **免费试用**：从 30 天免费试用开始探索功能。
- **临时执照**：获取临时许可证以进行延长测试。
- **购买**：购买许可证以获得完全访问和支持。

现在，通过添加必要的导入来初始化 Java 应用程序中的 Aspose.Slides，如下所示。

## 实施指南

### 目录设置
首先，确保我们的目录存在，用于存储演示文稿文件。此步骤可防止文件保存过程中出现错误。

#### 如果目录不存在则创建
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // 创建目录
    new File(dataDir).mkdirs();
}
```
此代码片段检查指定的目录，如果不存在则创建它。它使用 `File.exists()` 验证存在和 `File.mkdirs()` 创建目录。

### 演示初始化

接下来，初始化您将添加散点图的演示对象。

#### 初始化您的演示文稿
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
这里， `new Presentation()` 创建一个空白演示文稿。我们直接访问第一张幻灯片进行操作。

### 图表创建
接下来在我们初始化的幻灯片上创建散点图。

#### 将散点图添加到幻灯片
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
此代码片段在第一张幻灯片中添加了一个带有平滑线条的散点图。参数定义了图表的位置和大小。

### 图表数据管理
现在让我们通过清除任何现有系列并添加新系列来管理我们的图表数据。

#### 管理图表系列
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// 向图表添加新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
此部分清除现有数据并向散点图添加两个新系列。

### 散点图系列的数据点添加
为了可视化我们的数据，我们在散点图中的每个系列中添加点。

#### 添加数据点
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
我们使用 `addDataPointForScatterSeries()` 将数据点附加到我们的第一个系列。参数定义 X 和 Y 的值。

### 系列类型和标记修改
通过改变每个系列中标记的类型和样式来定制图表的外观。

#### 定制系列
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// 修改第二个系列
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
这些更改将系列类型调整为使用直线和标记。我们还设置了标记的大小和符号，以便进行视觉区分。

### 演示文稿保存
最后，保存所做的所有修改的演示文稿。

#### 保存您的演示文稿
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
使用 `SaveFormat.Pptx` 指定保存文件的 PowerPoint 格式。此步骤对于保存所有更改至关重要。

## 实际应用
以下是一些实际用例：
1. **财务分析**：使用散点图显示股票随时间的变化趋势。
2. **科学研究**：代表需要分析的实验数据点。
3. **项目管理**：可视化资源分配和进度指标。

将 Aspose.Slides 集成到您的系统中，您可以自动生成报告，从而提高生产力和准确性。

## 性能考虑
为了获得最佳性能：
- 通过保存后处理演示文稿来管理内存使用情况。
- 对大型数据集使用高效的数据结构。
- 尽量减少循环内的资源密集型操作。

最佳实践确保即使复杂的图表操作也能顺利执行。

## 结论
在本教程中，您学习了如何设置目录、初始化 Aspose.Slides 演示文稿、创建和自定义散点图、管理系列数据、修改标记以及保存工作。为了进一步探索 Aspose.Slides 的功能，您可以尝试探索动画和幻灯片切换等更高级的功能。

**后续步骤**：尝试不同的图表类型或将这些技术集成到更大的 Java 项目中。

## 常问问题

### 如何更改标记的颜色？
要更改标记颜色，请使用 `series.getMarker().getFillFormat().setFillColor(ColorObject)`， 在哪里 `ColorObject` 是您想要的颜色。

### 我可以向散点图添加两个以上的系列吗？
是的，您可以通过重复添加新系列和数据点的过程来添加所需数量的系列。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}