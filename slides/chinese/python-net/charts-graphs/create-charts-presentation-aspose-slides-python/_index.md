---
"date": "2025-04-23"
"description": "学习如何使用 Aspose.Slides for Python 的动态图表增强您的 PowerPoint 演示文稿。按照本分步指南，有效地创建、管理和格式化簇状柱形图。"
"title": "使用 Aspose.Slides for Python 在 PowerPoint 演示文稿中创建和格式化图表"
"url": "/zh/python-net/charts-graphs/create-charts-presentation-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Python 在 PowerPoint 演示文稿中创建和格式化图表

## 介绍

在当今数据驱动的世界中，将视觉上引人注目的图表融入演示文稿对于有效沟通至关重要。无论您是数据分析师、项目经理还是商务专业人士，动态图表都能显著提升您的信息传递效果。本教程将指导您使用 Aspose.Slides for Python 创建和格式化簇状柱形图，让您轻松提升 PowerPoint 幻灯片的品质。

**您将学到什么：**
- 如何安装和设置 Aspose.Slides for Python
- 创建新的演示文稿并添加聚集柱形图
- 管理图表内的数据系列和类别
- 填充并格式化系列数据以实现更好的可视化

准备好增强您的演示文稿了吗？让我们探索如何利用 Aspose.Slides 创建引人入胜的图表。

## 先决条件

在开始之前，请确保您具备以下条件：

- **Python已安装：** 建议使用 3.6 或更高版本。
- **Aspose.Slides for Python 包：** 使用 pip 安装此包。
- **Python编程基础知识：** 熟悉 Python 语法和文件处理将会很有帮助。

## 为 Python 设置 Aspose.Slides

首先，您需要安装 Aspose.Slides 库。这个强大的工具简化了使用 Python 创建和操作 PowerPoint 演示文稿的过程。

### 安装

运行以下命令来安装该包：

```bash
pip install aspose.slides
```

### 许可证获取

Aspose 提供免费试用许可证，让您可以无限制地探索其全部功能。请按照以下步骤获取：

1. 访问 [Aspose 免费试用](https://releases.aspose.com/slides/python-net/) 下载试用包。
2. 或者，通过以下方式申请临时许可证 [临时许可证页面](https://purchase。aspose.com/temporary-license/).

获得许可证文件后，请在 Python 脚本中对其进行初始化：

```python
from aspose.slides import License

# 设置 Aspose.Slides 许可证
license = License()
license.set_license("path/to/your/license/file.lic")
```

## 实施指南

我们将把该过程分为三个主要特征：创建图表、管理数据系列和类别以及填充和格式化系列数据。

### 功能 1：创建图表并将其添加到演示文稿中

#### 概述

此功能专注于使用 Aspose.Slides for Python 向您的演示文稿添加聚集柱形图。

#### 逐步实施

```python
import aspose.slides as slides

def create_and_add_chart():
    with slides.Presentation() as pres:
        # 在位置 (100, 100) 添加一个簇状柱形图，宽度为 400，高度为 300。
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        # 将演示文稿保存到输出目录中的文件中。
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_creation_out.pptx", slides.export.SaveFormat.PPTX)

create_and_add_chart()
```

**解释：**
- **图表位置和大小：** 这 `add_chart` 方法与指定图表类型、位置（x，y）、宽度和高度的参数一起使用。
- **保存演示文稿：** 演示文稿保存在指定目录中。

### 功能2：管理图表数据系列和类别

#### 概述

本节演示如何有效地管理图表中的数据系列和类别。

#### 逐步实施

```python
import aspose.slides as slides

def manage_chart_data_series_and_categories():
    with slides.Presentation() as pres:
        # 在位置 (100, 100) 添加一个簇状柱形图，宽度为 400，高度为 300。
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # 添加新的系列和类别之前，请清除现有的系列和类别。
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # 向图表中添加名为“系列 1”的新系列。
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # 向图表数据添加三个类别。
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # 将演示文稿保存到输出目录中的文件中。
        pres.save("YOUR_OUTPUT_DIRECTORY/chart_series_categories_out.pptx", slides.export.SaveFormat.PPTX)

manage_chart_data_series_and_categories()
```

**解释：**
- **清除现有数据：** 在添加新的系列和类别之前，会清除现有的系列和类别以防止数据重复。
- **添加系列和类别：** 使用 `chart_data_workbook` 目的。

### 功能 3：填充系列数据并格式化图表

#### 概述

在此功能中，我们将用数据点填充您的图表并应用格式以增强其视觉吸引力。

#### 逐步实施

```python
import aspose.slides as slides
import aspose.pydrawing as drawing

def populate_and_format_series_data():
    with slides.Presentation() as pres:
        # 在位置 (100, 100) 添加一个簇状柱形图，宽度为 400，高度为 300。
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # 添加新的系列和类别之前，请清除现有的系列和类别。
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # 向图表中添加名为“系列 1”的新系列。
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # 向图表数据添加三个类别。
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # 取第一个图表系列并用数据点填充它。
        series = chart.chart_data.series[0]
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 1, 1, -20)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 2, 1, 50)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 3, 1, -30)
        )
        
        # 设置系列中负值的颜色。
        invert_color = drawing.Color.red
        series.invert_if_negative = True
        series.format.fill.fill_type = slides.FillType.SOLID
        series.format.fill.solid_fill_color.color = series.get_automatic_series_color()
        series.inverted_solid_fill_color.color = invert_color
        
        # 将演示文稿保存到输出目录中的文件中。
        pres.save("YOUR_OUTPUT_DIRECTORY/populate_format_series_out.pptx", slides.export.SaveFormat.PPTX)

populate_and_format_series_data()
```

**解释：**
- **数据点添加：** 使用以下方式添加数据点 `add_data_point_for_bar_series`。
- **格式化负值：** 图表格式选项（如负值的颜色反转）增强了数据的可读性。

## 实际应用

使用 Aspose.Slides 在演示文稿中添加和格式化图表有许多应用：

1. **商业报告：** 通过动态视觉效果增强季度报告，清晰地传达关键指标。
2. **教育材料：** 通过直观地呈现复杂信息来创建引人入胜的教育内容。
3. **项目介绍：** 使用图表有效地说明项目进度和成果。

通过遵循本指南，您可以利用 Aspose.Slides for Python 创建引人注目的演示文稿。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}