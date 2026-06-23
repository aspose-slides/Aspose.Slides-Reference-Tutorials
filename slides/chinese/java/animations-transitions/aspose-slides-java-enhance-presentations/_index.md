---
date: '2026-06-23'
description: 了解如何在 PowerPoint 中创建表格、向表格单元格添加文本、在文本周围绘制框架，并使用 Aspose.Slides for Java
  将演示文稿保存为 pptx。
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
title: 如何在 PowerPoint 中创建表格并使用 Aspose.Slides for Java 绘制框架
url: /zh/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint 中创建表格并使用 Aspose.Slides for Java 绘制框架

## 介绍

创建 **create table in PowerPoint** 程序化可以为您节省大量手动格式化的时间，尤其是在需要突出关键数字或添加说明性注释时。在本教程中，您将学习如何向表格单元格添加文本、在特定段落周围绘制框架、设置精确的文本对齐方式，最后 **save presentation as pptx** ——全部使用强大的 Aspose.Slides for Java API。完成后，您将拥有一张外观精致、易于阅读、能够瞬间吸引观众注意力的幻灯片。

## 快速答案
- **“add text to table” 是什么意思？** 它指的是以编程方式插入或更新单个表格单元格的文本内容。  
- **哪个方法保存文件？** `pres.save("output.pptx", SaveFormat.Pptx)` —— 这一步 **save presentation as pptx** 完成了更改。  
- **如何在形状内部对齐文本？** 使用 `TextAlignment.Left`（或 Center/Right），通过 `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`。  
- **我可以在段落周围绘制矩形吗？** 可以——遍历段落，获取其边界矩形，并添加一个没有填充且线条为黑色的 `IAutoShape`。  
- **我需要许可证吗？** 临时许可证可用于评估；正式使用需购买完整许可证。  

## 为什么在文本周围绘制框架？

在段落或特定部分（例如包含字符 **'0'** 的任何文本）周围绘制框架（或矩形），可以立即吸引观众的注意力。它在不改变原始文本的情况下提供清晰的视觉提示，非常适合突出关键数字、警示信息或在幻灯片中划分章节。

## 前提条件

在深入代码之前，请确保具备以下条件：

### 必需的库
您需要 Aspose.Slides for Java。以下是使用 Maven 或 Gradle 引入它的方法：

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

### 环境设置
确保已安装 Java Development Kit（JDK），建议使用 JDK 16 或更高版本，因为本示例使用 `jdk16` 分类器。

### 知识前提
- 对 Java 编程有基本了解。  
- 熟悉 PowerPoint 等演示软件。  
- 有使用集成开发环境（IDE），如 IntelliJ IDEA 或 Eclipse 的经验。  

## 设置 Aspose.Slides for Java

`Presentation` 是 Aspose.Slides 的核心类，表示内存中的 PowerPoint 文件，并提供对幻灯片、形状和表格的访问。要开始使用 Aspose.Slides，请按照以下步骤操作：

1. **安装库**：使用 Maven 或 Gradle 管理依赖，或直接从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载。  
2. **获取许可证**：  
   - 通过从 [Temporary License](https://purchase.aspose.com/temporary-license/) 下载临时许可证，开始免费试用。  
   - 如需完整功能，可在 [Purchase Aspose.Slides](https://purchase.aspose.com/buy) 购买许可证。  
3. **基本初始化**：  
   使用以下代码片段初始化演示环境：  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## 如何在 Aspose.Slides for Java 中向表格添加文本？

加载一个新的 `Presentation`，在指定坐标创建表格，用 `TextFrame` 对象填充单元格，最后调用 `pres.save("output.pptx", SaveFormat.Pptx)`。此过程会 **create table in PowerPoint**，向每个单元格注入自定义文本，并将结果写入 PPTX 文件，实现单一步骤高效工作流。

### 功能 1：创建表格并向单元格添加文本

#### 概述
此功能演示如何 **create table**，随后 **add text to table** 单元格，最后 **save presentation as pptx**。

#### 步骤

**1. 创建表格**  
首先，初始化演示文稿并在位置 (50, 50) 添加一个表格，指定列宽和行高。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 向单元格添加文本**  
创建包含文本片段的段落，并将其添加到指定单元格。  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. 保存演示文稿**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### 功能 2：向 AutoShape 添加 TextFrame 并设置对齐方式

#### 概述
学习如何向 AutoShape 添加具有特定对齐方式的文本框——这是 **set text alignment java** 的示例。

#### 步骤

AutoShape 是一种可以容纳文本和图形的形状。

**1. 添加 AutoShape**  
在位置 (400, 100) 添加一个矩形 AutoShape，指定尺寸。  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` 枚举定义了形状中文本的水平对齐选项。

**2. 设置文本对齐**  
将文本设置为 “Text in shape” 并左对齐。  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. 保存演示文稿**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### 功能 3：在表格单元格的段落和文本片段周围绘制框架

#### 概述
此功能聚焦于 **draw frames around text**，以及针对包含字符 ‘0’ 的文本片段 **draw rectangle around paragraph**。

#### 步骤

`IAutoShape` 表示可以在幻灯片上绘制的形状对象，例如用于框架的矩形。

**1. 创建表格**  
复用 “Create Table and Add Text to Cells” 中的代码进行初始设置。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 添加段落**  
复用前一功能中的段落创建代码。  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. 绘制框架**  
遍历段落和文本片段，在其周围绘制框架。  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. 保存演示文稿**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## 常见陷阱与技巧

- **空值检查** – 始终在 try‑finally 块中使用 `Presentation`，确保调用 `pres.dispose()` 以释放本机资源。  
- **边界矩形的准确性** – `para.getRect()` 返回的矩形反映当前布局；如果更改字体大小或边距，请在绘制框架前重新计算矩形。  
- **性能** – 处理非常大的表格时，考虑批量添加形状或复用单个 `IAutoShape` 实例并更新其几何形状，以降低内存开销。  

## 常见问题解答

**问：我可以在旧版 JDK 上使用这些 API 吗？**  
答：该库支持 JDK 8 及以上，但 `jdk16` 分类器在新版运行时上性能最佳。

**问：如何更改框架颜色？**  
答：修改线条格式的填充颜色，例如 `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`。

**问：是否可以将最终幻灯片导出为图像？**  
答：可以——使用 `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`，然后保存字节数组。

**问：如果只需要突出显示单元格内的单词 “Total” 怎么办？**  
答：遍历 `cell.getTextFrame().getParagraphs()`，定位包含 “Total” 的文本片段，并在该片段的边界框周围绘制矩形。

**问：Aspose.Slides 能高效处理大型演示文稿吗？**  
答：API 会流式传输数据，并在调用 `pres.dispose()` 时释放资源，这有助于大型文件的内存管理。

---

**最后更新：** 2026-06-23  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [Aspose.Slides for Java: 掌握 PowerPoint 演示文稿中的 PPTX 表格和文本操作](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中创建动态文本框](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [使用 Aspose.Slides for Java 在文本框中添加列](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}