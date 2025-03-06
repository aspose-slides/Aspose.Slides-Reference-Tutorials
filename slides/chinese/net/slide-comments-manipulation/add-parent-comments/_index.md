---
title: 使用 Aspose.Slides 将父注释添加到幻灯片
linktitle: 将家长评论添加到幻灯片
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for .NET 向您的 PowerPoint 演示文稿添加交互式评论和回复。增强参与度和协作。
weight: 12
url: /zh/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


您是否希望使用交互式功能增强 PowerPoint 演示文稿？Aspose.Slides for .NET 允许您合并评论和回复，为您的观众创造动态且引人入胜的体验。在本分步教程中，我们将向您展示如何使用 Aspose.Slides for .NET 向幻灯片添加父评论。让我们深入探索这一令人兴奋的功能。

## 先决条件

在开始之前，请确保您已满足以下先决条件：

1.  Aspose.Slides for .NET：确保您已安装 Aspose.Slides for .NET。您可以下载它[这里](https://releases.aspose.com/slides/net/).

2. Visual Studio：您需要 Visual Studio 来创建和运行您的 .NET 应用程序。

3. C# 基础知识：本教程假设您对 C# 编程有基本的了解。

现在我们已经满足了先决条件，让我们继续导入必要的命名空间。

## 导入命名空间

首先，您需要将相关的命名空间导入到您的项目中。这些命名空间提供了使用 Aspose.Slides for .NET 所需的类和方法。

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

有了先决条件和命名空间，让我们将向幻灯片添加父注释的过程分解为多个步骤。

## 步骤 1：创建演示文稿

首先，您需要使用 Aspose.Slides for .NET 创建一个新演示文稿。此演示文稿将成为您添加评论的画布。

```csharp
//输出目录的路径。
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    //您添加评论的代码将放在这里。
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

在上面的代码中，替换`"Output Path"`使用输出演示所需的路径。

## 第 2 步：添加评论作者

在添加评论之前，您需要定义这些评论的作者。在此示例中，我们有两个作者，“Author_1”和“Author_2”，每个作者都由一个实例表示`ICommentAuthor`.

```csharp
//添加评论
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

//添加对评论1的回复
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

这一步我们创建两个评论作者，并添加初始评论和对评论的回复。

## 步骤 3：添加更多回复

要创建评论的层次结构，您可以向现有评论添加更多回复。这里，我们向“评论 1”添加第二个回复。

```csharp
//添加对评论1的回复
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

这会在您的演示文稿中建立对话流。

## 步骤 4：添加嵌套回复

评论也可以嵌套回复。为了演示这一点，我们添加了对“评论 1 的回复 2”的回复，从而创建了子回复。

```csharp
//添加回复以回复
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

此步骤突出了 Aspose.Slides for .NET 在管理评论层次结构方面的多功能性。

## 步骤 5：更多评论和回复

您可以根据需要继续添加更多评论和回复。在此示例中，我们添加了另外两条评论，并对其中一条评论进行了回复。

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

此步骤演示如何为您的演示文稿创建引人入胜且具有交互性的内容。

## 步骤 6：显示层次结构

要直观地显示评论层次结构，您可以在控制台上显示它。此步骤是可选的，但有助于调试和理解结构。

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## 步骤 7：删除评论

在某些情况下，您可能需要删除评论及其回复。以下代码片段演示了如何删除“comment1”及其所有回复。

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

此步骤对于管理和更新您的演示文稿内容很有用。

通过这些步骤，您可以使用 Aspose.Slides for .NET 创建带有交互式评论和回复的演示文稿。无论您是想吸引观众还是与团队成员合作，此功能都提供了广泛的可能性。

## 结论

Aspose.Slides for .NET 提供了一套强大的工具来增强您的 PowerPoint 演示文稿。通过添加评论和回复的功能，您可以创建吸引观众的动态交互式内容。本分步指南向您展示了如何向幻灯片添加父评论、建立层次结构，甚至在必要时删除评论。通过遵循这些步骤并浏览 Aspose.Slides 文档[这里](https://reference.aspose.com/slides/net/)，您可以将您的演示提升到一个新的水平。

## 常见问题解答

### 我可以在演示文稿中的特定幻灯片中添加评论吗？
是的，您可以在创建评论时指定目标幻灯片，从而为演示文稿中的任何幻灯片添加评论。

### 是否可以自定义演示文稿中评论的外观？
Aspose.Slides for .NET 允许您自定义注释的外观，包括其文本、作者信息和幻灯片上的位置。

### 我可以将评论和回复导出到单独的文件吗？
是的，您可以将评论和回复导出到单独的演示文稿文件，如步骤 7 所示。

### Aspose.Slides for .NET 是否与最新版本的 PowerPoint 兼容？
Aspose.Slides for .NET 旨在与多种 PowerPoint 版本兼容，确保与最新版本兼容。

### Aspose.Slides for .NET 是否有任何可用的许可选项？
是的，您可以在 Aspose 网站上探索许可选项，包括临时许可证[这里](https://purchase.aspose.com/buy)或尝试免费试用[这里](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
