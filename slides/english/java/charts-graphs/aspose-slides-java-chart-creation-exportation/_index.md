---
title: "Export Chart to Excel and Create Charts with Aspose.Slides"
description: "Learn how to export chart to Excel and create chart Java using Aspose.Slides for Java. Master data visualization, business report slides, and workbook generation."
date: "2026-06-03"
weight: 1
url: "/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
keywords:
  - export chart to excel
  - create chart java
  - how to create chart
  - add chart to powerpoint
  - java chart visualization
schemas:
- type: TechArticle
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  dateModified: '2026-06-03'
  author: Aspose
- type: HowTo
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
- type: FAQPage
  questions:
  - question: Can I use a different chart type (e.g., Bar, Line) with the same code?
    answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
  - question: Is it possible to update the external workbook after the chart is created?
    answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
  - question: Do I need a separate license for the Excel export feature?
    answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
  - question: Which Java versions are supported?
    answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
  - question: How can I embed the generated Excel workbook inside the PPTX file?
    answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Chart to Excel and Create Charts with Aspose.Slides

**Master Data Visualization Techniques with Aspose.Slides for Java**

In today's data‑driven landscape, *export chart to excel* programmatically is a skill that can turn raw numbers into compelling visual stories. Whether you’re building a business report slide deck or an interactive analytics dashboard, Aspose.Slides for Java gives you the power to generate, customize, and export charts directly from your code. In this tutorial you’ll learn how to create chart objects, export chart data to Excel, and link charts to external workbooks for seamless data management.

## Quick Answers
- **What library is needed?** Aspose.Slides for Java (v25.4+).  
- **Can I export chart data to Excel?** Yes – use `readWorkbookStream()` and write the bytes to an *.xlsx* file.  
- **Which Java version is required?** JDK 16 or higher.  
- **Do I need a license?** A free trial works for evaluation; a permanent license is required for production.  
- **What chart type is demonstrated?** A Pie chart, but the same approach works for Bar, Line, and other chart types.

## What is Aspose.Slides for Java?
Aspose.Slides for Java is a pure‑Java API that lets developers create, edit, and convert PowerPoint presentations without Microsoft Office. It provides a comprehensive set of classes for slide manipulation, chart generation, and format conversion, enabling automated reporting solutions. It supports **50+ chart types**, full data binding, and direct Excel export, making it ideal for **data visualization java** projects.

## Why use Aspose.Slides to create chart and export chart to Excel?
Export chart to Excel quickly and reliably. Aspose.Slides eliminates the need for Office installations, offers **over 50‑built‑in chart styles**, and processes presentations **up to 300 MB in under 30 seconds** on standard server hardware. You also get native Excel workbook generation, which lets downstream analysts work with raw numbers without manual copy‑paste.

## Prerequisites
Before we dive in, make sure you have the following:

### Required Libraries and Versions
- **Aspose.Slides for Java** version 25.4 or later (supports JDK 16+)

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
Load an existing PowerPoint file before you can add or modify charts.  
The `Presentation` class represents a PowerPoint file in memory, exposing slides, shapes, and chart objects.  
Load your file with `new Presentation("input.pptx")`, then work with the first slide using `presentation.getSlides().get_Item(0)`. Always call `presentation.dispose()` in a `finally` block to release native resources.

### How to create chart – Add a Pie Chart to a Slide
Insert a Pie chart, perfect for showing proportional data.  
The `IChart` interface is the primary entry point for chart manipulation; `addChart` creates a new chart on the target slide. Provide the chart type (`ChartType.Pie`), X/Y coordinates, and width/height. After creation, you can customize titles, legend, and data series through the `ChartData` object.

### How to export chart to Excel – Export Chart Data
Exporting chart data lets analysts work with the numbers in Excel, enabling deeper insights.  
`readWorkbookStream()` returns the chart's underlying Excel workbook as a byte array. Call `chart.getChartData().readWorkbookStream()` to retrieve the workbook and write this array to a file named `externalWorkbook1.xlsx` using standard Java I/O. The resulting Excel file contains the exact data used by the chart, ready for further analysis.

### How to create chart – Set External Workbook for Dynamic Data
Link a chart to an external workbook to enable live data updates without rebuilding the slide.  
`setExternalWorkbook()` binds the chart to an external Excel file for dynamic data updates. Use `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` to bind the chart to the external file. When the Excel workbook is edited, the chart automatically reflects the changes the next time the presentation is opened, supporting dynamic reporting scenarios.

## Practical Applications
Aspose.Slides offers versatile solutions for various real‑world scenarios:

1. **Business Report Slides:** Generate quarterly performance charts automatically from your data pipelines.  
2. **Academic Presentations:** Turn research data into clear visualizations without manual charting.  
3. **Financial Analysis:** Export chart data to Excel for auditors to verify numbers, reducing manual errors.  
4. **Marketing Analytics:** Visualize campaign metrics and share editable workbooks with stakeholders for collaborative decision‑making.  
5. **Automated Dashboard Generation:** Combine the chart‑creation API with scheduled jobs to produce up‑to‑date slide decks each morning.

## Common Issues & Troubleshooting
- **`FileNotFoundException`** – Verify that `dataDir` points to a valid folder and that the output path is writable.  
- **Memory leaks** – Always call `presentation.dispose()` in a `finally` block to free native resources.  
- **Chart not appearing** – Ensure the slide index (`get_Item(0)`) matches an existing slide, and that the chart’s dimensions are within the slide bounds.  
- **Excel export produces empty file** – Confirm that the chart actually contains data series before calling `readWorkbookStream()`.

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

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recover Workbook Data from PowerPoint Charts Using Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}