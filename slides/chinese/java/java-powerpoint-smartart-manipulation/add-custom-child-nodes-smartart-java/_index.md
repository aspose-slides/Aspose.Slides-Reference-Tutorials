---
title: 使用 Java 在 SmartArt 中添加自定义子节点
linktitle: 使用 Java 在 SmartArt 中添加自定义子节点
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Java 和 Aspose.Slides 在 PowerPoint 演示文稿中向 SmartArt 添加自定义子节点。轻松使用专业图形增强幻灯片效果。
type: docs
weight: 11
url: /zh/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---
## 介绍
SmartArt 是 PowerPoint 中的一个强大功能，它允许用户快速轻松地创建具有专业外观的图形。在本教程中，我们将学习如何使用 Java 和 Aspose.Slides 将自定义子节点添加到 SmartArt。
## 先决条件
在开始之前，请确保您已准备好以下内容：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 Java。
2.  Aspose.Slides for Java：从以下网站下载并安装 Aspose.Slides for Java[这里](https://releases.aspose.com/slides/java/).

## 导入包
首先，在您的 Java 项目中导入必要的包：
```java
import com.aspose.slides.*;
```
## 步骤 1：加载演示文稿
加载要向 SmartArt 添加自定义子节点的 PowerPoint 演示文稿：
```java
String dataDir = "Your Document Directory";
//加载所需的演示文稿
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## 步骤 2：将 SmartArt 添加到幻灯片
现在，让我们将 SmartArt 添加到幻灯片中：
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## 步骤 3：移动 SmartArt 形状
将 SmartArt 形状移动到新位置：
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## 步骤 4：更改形状宽度
更改 SmartArt 形状的宽度：
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## 步骤 5：更改形状高度
更改 SmartArt 形状的高度：
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## 步骤 6：旋转形状
旋转 SmartArt 形状：
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## 步骤 7：保存演示文稿
最后，保存修改后的演示文稿：
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## 结论
在本教程中，我们学习了如何使用 Java 和 Aspose.Slides 向 SmartArt 添加自定义子节点。通过遵循这些步骤，您可以使用自定义图形增强演示文稿，使其更具吸引力和专业性。
## 常见问题解答
### 我可以使用 Aspose.Slides for Java 添加不同类型的 SmartArt 布局吗？
是的，Aspose.Slides for Java 支持各种 SmartArt 布局，允许您选择最适合您的演示需求的布局。
### Aspose.Slides for Java 是否与不同版本的 PowerPoint 兼容？
Aspose.Slides for Java 旨在与不同版本的 PowerPoint 无缝协作，确保跨平台的兼容性和一致性。
### 我可以通过编程自定义 SmartArt 形状的外观吗？
当然！使用 Aspose.Slides for Java，您可以通过编程自定义 SmartArt 形状的外观、大小、颜色和布局，以满足您的设计偏好。
### Aspose.Slides for Java 是否提供文档和支持？
是的，您可以在 Aspose 网站上找到全面的文档并访问社区支持论坛。
### Aspose.Slides for Java 有试用版吗？
是的，您可以从网站下载 Aspose.Slides for Java 的免费试用版，以便在购买之前了解其功能和性能[这里](https://releases.aspose.com/slides/java/).