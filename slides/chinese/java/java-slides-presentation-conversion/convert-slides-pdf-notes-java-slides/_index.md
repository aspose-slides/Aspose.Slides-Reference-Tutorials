---
title: 使用 Java Slides 将幻灯片转换为带注释的 PDF
linktitle: 使用 Java Slides 将幻灯片转换为带注释的 PDF
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 将 PowerPoint 幻灯片转换为带注释的 PDF。面向 Java 开发人员的分步指南。增强您的演示文稿共享。
weight: 19
url: /zh/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 使用 Java 中的注释将幻灯片转换为 PDF 的简介

在数字演示领域，将幻灯片转换为带有注释的 PDF 是一项宝贵的功能。Java 开发人员可以使用 Aspose.Slides for Java 库实现此目的，该库提供了一套强大的工具，可用于以编程方式处理 PowerPoint 演示文稿。在本分步指南中，我们将探讨如何使用 Java 和 Aspose.Slides for Java 将幻灯片转换为带有注释的 PDF。

## 先决条件

在深入研究代码之前，请确保您已满足以下先决条件：

- 您的系统上安装了 Java 开发工具包 (JDK)。
-  Aspose.Slides for Java 库。您可以从以下网址下载[这里](https://releases.aspose.com/slides/java/).

现在我们有了大纲，让我们逐步深入实施。
## 步骤 1：设置项目

首先，创建一个 Java 项目并将 Aspose.Slides for Java 库添加到项目的依赖项中。

## 第 2 步：加载演示文稿

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 步骤 3：创建新的演示文稿

```java
Presentation auxPresentation = new Presentation();
```

## 步骤 4：复制幻灯片

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## 步骤 5：调整幻灯片大小

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 步骤 6：配置 PDF 选项

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## 步骤 7：另存为 PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Java Slides 中将幻灯片转换为带注释的 PDF 的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//实例化代表演示文件的 Presentation 对象
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		//设置幻灯片类型和大小
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java 将幻灯片转换为带有注释的 PDF。我们介绍了设置项目、加载演示文稿、创建新演示文稿、复制幻灯片、调整幻灯片大小、配置 PDF 选项，以及最后将演示文稿保存为带有注释的 PDF。

## 常见问题解答

### 如何安装 Aspose.Slides for Java？

要安装 Aspose.Slides for Java，请按照以下步骤操作：
1. 下载地址：[这里](https://releases.aspose.com/slides/java/).
2. 将 JAR 文件添加到 Java 项目的类路径。

### 我可以自定义生成的 PDF 中的注释位置吗？

是的，您可以通过修改`NotesPositions`PDF 选项中的枚举。在本教程中，我们将其设置为`BottomFull`，但您也可以探索其他选项。

### 使用 Aspose.Slides for Java 有任何许可要求吗？

是的，Aspose.Slides for Java 是一个商业库，您可能需要获得许可证才能在生产中使用它。请访问 Aspose 网站了解许可详情。

### 我可以一次转换多张幻灯片吗？

当然可以！您可以循环浏览演示文稿中的幻灯片并将其克隆到新演示文稿中，这样您就可以一次性将多张幻灯片转换为带有注释的 PDF。

### 在哪里可以找到有关 Aspose.Slides for Java 的更多文档？

您可以在网站上找到有关 Aspose.Slides for Java 的详细文档：[Aspose.Slides for Java API 参考](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
