---
"description": "学习如何使用 Java 和 Aspose.Slides 调整 PowerPoint 演示文稿中的字体高度。轻松增强幻灯片中的文本格式。"
"linktitle": "使用 Java 在 PowerPoint 中设置本地字体高度值"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "使用 Java 在 PowerPoint 中设置本地字体高度值"
"url": "/zh/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 PowerPoint 中设置本地字体高度值

## 介绍
在本教程中，您将学习如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中控制不同级别的字体高度。控制字体大小对于创建具有视觉吸引力和结构化的演示文稿至关重要。我们将通过分步示例来说明如何设置不同文本元素的字体高度。
## 先决条件
开始之前，请确保您已具备以下条件：
- 系统上安装了 Java 开发工具包 (JDK)
- Aspose.Slides for Java 库。您可以下载 [这里](https://releases。aspose.com/slides/java/).
- 对 Java 编程和 PowerPoint 演示文稿有基本的了解
## 导入包
确保在 Java 文件中包含必要的 Aspose.Slides 包：
```java
import com.aspose.slides.*;
```
## 步骤 1：初始化演示对象
首先，创建一个新的 PowerPoint 演示文稿对象：
```java
Presentation pres = new Presentation();
```
## 步骤 2：添加形状和文本框
在第一张幻灯片中添加带有文本框的自动形状：
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## 步骤 3：创建文本部分
定义具有不同字体高度的文本部分：
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## 步骤4：设置字体高度
设置不同级别的字体高度：
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## 步骤 5：保存演示文稿
将修改后的演示文稿保存到文件：
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## 结论
本教程演示了如何使用 Aspose.Slides for Java 以编程方式调整 PowerPoint 幻灯片中的字体高度。通过在不同级别（演示文稿范围、段落和部分）调整字体大小，您可以精确控制演示文稿中的文本格式。
## 常见问题解答
### 什么是 Aspose.Slides for Java？
Aspose.Slides for Java 是一个功能强大的 API，用于以编程方式操作 PowerPoint 演示文稿。
### 在哪里可以找到 Aspose.Slides for Java 的文档？
您可以找到文档 [这里](https://reference。aspose.com/slides/java/).
### 我可以在购买之前试用 Aspose.Slides for Java 吗？
是的，您可以免费试用 [这里](https://releases。aspose.com/).
### 如何获得 Aspose.Slides for Java 的支持？
如需支持，请访问 [Aspose.Slides论坛](https://forum。aspose.com/c/slides/11).
### 我可以在哪里购买 Aspose.Slides for Java 的许可证？
您可以购买许可证 [这里](https://purchase。aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}