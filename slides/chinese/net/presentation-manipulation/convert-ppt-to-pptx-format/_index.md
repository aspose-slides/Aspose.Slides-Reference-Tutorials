---
"description": "学习如何使用 Aspose.Slides for .NET 轻松将 PPT 转换为 PPTX。本指南包含代码示例，可帮助您实现无缝格式转换。"
"linktitle": "将PPT转换为PPTX格式"
"second_title": "Aspose.Slides .NET PowerPoint 处理 API"
"title": "将PPT转换为PPTX格式"
"url": "/zh/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 将PPT转换为PPTX格式


如果您曾经需要使用 .NET 将 PowerPoint 文件从旧版 PPT 格式转换为新版 PPTX 格式，那么您来对地方了。在本分步教程中，我们将使用 Aspose.Slides for .NET API 引导您完成整个过程。借助这个强大的库，您可以轻松完成此类转换。让我们开始吧！

## 先决条件

在深入研究代码之前，请确保您已进行以下设置：

- Visual Studio：确保您已安装 Visual Studio 并准备好进行 .NET 开发。
- Aspose.Slides for .NET：从以下位置下载并安装 Aspose.Slides for .NET 库 [这里](https://releases。aspose.com/slides/net/).

## 设置项目

1. 创建新项目：打开 Visual Studio 并创建一个新的 C# 项目。

2. 添加对 Aspose.Slides 的引用：在解决方案资源管理器中右键单击您的项目，选择“管理 NuGet 包”，然后搜索“Aspose.Slides”。安装该包。

3. 导入所需的命名空间：

```csharp
using Aspose.Slides;
```

## 将 PPT 转换为 PPTX

现在我们已经设置好了项目，让我们编写代码将 PPT 文件转换为 PPTX。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// 实例化代表 PPT 文件的 Presentation 对象
Presentation pres = new Presentation(srcFileName);

// 将演示文稿保存为 PPTX 格式
pres.Save(outPath, SaveFormat.Pptx);
```

在此代码片段中：

- `dataDir` 应替换为您的 PPT 文件所在的目录路径。
- `outPath` 应替换为您要保存转换后的 PPTX 文件的目录。
- `srcFileName` 是您输入的PPT文件的名称。
- `destFileName` 是输出 PPTX 文件的所需名称。

## 结论

恭喜！您已成功使用 Aspose.Slides for .NET API 将 PowerPoint 演示文稿从 PPT 转换为 PPTX 格式。这个强大的库简化了此类复杂任务，让您的 .NET 开发体验更加流畅。

如果你还没有， [下载 Aspose.Slides for .NET](https://releases.aspose.com/slides/net/) 并进一步探索其能力。

如需更多教程和技巧，请访问我们的 [文档](https://reference。aspose.com/slides/net/).

## 常见问题

### 1.什么是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一个 .NET 库，允许开发人员以编程方式创建、操作和转换 PowerPoint 演示文稿。

### 2. 我可以使用 Aspose.Slides for .NET 将其他格式转换为 PPTX 吗？
是的，Aspose.Slides for .NET 支持各种格式，包括 PPT、PPTX、ODP 等。

### 3. Aspose.Slides for .NET 可以免费使用吗？
不，这是一个商业图书馆，但你可以探索 [免费试用](https://releases.aspose.com/) 来评估其特征。

### 4. Aspose.Slides for .NET 还支持其他文档格式吗？
是的，Aspose.Slides for .NET 还支持处理 Word 文档、Excel 电子表格和其他文件格式。

### 5. 在哪里可以获得有关 Aspose.Slides for .NET 的支持或询问相关问题？
您可以在以下位置找到问题的答案并寻求支持 [Aspose.Slides 论坛](https://forum。aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}