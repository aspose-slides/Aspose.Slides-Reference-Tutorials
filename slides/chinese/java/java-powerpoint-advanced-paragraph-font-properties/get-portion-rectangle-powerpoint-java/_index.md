---
title: 使用 Java 在 PowerPoint 中获取部分矩形
linktitle: 使用 Java 在 PowerPoint 中获取部分矩形
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 通过本详细的分步教程学习如何使用 Aspose.Slides for Java 获取 PowerPoint 中的部分矩形。非常适合 Java 开发人员。
weight: 12
url: /zh/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介绍
使用 Aspose.Slides for Java 可以轻松在 Java 中创建动态演示文稿。在本教程中，我们将深入探讨使用 Aspose.Slides 在 PowerPoint 中获取部分矩形的细节。我们将介绍从设置环境到逐步分解代码的所有内容。那么，让我们开始吧！
## 先决条件
在我们进入代码之前，让我们确保您拥有顺利进行所需的一切：
1. Java 开发工具包 (JDK)：确保您的机器上安装了 JDK 8 或更高版本。
2.  Aspose.Slides for Java：从以下网址下载最新版本[这里](https://releases.aspose.com/slides/java/).
3. 集成开发环境 (IDE)：Eclipse、IntelliJ IDEA 或您选择的任何其他 Java IDE。
4. Java 基础知识：了解 Java 编程至关重要。
## 导入包
首先，让我们导入必要的软件包。这将包括 Aspose.Slides 和其他一些用于高效处理任务的软件包。
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## 步骤 1：设置演示文稿
第一步是创建一个新的演示文稿。这将是我们工作的画布。
```java
Presentation pres = new Presentation();
```
## 步骤 2：创建表
现在，让我们在演示文稿的第一张幻灯片中添加一个表格。该表格将包含我们要添加文本的单元格。
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## 步骤 3：向单元格添加段落
接下来，我们将创建段落并将其添加到表格中的特定单元格。这涉及清除所有现有文本，然后添加新段落。
```java
//创建段落
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
//在表格单元格中添加文本
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## 步骤 4：向自选图形添加文本框
为了使我们的演示文稿更具活力，我们将向自选图形添加一个文本框并设置其对齐方式。
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## 步骤5：计算坐标
我们需要获取表格单元格左上角的坐标。这将帮助我们准确放置形状。
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## 步骤 6：为段落和部分添加框架
使用`IParagraph.getRect()`和`IPortion.getRect()`方法，我们可以为段落和部分添加框架。这涉及遍历段落和部分、在它们周围创建形状以及自定义它们的外观。
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## 步骤 7：向自选图形段落添加框架
同样，我们将为自选图形中的段落添加框架，以增强演示文稿的视觉吸引力。
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## 步骤 8：保存演示文稿
最后，我们将演示文稿保存到指定路径。
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## 步骤 9：清理
处置表示对象以释放资源是一种很好的做法。
```java
if (pres != null) pres.dispose();
```
## 结论
恭喜！您已成功学会如何使用 Aspose.Slides for Java 获取 PowerPoint 中的部分矩形。这个功能强大的库为以编程方式创建动态且具有视觉吸引力的演示文稿开辟了无限可能。深入了解 Aspose.Slides 并探索更多功能以进一步增强您的演示文稿。
## 常见问题解答
### 什么是 Aspose.Slides for Java？
Aspose.Slides for Java 是一个功能强大的库，允许开发人员以编程方式创建、修改和操作 PowerPoint 演示文稿。
### 我可以在商业项目中使用 Aspose.Slides for Java 吗？
是的，Aspose.Slides for Java 可用于商业项目。您可以从以下网站购买许可证[这里](https://purchase.aspose.com/buy).
### Aspose.Slides for Java 有免费试用版吗？
是的，你可以从下载免费试用版[这里](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.Slides for Java 的文档？
文档可用[这里](https://reference.aspose.com/slides/java/).
### 如何获得 Aspose.Slides for Java 的支持？
您可以从 Aspose 论坛获得支持[这里](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
