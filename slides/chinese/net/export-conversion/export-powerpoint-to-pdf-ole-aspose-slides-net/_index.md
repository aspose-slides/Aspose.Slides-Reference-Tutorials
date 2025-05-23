---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 将 PowerPoint 演示文稿导出为 PDF，同时保留嵌入的 OLE 数据，确保完整的功能和交互性。"
"title": "如何使用 Aspose.Slides for .NET 将 PowerPoint 演示文稿导出为带有嵌入式 OLE 的 PDF"
"url": "/zh/net/export-conversion/export-powerpoint-to-pdf-ole-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 将 PowerPoint 演示文稿导出为包含嵌入 OLE 数据的 PDF

## 介绍

您是否需要以 PDF 格式共享内容丰富、可交互的 PowerPoint 演示文稿，同时又保留其功能？有了 **Aspose.Slides for .NET**导出包含嵌入对象链接与嵌入 (OLE) 数据的演示文稿非常简单。本教程将指导您轻松实现此功能，从而增强您的文档处理能力。

**关键要点：**
- 掌握将 PowerPoint 演示文稿导出为 PDF 的过程。
- 了解 OLE 数据如何保留文档内的交互性。
- 了解 Aspose.Slides for .NET 如何简化复杂的操作。
- 探索实际应用和性能优化。

在深入实施指南之前，让我们先了解一下所需的先决条件。

## 先决条件

开始之前，请确保您已准备好以下事项：

1. **所需库：**
   - Aspose.Slides for .NET（建议使用 21.3 或更高版本）。
2. **环境设置：**
   - 类似 Visual Studio 且支持 .NET 框架的开发环境。
3. **知识前提：**
   - 对 C# 和 .NET 应用程序开发有基本的了解。

## 设置 Aspose.Slides for .NET

要开始使用 Aspose.Slides，请在您的项目中安装该库。

**通过 .NET CLI 安装：**

```bash
dotnet add package Aspose.Slides
```

**使用包管理器：**

```powershell
Install-Package Aspose.Slides
```

或者，使用 Visual Studio 中的 NuGet 包管理器 UI 搜索“Aspose.Slides”并安装最新版本。

#### 许可证获取
- **免费试用：** 从以下位置下载试用包 [Aspose 的发布页面](https://releases.aspose.com/slides/net/) 测试功能。
- **临时执照：** 访问以下网址获取延长测试的临时许可证 [Aspose 的临时许可证页面](https://purchase。aspose.com/temporary-license/).
- **购买：** 如需完全访问权限，请从 [Aspose 的购买页面](https://purchase。aspose.com/buy).

安装后，使用适当的许可证文件初始化 Aspose.Slides 以释放其全部潜力。

## 实施指南

让我们将实现过程分解为可管理的步骤，以便在嵌入 OLE 数据的同时将 PowerPoint 演示文稿导出为 PDF。

### 将 PPT 导出为包含嵌入 OLE 数据的 PDF

**概述：**
此功能允许您将演示文稿导出为 PDF 格式，保留嵌入的 OLE 对象并维护其功能和外观。

#### 步骤1：初始化演示对象

```csharp
// 使用 Aspose.Slides 加载您的 PowerPoint 文件。
Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx");
```
- **解释：** 在这里，我们创建一个 `Presentation` 通过从指定目录加载 PPTX 文件来对象。

#### 步骤 2：配置 PDF 选项

```csharp
// 设置 PDF 选项以包含 OLE 对象。
PdfOptions pdfOptions = new PdfOptions();
pdfOptions.EmbedFullFonts = true; // 确保字体嵌入在 PDF 中
```
- **参数：** `EmbedFullFonts` 确保包含所有字体，保留文本外观。

#### 步骤 3：导出演示文稿

```csharp
// 将演示文稿保存为带有 OLE 数据的 PDF。
presentation.Save(outFilePath + "ExportedPresentation.pdf\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}