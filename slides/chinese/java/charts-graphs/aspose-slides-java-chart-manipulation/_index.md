---
date: '2026-01-17'
description: 学习如何使用 Aspose.Slides 在 Java 中创建图表，添加簇状柱形图，并将演示文稿保存为 pptx。面向 Java 开发者的逐步指南。
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: 如何在 Java 中使用 Aspose.Slides for Java 创建图表
url: /zh/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose.Slides for Java 创建图表

## 介绍
创建一个 **在 Java 中创建图表** 的专业外观并不一定要头疼。借助 **Aspose.Slides for Java**，您可以以编程方式在 PowerPoint 演示文稿中直接添加、设置样式并保存图表——例如簇状柱形图。在本教程中，我们将逐步演示如何设置库、初始化演示文稿、插入簇状柱形图、微调绘图区域，最后将文件保存为 PPTX。完成后，您将拥有一段可在任何 Java 项目中复用的代码片段。

**您将学到的内容**
- 如何设置 Aspose.Slides 的 Maven 或 Gradle 依赖  
- 如何 **在 Java 中创建图表** 并添加簇状柱形图  
- 如何配置绘图区域（位置、大小、布局）  
- 如何 **将演示文稿保存为 pptx** 并正确处理资源  

准备好让您的数据以可视化方式说话了吗？让我们开始吧！

## 快速回答
- **需要哪个库？** Aspose.Slides for Java（Maven/Gradle）。  
- **演示的图表类型是什么？** 簇状柱形图。  
- **如何保存文件？** 使用 `presentation.save(..., SaveFormat.Pptx)`。  
- **是否需要许可证？** 开发阶段可使用免费试用版；生产环境需要正式许可证。  
- **可以更改绘图区域吗？** 可以，您可以设置 X、Y、宽度、高度以及布局目标类型。

## 什么是 create chart in java？
在 Java 中创建图表是指使用库生成图表对象、填充数据并将其嵌入文档——这里是 PowerPoint 幻灯片。Aspose.Slides 抽象了底层的 Office Open XML 细节，让您专注于视觉效果。

## 为什么要使用 Aspose.Slides 添加簇状柱形图？
簇状柱形图非常适合并排比较多个数据系列。它在商业报告、仪表盘和演示文稿中被广泛使用。Aspose.Slides 让您无需手动打开 PowerPoint，即可完全控制颜色、标记、坐标轴和布局。

## 前置条件
- **Aspose.Slides for Java** 库（版本 25.4 或更高）。  
- **JDK 16**（或更高）已安装。  
- IntelliJ IDEA 或 Eclipse 等 IDE。  
- 基本的 Java 语法熟悉度。

## 设置 Aspose.Slides for Java
### Maven
在 `pom.xml` 中添加依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 中引入库：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
或者从 [Aspose 官方站点](https://releases.aspose.com/slides/java/) 下载最新发布版。

#### 许可证获取
使用免费试用或临时许可证进行测试。生产部署请购买正式许可证。

### 基本初始化与设置
新建一个 Java 类并导入核心类：

```java
import com.aspose.slides.Presentation;
```

## 实现指南
我们将逐步讲解每一步，并提供清晰说明。

### 演示文稿初始化与幻灯片操作
#### 概述
首先，创建一个全新的演示文稿并获取第一张幻灯片，以便放置图表。

**1. 创建并初始化 Presentation**

```java
Presentation presentation = new Presentation();
```

**2. 访问第一张幻灯片**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. 添加簇状柱形图**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **专业提示：** 始终在 `try‑finally` 块中使用演示文稿，并在 `finally` 中调用 `presentation.dispose()` 以释放本机资源。

### 绘图区域配置
#### 概述
微调图表的绘图区域，以控制数据在幻灯片中的显示位置。

**1. 设置位置和大小**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. 定义布局目标类型**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### 演示文稿保存
#### 概述
自定义图表后，将演示文稿持久化为 PPTX 文件。

**1. 保存到文件**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **警告：** 确保输出目录已存在且应用程序具有写入权限；否则保存操作将失败。

## 常见使用场景
- **商业报告：** 嵌入销售趋势和财务关键绩效指标。  
- **教育幻灯片：** 可视化实验结果或统计数据。  
- **项目提案：** 突出里程碑和资源分配。  
- **营销演示：** 用生动的图表展示活动绩效。  
- **活动策划：** 显示与会者人口统计或日程拆分。

## 性能注意事项
- 及时释放 `Presentation` 对象以避免内存泄漏。  
- 对于大数据集，建议增量填充图表系列，而不是一次性加载全部。  
- 使用 Java 内置的分析工具监控堆内存使用情况。

## 常见问题

**Q: 如何添加其他图表类型？**  
A: 在调用 `addChart` 时使用 `ChartType` 枚举（例如 `ChartType.Pie`、`ChartType.Line`）。

**Q: 能自定义图表颜色吗？**  
A: 可以，通过 `IChart` API 修改系列的填充格式或图表的调色板。

**Q: 演示文稿无法保存——怎么回事？**  
A: 检查 `YOUR_OUTPUT_DIRECTORY` 是否正确、是否存在且可写。还要确认没有残留的文件锁。

**Q: 如何高效处理非常大的演示文稿？**  
A: 将幻灯片分批处理，使用后立即释放每个 `Presentation`，必要时增大 JVM 堆大小。

**Q: Aspose.Slides 对商业项目免费吗？**  
A: 可使用免费试用版进行评估，但商业部署必须购买正式许可证。

## 资源
- [文档](https://reference.aspose.com/slides/java/)
- [下载 Aspose.Slides](https://releases.aspose.com/slides/java/)
- [购买许可证](https://purchase.aspose.com/buy)
- [免费试用](https://releases.aspose.com/slides/java/)
- [临时许可证](https://purchase.aspose.com/temporary-license/)
- [支持论坛](https://forum.aspose.com/c/slides/11)

立即使用 Aspose.Slides for Java 开始创建视觉冲击力十足的演示文稿吧！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-17  
**测试环境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose  

---