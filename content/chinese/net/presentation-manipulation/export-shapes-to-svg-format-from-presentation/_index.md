---
title: 将演示文稿中的形状导出为 SVG 格式
linktitle: 将演示文稿中的形状导出为 SVG 格式
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for .NET 将形状从 PowerPoint 演示文稿导出为 SVG 格式。包含源代码的分步指南。有效提取各种应用的形状。
type: docs
weight: 16
url: /zh/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
本指南将引导您完成使用 Aspose.Slides for .NET 库将形状从演示文稿导出为 SVG 格式的过程。 Aspose.Slides 是一个功能强大的 API，允许您以编程方式处理 Microsoft PowerPoint 文件。在本教程中，您将学习如何使用 C# 从演示文稿中提取形状并将其保存为 SVG 格式。

## 先决条件

在开始之前，请确保您具备以下先决条件：

- 安装了 Visual Studio
- 对 C# 编程有基本了解
-  Aspose.Slides for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/slides/net/).

## 分步指南

请按照以下步骤将演示文稿中的形状导出为 SVG 格式：

### 1. 创建一个新项目

打开 Visual Studio 并创建一个新的 C# 项目。

### 2.添加对Aspose.Slides的引用

在您的项目中，右键单击解决方案资源管理器中的“引用”，然后单击“添加引用”。浏览并选择您下载的 Aspose.Slides DLL。

### 3. 加载演示文稿

```csharp
using Aspose.Slides;

//加载演示文稿
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. 迭代形状

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    //检查形状是否为组形状
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            //将形状导出为 SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        //将形状导出为 SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5.保存SVG文件

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); //保存对演示文稿的更改
```

## 常见问题解答

### 如何安装 Aspose.Slides for .NET？

您可以从以下位置下载 Aspose.Slides for .NET 库：[这里](https://releases.aspose.com/slides/net/)。请按照文档中提供的安装说明进行操作。

### 如何使用 Aspose.Slides 加载 PowerPoint 演示文稿？

您可以使用以下方式加载演示文稿`Presentation`类构造函数。提供 PowerPoint 文件的路径作为参数。

### 如何将形状导出为 SVG 格式？

您可以使用`WriteAsSvg`上的方法`IShape`对象将其导出为 SVG 格式。您需要指定 SVG 输出的文件名。

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for .NET 库将形状从 PowerPoint 演示文稿导出为 SVG 格式。当您需要提取单个形状以在支持 SVG 图形的其他应用程序或平台中使用时，这会很有用。 Aspose.Slides 提供了一种简单有效的方法来以编程方式实现此目的。

有关更多详细信息和高级功能，请参阅[Aspose.Slides for .NET API 参考](https://reference.aspose.com/slides/net/).