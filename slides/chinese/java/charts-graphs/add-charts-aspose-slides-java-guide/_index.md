---
date: '2026-06-03'
description: 了解如何使用 aspose slides maven 依赖添加图表、配置数据标签，并在 Java 演示文稿中生成动态图表。
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: aspose slides maven 依赖：在演示文稿中使用 Aspose.Slides for Java 添加和配置图表
url: /zh/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency：在演示文稿中使用 Aspose.Slides for Java 添加和配置图表

## 介绍
**aspose slides maven dependency** 让 Java 开发者能够以编程方式创建、修改和丰富 PowerPoint 文件，而无需实际打开 PowerPoint 本身。在许多商业和学术场景中，手动插入图表既耗时又容易出错。本教程逐步演示如何添加气泡图表、将数据标签绑定到工作表单元格并保存结果——全部通过使用 aspose slides maven dependency 以简洁、可重复的方式实现。

**您将学习**
- 如何使用 aspose slides maven 依赖添加图表
- 使用 Maven 或 Gradle 设置 Java 项目
- 加载现有演示文稿并插入气泡图表
- 使用单元格引用配置数据标签（添加数据标签图表）
- 保存更新后的文件以供后续分发
- 实际用例，如动态图表生成和创建演示文稿图表工作流

## 快速答案
- **哪个 Maven 构件提供图表功能？** `com.aspose:aspose-slides:25.4`（或最新）  
- **我可以将数据标签绑定到 Excel 样式的单元格吗？** 是的——使用 `ChartDataLabel` 的 `setDataLabelFormat` 并提供单元格引用。  
- **生产环境是否需要许可证？** 完整许可证会去除评估水印并解锁所有功能。  
- **这在 Java 11+ 上能工作吗？** 当然；该库兼容 Java 8 到 Java 21。  
- **支持多少种图表类型？** 超过 70 种不同的图表类型，包括气泡图、雷达图和股票图表。

## 什么是 aspose slides maven 依赖？
**aspose slides maven dependency** 是一个兼容 Maven 的包，提供完整的 API 用于在 Java 中创建和编辑 PowerPoint（PPTX、PPT、ODP）文件。将此依赖添加到 `pom.xml` 或 `build.gradle` 后，您即可使用超过 70 种图表类型、150 多种幻灯片布局，以及在未安装 Office 的情况下操作形状、动画和元数据的能力。

## 为什么在图表自动化中使用 aspose slides maven 依赖？
Aspose.Slides 能在标准服务器硬件上在不到一秒的时间内处理数千页的幻灯片文稿，支持 **70+ 图表类型**，并且能够渲染最多 **10,000 张幻灯片** 的演示文稿而无需将整个文件加载到内存中。这些可量化的能力使其非常适合企业级的动态图表生成，在此类场景中性能和可扩展性是不可妥协的。

## 前置条件
- **Java 开发工具包 (JDK)** 8 或更高（推荐使用 Java 11+）。  
- **Maven** 3.6+ **或** **Gradle** 6+。  
- **Aspose.Slides for Java** 库（aspose slides maven 依赖，版本 25.4 或更高）。  
- 熟悉 Java 集合和文件 I/O 的基本用法。  
- 如果计划在试用期后运行代码，需要提供评估或完整许可证文件（`license.json`）。

## 如何使用 Aspose.Slides 向幻灯片添加图表？
加载目标演示文稿，在所需幻灯片上创建新的图表形状，并指定图表类型（本例为气泡图）。一旦引用了库，整个操作可以用 **三行简洁的代码** 完成，非常适合快速原型开发和生产流水线。

### 步骤 1：添加 aspose slides maven 依赖
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
这些代码片段直接从 Maven Central 拉取完整的 Aspose.Slides API——包括图表支持。

### 步骤 2：加载演示文稿并插入气泡图表
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 步骤 3：配置图表的数据系列和标签
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 步骤 4：保存修改后的演示文稿
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## 如何使用单元格引用配置数据标签？
数据标签可以绑定到外部单元格值，类似 Excel 的 “链接到单元格” 功能。此方法消除了硬编码值，并实现 **动态图表生成**，即标签内容会随底层数据的变化自动更新。通过将每个标签链接到特定的工作簿单元格，您可以确保源数据的任何修改都会即时反映在演示文稿中，从而降低维护工作量并最大程度避免信息过时的风险。

### 直接答案
调用 `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` 并传入引用单元格地址（如 `"Sheet1!A2"`）的 `DataLabelFormat`。Aspose.Slides 在运行时解析该引用，将单元格的当前值插入图表标签中。

### 步骤说明
1. 确定要标记的系列。  
2. 获取每个数据点的 `IDataLabel` 对象。  
3. 使用配置了 `CellReference` 的 `DataLabelFormat` 调用 `setDataLabelFormat`。  
4. 可选地自定义字体、颜色和显示选项。

## 如何保存修改后的演示文稿？
保存只需一次方法调用，将内存中的 `Presentation` 对象写入文件路径或输出流。您还可以通过传入相应的 `SaveFormat` 枚举来选择输出格式（PPTX、PDF、ODP）。此操作直接将结果流式写入磁盘，在 `Presentation` 实例关闭或超出作用域时自动释放所有本机资源，即使对于大型文稿也能保持低内存使用。

### 直接答案
调用 `presentation.save("output.pptx", SaveFormat.Pptx)`；库会直接将结果流式写入磁盘，在 `Presentation` 实例关闭或超出作用域时自动释放所有本机资源。

## 实际应用
- **商业报告：** 自动从数据库转储生成季度销售图表。  
- **学术讲座：** 将实时研究数据拉入每堂课的幻灯片。  
- **销售演示：** 现场构建针对客户的绩效仪表盘。  
- **项目管理：** 使用动态数据标签可视化甘特式时间线。  
- **营销分析：** 将活动关键绩效指标嵌入演示文稿，随新指标到达自动更新。

## 性能考虑
- **内存管理：** 使用 try‑with‑resources 或显式调用 `presentation.dispose()` 及时释放本机内存。  
- **大数据集：** 处理超过 10,000 个数据点时，通过 `ChartDataWorkbook` 填充图表数据，以避免将整个数据集加载到 Java 对象中。  
- **线程安全：** 每个线程应使用各自的 `Presentation` 实例；API 对共享对象并非线程安全。

## 常见问题及解决方案
- **问题：** “未找到许可证文件”。  
  **解决方案：** 将 `license.json` 放在类路径中，并在使用任何 API 之前调用 `License license = new License(); license.setLicense("license.json");`。  
- **问题：** 保存后图表为空白。  
  **解决方案：** 确保图表的数据工作簿随演示文稿一起保存（`presentation.getCharts().setDataWorkbook(chartWorkbook);`）。  
- **问题：** 数据标签显示 “#REF!” 错误。  
  **解决方案：** 验证单元格引用字符串与确切的工作表名称和地址匹配，并确保引用的工作簿已附加到图表。

## 常见问答

**问：我可以添加除气泡图之外的其他图表类型吗？**  
答：可以，`ChartType` 枚举包括折线、柱形、饼图、雷达图、股票图等超过 70 种其他类型。

**问：aspose slides maven 依赖能在 OpenJDK 上使用吗？**  
答：当然；它完全兼容 OpenJDK 8‑21，并可在所有主流操作系统上运行。

**问：如何嵌入来自现有 Excel 文件的图表？**  
答：使用 `WorkbookFactory.create(new FileInputStream("data.xlsx"))` 加载 Excel 工作簿，然后在设置单元格引用之前将图表的 `ChartDataWorkbook` 绑定到该工作簿。

**问：每张幻灯片的图表数量有限制吗？**  
答：实际上没有——Aspose.Slides 能在每张幻灯片上处理数十个图表，唯一限制是可用内存。

**问：最终演示文稿可以导出为何种格式？**  
答：支持 PPTX、PPT、ODP、PDF、XPS、HTML，甚至 PNG、JPEG 等图像格式。

## 资源
- [Aspose.Slides for Java 发行版](https://releases.aspose.com/slides/java/) – 下载最新的库二进制文件。  
- [Aspose.Slides 文档](https://reference.aspose.com/slides/java/) – 综合的 API 参考和指南。  
- [下载 Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – Maven/Gradle 包的直接下载页面。  
- [购买许可证](https://purchase.aspose.com/buy) – 获取完整商业许可证。  
- [免费试用](https://releases.aspose.com/slides/java/) – 开始试用以评估功能。  
- [临时许可证](https://purchase.aspose.com/temporary-license/) – 申请临时密钥以延长评估。  
- [Aspose 支持论坛](https://forum.aspose.com/c/slides/11) – 从社区和 Aspose 工程师处获取帮助。

## 结论
现在您已经拥有使用 **aspose slides maven 依赖** 在 Java 演示文稿中添加、配置和持久化图表的完整端到端指南。按照上述步骤，您可以实现图表创建自动化，将数据标签绑定到实时单元格值，并大规模生成专业级演示文稿。尝试其他图表类型，探索动画 API，并将此工作流集成到您的报告流水线中，以获得最大效果。

---  
**最后更新：** 2026-06-03  
**测试环境：** Aspose.Slides for Java 25.4  
**作者：** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## 相关教程

- [如何使用 Aspose.Slides Java 创建和配置演示文稿：分步指南](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [使用 Aspose.Slides Maven 创建 PPTX Java – 自动化指南](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [如何在 Java 中使用 Aspose.Slides 创建图表：全面指南](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}