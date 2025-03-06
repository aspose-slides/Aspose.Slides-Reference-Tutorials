---
title: 使用 Aspose.Slides 更改演示文稿中的 OLE 对象数据
linktitle: 使用 Aspose.Slides 更改演示文稿中的 OLE 对象数据
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 探索 Aspose.Slides for .NET 的强大功能，轻松更改 OLE 对象数据。使用动态内容增强您的演示文稿。
type: docs
weight: 25
url: /zh/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---
## 介绍
创建动态和交互式 PowerPoint 演示文稿是当今数字世界的常见要求。实现此目的的一个强大工具是 Aspose.Slides for .NET，这是一个强大的库，允许开发人员以编程方式操作和增强 PowerPoint 演示文稿。在本教程中，我们将深入研究使用 Aspose.Slides 在演示文稿幻灯片中更改 OLE（对象链接和嵌入）对象数据的过程。
## 先决条件
在开始使用 Aspose.Slides for .NET 之前，请确保您已满足以下先决条件：
1. 开发环境：设置安装了.NET 的开发环境。
2.  Aspose.Slides 库：下载并安装 Aspose.Slides for .NET 库。您可以找到该库[这里](https://releases.aspose.com/slides/net/).
3. 基本理解：熟悉 C# 编程和 PowerPoint 演示文稿的基本概念。
## 导入命名空间
在您的 C# 项目中，导入必要的命名空间以使用 Aspose.Slides 功能：
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## 步骤 1：设置你的项目
首先创建一个新的 C# 项目并导入 Aspose.Slides 库。确保您的项目配置正确，并且已安装所需的依赖项。
## 第 2 步：访问演示文稿和幻灯片
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## 步骤 3：找到 OLE 对象
遍历幻灯片中的所有形状以找到 OLE 对象框架：
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## 步骤 4：读取和修改工作簿数据
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        //读取工作簿中的对象数据
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            //修改工作簿数据
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            //更改 Ole 框架对象数据
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## 步骤 5：保存演示文稿
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## 结论
通过遵循这些步骤，您可以使用 Aspose.Slides for .NET 无缝更改演示文稿幻灯片中的 OLE 对象数据。这为您创建满足您特定需求的动态和定制演示文稿开辟了无限可能。
## 经常问的问题
### 什么是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一个功能强大的库，使开发人员能够以编程方式处理 PowerPoint 演示文稿，从而轻松进行操作和增强。
### 我在哪里可以找到 Aspose.Slides 文档？
可以找到 Aspose.Slides for .NET 的文档[这里](https://reference.aspose.com/slides/net/).
### 如何下载 Aspose.Slides for .NET？
您可以从发布页面下载该库[这里](https://releases.aspose.com/slides/net/).
### Aspose.Slides 有免费试用版吗？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 在哪里可以获得 Aspose.Slides for .NET 的支持？
如需支持和讨论，请访问[Aspose.Slides 论坛](https://forum.aspose.com/c/slides/11).