---
title: Java Slides 中不使用 XPS 选项进行转换
linktitle: Java Slides 中不使用 XPS 选项进行转换
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 XPS 格式。带有源代码的分步指南。
weight: 33
url: /zh/java/presentation-conversion/convert-without-xps-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides 中不使用 XPS 选项进行转换


## 简介 在 Aspose.Slides for Java 中不使用 XPS 选项将 PowerPoint 转换为 XPS

在本教程中，我们将指导您使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 XPS（XML 纸张规范）文档的过程，而无需指定任何 XPS 选项。我们将为您提供完成此任务的分步说明和 Java 源代码。

## 先决条件

开始之前，请确保您已满足以下先决条件：

1.  Aspose.Slides for Java：确保您已在 Java 项目中安装并配置了 Aspose.Slides for Java 库。您可以从[Aspose.Slides for Java 网站](https://downloads.aspose.com/slides/java).

2. Java 开发环境：您应该在计算机上设置一个 Java 开发环境。

## 步骤 1：导入 Aspose.Slides for Java

在您的 Java 项目中，在 Java 文件的开头导入必要的 Aspose.Slides for Java 类：

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 第 2 步：加载 PowerPoint 演示文稿

现在，我们将加载要转换为 XPS 的 PowerPoint 演示文稿。替换`"Your Document Directory"`替换为您的 PowerPoint 演示文稿文件的实际路径：

```java
//文档目录的路径。
String dataDir = "Your Document Directory";

//实例化代表演示文件的 Presentation 对象
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

确保更换`"Convert_XPS.pptx"`使用您的 PowerPoint 文件的实际名称。

## 步骤 3：另存为 XPS（无 XPS 选项）

使用 Aspose.Slides for Java，您可以轻松地将加载的演示文稿保存为 XPS 文档，而无需指定任何 XPS 选项。操作方法如下：

```java
try {
    //将演示文稿保存为 XPS 文档
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

此代码块将演示文稿保存为 XPS 文档，名称为`"XPS_Output_Without_XPSOption_out.xps"`.您可以根据需要更改输出文件名。

## Java Slides 中无 XPS 选项转换的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//实例化代表演示文件的 Presentation 对象
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	//将演示文稿保存为 XPS 文档
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 XPS 文档，而无需指定任何 XPS 选项。您可以通过探索 Aspose.Slides for Java 提供的选项进一步自定义转换过程。如需更多高级功能和深入文档，请访问[Aspose.Slides for Java 文档](https://docs.aspose.com/slides/java/).

## 常见问题解答

### 如何在转换时指定 XPS 选项？

要在转换 PowerPoint 演示文稿时指定 XPS 选项，您可以使用`XpsOptions`类并设置各种属性，如图像压缩和字体嵌入。如果您对 XPS 转换有特定要求，请参阅[Aspose.Slides for Java 文档](https://docs.aspose.com/slides/java/)更多细节。

### 还有其他选项可以保存为其他格式吗？

是的，Aspose.Slides for Java 除了 XPS 之外还提供各种输出格式，例如 PDF、TIFF 和 HTML。您可以通过更改`SaveFormat`调用时的参数`save`方法。请参阅文档以获取受支持格式的完整列表。

### 如何处理转换过程中的异常？

您可以实现异常处理，以妥善处理转换过程中可能发生的任何错误。如代码所示，`try`和`finally`即使发生异常，块也可以确保正确处置资源。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
