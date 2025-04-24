---
title: "How to Set a Chart's Vertical Axis Title Rotation in Aspose.Slides for Python"
description: "Learn how to adjust the rotation angle of chart titles in presentations using Aspose.Slides for Python, enhancing readability and aesthetics."
date: "2025-04-23"
weight: 1
url: "/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
keywords:
- Aspose.Aspose.Slides
- Python-net
- Document Processing

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# How to Set a Chart's Vertical Axis Title Rotation in Aspose.Slides for Python

## Introduction

In data presentations, improving chart readability is crucial. Adjusting the rotation angle of your chart’s vertical axis title using Aspose.Slides for Python can make titles fit neatly or stand out in your slides. This tutorial guides you through setting this rotation angle to enhance both functionality and visual appeal.

**What You'll Learn:**
- How to install and configure Aspose.Slides for Python.
- Steps to add and customize charts within your slides.
- Techniques to set the rotation angle of chart titles.
- Real-world applications for these features in data visualization.

Let’s start by covering the prerequisites before diving into implementation.

## Prerequisites

Before starting, ensure you have:
- **Python Environment**: Install Python 3.x from [python.org](https://www.python.org/).
- **Aspose.Slides Library**: Install via pip to manipulate presentations effectively.
- **Basic Knowledge of Python Programming**: Familiarity with Python syntax and file operations will help you follow along.

## Setting Up Aspose.Slides for Python

To use Aspose.Slides, install it using pip. Open your terminal or command prompt and run:

```bash
pip install aspose.slides
```

### License Acquisition Steps

Aspose offers different license options:
- **Free Trial**: Download a trial version from [Aspose's release page](https://releases.aspose.com/slides/python-net/).
- **Temporary License**: Obtain a temporary license for extended features via the [purchase portal](https://purchase.aspose.com/temporary-license/).
- **Purchase**: Consider purchasing if you find the tool indispensable, available from the [Aspose purchase page](https://purchase.aspose.com/buy).

#### Basic Initialization and Setup

Here’s how to initialize Aspose.Slides in your Python script:

```python
import aspose.slides as slides

# Create a presentation object
def main():
    with slides.Presentation() as pres:
        # Your code will go here
        pass

if __name__ == "__main__":
    main()
```

## Implementation Guide

### Adding and Customizing Charts

#### Overview

In this section, we’ll add a clustered column chart to your slide and customize it by setting the rotation angle of its vertical axis title.

#### Steps:

##### Step 1: Add a Clustered Column Chart

Start by adding a chart at specific coordinates with defined dimensions:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Add a clustered column chart to slide 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Step 2: Configure the Vertical Axis Title

Enable and set the rotation angle for the vertical axis title:

```python
def configure_chart(chart):
    # Enable the vertical axis title
    chart.axes.vertical_axis.has_title = True
    
    # Set the rotation angle to 90 degrees
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Step 3: Save Your Presentation

Finally, save your presentation with the changes:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Save the presentation
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}