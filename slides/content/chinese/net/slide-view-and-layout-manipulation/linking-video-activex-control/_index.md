---
title: 在 PowerPoint 中通过 ActiveX 控件链接视频
linktitle: 通过 ActiveX 控件链接视频
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for .NET 将视频链接到 PowerPoint 幻灯片。本分步指南包含源代码和使用链接视频创建交互式引人入胜的演示文稿的技巧。
type: docs
weight: 12
url: /zh/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---
使用 Aspose.Slides for .NET 在演示文稿中通过 ActiveX 控件链接视频

在 Aspose.Slides for .NET 中，您可以使用 ActiveX 控件以编程方式将视频链接到演示文稿幻灯片。这允许您创建交互式演示文稿，其中可以直接在幻灯片中播放视频内容。在本分步指南中，我们将引导您完成使用 Aspose.Slides for .NET 将视频链接到演示文稿幻灯片的过程。

## 先决条件：
- Visual Studio（或任何其他.NET 开发环境）
-  Aspose.Slides for .NET 库。您可以从以下位置下载[这里](https://releases.aspose.com/slides/net/).

## 步骤 1：创建新项目
在您喜欢的 .NET 开发环境（例如 Visual Studio）中创建一个新项目并添加对 Aspose.Slides for .NET 库的引用。

## 第 2 步：导入必要的命名空间
在您的项目中，导入使用 Aspose.Slides 所需的命名空间：

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## 步骤 3：加载演示文稿
加载您想要添加链接视频的 PowerPoint 演示文稿：

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    //添加链接视频的代码将在此处显示
}
```

## 步骤 4：添加 ActiveX 控件
创建一个实例`IOleObjectFrame`将ActiveX控件添加到幻灯片的界面：

```csharp
ISlide slide = presentation.Slides[0]; //选择要添加视频的幻灯片
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

在上面的代码中，我们向幻灯片中添加了一个尺寸为 640x480 的 ActiveX 控件框架。我们为 ShockwaveFlash ActiveX 控件指定了 ProgID，该控件通常用于嵌入视频。

## 步骤5：设置ActiveX控件的属性
设置ActiveX控件的属性，指定链接的视频源：

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); //替换为实际的视频文件路径
oleObjectFrame.AlternativeText = "Linked Video";
```

代替`"YourVideoPathHere"`替换为视频文件的实际路径。`AlternativeText`属性提供了链接视频的描述。

## 步骤 6：保存演示文稿
保存修改后的演示文稿：

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## 常见问题解答：

### 如何指定幻灯片上链接视频的大小和位置？
您可以使用以下参数调整 ActiveX 控件框架的尺寸和位置：`AddOleObjectFrame`方法。四个数值参数分别表示左上角的X和Y坐标以及框架的宽度和高度。

### 我可以使用此方法链接不同格式的视频吗？
是的，只要有适合该格式的 ActiveX 控件，您就可以链接各种格式的视频。例如，本指南中使用的 ShockwaveFlash ActiveX 控件适用于 Flash 视频 (SWF)。对于其他格式，您可能需要使用不同的 ProgID。

### 链接视频的大小有限制吗？
链接视频的大小可能会影响演示文稿的整体大小和性能。建议在将视频链接到演示文稿之前对其进行优化，以使其适合网络播放。

### 结论：
按照本指南中概述的步骤，您可以使用 Aspose.Slides for .NET 在演示文稿中通过 ActiveX 控件轻松链接视频。此功能使您能够创建无缝整合多媒体内容的引人入胜且互动的演示文稿。

有关更多详细信息和高级选项，您可以参考[Aspose.Slides for .NET 文档](https://reference.aspose.com/slides/net/).