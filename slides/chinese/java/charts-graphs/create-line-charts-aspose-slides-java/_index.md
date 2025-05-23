---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides 在 Java 中创建带有标记的折线图。本教程涵盖图表创建、系列添加以及演示文稿的有效保存。"
"title": "使用 Aspose.Slides for Java 创建带有默认标记的折线图"
"url": "/zh/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 创建带有默认标记的折线图
## 介绍
创建视觉吸引力强且信息丰富的图表对于演示文稿、报告和仪表板至关重要。在软件开发中实现此过程的自动化可以节省时间并确保文档之间的一致性。本教程演示如何使用 Aspose.Slides for Java 创建带有标记的折线图。
**Aspose.Slides for Java** 是一个功能强大的库，使开发人员无需安装 Microsoft Office 即可以编程方式操作 PowerPoint 演示文稿。它简化了创建、编辑和导出幻灯片等任务，使其成为自动生成文档的重要工具。
**您将学到什么：**
- 如何初始化 Aspose.Slides for Java
- 创建带标记的折线图的步骤
- 向图表添加系列和类别
- 配置图表图例
- 保存演示文稿
准备好了吗？首先，请确保您已完成所有设置！
## 先决条件
在开始之前，请确保您的开发环境已准备就绪：
1. **库和依赖项：**
   - Aspose.Slides for Java 库（推荐 25.4 版本）
   - Java 开发工具包 (JDK) 16 或更高版本
2. **环境设置：**
   - 您的 IDE 应该支持 Maven 或 Gradle 构建工具。
   - 如果需要，请确保您拥有有效的许可证文件。
3. **知识前提：**
   - 对 Java 编程有基本的了解
   - 熟悉使用 Maven 或 Gradle 构建项目
有了这些，让我们为您的项目设置 Aspose.Slides！
## 设置 Aspose.Slides for Java
要使用 Aspose.Slides for Java，您需要将其作为依赖项添加到您的项目中。根据您使用的是 Maven 还是 Gradle，设置会略有不同。
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
**许可证获取步骤：**
- 如需免费试用，请访问 [免费试用页面](https://releases。aspose.com/slides/java/).
- 要获取临时许可证，请导航至 [临时执照页面](https://purchase。aspose.com/temporary-license/).
- 通过他们的购买完整许可证 [购买门户](https://purchase。aspose.com/buy).
**基本初始化：**
下面介绍如何在 Java 应用程序中初始化 Aspose.Slides：
```java
import com.aspose.slides.Presentation;
// 初始化新的展示对象
Presentation pres = new Presentation();
```
现在，让我们开始创建图表！
## 实施指南
### 功能 1：使用默认标记创建图表
本节演示如何创建带有标记的折线图。此功能对于有效地可视化数据趋势至关重要。
#### 添加折线图
要添加带有标记的折线图：
```java
import com.aspose.slides.*;
// 访问第一张幻灯片
ISlide slide = pres.getSlides().get_Item(0);
// 在幻灯片中位置 (10, 10) 处添加带有标记的折线图，大小为 (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### 清算系列和类别
重新开始：
```java
// 清除现有系列和类别，确保一切顺利
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// 获取图表的数据工作簿以进行进一步操作
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### 功能2：添加系列和类别
添加系列和类别对于用有意义的数据填充图表至关重要。
#### 创建新系列
要添加名为“系列 1”的新系列：
```java
// 向图表添加新系列
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// 访问第一个系列的数据填充
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### 填充类别和数据点
要添加类别和相应的数据点：
```java
// 添加类别名称及其各自的数据点
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// 优雅地处理空数据点
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### 功能 3：添加第二个系列并填充数据点
添加额外的系列可以为您的图表提供更多的深度。
#### 创建并填充第二个系列
要添加“系列 2”：
```java
// 添加另一个名为“系列 2”的系列
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// 访问第二个系列的数据填充
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// 为“系列 2”添加数据点
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### 功能四：配置图表图例
配置图例可增强图表的可读性。
#### 调整图例设置
配置方法：
```java
// 启用图例并将其设置为不覆盖在数据点上
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### 功能 5：保存演示文稿
图表准备好后，将演示文稿保存到文件中。
```java
try {
    // 将修改后的演示文稿保存到指定目录
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## 实际应用
1. **业务报告：**
   - 使用财务报告中的图表来描述一段时间内的趋势。
2. **数据分析：**
   - 在分析阶段可视化数据模式和相关性。
3. **教育材料：**
   - 为学术讲座或演示创建信息幻灯片。
4. **项目管理：**
   - 使用可视化图表元素增强项目时间表。
5. **营销演示：**
   - 使用图表有效地展示销售趋势和活动结果。
## 结论
您已经学习了如何使用 Aspose.Slides 在 Java 中创建带标记的折线图、添加系列和类别、配置图例以及保存演示文稿。这些技能对于在各种专业应用程序中创建动态可视化内容非常有帮助。
要了解有关 Aspose.Slides 功能的更多信息或寻求社区支持，请访问他们的 [官方文档](https://docs.aspose.com/slides/java/) 或加入 Stack Overflow 等论坛。
编码愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}