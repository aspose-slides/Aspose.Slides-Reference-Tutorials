---
title: 将演示文稿转换为带有嵌入字体的 HTML
linktitle: 将演示文稿转换为带有嵌入字体的 HTML
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 使用 Aspose.Slides for .NET 将 PowerPoint 演示文稿转换为带有嵌入字体的 HTML。无缝保持原创性。
weight: 13
url: /zh/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将演示文稿转换为带有嵌入字体的 HTML


在当今的数字时代，在线共享演示文稿和文档已成为一种常见做法。然而，经常出现的一个挑战是确保在将演示文稿转换为 HTML 时正确显示字体。本分步教程将指导您完成使用 Aspose.Slides for .NET 将演示文稿转换为带有嵌入字体的 HTML 的过程，确保您的文档看起来与您想要的一样。

## Aspose.Slides for .NET 简介

在深入研究本教程之前，让我们简要介绍一下 Aspose.Slides for .NET。它是一个功能强大的库，允许开发人员在 .NET 应用程序中处理 PowerPoint 演示文稿。使用 Aspose.Slides，您可以以编程方式创建、修改和转换 PowerPoint 文件。

## 先决条件

在开始之前，请确保您已满足以下先决条件：

-  Aspose.Slides for .NET：您应该在项目中安装 Aspose.Slides 库。您可以从以下网址下载[这里](https://releases.aspose.com/slides/net/).

## 步骤 1：设置你的项目

1. 在您首选的 .NET 开发环境中创建一个新项目或打开一个现有项目。

2. 在您的项目中添加对 Aspose.Slides 库的引用。

3. 在代码中导入必要的命名空间：

   ```csharp
   using Aspose.Slides;
   ```

## 第 2 步：加载演示文稿

首先，您需要加载要转换为 HTML 的演示文稿。替换`"Your Document Directory"`与演示文稿文件所在的实际目录。

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    //您的代码在此处
}
```

## 步骤 3：排除默认演示字体

在此步骤中，您可以指定要从嵌入中排除的任何默认演示字体。这有助于优化生成的 HTML 文件的大小。

```csharp
string[] fontNameExcludeList = { };
```

## 步骤 4：选择 HTML 控制器

现在，您有两种在 HTML 中嵌入字体的选项：

### 选项 1：嵌入所有字体

要嵌入演示文稿中使用的所有字体，请使用`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### 选项 2：链接所有字体

要链接到演示文稿中使用的所有字体，请使用`LinkAllFontsHtmlController`您应该指定字体在系统中所在的目录。

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## 步骤 5：定义 HTML 选项

创建一个`HtmlOptions`对象并将 HTML 格式化程序设置为您在上一步中选择的格式化程序。

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) //使用 embedFontsController 嵌入所有字体
};
```

## 步骤 6：另存为 HTML

最后，将演示文稿保存为 HTML 文件。您可以选择`SaveFormat.Html`或者`SaveFormat.Html5`取决于您的要求。

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## 结论

恭喜！您已成功使用 Aspose.Slides for .NET 将演示文稿转换为带有嵌入字体的 HTML。这可确保您的字体在网上共享演示文稿时能够正确显示。

现在，您可以轻松自信地分享格式精美的演示文稿，因为您知道观众将看到与您预期完全一致的内容。

有关更多信息和详细的 API 参考，请查看[Aspose.Slides for .NET 文档](https://reference.aspose.com/slides/net/).

## 常见问题解答

### 1. 我可以使用 Aspose.Slides for .NET 以批处理模式将 PowerPoint 演示文稿转换为 HTML 吗？

是的，您可以使用 Aspose.Slides for .NET 将多个演示文稿批量转换为 HTML，方法是循环遍历演示文稿文件并将转换过程应用于每个演示文稿。

### 2. 有没有办法自定义 HTML 输出的外观？

当然！Aspose.Slides for .NET 提供了各种选项来自定义 HTML 输出的外观和格式，例如调整颜色、字体和布局。

### 3. 使用 Aspose.Slides for .NET 在 HTML 中嵌入字体有什么限制吗？

虽然 Aspose.Slides for .NET 提供了出色的字体嵌入功能，但请记住，嵌入字体时 HTML 文件的大小可能会增加。请确保优化您的字体选择以适合网络使用。

### 4. 我可以使用 Aspose.Slides for .NET 将 PowerPoint 演示文稿转换为其他格式吗？

是的，Aspose.Slides for .NET 支持多种输出格式，包括 PDF、图像等。您可以轻松地将演示文稿转换为您选择的格式。

### 5. 在哪里可以找到有关 Aspose.Slides for .NET 的更多资源和支持？

您可以访问丰富的资源，包括文档，[Aspose.Slides for .NET API 参考](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
