---
"date": "2025-04-22"
"description": "学习如何使用 Aspose.Slides for Python 在 PowerPoint 演示文稿的图表上轻松显示百分比标签。非常适合增强数据可视化。"
"title": "如何使用 Aspose.Slides for Python 在图表上显示百分比标签——综合指南"
"url": "/zh/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在图表上显示百分比标签

## 介绍

在演示文稿和报告中，有效地可视化数据至关重要，尤其是在您想要清晰地突出比例或分布时。但是，如果您需要将这些百分比直接显示在图表上，该怎么办？本指南将指导您如何使用 **Aspose.Slides for Python** 轻松地将百分比值显示为图表上的标签。

### 您将学到什么：
- 如何使用 Aspose.Slides for Python 在 PowerPoint 演示文稿中创建和嵌入图表。
- 在图表上将数据点显示为百分比标签。
- 有效地保存和管理 PowerPoint 演示文稿。

准备好为你的数据添加富有洞察力的视觉效果了吗？在深入研究代码之前，我们先来看看你需要什么！

## 先决条件

在开始之前，请确保您具备以下条件：
- **Aspose.Slides for Python**：此库对于以编程方式创建和操作 PowerPoint 演示文稿至关重要。
- **Python 环境**：对 Python 编程和环境设置有基本的了解。
- **PIP 包管理器**：用于安装Aspose.Slides。

## 为 Python 设置 Aspose.Slides

要开始使用 Aspose.Slides，您首先需要安装它：

```bash
pip install aspose.slides
```

### 许可证获取步骤：
您可以免费试用，或获取临时许可证以探索 Aspose.Slides 的全部功能。如需长期使用，请考虑购买订阅。

#### 基本初始化和设置

安装完成后，您将像这样初始化演示环境：

```python
import aspose.slides as slides

# 初始化 Presentation 对象
def create_presentation():
    with slides.Presentation() as presentation:
        # 您的代码在这里
```

## 实施指南

现在我们已经设置好了，让我们深入研究在图表上显示百分比。

### 创建图表并添加数据

#### 概述
我们将创建一个堆积柱形图，每个数据点都有百分比标签，让查看者一眼就能看到准确的比例。

##### 步骤 1：向幻灯片添加图表

```python
# 访问演示文稿中的第一张幻灯片
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # 添加堆积柱形图
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

此代码片段向第一张幻灯片添加了一个基本图表。 `add_chart` 方法指定图表的类型及其位置和大小。

##### 第 2 步：计算类别的总值

```python
def calculate_totals(chart):
    total_for_category = []
    # 对每个类别的所有系列的值进行求和
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

此循环计算整个系列中所有数据点的总和，这对于百分比计算至关重要。

#### 设置百分比标签

##### 步骤 3：配置系列数据点

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # 设置默认标签选项以隐藏非必要信息
        series.labels.default_data_label_format.show_legend_key = False
        
        # 计算并设置百分比标签
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # 创建带有百分比值的文本部分
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # 清除现有标签并添加新的百分比标签
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # 隐藏其他数据标签元素
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

该部分处理每个数据点以计算其占总数的百分比并将其分配为标签。

### 保存您的演示文稿

```python
def save_presentation(presentation, output_directory):
    # 保存您的演示文稿并进行修改
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}