---
"date": "2025-04-22"
"description": "学习如何使用 Aspose.Slides for Python 在 PowerPoint 中创建和自定义圆环图。本教程涵盖圆环图的设置、演示文稿的保存以及最佳实践。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中创建自定义孔径的甜甜圈图"
"url": "/zh/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中创建自定义孔径的甜甜圈图

## 介绍
在 PowerPoint 中创建视觉上引人入胜的图表可以让您的数据更具吸引力，更易于理解。一个常见的挑战是，以编程方式生成这些图表时缺乏自定义选项。本教程将演示如何使用 Aspose.Slides for Python 创建具有自定义孔径的圆环图来解决这个问题。

**关键词：** Aspose.Slides Python，圆环图，自定义孔径

### 您将学到什么：
- 设置并使用 Aspose.Slides for Python
- 在 PowerPoint 中创建圆环图
- 自定义圆环图的孔径
- 保存和导出演示文稿的最佳实践

## 先决条件
在开始之前，请确保您已：
- **Python 3.x** 安装在您的系统上。
- Python 编程概念的基本知识。
- 这 `aspose.slides` 库（下面提供安装说明）。

## 为 Python 设置 Aspose.Slides
首先，使用 pip 安装 Aspose.Slides for Python：

```bash
pip install aspose.slides
```

### 许可证获取
Aspose 提供免费试用，让您可以探索其功能，不受文档数量或使用时间的限制：
- **免费试用：** 从临时许可证开始测试全部功能。
- **临时执照：** 可用于评估目的。
- **购买：** 为了长期使用，请考虑购买许可证。

安装和设置完成后，您就可以开始以编程方式创建演示文稿了。以下是如何初始化 Aspose.Slides：

```python
import aspose.slides as slides

# 初始化演示对象
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # 您的代码在此处
```

## 实施指南
本节详细介绍了使用 Aspose.Slides 在 PowerPoint 中创建和自定义圆环图所需的步骤。

### 步骤 1：访问和修改幻灯片
首先，打开演示文稿的第一张幻灯片。在这里，您可以添加自定义圆环图。

```python
# 访问第一张幻灯片
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### 步骤2：添加圆环图
您可以通过指定位置和大小将圆环图添加到任何幻灯片。在这里，我们将其放置在坐标 (50, 50) 处，尺寸为 400x400。

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # 添加圆环图
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### 步骤3：自定义孔尺寸
调整圆环图的孔径很简单。将其设置为 90% 即可获得明显的效果。

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # 设置自定义孔尺寸
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### 步骤4：保存演示文稿
最后，使用所选的文件名将演示文稿保存到所需位置。

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # 保存演示文稿
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## 实际应用
创建自定义圆环图在各种情况下都很有用，包括：
- **商业报告：** 通过视觉上不同的部分突出显示关键绩效指标。
- **教育内容：** 向学生或同事说明统计数据。
- **营销材料：** 展示产品细目或客户人口统计数据。

通过将图表导出为图像或使用 Aspose 的综合 API 将其嵌入到 Web 应用程序中，可以与其他系统集成。

## 性能考虑
使用 Aspose.Slides 时，请考虑以下提示以获得最佳性能：
- 仅加载必要的幻灯片以最大限度地减少资源使用。
- 使用后立即关闭演示文稿，有效管理内存。
- 利用批处理一次生成多个图表。

遵循最佳实践可确保您的应用程序平稳高效地运行。

## 结论
通过本指南，您学习了如何使用 Aspose.Slides for Python 在 PowerPoint 中创建自定义孔径的圆环图。这不仅可以增强演示文稿的视觉吸引力，还可以提高数据呈现的灵活性。

为了进一步探索 Aspose.Slides 的功能，您可以尝试其他图表类型和演示功能。祝您编码愉快！

## 常见问题解答部分
1. **我可以为环形图设置的最大孔径是多少？**
   - 您可以将其设置为 100% 以获得完整的圆形图表。
2. **我可以使用 Aspose.Slides 修改 PowerPoint 文件中的现有图表吗？**
   - 是的，您可以加载和编辑现有的演示文稿。
3. **保存演示文稿时如何处理错误？**
   - 确保输出路径可写并检查权限问题。
4. **除了环形图之外，还支持其他图表类型吗？**
   - 当然，Aspose.Slides 支持多种图表类型。
5. **Aspose.Slides 可以与 Web 应用程序一起使用吗？**
   - 是的，它的 API 可以集成到后端系统并通过 Web 服务公开。

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