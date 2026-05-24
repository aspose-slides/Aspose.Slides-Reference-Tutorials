---
date: '2026-02-24'
description: 了解如何使用 Aspose.Slides for Java 自定义散点图。本指南将带您一步步创建、样式化并保存演示文稿中的动态散点图。
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: 在 Java 中自定义 Aspose 散点图
url: /zh/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 Java 中自定义 Aspose 散点图

在本教程中，您将学习如何使用强大的 Aspose.Slides for Java 库 **customize scatter chart aspose**。我们将演示如何设置项目、创建散点图、调整系列类型和标记，最后保存演示文稿。完成后，您将能够以编程方式生成专业外观的散点图，并根据品牌或报告需求定制每个视觉细节。

## 快速答案
- **我需要哪个库？** Aspose.Slides for Java (v25.4+).  
- **支持哪个 Java 版本？** JDK 8 或更高。  
- **我可以更改标记形状吗？** 可以 – 使用 `MarkerStyleType` 选择星形、圆形等。  
- **如何保存文件？** 调用 `pres.save("output.pptx", SaveFormat.Pptx)`。  
- **是否需要许可证？** 免费试用可用于开发；生产环境需要商业许可证。

## 什么是 “customize scatter chart aspose”？
使用 Aspose 自定义散点图意味着以编程方式定义图表的数据、外观和行为——从点坐标到标记符号——而无需手动打开 PowerPoint。这种方法非常适合自动化报告、数据驱动的演示或任何需要可重复、高质量可视化的场景。

## 为什么使用 Aspose.Slides 自定义散点图？
- **完全控制** – 通过 Java 代码修改系列类型、标记样式、颜色等。  
- **自动化** – 实时生成数十个图表，用于仪表板或批量报告。  
- **跨平台** – 在任何支持 Java 的操作系统上运行，无需安装 Office。  
- **性能** – 轻量级 API，高效处理大数据集。

## 先决条件

要跟随操作，请确保您拥有：

- **Aspose.Slides for Java**（v25.4 或更高）。  
- 已安装 **Java Development Kit (JDK)** 8 +。  
- 用于依赖管理的 Maven 或 Gradle（或手动下载 JAR）。  
- 基本的 Java 知识以及熟悉您选择的构建工具。

## 设置 Aspose.Slides for Java

使用以下方法之一将库集成到项目中。

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或从 [Aspose Releases](https://releases.aspose.com/slides/java/) 获取最新发布。

#### 许可证获取
- **免费试用** – 30 天评估。  
- **临时许可证** – 延长测试期。  
- **完整许可证** – 生产使用并提供高级支持。

## 步骤指南：自定义 Aspose 散点图

### 1️⃣ 为演示文件准备文件夹
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*原因说明:* 确保输出文件夹存在，可防止在稍后保存 PPTX 时出现 `FileNotFoundException`。

### 2️⃣ 创建新演示文稿并获取第一张幻灯片
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
全新的 `Presentation` 为您提供干净的画布；第一张幻灯片是我们放置图表的地方。

### 3️⃣ 添加平滑线散点图
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` 创建平滑线散点图，非常适合趋势可视化。

### 4️⃣ 清除默认系列并添加自定义系列
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
删除默认系列后，您可以完全控制要显示的数据。

### 5️⃣ 用数据点填充第一个系列
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` 接受 X 值单元格和 Y 值单元格，逐点构建散点图。

### 6️⃣ 自定义系列类型和标记外观
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
这里我们通过切换为直线、放大标记并选择不同符号（星形与圆形）来 **customize the scatter chart aspose**，以提升视觉清晰度。

### 7️⃣ 保存演示文稿
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
保存为 `Pptx` 可保留所有图表自定义，并使文件准备好共享或进一步编辑。

## 自定义散点图的常见用例
- **金融仪表盘** – 绘制股票价格与成交量。  
- **科学研究** – 显示带误差标记的实验测量。  
- **项目管理** – 对比任务的计划工作量与实际工作量。

## 性能技巧
- 在保存后释放 `Presentation` 对象（`pres.dispose()`），以释放本机资源。  
- 对于大数据集，先填充工作簿再绑定系列，以避免重复的 UI 刷新。  
- 在添加多个系列时复用单个 `IChartDataWorkbook` 实例。

## 常见问题

### 如何更改标记的颜色？
使用 `series.getMarker().getFillFormat().setFillColor(Color)`，其中 `Color` 是 `java.awt.Color` 的实例（例如 `Color.RED`）。

### 我可以向散点图添加超过两个系列吗？
当然可以。对每个额外的系列重复调用 `chart.getChartData().getSeries().add(...)`，并相应地填充其数据点。

### 是否可以为每个系列设置自定义图例？
可以。在创建系列后，调用 `series.getLegend().setText("Your Legend Text")` 来覆盖默认名称。

### 如何将图表导出为图像而不是 PPTX？
在配置图表后，调用 `chart.getImage().save("chart.png", ImageFormat.Png)`。这会生成独立的 PNG 文件。

### 如果需要为散点添加动画怎么办？
Aspose.Slides 支持动画效果。使用 `chart.getTimeline().getMainSequence().addEffect(...)` 为图表或单个系列添加进入或强调动画。

---

**最后更新：** 2026-02-24  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}