---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 创建散点图，增强您的演示文稿效果。遵循本指南，高效创建和自定义图表。"
"title": "使用 Aspose.Slides .NET 在演示文稿中添加散点图——分步指南"
"url": "/zh/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides .NET 在演示文稿中添加散点图：分步指南

## 介绍
您是否希望通过轻松集成散点图来增强演示文稿的效果？借助 Aspose.Slides for .NET 的强大功能，创建和自定义图表变得轻而易举。本教程将指导您使用 Aspose.Slides for .NET 将散点图添加到幻灯片中。掌握这些技巧后，您将能够更有效地呈现数据，并创建更具视觉吸引力的演示文稿。

**您将学到什么：**
- 在您的项目中设置 Aspose.Slides for .NET
- 创建新的演示文稿并访问其第一张幻灯片
- 在幻灯片中添加带有平滑线条的散点图
- 清除现有系列并向图表添加新系列
- 修改数据点和标记样式以增强可视化
- 将演示文稿保存到指定目录

让我们首先回顾一下先决条件。

## 先决条件
在实施 Aspose.Slides for .NET 之前，请确保您具备以下条件：
- **Aspose.Slides for .NET 库**：版本 23.7 或更高版本。
- **开发环境**：Visual Studio 2019 或更新版本，带有 .NET Framework 4.6.1+ 或 .NET Core/5+。
- **基本 C# 知识**：熟悉C#面向对象编程。

## 设置 Aspose.Slides for .NET
要开始使用 Aspose.Slides，您需要在项目中安装该库。具体步骤如下：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**使用包管理器控制台：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 包管理器 UI：**
- 搜索“Aspose.Slides”并安装最新版本。

### 许可证获取
您可以先免费试用，也可以申请临时许可证来探索所有功能。购买许可证的步骤如下：
1. 访问 [购买 Aspose.Slides](https://purchase.aspose.com/buy) 购买完整许可证。
2. 如需临时许可证，请访问 [临时许可证页面](https://purchase。aspose.com/temporary-license/).

获取许可证文件后，请使用以下命令将其添加到您的项目中：
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## 实施指南
我们将根据特性将实现分解为逻辑部分。

### 创建演示文稿并添加幻灯片
本节演示如何创建演示文稿并访问其第一张幻灯片。

#### 概述
首先创建一个 `Presentation` 类，代表您的 PowerPoint 文件。使用此对象模型可以轻松访问幻灯片。

#### 实施步骤
**步骤 1：初始化演示文稿**
```csharp
using Aspose.Slides;

// 创建新演示文稿
t Presentation pres = new Presentation();
```
此代码初始化一个新的演示文档。

**第 2 步：访问第一张幻灯片**
```csharp
// 访问演示文稿中的第一张幻灯片
ISlide slide = pres.Slides[0];
```
这里， `pres.Slides[0]` 访问第一张幻灯片。 

### 将散点图添加到幻灯片
现在让我们向您的演示文稿添加一个散点图。

#### 概述
添加图表可以帮助您在演示文稿中直观地呈现数据。Aspose.Slides 可以轻松合并各种类型的图表，包括散点图。

#### 实施步骤
**步骤 1：创建并添加散点图**
```csharp
using Aspose.Slides.Charts;

// 创建并添加带有平滑线的默认散点图
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
此代码片段在指定的位置和大小添加散点图。

### 清除图表数据并添加系列
#### 概述
您可能需要通过清除现有系列并添加新系列来自定义图表。本节介绍此功能。

#### 实施步骤
**步骤 1：访问图表数据工作簿**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// 清除所有预先存在的系列
chart.ChartData.Series.Clear();
```
此代码清除现有数据以重新开始新系列。

**第 2 步：添加新系列**
```csharp
// 添加名为“系列 1”的新系列
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// 添加另一个名为“Series 2”的系列
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
这些步骤向图表添加了两个新系列。

### 修改第一个系列数据点和标记样式
#### 概述
自定义数据点和标记样式，以便更好地可视化散点图。

#### 实施步骤
**步骤 1：访问并添加数据点**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// 添加数据点 (1, 3) 和 (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**步骤 2：修改标记样式**
```csharp
// 更改系列类型并修改标记样式
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### 修改第二个系列数据点和标记样式
#### 概述
同样，定制第二个系列以满足您的演示需求。

#### 实施步骤
**步骤 1：访问并添加多个数据点**
```csharp
// 访问第二个图表系列
series = chart.ChartData.Series[1];

// 添加多个数据点
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**步骤 2：修改标记样式**
```csharp
// 更改第二个系列的标记大小和符号
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### 保存演示文稿
最后，将您的演示文稿保存到指定目录。

#### 实施步骤
**步骤 1：定义目录**
确保输出目录存在。如果不存在，请创建它：
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// 保存演示文稿
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
此代码将您的演示文稿文件保存到指定位置。

## 结论
现在，您已成功使用 Aspose.Slides for .NET 将散点图添加到您的演示文稿中。请继续探索库中提供的其他功能和自定义功能，以增强您的数据可视化技能。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}