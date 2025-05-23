---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 中创建和自定义 SmartArt 图形，并使用动态组织结构图增强您的演示文稿。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中创建和自定义 SmartArt"
"url": "/zh/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中创建和自定义 SmartArt

## 介绍

演示文稿是直观呈现组织结构或头脑风暴会议的重要工具。使用 Aspose.Slides for Python，您可以轻松创建和自定义 SmartArt 图形。本教程将指导您如何在 PowerPoint 幻灯片中添加组织结构图 SmartArt 图形。

**您将学到什么：**
- 使用 Aspose.Slides for Python 在 PowerPoint 中添加 SmartArt 图形。
- 自定义 SmartArt 节点的布局。
- 高效地保存和导出演示文稿。

让我们开始设置您的环境！

## 先决条件

在开始创建 SmartArt 图形之前，请确保您满足以下先决条件：

### 所需库
- **Aspose.Slides for Python**：如果尚未完成，请使用 pip 安装此库。

### 环境设置要求
- Python 的工作安装（建议使用 3.x）。
- 对 Python 编程有基本的了解。
- 熟悉 Microsoft PowerPoint 会有所帮助，但不是必需的。

## 为 Python 设置 Aspose.Slides

首先，在您的 Python 环境中设置 Aspose.Slides 库：

**Pip安装：**
```bash
pip install aspose.slides
```

### 许可证获取步骤
Aspose 提供多种许可选项：
- **免费试用**：下载临时许可证以评估全部功能。
- **临时执照**：获取免费的临时许可证以供短期使用。
- **购买**：考虑购买长期项目的订阅。

### 基本初始化和设置

安装完成后，使用 Aspose.Slides 初始化您的 Python 脚本，如下所示：

```python
import aspose.slides as slides

# 使用 slides.Presentation() 初始化 Presentation 类作为演示文稿：
    # 添加 SmartArt 的代码将在此处显示
```

## 实施指南

现在让我们分解使用 Aspose.Slides for Python 在 PowerPoint 中添加和自定义 SmartArt 的过程。

### 添加 SmartArt 图形

#### 概述
创建新幻灯片并向其中添加组织结构图类型 SmartArt 图形：

```python
import aspose.slides as slides

# 创建一个演示文稿实例\使用 slides.Presentation() 作为演示文稿：
    # 在位置 (10, 10) 添加具有指定尺寸的 SmartArt
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### 参数和方法目的
- **x, y**：SmartArt 图形在幻灯片上的位置。
- **宽度、高度**：适当可见性的尺寸。
- **布局类型**：指定 SmartArt 布局的类型，在本例中为组织结构图。

### 自定义组织结构图布局

#### 概述
通过将布局设置为 LEFT_HANGING 来自定义 SmartArt 图形中的第一个节点：

```python
# 将第一个节点设置为左挂布局
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### 关键配置选项说明
- **组织结构图布局类型**：确定节点的显示方式，增强可读性和美感。

### 保存演示文稿

最后，将您的演示文稿保存到指定目录：

```python
# 使用 SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\ 保存演示文稿

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}