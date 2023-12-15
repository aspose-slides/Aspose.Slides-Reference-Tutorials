---
title: 在具有自定义尺寸的幻灯片中生成缩略图
linktitle: 生成具有自定义尺寸的缩略图
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for .NET 从 PowerPoint 演示文稿生成自定义缩略图。增强用户体验和功能。
type: docs
weight: 13
url: /zh/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

无论您是构建交互式应用程序、增强用户体验还是优化各种平台的内容，创建 PowerPoint 演示文稿的自定义缩略图都是一项宝贵的资产。在本教程中，我们将指导您完成使用 Aspose.Slides for .NET 库从 PowerPoint 演示文稿生成自定义缩略图的过程。这个功能强大的库允许您在 .NET 应用程序中以编程方式操作、转换和增强 PowerPoint 文件。

## 先决条件

在我们深入生成自定义缩略图之前，请确保您满足以下先决条件：

### 1..NET 的 Aspose.Slides

您需要在项目中安装 Aspose.Slides for .NET 库。如果您还没有，您可以找到必要的文档和下载链接[这里](https://reference.aspose.com/slides/net/).

### 2. PowerPoint 演示

确保您拥有要从中生成自定义缩略图的 PowerPoint 演示文稿。该演示文稿应该可以在您的项目目录中访问。

### 三、开发环境

要学习本教程，您应该具备使用 C# 进行 .NET 编程的实用知识，并设置开发环境（例如 Visual Studio）。

现在我们已经介绍了先决条件，让我们将生成自定义缩略图的过程分解为分步说明。

## 导入命名空间

首先，您需要在 C# 代码中包含所需的命名空间。这些命名空间允许您使用 Aspose.Slides 并操作 PowerPoint 演示文稿。

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 第 1 步：加载演示文稿

首先，加载要从中生成自定义缩略图的 PowerPoint 演示文稿。这是使用 Aspose.Slides 库实现的。

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

//实例化表示演示文稿文件的演示文稿类
using (Presentation pres = new Presentation(srcFileName))
{
    //您的缩略图生成代码将位于此处
}
```

## 第 2 步：访问幻灯片

在加载的演示文稿中，您需要访问要从中生成自定义缩略图的特定幻灯片。您可以通过索引选择幻灯片。

```csharp
//访问第一张幻灯片（您可以根据需要更改索引）
ISlide sld = pres.Slides[0];
```

## 第 3 步：定义自定义缩略图尺寸

指定自定义缩略图所需的尺寸。您可以根据应用程序的要求定义宽度和高度（以像素为单位）。

```csharp
int desiredX = 1200; //宽度
int desiredY = 800;  //高度
```

## 第 4 步：计算比例因子

要保持幻灯片的纵横比，请根据幻灯片的尺寸和所需尺寸计算 X 和 Y 尺寸的缩放系数。

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 第 5 步：生成缩略图

使用指定的自定义尺寸创建幻灯片的全尺寸图像，并将其以 JPEG 格式保存到磁盘。

```csharp
//创建全尺寸图像
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

//将图像以 JPEG 格式保存到磁盘
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

现在您已经执行了这些步骤，您应该已经成功地从 PowerPoint 演示文稿生成了自定义缩略图。

## 结论

使用 Aspose.Slides for .NET 从 PowerPoint 演示文稿生成自定义缩略图是一项宝贵的技能，可以增强应用程序的用户体验和功能。通过遵循本教程中概述的步骤，您可以轻松创建满足您的特定要求的自定义缩略图。

---

## 常见问题解答（常见问题）

### 什么是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一个功能强大的库，允许开发人员在 .NET 应用程序中以编程方式处理 PowerPoint 演示文稿。

### 在哪里可以找到 Aspose.Slides for .NET 的文档？
你可以找到文档[这里](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET 可以免费使用吗？
 Aspose.Slides for .NET 是一个商业库。您可以找到定价和许可信息[这里](https://purchase.aspose.com/buy).

### 我需要高级编程技能才能使用 Aspose.Slides for .NET 吗？
虽然了解一些 .NET 编程知识是有益的，但 Aspose.Slides for .NET 提供了一个用户友好的 API，可以简化 PowerPoint 演示文稿的使用。

### Aspose.Slides for .NET 是否提供技术支持？
是的，您可以访问技术支持和社区论坛[这里](https://forum.aspose.com/).