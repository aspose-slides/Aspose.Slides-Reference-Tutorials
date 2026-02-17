---
date: '2026-02-17'
description: 学习如何使用 Aspose.Slides for Java 创建环形图 PowerPoint 并以编程方式添加图表数据点。按照简易步骤和代码示例操作。
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: 使用 Aspose.Slides for Java 创建环形图 PowerPoint
url: /zh/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 创建环形图 PowerPoint

## 介绍
创建引人入胜的演示文稿往往不仅仅需要文字和图片；图表可以通过有效地可视化数据显著提升叙事效果。然而，许多开发者在以编程方式将动态图表功能集成到 PowerPoint 文件中时会遇到困难。本教程演示如何使用 Aspose.Slides for Java **创建环形图 PowerPoint**——一款兼具灵活性和易用性的强大工具。

**您将学习到：**
- 如何使用 Aspose.Slides for Java 初始化演示文稿
- 添加环形图到幻灯片的逐步指南
- 配置数据点并自定义标签属性
- 以高保真度保存修改后的演示文稿

让我们一起探索如何利用这些功能提升演示效果。在开始之前，请确保您熟悉基本的 Java 编程概念。

## 快速答疑
- **哪个库可以创建环形图 PowerPoint？** Aspose.Slides for Java
- **可以通过代码添加图表数据点吗？** 可以，使用图表 API
- **生产环境需要许可证吗？** 需要有效的 Aspose.Slides 许可证
- **支持哪些 Java 版本？** Java 8 及以上（示例中使用 JDK 16 分类器）
- **可以添加多少系列？** 示例最多添加 15 系列，您可以根据需要进行调整

## 什么是 PowerPoint 中的环形图？
环形图是带有空心中心的饼图变体，能够在紧凑且视觉上更具吸引力的方式下显示多个数据系列。它非常适合展示部分与整体的关系，同时保持设计简洁。

## 为什么使用 Aspose.Slides for Java 来创建环形图？
- **完全控制** 图表外观、数据和布局，无需打开 PowerPoint
- **无 COM 互操作** —— 在任何支持 Java 的平台上均可运行
- **高性能**，适用于生成大型演示文稿或与 Web 服务集成
- **丰富的自定义**，如爆炸效果、孔径大小、切片角度和标签格式化

## 前置条件
- 基础的 Java 编程知识
- IntelliJ IDEA 或 Eclipse 等 IDE
- 用于依赖管理的 Maven 或 Gradle
- 有效的 Aspose.Slides for Java 许可证（提供免费试用）

## 设置 Aspose.Slides for Java
选择适合您项目的依赖管理工具。

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

如果您更倾向于直接下载，请访问 [Aspose.Slides for Java 发布页面](https://releases.aspose.com/slides/java/)。

### 许可证获取
您可以先使用免费试用版来探索 Aspose.Slides 功能。若需长期使用，请购买许可证或从 [Aspose 网站](https://purchase.aspose.com/temporary-license/) 申请临时许可证。按照提供的说明设置环境并在应用程序中初始化 Aspose.Slides。

## 使用 Aspose.Slides for Java 创建环形图 PowerPoint 的步骤
以下是完整的逐步指南。每段代码块前都有解释，帮助您明确每一步的作用。

### 步骤 1：初始化演示文稿
首先，加载已有的 PPTX 或创建一个新文件。这将为后续的幻灯片修改做好准备。

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 步骤 2：向幻灯片添加环形图
我们添加图表形状，清除默认的系列/类别，并设置基本的视觉属性。

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 步骤 3：添加图表数据点并自定义标签
在这里我们填充类别，为每个系列添加数据点，并微调标签外观。这正是 **add chart data points** 关键字发挥作用的地方。

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### 步骤 4：保存更新后的演示文稿
最后，将更改持久化为新的 PPTX 文件。

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 实际应用场景
环形图可用于多种真实业务场景：
- **财务报告：** 可视化预算分配或费用构成
- **市场分析：** 展示竞争对手之间的市场份额分布
- **调查结果：** 以紧凑形式呈现分类调查数据
- **仪表盘生成：** 结合数据库查询生成实时更新的幻灯片

## 性能注意事项
- **释放资源**：完成后调用 `pres.dispose()` 以释放本机内存
- **限制图表数量**：添加数百个图表会增加内存占用，必要时采用批处理
- **使用流式处理**：对于海量数据集，直接从流填充工作簿，而非使用内存数组

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **图表显示为空白** | 数据单元格未正确填充 | 确认 `workBook.getCell(...)` 引用了正确的行/列索引 |
| **标签重叠** | 类别过多导致空间不足 | 增大 `DoughnutHoleSize` 或调整 `FirstSliceAngle` |
| **OutOfMemoryError** | 大型演示文稿未释放资源 | 保存后调用 `pres.dispose()`，并考虑增大 JVM 堆大小 |

## 常见问答

**问：可以在商业应用中使用 Aspose.Slides for Java 吗？**  
答：可以，但需要有效的商业许可证。提供免费试用供评估使用。

**问：如何添加超过 15 系列？**  
答：在 “添加环形图” 步骤中增大循环上限，并确保工作簿中有足够的行。

**问：创建后可以修改环形孔径大小吗？**  
答：可以，在保存前调用 `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` 即可。

**问：能将图表导出为图片而不是 PPTX 吗？**  
答：完全可以。使用 `chart.getImage()` 并将返回的 `java.awt.image.BufferedImage` 保存为您需要的格式。

**问：Aspose.Slides 支持动画图表吗？**  
答：可以通过 `ISlide.getTimeline()` API 添加动画，但超出本教程范围。

## 结论
现在，您已经掌握了使用 Aspose.Slides for Java **创建环形图 PowerPoint** 的完整、可投入生产的方法，包括 **add chart data points**、自定义标签以及性能优化技巧。尝试不同的配色、数据源和图表类型，让您的演示文稿真正脱颖而出。

---

**最后更新：** 2026-02-17  
**测试环境：** Aspose.Slides for Java 25.4（JDK 16 分类器）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}