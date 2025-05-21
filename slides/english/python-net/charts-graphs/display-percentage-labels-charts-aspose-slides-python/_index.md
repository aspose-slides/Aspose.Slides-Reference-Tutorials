---
title: "How to Display Percentage Labels on Charts Using Aspose.Slides for Python&#58; A Comprehensive Guide"
description: "Learn how to effortlessly display percentage labels on charts in PowerPoint presentations using Aspose.Slides for Python. Perfect for enhancing data visualization."
date: "2025-04-22"
weight: 1
url: "/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
keywords:
- Aspose.Aspose.Slides
- Python-net
- Document Processing

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Display Percentage Labels on Charts Using Aspose.Slides for Python

## Introduction

Visualizing data effectively is crucial in presentations and reports, especially when you want to highlight proportions or distributions clearly. But what if you need those percentages displayed directly on your charts? This comprehensive guide will walk you through using **Aspose.Slides for Python** to display percentage values as labels on a chart effortlessly.

### What You'll Learn:
- How to create and embed charts in PowerPoint presentations using Aspose.Slides for Python.
- Displaying data points as percentage labels on your charts.
- Saving and managing PowerPoint presentations efficiently.

Ready to start adding insightful visuals to your data? Let's first look at what you need before diving into the code!

## Prerequisites

Before we begin, ensure that you have the following:
- **Aspose.Slides for Python**: This library is essential for creating and manipulating PowerPoint presentations programmatically.
- **Python Environment**: A basic understanding of Python programming and environment setup.
- **PIP Package Manager**: Used to install Aspose.Slides.

## Setting Up Aspose.Slides for Python

To start using Aspose.Slides, you'll first need to install it:

```bash
pip install aspose.slides
```

### License Acquisition Steps:
You can get started with a free trial or obtain a temporary license to explore the full capabilities of Aspose.Slides. For extended use, consider purchasing a subscription.

#### Basic Initialization and Setup

Once installed, you'll initialize your presentation environment like so:

```python
import aspose.slides as slides

# Initialize a Presentation object
def create_presentation():
    with slides.Presentation() as presentation:
        # Your code here
```

## Implementation Guide

Now that we're set up let's dive into displaying percentages on charts.

### Creating the Chart and Adding Data

#### Overview
We'll create a stacked column chart with percentage labels for each data point, allowing viewers to see the exact proportions at a glance.

##### Step 1: Add a Chart to Your Slide

```python
# Access the first slide in your presentation
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Add a stacked column chart
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

This code snippet adds a basic chart to the first slide. The `add_chart` method specifies the type of chart and its position and size.

##### Step 2: Calculate Total Values for Categories

```python
def calculate_totals(chart):
    total_for_category = []
    # Sum up values across all series for each category
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

This loop calculates the total of all data points across series, which is crucial for percentage calculations.

#### Setting Percentage Labels

##### Step 3: Configure Series Data Points

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Set default label options to hide non-essential info
        series.labels.default_data_label_format.show_legend_key = False
        
        # Calculate and set percentage labels
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Create a text portion with the percentage value
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Clear existing labels and add new percentage label
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Hide other data label elements
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

This segment processes each data point to calculate its percentage of the total and assigns it as a label.

### Saving Your Presentation

```python
def save_presentation(presentation, output_directory):
    # Save your presentation with modifications
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}