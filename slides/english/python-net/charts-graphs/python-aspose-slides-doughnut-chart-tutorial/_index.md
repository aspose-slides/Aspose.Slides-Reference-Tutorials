---
title: "How to Create Doughnut Charts in Python Using Aspose.Slides&#58; A Step-by-Step Guide"
description: "Learn how to create doughnut charts with Python and Aspose.Slides. This step-by-step guide covers setup, customization, and best practices for enhancing your presentations."
date: "2025-04-22"
weight: 1
url: "/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
keywords:
- doughnut chart Python
- Aspose.Slides doughnut chart
- create charts in Python

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create Doughnut Charts in Python Using Aspose.Slides: A Step-by-Step Guide

In the realm of data visualization, effectively presenting information can significantly impact understanding and decision-making. Whether you're crafting a business presentation or analyzing complex datasets, charts are essential tools. Among various chart types, doughnut charts provide an appealing way to represent proportional data with an intuitive center hole. This step-by-step guide will walk you through creating a doughnut chart in Python using Aspose.Slides—a powerful library for manipulating presentations.

## What You'll Learn
- How to set up and use Aspose.Slides for Python
- The process of adding a doughnut chart to your presentation slides
- Customizing series and categories within the chart
- Adjusting visual elements such as labels, colors, and explosion effects
- Best practices for optimizing performance with Aspose.Slides

## Prerequisites
Before starting, ensure you have:
- **Python Environment**: Python 3.x installed on your machine.
- **Aspose.Slides for Python**: Install this library using pip.
- **Basic Understanding of Python Programming**: Familiarity with loops and object-oriented programming will be helpful.

## Setting Up Aspose.Slides for Python
To get started, install the Aspose.Slides library via pip:

```bash
pip install aspose.slides
```

### License Acquisition
Aspose offers a free trial to test features without limitations for a limited time. To obtain this:
1. Visit the [Free Trial](https://releases.aspose.com/slides/python-net/) page.
2. Follow instructions to download and apply your temporary license.

For continued use, consider purchasing a subscription from the [Purchase Page](https://purchase.aspose.com/buy).

### Basic Initialization
After setting up Aspose.Slides, initialize it as follows:

```python
import aspose.slides as slides

# Create an instance of Presentation class.
with slides.Presentation() as pres:
    # Your code to manipulate presentations goes here.

# Save the presentation after making changes.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Implementation Guide
With Aspose.Slides set up, follow these steps to add a doughnut chart to your presentation slide-by-slide.

### Creating a New Presentation and Adding a Slide
Start by creating an instance of the `Presentation` class:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Access or create slides within this context.
```

### Adding a Doughnut Chart to the First Slide
Access the first slide and use the `add_chart` method. Specify the chart type as `DOUGHNUT`, along with position and size:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Configuring Chart Data
Clear existing data and configure settings such as hiding the legend:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Adding Series and Categories
Add multiple series and categories for a doughnut chart. Here's how to create 15 series with specific properties:

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

Add categories similarly:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Add data points for each series.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Customize the appearance of each data point.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Configure label settings for the last series.
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

### Saving the Presentation
Finally, save your presentation to a specified directory:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Practical Applications
Doughnut charts are versatile and can be used in various scenarios such as:
1. **Budget Allocation**: Displaying how different departments use their allocated funds.
2. **Market Share Analysis**: Comparing the market share of competing products or companies.
3. **Survey Results**: Visualizing responses to survey questions about preferences or satisfaction levels.

## Performance Considerations
To ensure optimal performance when using Aspose.Slides:
- Minimize memory usage by disposing of objects properly after use.
- Only load presentations into memory when necessary, and close them as soon as possible.
- Consider batch processing slides if you're working with a large number of charts.

## Conclusion
By following this guide, you've learned how to create dynamic doughnut charts using Aspose.Slides for Python. These visualizations can enhance your presentations by making data more digestible and engaging. Continue exploring the library's features to further customize and optimize your charts.

## FAQ Section
1. **Can I use Aspose.Slides without purchasing a license?**
   - Yes, you can start with a free trial license for evaluation purposes.
2. **How do I change chart colors in Aspose.Slides?**
   - Use the `fill_format` property to set the desired color for your chart elements.
3. **Is it possible to export charts as images?**
   - Yes, you can render slides containing charts into image formats using the library's rendering capabilities.
4. **What are some common issues when adding charts?**
   - Ensure that all data points and categories are properly added before attempting to save or display your chart.
5. **Can I integrate Aspose.Slides with other Python libraries?**
   - Absolutely! You can use it alongside libraries like Pandas for enhanced data manipulation capabilities.

## Resources
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/python-net/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial and Temporary License](https://releases.aspose.com/slides/python-net/)
- [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}