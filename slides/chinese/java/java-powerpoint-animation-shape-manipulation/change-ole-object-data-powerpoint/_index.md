---
title: 在 PowerPoint 中更改 OLE 对象数据
linktitle: 在 PowerPoint 中更改 OLE 对象数据
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 更改 PowerPoint 中的 OLE 对象数据。高效、轻松更新的分步指南。
weight: 14
url: /zh/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介绍
当您需要更新嵌入内容而无需手动编辑每张幻灯片时，更改 PowerPoint 演示文稿中的 OLE 对象数据可能是一项至关重要的任务。本综合指南将引导您使用 Aspose.Slides for Java（一个专为处理 PowerPoint 演示文稿而设计的强大库）完成该过程。无论您是经验丰富的开发人员还是刚刚起步，您都会发现本教程很有帮助且易于理解。
## 先决条件
在深入研究代码之前，让我们确保您拥有开始所需的一切。
1.  Java 开发工具包 (JDK)：确保你的系统上安装了 JDK。你可以从以下网址下载：[Oracle 的网站](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java：从下载最新版本[Aspose.Slides 下载页面](https://releases.aspose.com/slides/java/).
3. 集成开发环境 (IDE)：您可以使用任何 Java IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。
4.  Aspose.Cells for Java：这是修改 OLE 对象内嵌入数据所必需的。从以下位置下载[Aspose.Cells 下载页面](https://releases.aspose.com/cells/java/).
5. 演示文件：准备好一个嵌入 OLE 对象的 PowerPoint 文件。在本教程中，我们将其命名为`ChangeOLEObjectData.pptx`.
## 导入包
首先，让我们在你的 Java 项目中导入必要的包。
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

现在，让我们将这个过程分解为简单、易于管理的步骤。
## 步骤 1：加载 PowerPoint 演示文稿
首先，您需要加载包含 OLE 对象的 PowerPoint 演示文稿。
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## 步骤 2：访问包含 OLE 对象的幻灯片
接下来，获取嵌入 OLE 对象的幻灯片。
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 步骤 3：在幻灯片中查找 OLE 对象
遍历幻灯片中的形状来定位 OLE 对象。
```java
OleObjectFrame ole = null;
//遍历 Ole 框架的所有形状
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## 步骤 4：从 OLE 对象中提取嵌入的数据
如果找到 OLE 对象，则提取其嵌入的数据。
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## 步骤 5：使用 Aspose.Cells 修改嵌入数据
现在，使用 Aspose.Cells 读取和修改嵌入的数据，在本例中可能是 Excel 工作簿。
```java
    Workbook wb = new Workbook(msln);
    //修改工作簿数据
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## 步骤 6：将修改后的数据保存回 OLE 对象
进行必要的更改后，将修改后的工作簿保存回 OLE 对象。
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## 步骤 7：保存更新后的演示文稿
最后，保存更新后的 PowerPoint 演示文稿。
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 结论
使用 Aspose.Slides for Java 更新 PowerPoint 演示文稿中的 OLE 对象数据是一个简单的过程，只要将其分解为简单的步骤即可。本指南引导您完成加载演示文稿、访问和修改嵌入的 OLE 数据以及保存更新的演示文稿。通过这些步骤，您可以高效地以编程方式管理和更新 PowerPoint 幻灯片中的嵌入内容。
## 常见问题解答
### PowerPoint 中的 OLE 对象是什么？
OLE（对象链接和嵌入）对象允许将其他应用程序（如 Excel 电子表格）的内容嵌入到 PowerPoint 幻灯片中。
### 我可以将 Aspose.Slides 与其他编程语言一起使用吗？
是的，Aspose.Slides 支持多种语言，包括 .NET、Python 和 C++.
### 我需要 Aspose.Cells 来修改 PowerPoint 中的 OLE 对象吗？
是的，如果 OLE 对象是 Excel 电子表格，则需要 Aspose.Cells 来修改它。
### Aspose.Slides 有试用版吗？
是的，你可以得到一个[免费试用](https://releases.aspose.com/)测试 Aspose.Slides 的功能。
### 在哪里可以找到 Aspose.Slides 的文档？
您可以找到有关[Aspose.Slides 文档页面](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
