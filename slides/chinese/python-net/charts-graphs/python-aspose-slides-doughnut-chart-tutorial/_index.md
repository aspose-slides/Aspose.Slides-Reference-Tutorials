---
"date": "2025-04-22"
"description": "学习如何使用 Python 和 Aspose.Slides 创建圆环图。本分步指南涵盖设置、自定义以及增强演示文稿的最佳实践。"
"title": "如何使用 Aspose.Slides 在 Python 中创建甜甜圈图——分步指南"
"url": "/zh/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides 在 Python 中创建甜甜圈图：分步指南

在数据可视化领域，有效地呈现信息可以显著影响理解和决策。无论您是制作商业演示文稿还是分析复杂数据集，图表都是必不可少的工具。在众多图表类型中，圆环图提供了一种以直观的中心孔来表示比例数据的吸引人的方式。本分步指南将指导您使用 Aspose.Slides（一个功能强大的演示文稿处理库）在 Python 中创建圆环图。

## 您将学到什么
- 如何设置和使用 Aspose.Slides for Python
- 在演示文稿幻灯片中添加圆环图的过程
- 自定义图表中的系列和类别
- 调整标签、颜色和爆炸效果等视觉元素
- 使用 Aspose.Slides 优化性能的最佳实践

## 先决条件
在开始之前，请确保您已：
- **Python 环境**：您的机器上安装了 Python 3.x。
- **Aspose.Slides for Python**：使用 pip 安装此库。
- **对 Python 编程的基本了解**：熟悉循环和面向对象编程将会有所帮助。

## 为 Python 设置 Aspose.Slides
首先，通过 pip 安装 Aspose.Slides 库：

```bash
pip install aspose.slides
```

### 许可证获取
Aspose 提供免费试用，供您在限定时间内无限制地测试各项功能。获取方法：
1. 访问 [免费试用](https://releases.aspose.com/slides/python-net/) 页。
2. 按照说明下载并应用您的临时许可证。

为了继续使用，请考虑从 [购买页面](https://purchase。aspose.com/buy).

### 基本初始化
设置Aspose.Slides后，按如下方式初始化它：

```python
import aspose.slides as slides

# 创建 Presentation 类的实例。
with slides.Presentation() as pres:
    # 用于操作演示文稿的代码放在这里。

# 进行更改后保存演示文稿。
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## 实施指南
设置 Aspose.Slides 后，按照以下步骤将环形图逐张添加到演示文稿中。

### 创建新演示文稿并添加幻灯片
首先创建一个 `Presentation` 班级：

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # 在此上下文中访问或创建幻灯片。
```

### 在第一张幻灯片中添加圆环图
访问第一张幻灯片并使用 `add_chart` 方法。指定图表类型为 `DOUGHNUT`，以及位置和大小：

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### 配置图表数据
清除现有数据并配置隐藏图例等设置：

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### 添加系列和类别
为圆环图添加多个系列和类别。以下是如何创建具有特定属性的 15 个系列：

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

类似地添加类别：

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # 为每个系列添加数据点。
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # 自定义每个数据点的外观。
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # 配置最后一个系列的标签设置。
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### 保存演示文稿
最后，将您的演示文稿保存到指定目录：

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## 实际应用
圆环图用途广泛，可用于各种场景，例如：
1. **预算分配**：显示不同部门如何使用其分配的资金。
2. **市场份额分析**：比较竞争产品或公司的市场份额。
3. **调查结果**：可视化有关偏好或满意度水平的调查问题的答复。

## 性能考虑
为确保使用 Aspose.Slides 时获得最佳性能：
- 通过在使用后正确处理对象来最大限度地减少内存使用。
- 仅在必要时将演示文稿加载到内存中，并尽快关闭它们。
- 如果您要处理大量图表，请考虑批量处理幻灯片。

## 结论
通过本指南，您已经学习了如何使用 Aspose.Slides for Python 创建动态圆环图。这些可视化效果可以使数据更易于理解和引人入胜，从而增强您的演示文稿。继续探索库的功能，进一步自定义和优化您的图表。

## 常见问题解答部分
1. **我可以在不购买许可证的情况下使用 Aspose.Slides 吗？**
   - 是的，您可以从免费试用许可证开始进行评估。
2. **如何在 Aspose.Slides 中更改图表颜色？**
   - 使用 `fill_format` 属性来设置图表元素所需的颜色。
3. **可以将图表导出为图像吗？**
   - 是的，您可以使用库的渲染功能将包含图表的幻灯片渲染为图像格式。
4. **添加图表时有哪些常见问题？**
   - 在尝试保存或显示图表之前，请确保所有数据点和类别都已正确添加。
5. **我可以将 Aspose.Slides 与其他 Python 库集成吗？**
   - 当然！您可以将其与 Pandas 等库一起使用，以增强数据处理功能。

## 资源
- [Aspose.Slides文档](https://reference.aspose.com/slides/python-net/)
- [下载 Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [购买许可证](https://purchase.aspose.com/buy)
- [免费试用和临时许可证](https://releases.aspose.com/slides/python-net/)
- [Aspose 社区论坛](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}