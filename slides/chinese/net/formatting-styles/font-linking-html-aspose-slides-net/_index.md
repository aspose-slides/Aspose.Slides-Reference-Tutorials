---
"date": "2025-04-15"
"description": "了解如何通过直接嵌入字体，确保在使用 Aspose.Slides for .NET 将演示文稿转换为 HTML 时字体渲染的一致性。"
"title": "如何使用 Aspose.Slides for .NET 在 HTML 中链接字体——分步指南"
"url": "/zh/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 在 HTML 中链接字体

## 介绍

将演示文稿转换为 HTML，同时保持跨平台一致的字体渲染可能具有挑战性。 **Aspose.Slides for .NET** 提供无缝解决方案，允许您通过嵌入的字体文件直接在 HTML 输出中链接演示文稿中使用的所有字体。

在本教程中，我们将探讨如何使用 Aspose.Slides for .NET 实现字体链接并确保跨不同平台的设计一致性。 

**您将学到什么：**
- 使用 Aspose.Slides for .NET 设置您的环境
- HTML 转换中的链接字体
- 编写用于字体嵌入的自定义控制器
- 实际应用和性能考虑

让我们深入了解实现这一目标所需的步骤。

## 先决条件

在开始之前，请确保您具备以下条件：

### 所需的库和依赖项
- **Aspose.Slides for .NET** 库：我们实现的核心组件。

### 环境设置要求
- 安装了 .NET Framework 或 .NET Core 的开发环境。

### 知识前提
- 对 C# 编程有基本的了解。
- 熟悉 HTML 和 CSS，特别是 `@font-face` 规则。

## 设置 Aspose.Slides for .NET

要在 .NET 项目中使用 Aspose.Slides，您需要安装该库。以下是几种方法：

### 使用 .NET CLI
```bash
dotnet add package Aspose.Slides
```

### 使用包管理器控制台
```powershell
Install-Package Aspose.Slides
```

### 通过 NuGet 包管理器 UI
- 在 Visual Studio 中打开您的项目。
- 导航到“NuGet 包管理器”。
- 搜索“Aspose.Slides”并安装最新版本。

### 许可证获取步骤
您可以按照以下步骤获取免费试用许可证，以无限制地测试所有功能：
1. **免费试用**：下载临时许可证 [这里](https://releases。aspose.com/slides/net/).
2. **临时执照**：申请延长访问权限 [这里](https://purchase。aspose.com/temporary-license/).
3. **购买**：如需完整功能，请购买许可证 [这里](https://purchase。aspose.com/buy).

### 基本初始化和设置
```csharp
// 创建 License 类的实例
easpose.slides.License license = new aspose.slides.License();

// 从文件路径应用许可证
license.SetLicense("Aspose.Slides.lic");
```

## 实施指南

现在，让我们使用以下方法在 HTML 转换中实现字体链接 **Aspose.Slides for .NET**。

### 功能概述：HTML 转换中的链接字体
此功能通过嵌入字体文件，确保演示文稿中使用的所有字体都直接链接到生成的 HTML 文件中。此方法为在不同浏览器和平台上保持设计一致性提供了一个强大的解决方案。

#### 步骤 1：创建自定义控制器
创建自定义控制器类 `LinkAllFontsHtmlController` 继承自 `EmbedAllFontsHtmlController`：
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // 设置字体文件的存储目录
    }
}
```
#### 第二步：实现字体书写方法
这 `WriteFont` 方法将字体数据写入文件并生成相应的 HTML 代码以供嵌入：
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // 确定要使用的字体名称，如果可用则优先使用替代字体。
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // 为.woff 字体文件构建文件路径。
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // 将字体数据写入指定的文件路径。
    File.WriteAllBytes(path, fontData);

    // 使用@font-face 规则生成嵌入字体的 HTML 样式块。
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}