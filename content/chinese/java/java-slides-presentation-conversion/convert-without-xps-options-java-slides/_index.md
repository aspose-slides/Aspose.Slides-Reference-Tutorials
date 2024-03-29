---
title: Java 幻灯片中不使用 XPS 选项进行转换
linktitle: Java 幻灯片中不使用 XPS 选项进行转换
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 XPS 格式。带有源代码的分步指南。
type: docs
weight: 33
url: /zh/java/presentation-conversion/convert-without-xps-options-java-slides/
---

## 简介 在 Aspose.Slides for Java 中将 PowerPoint 转换为 XPS，无需使用 XPS 选项

在本教程中，我们将指导您完成使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 XPS（XML 纸张规范）文档的过程，而无需指定任何 XPS 选项。我们将为您提供完成此任务的分步说明和 Java 源代码。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1.  Aspose.Slides for Java：确保您已在 Java 项目中安装并配置了 Aspose.Slides for Java 库。您可以从[Aspose.Slides for Java 网站](https://downloads.aspose.com/slides/java).

2. Java 开发环境：您的计算机上应该安装有 Java 开发环境。

## 第 1 步：导入 Java 版 Aspose.Slides

在您的 Java 项目中，在 Java 文件的开头导入 Java 类所需的 Aspose.Slides：

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 第 2 步：加载 PowerPoint 演示文稿

现在，我们将加载您想要转换为 XPS 的 PowerPoint 演示文稿。代替`"Your Document Directory"`与 PowerPoint 演示文稿文件的实际路径：

```java
//文档目录的路径。
String dataDir = "Your Document Directory";

//实例化表示演示文稿文件的演示文稿对象
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

确保您更换`"Convert_XPS.pptx"`与您的 PowerPoint 文件的实际名称。

## 步骤 3：另存为 XPS（不带 XPS 选项）

使用 Aspose.Slides for Java，您可以轻松地将加载的演示文稿另存为 XPS 文档，而无需指定任何 XPS 选项。您可以这样做：

```java
try {
    //将演示文稿保存到 XPS 文档
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

此代码块将演示文稿另存为 XPS 文档，名称为`"XPS_Output_Without_XPSOption_out.xps"`。您可以根据需要更改输出文件名。

## Java 幻灯片中不带 XPS 选项的转换的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//实例化表示演示文稿文件的演示文稿对象
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	//将演示文稿保存到 XPS 文档
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 XPS 文档，而无需指定任何 XPS 选项。您可以通过探索 Aspose.Slides for Java 提供的选项来进一步自定义转换过程。如需更多高级功能和深入文档，请访问[Aspose.Slides for Java 文档](https://docs.aspose.com/slides/java/).

## 常见问题解答

### 转换时如何指定 XPS 选项？

要在转换 PowerPoint 演示文稿时指定 XPS 选项，您可以使用`XpsOptions`类并设置各种属性，例如图像压缩和字体嵌入。如果您对 XPS 转换有特定要求，请参阅[Aspose.Slides for Java 文档](https://docs.aspose.com/slides/java/)更多细节。

### 是否有其他选项可以保存为其他格式？

是的，Aspose.Slides for Java 还提供除 XPS 之外的各种输出格式，例如 PDF、TIFF 和 HTML。您可以通过更改来指定所需的输出格式`SaveFormat`调用时的参数`save`方法。请参阅文档以获取支持格式的完整列表。

### 转换过程中出现异常如何处理？

您可以实现异常处理，以优雅地处理转换过程中可能发生的任何错误。如代码所示，一个`try`和`finally`即使发生异常，也可以使用块来确保正确的资源处理。