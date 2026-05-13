---
date: '2026-02-19'
description: 学习如何使用 Aspose.Slides 在 Java 中创建饼图，并自定义饼图颜色、添加图表系列、操作图表数据工作表以及设置旋转角度。
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 使用 Aspose.Slides 在 Java 中自定义饼图颜色 – 完整指南
url: /zh/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 创建饼图：完整教程

## 介绍
创建动态且视觉上吸引人的演示文稿对于传递有冲击力的信息至关重要。借助 Aspose.Slides for Java，您可以轻松地在幻灯片中集成复杂的图表（如饼图），**自定义饼图颜色**，并毫不费力地提升数据可视化效果。本指南将手把手教您如何使用 Aspose.Slides Java 创建并自定义饼图，轻松解决常见的演示难题。

**您将学习的内容：**
- 初始化演示文稿并添加幻灯片。
- 在幻灯片上创建并配置饼图。
- 设置图表标题、数据标签以及**自定义饼图颜色**。
- 优化性能并有效管理资源。
- 使用 Maven 或 Gradle 将 Aspose.Slides 集成到 Java 项目中。

让我们先确保您具备所有必要的工具和知识，随后即可开始实践！

## 快速答疑
- **启动演示文稿的主要类是什么？** `Presentation`，来自 `com.aspose.slides`。
- **哪个方法向幻灯片添加饼图？** `addChart(ChartType.Pie, …)`。
- **如何为每个切片启用不同颜色？** 在系列组上调用 `setColorVaried(true)`。
- **可以旋转饼图吗？** 可以，使用图表对象的 `setRotationAngle(double)`。
- **生产环境需要许可证吗？** 商业部署必须使用 Aspose.Slides 许可证。

## 什么是 “customize pie chart colors”？
自定义饼图颜色指为饼图的每个切片分配不同的填充颜色，以提升可读性和视觉冲击力。在 Aspose.Slides 中，您只需启用多彩模式，然后为各个数据点设置实色填充即可实现。

## 为什么使用 Aspose.Slides for Java 创建饼图？
- **完全控制** 图表外观，无需依赖 Microsoft Office。
- **跨平台** 兼容——在 Windows、Linux 和 macOS 上均可运行。
- **丰富的 API** 支持数据绑定、样式设置以及导出为 PPTX、PDF 或图片。
- **许可证灵活**——可先使用免费试用版，后续根据需求升级至完整功能。

## 前置条件
在开始本教程之前，请确保已完成以下准备工作：

### 必需的库、版本及依赖
- **Aspose.Slides for Java**：版本 25.4 或更高。
- **Java Development Kit (JDK)**：版本 16 或更高。

### 环境搭建要求
- 已安装并配置好的 Java 开发环境。
- 使用 IntelliJ IDEA、Eclipse 或 NetBeans 等集成开发环境（IDE）。

### 知识前提
- 具备基本的 Java 编程概念。
- 熟悉 Maven 或 Gradle 用于依赖管理。

## 设置 Aspose.Slides for Java
要在 Java 项目中使用 Aspose.Slides，需将其添加为依赖。以下示例展示了不同构建工具的配置方式：

**Maven**  
在 `pom.xml` 中加入以下代码片段：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
在 `build.gradle` 中加入以下内容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载**  
如果不使用构建工具，可从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新发行版。

### 许可证获取步骤
- **免费试用**：先获取免费试用版，体验 Aspose.Slides 功能。  
- **临时许可证**：获取临时许可证，以在无功能限制的情况下延长使用时间。  
- **购买**：若需长期使用，请考虑购买正式许可证。

**基础初始化与设置**  
下面的代码演示了如何创建一个新的演示文稿对象以开始使用 Aspose.Slides：
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 实现指南
接下来我们将把添加并自定义饼图的过程拆解为若干可管理的步骤。

### 初始化演示文稿和幻灯片
首先创建一个新演示文稿并获取第一张幻灯片，这将作为绘制图表的画布：
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### 向幻灯片添加饼图
在指定位置插入一个默认数据集的饼图：
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 设置图表标题
通过设置并居中标题来自定义图表：
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 为系列配置数据标签
确保数据标签显示数值，以提升可读性：
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 准备图表数据工作表
通过清除已有的系列和类别，初始化图表的数据工作表：
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 向图表添加类别
为饼图定义类别：
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 添加系列并填充数据点
创建系列并填充数据点——这一步 **add chart series**：
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 自定义系列颜色和边框
通过设置颜色并自定义边框来提升视觉效果——这直接 **customizes pie chart colors**：
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### 配置自定义数据标签
微调每个数据点的标签：
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### 设置旋转角度并保存演示文稿
通过 **set rotation angle** 完成饼图的最终调整并保存文件：
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **切片全部显示相同颜色** | 未调用 `setColorVaried(true)` | 确保在系列组上启用多彩模式。 |
| **数据标签未显示** | `showValue` 标志未开启 | 在相应的标签格式上调用 `setShowValue(true)`。 |
| **旋转无效** | 使用了旧版 Aspose.Slides | 升级至 25.4 或更高版本。 |
| **运行时出现许可证异常** | 缺少或无效的许可证文件 | 在创建 `Presentation` 前加载许可证：`License license = new License(); license.setLicense("Aspose.Slides.lic");` |

## 常见问答

**Q: 如何获取 Aspose.Slides 的 Java 许可证？**  
A: 您可以在 Aspose 官网申请免费试用，然后购买永久许可证。运行时按上表所示加载许可证即可。

**Q: 这段代码能在旧版 JDK 上运行吗？**  
A: API 要求 JDK 16 或更高，旧版 JDK 不受支持。

**Q: 能否将图表导出为图片而不是 PPTX？**  
A: 可以，在渲染后调用 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`。

**Q: 如果需要在饼图中添加多个系列怎么办？**  
A: 饼图通常只显示单一系列；若需多系列展示，请考虑使用环形图（doughnut chart）。

**Q: 该库能在 Linux 服务器上运行吗？**  
A: 完全可以——Aspose.Slides for Java 与平台无关，只要有兼容的 JDK 即可运行。

---

**最后更新：** 2026-02-19  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}