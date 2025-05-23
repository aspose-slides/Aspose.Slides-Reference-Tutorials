---
"description": "使用 Aspose.Slides for .NET 轻松将带有演讲者备注的演示文稿幻灯片转换为 PDF。无缝保留内容和上下文。"
"linktitle": "将幻灯片转换为带注释的 PDF"
"second_title": "Aspose.Slides .NET PowerPoint 处理 API"
"title": "将幻灯片转换为带注释的 PDF"
"url": "/zh/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 将幻灯片转换为带注释的 PDF


# 编写使用 Aspose.Slides for .NET 将幻灯片转换为带注释的 PDF 的分步教程指南

您是否正在寻找一种可靠的方法，将 PowerPoint 幻灯片转换为 PDF 格式，同时保留所有重要笔记？不用再找了！在本综合教程中，我们将指导您逐步使用 Aspose.Slides for .NET 完成此任务。

## 1. 简介

将 PowerPoint 幻灯片转换为带有注释的 PDF 格式，是共享演示文稿的有效工具，同时还能确保保留重要的内容和注释。Aspose.Slides for .NET 为这项任务提供了强大的解决方案。

## 2. 设置您的环境

在深入编码过程之前，请确保您已设置必要的环境。您需要：

- Visual Studio 或您首选的 .NET 开发环境。
- 已安装 Aspose.Slides for .NET 库。
- 包含要转换的注释的 PowerPoint 演示文稿。

## 3. 加载演示文稿

在 C# 代码中，你需要加载要转换的 PowerPoint 演示文稿。操作方法如下：

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. 克隆幻灯片

为了确保您的 PDF 包含所有必要的带注释的幻灯片，您可以从原始演示文稿中克隆它们。操作方法如下：

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5.调整幻灯片大小

您可能需要调整幻灯片大小以适合您的 PDF。Aspose.Slides for .NET 可让您轻松实现这一点：

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6.配置 PDF 选项

要控制注释在 PDF 中的显示方式，您可以配置 PDF 选项：

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. 使用注释保存为 PDF

最后，您可以将演示文稿保存为带有注释的 PDF：

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. 结论

恭喜！您已成功将 PowerPoint 幻灯片转换为 PDF 格式，同时保留了所有重要注释。Aspose.Slides for .NET 使此过程变得简单高效。

## 9. 常见问题解答

### Q1：我可以自定义 PDF 中注释的布局吗？

是的，您可以使用 `INotesCommentsLayoutingOptions` 在 PDF 选项中。

### 问题2：Aspose.Slides for .NET 除了支持 PDF 之外还支持其他输出格式吗？

是的，Aspose.Slides for .NET 支持各种输出格式，包括 PPTX、DOCX 等。

### 问题 3：Aspose.Slides for .NET 有试用版吗？

是的，您可以免费试用 Aspose.Slides for .NET，网址： [https://releases.aspose.com/](https://releases。aspose.com/).

### 问题 4：在哪里可以获得 Aspose.Slides for .NET 的支持？

您可以在以下位置找到支持和社区讨论 [https://forum.aspose.com/](https://forum。aspose.com/).

### Q5：我可以购买 Aspose.Slides for .NET 的临时许可证吗？

是的，您可以购买临时许可证 [https://purchase.aspose.com/temporary-license/](https://purchase。aspose.com/temporary-license/).

总而言之，使用 Aspose.Slides for .NET，您可以轻松地将 PowerPoint 幻灯片转换为 PDF 格式，并保留注释。对于需要与同事和客户共享演示文稿，同时又能确保重要内容不丢失的专业人士来说，它是一款非常实用的工具。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}