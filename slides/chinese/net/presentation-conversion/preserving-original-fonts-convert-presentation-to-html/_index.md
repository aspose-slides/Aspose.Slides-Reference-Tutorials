---
title: 保留原始字体 - 将演示文稿转换为 HTML
linktitle: 保留原始字体 - 将演示文稿转换为 HTML
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何在使用 Aspose.Slides for .NET 将演示文稿转换为 HTML 时保留原始字体。轻松确保字体一致性和视觉冲击力。
weight: 14
url: /zh/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


在本综合指南中，我们将引导您完成使用 Aspose.Slides for .NET 将演示文稿转换为 HTML 时保留原始字体的过程。我们将为您提供必要的 C# 源代码并详细解释每个步骤。在本教程结束时，您将能够确保转换后的 HTML 文档中的字体与原始演示文稿保持一致。

## 1. 简介

将 PowerPoint 演示文稿转换为 HTML 时，保留原始字体以确保内容的视觉一致性至关重要。Aspose.Slides for .NET 为实现此目的提供了强大的解决方案。在本教程中，我们将指导您完成在转换过程中保留原始字体所需的步骤。

## 2. 先决条件

在开始之前，请确保您已满足以下先决条件：

- 您的机器上安装了 Visual Studio。
- Aspose.Slides for .NET 库已添加到您的项目中。

## 3. 设置你的项目

首先，在 Visual Studio 中创建一个新项目并添加 Aspose.Slides for .NET 库作为参考。

## 4. 加载演示文稿

使用以下代码加载您的 PowerPoint 演示文稿：

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    //您的代码在这里
}
```

代替`"Your Document Directory"`以及您的演示文稿文件的路径。

## 5. 排除默认字体

要排除 Calibri 和 Arial 等默认字体，请使用以下代码：

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

您可以根据需要自定义此列表。

## 6. 嵌入所有字体

接下来，我们将所有字体嵌入到 HTML 文档中。这可确保保留原始字体。使用以下代码：

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. 另存为 HTML

现在，将演示文稿保存为嵌入字体的 HTML 文档：

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

代替`"output.html"`使用您想要的输出文件名。

## 8. 结论

在本教程中，我们演示了如何在使用 Aspose.Slides for .NET 将 PowerPoint 演示文稿转换为 HTML 时保留原始字体。通过遵循这些步骤，您可以确保转换后的 HTML 文档保持原始演示文稿的视觉完整性。

## 9. 常见问题解答

### Q1：我可以自定义排除字体的列表吗？

是的，你可以。修改`fontNameExcludeList`数组根据您的要求包含或排除特定字体。

### Q2：如果我不想嵌入所有字体怎么办？

如果您只想嵌入特定字体，您可以相应地修改代码。有关更多详细信息，请参阅 Aspose.Slides for .NET 文档。

### Q3: 使用 Aspose.Slides for .NET 有任何许可要求吗？

是的，您可能需要有效的许可证才能在项目中使用 Aspose.Slides for .NET。请参阅 Aspose 网站以获取许可信息。

### Q4: 我可以使用 Aspose.Slides for .NET 将其他文件格式转换为 HTML 吗？

Aspose.Slides for .NET 主要专注于 PowerPoint 演示文稿。要将其他文件格式转换为 HTML，您可能需要探索针对这些格式定制的其他 Aspose 产品。

### Q5：我可以在哪里获得更多资源和支持？

您可以在 Aspose 网站上找到更多文档、教程和支持。请访问[Aspose.Slides for .NET 文档](https://reference.aspose.com/slides/net/)了解详细信息。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
