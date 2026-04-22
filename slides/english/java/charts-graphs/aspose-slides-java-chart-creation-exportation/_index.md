---
title: "How to Create Chart with Aspose.Slides Java"
description: "Learn how to create chart and export chart to Excel using Aspose.Slides for Java. Master data visualization, business report slides, and workbook generation."
date: "2026-02-09"
weight: 1
url: "/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create Chart Using Aspose.Slides for Java

**Master Data Visualization Techniques with Aspose.Slides for Java**

In today's data‑driven landscape, *how to create chart* programmatically is a skill that can turn raw numbers into compelling visual stories. Whether you’re building a business report slide deck or an interactive analytics dashboard, Aspose.Slides for Java gives you the power to generate, customize, and export charts directly from your code. In this tutorial you’ll learn how to create chart objects, export chart data to Excel, and link charts to external workbooks for seamless data management.

## Quick Answers
- **What library is needed?** Aspose.Slides for Java (v25.4+).  
- **Can I export chart data to Excel?** Yes – use `readWorkbookStream()` and write the bytes to an *.xlsx* file.  
- **Which Java version is required?** JDK 16 or higher.  
- **Do I need a license?** A free trial works for evaluation; a permanent license is required for production.  
- **What chart type is demonstrated?** A Pie chart, but the same approach works for Bar, Line, and other chart types.

## What is Aspose.Slides for Java?
Aspose.Slides for Java is a pure‑Java API that lets developers create, edit, and convert PowerPoint presentations without Microsoft Office. It supports a full range of chart types, data binding, and export capabilities, making it ideal for **data visualization java** projects.

## Why use Aspose.Slides to create chart and export chart to Excel?
- **No Office installation** – works on any server or cloud environment.  
- **Rich chart library** – dozens of chart types and full styling control.  
- **Direct Excel export** – generate an external workbook for downstream analysis.  
- **Performance‑oriented** – low memory footprint and fast processing for large decks.

## Prerequisites
Before we dive in, make sure you have the following:

### Required Libraries and Versions
- **Aspose.Slides for Java** version 25.4 or later

### Environment Setup Requirements
- Java Development Kit (JDK) 16 or higher  
- An IDE such as IntelliJ IDEA or Eclipse (or any text editor you prefer)

### Knowledge Prerequisites
- Basic Java programming skills  
- Familiarity with Maven or Gradle build tools

## Setting Up Aspose.Slides for Java
Add the library to your project using your favourite build system.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatively, you can [download the latest version directly](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
Aspose.Slides offers a free trial license to explore its full capabilities. You can also apply for a temporary license or purchase one for extended use. Follow these steps:

1. Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get your license.  
2. For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).  
3. Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).

Once you have the license file, initialize it in your Java application:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Step‑by‑Step Guide

### How to create chart – Load a Presentation
Loading an existing PowerPoint file is the first step before you can add or modify charts.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**Explanation:**  
- `Presentation` represents the PowerPoint file.  
- Always call `dispose()` to release native resources.

### How to create chart – Add a Pie Chart to a Slide
Now we’ll insert a Pie chart, which is perfect for showing proportional data.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Explanation:**  
- `addChart` inserts the chart onto the first slide.  
- The parameters define chart type, X/Y position, and size.

### How to export chart to Excel – Export Chart Data
Exporting chart data lets analysts work with the numbers in Excel, enabling deeper insights.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Explanation:**  
- `readWorkbookStream()` extracts the chart’s underlying Excel workbook as a byte array.  
- The byte array is written to `externalWorkbook1.xlsx`, giving you a ready‑to‑use Excel file.

### How to create chart – Set External Workbook for Dynamic Data
Linking a chart to an external workbook allows you to update the chart simply by editing the Excel file.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Explanation:**  
- `setExternalWorkbook` binds the chart to the specified Excel file, enabling live data updates without rebuilding the slide.

## Practical Applications
Aspose.Slides offers versatile solutions for various real‑world scenarios:

1. **Business Report Slides:** Generate quarterly performance charts automatically from your data pipelines.  
2. **Academic Presentations:** Turn research data into clear visualizations without manual charting.  
3. **Financial Analysis:** Export chart data to Excel for auditors to verify numbers.  
4. **Marketing Analytics:** Visualize campaign metrics and share editable workbooks with stakeholders.

## Common Issues & Troubleshooting
- **`FileNotFoundException`** – Verify that `dataDir` points to a valid folder and that the output path is writable.  
- **Memory leaks** – Always call `pres.dispose()` in a `finally` block to free native resources.  
- **Chart not appearing** – Ensure the slide index (`get_Item(0)`) matches a slide that actually exists.

## Frequently Asked Questions

**Q: Can I use a different chart type (e.g., Bar, Line) with the same code?**  
A: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such as `ChartType.Bar` or `ChartType.Line`.

**Q: Is it possible to update the external workbook after the chart is created?**  
A: Absolutely. Modify the Excel file directly; the linked chart will reflect the changes the next time the presentation is opened.

**Q: Do I need a separate license for the Excel export feature?**  
A: No. The Excel export capability is included in the standard Aspose.Slides for Java license.

**Q: Which Java versions are supported?**  
A: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may work but are not officially tested.

**Q: How can I embed the generated Excel workbook inside the PPTX file?**  
A: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook, or keep the external link for dynamic updates.

---

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}