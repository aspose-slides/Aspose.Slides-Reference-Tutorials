---
"date": "2025-04-23"
"description": "学习如何使用 Aspose.Slides for Python 创建和配置精美的图表。按照本指南一步步操作，在演示文稿中实现高效的数据可视化。"
"title": "使用 Aspose.Slides 在 Python 中创建图表——综合指南"
"url": "/zh/python-net/charts-graphs/creating-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Python 中创建图表：综合指南

## 介绍
在演示文稿中创建视觉上引人入胜的图表可以使数据更易于理解，让您轻松传达复杂的信息。本教程将指导您使用 Aspose.Slides for Python 创建和配置图表。Aspose.Slides for Python 是一个强大的库，通过提供强大的图表操作功能，彻底改变您的演示文稿设计方式。

**您将学到什么：**
- 如何在演示文稿中创建堆积柱形图
- 使用自定义标签添加和格式化数据系列
- 保存已配置的演示文稿

完成本教程后，您将获得使用 Aspose.Slides Python 增强演示文稿的实践经验。在开始创建精美图表之前，让我们先深入了解一下环境设置！

## 先决条件
在开始之前，请确保您满足以下先决条件：

1. **Python环境：** 您的系统上应该安装了 Python（建议使用 3.x 版本）。
2. **Python 版 Aspose.Slides：** 可以通过 pip 安装。
3. **许可证获取：** 虽然可以免费试用，但请考虑获取临时或完整许可证以解锁所有功能。

## 为 Python 设置 Aspose.Slides
要开始在您的项目中使用 Aspose.Slides，您需要安装该库并了解如何设置您的环境：

**安装：**
```bash
pip install aspose.slides
```

安装完成后，您可以通过将 Aspose.Slides 导入到脚本中来初始化并使用。为了充分利用其功能，请获取许可证。您可以免费试用，如果需要更长时间的使用，请考虑购买或申请临时许可证。

## 实施指南

### 功能 1：创建并配置带有图表的演示文稿
**概述：** 本节将引导您使用 Aspose.Slides Python 设置演示幻灯片并向其中添加图表。

#### 步骤 1：初始化演示文稿
首先创建一个新的演示对象。使用 `with` 自动资源管理语句：
```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # 访问演示文稿中的第一张幻灯片
    slide = presentation.slides[0]
```

#### 步骤 2：向幻灯片添加图表
在这里，我们在指定位置添加具有定义尺寸的堆积柱形图：
```python
# 在幻灯片中添加堆积柱形图
chart = slide.shapes.add_chart(slides.charts.ChartType.PERCENTS_STACKED_COLUMN, 20, 20, 500, 400)
```

#### 步骤 3：配置图表轴
设置垂直轴数字格式以更好地表示数据：
```python
# 配置垂直轴数字格式
chart.axes.vertical_axis.is_number_format_linked_to_source = False
chart.axes.vertical_axis.number_format = "0.00%"
```

### 功能 2：向图表添加和格式化数据系列
**概述：** 本节重点介绍如何添加数据系列、为其填充值以及自定义其外观。

#### 步骤 1：定义数据工作簿
初始化图表的数据工作簿：
```python
default_worksheet_index = 0
workbook = chart.chart_data.chart_data_workbook
```

#### 步骤 2：添加并填充数据系列
向图表中添加一个名为“Reds”的新系列，然后用数据点填充它：
```python
# 添加新系列并填充数据点
series = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 1, "Reds"), chart.type)

for i in range(1, 5):
    series.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 1, [0.30, 0.50, 0.80, 0.65][i-1])
    )
```

#### 步骤 3：设置系列外观格式
自定义填充颜色和数据标签格式：
```python
# 将系列填充设置为红色
series.format.fill.fill_type = slides.FillType.SOLID
series.format.fill.solid_fill_color.color = drawing.Color.red

# 配置百分比显示的数据标签
series.labels.default_data_label_format.show_value = True
series.labels.default_data_label_format.number_format = "0.0%"
```

### 功能 3：向图表添加并格式化第二个数据系列
**概述：** 本节扩展了添加具有其自身样式的第二个数据系列。

#### 步骤 1：添加第二个系列
添加另一个名为“Blues”的系列：
```python
# 添加第二个名为“Blues”的系列
series2 = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 2, "Blues"), chart.type)
```

#### 步骤 2：填充并格式化系列
用数据点填充它并应用格式：
```python
# 填充第二个系列
for i in range(1, 5):
    series2.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 2, [0.70, 0.50, 0.20, 0.35][i-1])
    )

# 将填充设置为蓝色并配置标签
series2.format.fill.fill_type = slides.FillType.SOLID
series2.format.fill.solid_fill_color.color = drawing.Color.blue

series2.labels.default_data_label_format.show_value = True
```

### 功能 4：将演示文稿保存到磁盘
**概述：** 图表配置完成后，保存演示文稿。

#### 步骤 1：保存您的工作
使用 `save` 存储文件的方法：
```python
# 将演示文稿保存到磁盘
directory = "YOUR_OUTPUT_DIRECTORY"
presentation.save(f"{directory}/charts_set_data_labels_percentage_sign_out.pptx", slides.export.SaveFormat.PPTX)
```

## 实际应用
使用 Aspose.Slides for Python，您可以增强各个领域的演示文稿：
1. **商业报告：** 创建带有动态图表的详细季度报告。
2. **教育内容：** 设计具有视觉数据表现形式的引人入胜的教育材料。
3. **销售演示：** 有效地说明销售趋势和预测。

这些示例演示了如何将 Aspose.Slides 集成到现有工作流程中以提供精美的演示文稿。

## 性能考虑
为确保最佳性能：
- 有效地管理内存，特别是在处理图表中的大型数据集时。
- 利用 Aspose.Slides 进行 Python 资源管理的最佳实践。
- 定期更新您的库以获得性能增强。

通过遵循这些提示，您可以在处理复杂的演示文稿时保持顺畅而高效的操作。

## 结论
在本教程中，我们探索了如何使用 Aspose.Slides for Python 在演示文稿中创建和配置图表。现在，您已经掌握了将视觉效果出众的数据可视化集成到项目中的知识。为了进一步提升您的技能，您可以探索库中的其他功能或尝试不同的图表类型。

**后续步骤：** 尝试在实际项目中实现这些概念以巩固您的理解。

## 常见问题解答部分
1. **如何安装 Aspose.Slides for Python？**
   - 使用 `pip install aspose.slides` 轻松下载并安装。
2. **我可以在不购买许可证的情况下使用 Aspose.Slides 吗？**
   - 是的，您可以先免费试用，或者申请临时许可证。
3. **是否可以进一步自定义图表数据标签？**
   - 当然！您可以探索库 API 提供的更多格式化选项。
4. **创建图表时有哪些常见问题？**
   - 确保所有数据点的格式正确并链接到适当的系列。
5. **如何将 Aspose.Slides 与其他系统集成？**
   - 使用其全面的 API 无缝集成到您现有的 Python 项目中。

## 资源
- [文档](https://reference.aspose.com/slides/python-net/)
- [下载](https://releases.aspose.com/slides/python-net/)
- [购买](https://purchase.aspose.com/buy)
- [免费试用](https://releases.aspose.com/slides/python-net/)
- [临时执照](https://purchase.aspose.com/temporary-license/)
- [支持论坛](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}