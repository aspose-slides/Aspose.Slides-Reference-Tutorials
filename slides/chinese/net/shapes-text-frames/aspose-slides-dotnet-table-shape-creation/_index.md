---
"date": "2025-04-16"
"description": "了解如何使用 Aspose.Slides for .NET 在 PowerPoint 演示文稿中创建动态表格和形状。按照我们的分步指南，增强视觉吸引力。"
"title": "使用 Aspose.Slides for .NET 在 PowerPoint 中创建表格和形状——分步指南"
"url": "/zh/net/shapes-text-frames/aspose-slides-dotnet-table-shape-creation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for .NET 在 PowerPoint 中创建表格和形状：分步指南

## 介绍

使用 Aspose.Slides for .NET 的 C# 语言创建动态表格或在文本周围绘制形状，增强您的 PowerPoint 演示文稿。本指南将指导您完成表格创建和形状绘制功能的实现过程，让您的幻灯片更具信息量和视觉吸引力。

在本教程中，我们将介绍：
- 在 PowerPoint 演示文稿中创建表格
- 将包含文本部分的段落添加到表格单元格中
- 在形状中嵌入文本框架
- 围绕特定文本元素绘制矩形

完成本指南后，您将能够使用 Aspose.Slides for .NET 增强您的演示文稿幻灯片。首先，让我们深入了解一下先决条件。

### 先决条件

要继续本教程，请确保您已具备：
- **开发环境**：您的机器上安装了 Visual Studio。
- **Aspose.Slides for .NET 库**：我们将使用 22.x 或更高版本。
- **基本 C# 知识**：需要熟悉 C# 语法和概念。

## 设置 Aspose.Slides for .NET

在开始编码之前，让我们先在项目中设置 Aspose.Slides 库。有几种安装方法：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**程序包管理器控制台**
```powershell
Install-Package Aspose.Slides
```

**NuGet 包管理器 UI**：搜索“Aspose.Slides”并点击安装按钮。

### 许可证获取

您可以先免费试用许可证，探索所有功能。如需长期使用，您可以选择临时许可证或购买许可证。 [Aspose 网站](https://purchase。aspose.com/buy).

安装完成后，通过添加以下内容在项目中初始化 Aspose.Slides：

```csharp
using Aspose.Slides;
```

## 实施指南

### 在幻灯片上创建表格

**概述：**
当您需要清晰地呈现数据时，创建表格至关重要。使用 Aspose.Slides，您可以轻松定义表格的尺寸和位置。

#### 步骤 1：初始化演示文稿
首先创建一个 `Presentation` 班级：

```csharp
Presentation pres = new Presentation();
```

#### 步骤 2：添加表
使用 `AddTable` 方法将表格添加到幻灯片。指定行和列的位置和大小：

```csharp
ITable tbl = pres.Slides[0].Shapes.AddTable(50, 50, new double[] { 50, 70 }, new double[] { 50, 50, 50 });
```

**参数说明：**
- `50, 50`：左上角的 X 和 Y 坐标。
- 数组指定列宽和行高。

#### 步骤 3：保存演示文稿
最后，保存您的演示文稿：

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY/CreateTable_Out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}