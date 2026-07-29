---
date: '2026-07-27'
description: 了解如何使用 Aspose.Slides 创建 doughnut chart java – 快速指南，设置 library、添加可自定义的
  doughnut chart、调整 hole size 并保存 presentation。
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: 了解如何使用 Aspose.Slides 创建 doughnut chart java – 快速指南，设置 library、添加可自定义的
  doughnut chart、调整 hole size 并保存 presentation。
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: 创建 doughnut chart java – 步骤指南，使用 Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: 创建 doughnut chart java – 步骤指南，使用 Aspose.Slides
url: /zh/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 Java 中使用 Aspose.Slides for Presentations 创建环形图

## 介绍
创建视觉上吸引人的演示文稿对于有效传达信息至关重要。**Create doughnut chart java** 是在需要以现代外观展示比例数据时的常见需求。在本教程中，您将学习如何设置 Aspose.Slides for Java，构建环形图，定制其孔径大小和颜色，最后保存演示文稿文件。完成后，您将拥有一个可在任何 Java 项目中自动生成 PowerPoint 幻灯片的可复用模式。

**您将学习：**
- 设置 Aspose.Slides for Java
- 在演示文稿中创建和配置环形图
- 调整图表外观，例如环孔大小
- 使用新图表保存演示文稿

让我们开始设置环境吧！

## 常见问题快速解答
- **哪个库可以创建 doughnut chart java？** Aspose.Slides for Java.
- **创建基本环形图需要多少行代码？** 大约 8–10 行（在实例化 Presentation 之后）。
- **我可以更改环孔大小吗？** 可以，`setHoleSize(double)` 方法接受 0 % 到 100 % 的值。
- **支持哪些输出格式？** PPTX、PDF、XPS、PNG、JPEG 等（共超过 50 种）。
- **生产环境需要许可证吗？** 商业许可证才能无限制使用；免费试用可用于评估。

## Aspose.Slides for Java 是什么？
**Aspose.Slides for Java** 是一个完全托管的 API，允许开发者在没有 Microsoft Office 的情况下创建、修改、转换和渲染 PowerPoint 文件。它支持超过 50 种文件格式，并且能够在保持低内存占用的同时处理包含数千张幻灯片的演示文稿。

## 为什么在演示文稿中使用环形图？
环形图展示部分与整体的关系，同时在中心留下空间用于标签或图像。Aspose.Slides 在典型的 2.5 GHz 服务器上能够以 **每分钟 500 张幻灯片** 的速度渲染环形图，并且能够在不将整个文件加载到内存的情况下处理 **数百页的演示文稿**，这使其非常适合大规模报表解决方案。

## 前提条件
在开始之前，请确保已满足以下前提条件：

### 必需的库和版本
要在 Java 中使用 Aspose.Slides，请通过 Maven、Gradle 或直接下载将其加入项目。

#### 环境设置要求
- 可用的 Java 开发工具包（JDK），建议版本 8 或更高。
- 集成开发环境（IDE），如 IntelliJ IDEA 或 Eclipse。

### 知识前提
熟悉 Java 及基本编程概念会有所帮助。了解 Maven 或 Gradle 将有助于简化设置过程。

## 设置 Aspose.Slides for Java
将 Aspose.Slides 集成到项目中有多种方式：

**Maven：**  
将此依赖添加到 `pom.xml` 文件中：  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**  
在 `build.gradle` 文件中加入以下内容：  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载：**  
或者，从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

### 许可证获取
- **免费试用：** 首先下载试用版以体验 Aspose.Slides 功能。  
- **临时许可证：** 获取临时许可证以获得无限制的扩展功能。  
- **购买：** 持续使用需要购买许可证。

一旦库已设置并且环境准备就绪，让我们继续实现环形图。

## 如何在 Java 中创建环形图？
加载一个新的 `Presentation` 对象，将环形图添加到幻灯片，设置孔径大小，然后保存文件——所有操作只需几行简洁的 API 调用。这种方式让您能够全面控制图表数据、外观和导出格式，并且无需在服务器上安装 Microsoft PowerPoint。

### 初始化 Presentation 对象
`Presentation` 类是 Aspose.Slides 的顶层对象，表示内存中的 PowerPoint 文件。  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
此步骤创建一个空白演示文稿，您可以在其中添加幻灯片、形状和图表。

### 向幻灯片添加环形图
`ISlide` 是单个幻灯片的接口；您可以检索第一张幻灯片或添加新幻灯片。  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
`addChart` 方法创建环形图；参数定义其在幻灯片上的位置（X、Y）和大小（宽度、高度）。

### 配置环形孔大小
`Chart` 提供 `setHoleSize(double)` 方法，以图表半径的百分比控制内部半径。  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
将孔径大小设置为 90 % 会使图表看起来几乎是完整的圆形，这在您想强调外部扇区时非常有用。

### 保存演示文稿
`presentation.save(String, SaveFormat)` 将文件以选定格式写入磁盘。  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
示例将结果保存为 `DoughnutHoleSize_out.pptx`，您也可以选择 PDF、PNG 或其他 50 多种支持的格式。

### 清理资源
调用 `presentation.dispose()` 释放本机资源并防止内存泄漏，尤其在长期运行的服务器应用中尤为重要。  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## 实际应用
环形图用途广泛。以下是一些典型场景：
1. **预算分配：** 显示预算在各部门之间的分配情况。  
2. **调查结果：** 可视化多选题的回答情况。  
3. **网站流量来源：** 显示来自不同渠道（自然搜索、付费、推荐等）的流量比例。

## 性能考虑
使用 Aspose.Slides 时，请参考以下优化建议：
- 在完成后尽快释放 `Presentation` 对象，以释放本机内存。  
- 对于大数据集使用流（`FileInputStream`、`ByteArrayOutputStream`），避免将整个文件加载到内存。  
- 在循环生成大量幻灯片时复用图表对象，以降低对象创建开销。

## 常见问题及解决方案
- **保存时出错：** 确认输出目录存在且应用程序具有写入权限。  
- **缺少图表数据：** 在调用 `setHoleSize` 之前确保已填充图表的 `ChartData` 集合。  
- **内存激增：** 对于包含数千张幻灯片的演示文稿，使用较小的 `Presentation.setSlideSize`，并及时释放中间幻灯片。

## 常见问答

**Q: 我可以调整环形图各段的颜色吗？**  
A: 可以。使用 `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` 然后指定所需的 RGB 颜色。

**Q: 我该如何为图表添加数据标签？**  
A: 调用 `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` 即可在每个扇区内部显示数值。

**Q: 是否可以将图表保存为 PPTX 之外的格式？**  
A: 当然可以。Aspose.Slides 支持 PDF、XPS、PNG、JPEG、TIFF 等多种格式——共超过 50 种。

**Q: 加载大型演示文稿时出现异常该怎么办？**  
A: 使用接受流的 `Presentation` 构造函数，并启用 `loadOptions.setLoadFormat(LoadFormat.Pptx)` 来流式读取文件，降低内存消耗。

**Q: 我能否使用实时数据源自动更新图表？**  
A: 可以。从数据库或 REST API 获取数据，更新 `ChartData` 集合，然后在保存演示文稿前调用 `chart.refresh()`。

## 资源
- **文档：** 在 [Aspose.Slides for Java](https://reference.aspose.com/slides/java/) 查看详细的 API 参考。  
- **下载：** 从 [Aspose.Slides releases](https://releases.aspose.com/slides/java/) 获取最新库版本。  
- **购买：** 在 [Aspose Purchase](https://purchase.aspose.com/buy) 购买许可证以获取完整功能。  
- **免费试用：** 在下载页面提供的免费试用版中体验 Aspose.Slides。  
- **临时许可证：** 获取临时许可证以进行无限制的扩展测试。  
- **支持：** 有问题？访问 [Aspose Forum](https://forum.aspose.com/c/slides/11) 获取帮助。

---

**最后更新：** 2026-07-27  
**测试环境：** Aspose.Slides for Java 24.12  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Slides for Java 向 PowerPoint 添加图表：一步步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [如何在 Java 中使用 Aspose.Slides 创建图表：全面指南](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}