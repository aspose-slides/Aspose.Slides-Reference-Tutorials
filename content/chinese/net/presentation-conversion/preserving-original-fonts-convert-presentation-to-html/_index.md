---
title: 保留原始字体 - 将演示文稿转换为 HTML
linktitle: 保留原始字体 - 将演示文稿转换为 HTML
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for .NET 将演示文稿转换为 HTML 时保留原始字体。轻松确保字体一致性和视觉冲击力。
type: docs
weight: 14
url: /zh/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

## 介绍

在数字时代，演示文稿已从传统的幻灯片演变为动态的多媒体体验。将演示文稿转换为 HTML 时，保持视觉完整性至关重要，尤其是在字体方面。 Aspose.Slides for .NET 是一个功能强大的库，可为这一需求提供无缝的解决方案。

## 了解字体保护的重要性

字体是任何演示文稿设计和品牌的基本方面。它们传达特定的语气、增强可读性并反映消息的本质。将演示文稿转换为 HTML 时，保留这些字体可确保一致且身临其境的用户体验。

## .NET 的 Aspose.Slides 入门

## 安装

首先，您需要安装 Aspose.Slides for .NET 库。您可以通过 NuGet（.NET 的包管理器）来执行此操作。打开 NuGet 包管理器控制台并运行以下命令：

```bash
Install-Package Aspose.Slides
```

## 加载演示文稿

安装该库后，您就可以开始在 .NET 应用程序中使用它。使用以下代码片段加载您的演示文稿：

```csharp
using Aspose.Slides;

//加载演示文稿
using var presentation = new Presentation("your-presentation.pptx");
```

## 保留原始字体

为了确保在转换过程中保留原始字体，您需要设置适当的选项。 Aspose.Slides 允许您控制字体在 HTML 输出中的嵌入方式。您可以这样做：

## 代码实现

```csharp
using Aspose.Slides.Export;

//创建 HTML 选项的实例
var options = new HtmlOptions
{
    FontsFolder = "fonts", //保存字体的文件夹
    HtmlFormatter = HtmlFormatter.CreateDocumentFormatter("", false),
    HtmlFormatterExternalResources = false,
    HtmlFormatterEmbedFonts = HtmlFormatterEmbedFontEnum.EmbedAll
};

//将演示文稿转换为 HTML
presentation.Save("output.html", SaveFormat.Html, options);
```

## 额外的定制

## 处理字体的 CSS

虽然上面的代码保留了字体，但您可能需要微调 CSS 以确保在不同设备上呈现一致的渲染。您可以在 CSS 文件中包含字体样式并将其链接到 HTML 输出。

## 处理外部资源

如果您的演示文稿包含图像或视频等外部资源，您应该在 HTML 文件中适当管理它们的路径，以保持演示文稿的完整性。

## 测试和质量保证

在最终完成 HTML 演示文稿之前，请在各种设备和浏览器上执行彻底的测试，以确保字体正确呈现。此步骤可确保您的观众按预期体验演示。

## 结论

将演示文稿转换为 HTML 时保留原始字体对于保持内容的视觉效果和可读性至关重要。 Aspose.Slides for .NET 简化了这一过程，使您能够无缝转换演示文稿，同时确保字体一致性。

## 常见问题解答

## Aspose.Slides 如何处理字体嵌入？

Aspose.Slides 提供不同的字体嵌入选项。您可以选择嵌入所有字体、仅嵌入演示文稿中使用的字体或根本不嵌入任何字体。

## 我可以进一步自定义 HTML 输出吗？

绝对地！您可以修改 CSS 样式、添加与 JavaScript 的交互性，并优化 HTML 结构以实现 SEO 和性能。

## Aspose.Slides 还可以将演示文稿转换为哪些其他格式？

除了 HTML 之外，Aspose.Slides 还支持转换为各种格式，包括 PDF、图像和 SVG。

## Aspose.Slides 适合简单和复杂的演示吗？

是的，Aspose.Slides 用途广泛，可以处理不同复杂程度的演示文稿，确保在整个转换过程中保持一致的字体。

## Aspose.Slides 多久更新一次？

Aspose.Slides 定期更新以纳入新功能、改进和兼容性增强，确保为演示文稿转换提供可靠且最新的解决方案。