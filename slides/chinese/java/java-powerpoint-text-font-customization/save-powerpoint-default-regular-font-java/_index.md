---
title: 使用 Java 以默认常规字体保存 PowerPoint
linktitle: 使用 Java 以默认常规字体保存 PowerPoint
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 以编程方式操作 PowerPoint 演示文稿。通过分步教程掌握 Java PowerPoint 处理。
weight: 12
url: /zh/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 以默认常规字体保存 PowerPoint

## 介绍
在 Java 开发领域，以编程方式创建和操作 PowerPoint 演示文稿可以大大提高生产力和自定义选项。Aspose.Slides for Java 是一个强大的库，使开发人员能够高效处理 PowerPoint 文件，提供从简单修改到复杂演示文稿的全套功能。
## 先决条件
在开始使用 Aspose.Slides for Java 之前，请确保您已设置以下先决条件：
1. Java 开发工具包 (JDK): Aspose.Slides for Java 需要 JDK 1.8 或更高版本才能正常运行。
2. Aspose.Slides for Java JAR: 从以下网址下载最新版本的 Aspose.Slides for Java[这里](https://releases.aspose.com/slides/java/).
3. 集成开发环境 (IDE)：使用 IntelliJ IDEA、Eclipse 或您选择的其他 Java IDE。
4. 对 Java 的基本了解：必须熟悉 Java 编程语言基础知识。

## 导入包
要开始使用 Aspose.Slides for Java，请导入必要的包：
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
这确保您可以访问 Aspose.Slides for Java 提供的所有类和方法。
## 步骤 1：设置你的项目
首先，在您的 IDE 中创建一个新的 Java 项目，并将 Aspose.Slides for Java JAR 文件包含在项目的构建路径中。
## 步骤 2：初始化展示对象
实例化`Presentation`通过从本地目录加载现有的 PowerPoint 文件 (.pptx) 来对象。
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
//负载演示
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
代替`"Your Document Directory"`和`"Your Output Directory"`与您的实际文件路径。
## 步骤 3：使用默认常规字体保存演示文稿
使用以下方式指定输出格式（HTML 和 PDF）的默认常规字体`HtmlOptions`和`PdfOptions`分别。
```java
try {
    // HTML 保存选项
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    //PDF 保存选项
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
确保更换`"Arial Black"`和`"Lucida Console"`使用您想要的默认常规字体。

## 结论
通过以下步骤，您学会了如何使用 Aspose.Slides for Java 有效地处理 PowerPoint 演示文稿。此功能允许您自动执行任务、自定义演示文稿并使用高级 PowerPoint 处理功能增强 Java 应用程序。
## 常见问题解答
### Aspose.Slides for Java 可以与旧版本的 JDK 一起使用吗？
Aspose.Slides for Java 需要 JDK 1.8 或更高版本才能兼容。
### 如何获得 Aspose.Slides for Java 的临时许可？
您可以从[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以找到有关 Aspose.Slides for Java 的更详细文档？
探索全面的文档[这里](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java 有社区支持吗？
是的，你可以获得社区支持[这里](https://forum.aspose.com/c/slides/11).
### 我可以免费试用 Aspose.Slides for Java 吗？
是的，下载免费试用版[这里](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
