---
date: '2026-01-14'
description: Pelajari cara mengekspor diagram ke Excel menggunakan Aspose.Slides untuk
  Java dan menambahkan slide diagram pai ke presentasi. Panduan langkah demi langkah
  dengan kode.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Ekspor Grafik ke Excel dengan Aspose.Slides Java
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ekspor Diagram ke Excel Menggunakan Aspose.Slides untuk Java

**Kuasai Teknik Visualisasi Data dengan Aspose.Slides untuk Java**

Di era data‑driven saat ini, kemampuan untuk **export chart to excel** langsung dari aplikasi Java Anda dapat mengubah visual PowerPoint statis menjadi set data yang dapat digunakan kembali dan dianalisis. Baik Anda perlu menghasilkan laporan, mengalirkan data ke pipeline analitik, atau sekadar membiarkan pengguna bisnis mengedit data diagram di Excel, Aspose.Slides mempermudah prosesnya. Tutorial ini memandu Anda membuat diagram, menambahkan slide diagram pai, dan mengekspor data diagram tersebut ke workbook Excel.

**Apa yang Akan Anda Pelajari:**
- Memuat dan memanipulasi file presentasi dengan mudah
- **Add pie chart slide** dan tipe diagram lainnya ke slide Anda
- **Export chart to excel** (generate excel from chart) untuk analisis lanjutan
- Menetapkan jalur workbook eksternal untuk **embed chart in presentation** dan menjaga sinkronisasi data

Mari kita mulai!

## Quick Answers
- **What is the primary purpose?** Export chart data from a PowerPoint slide to an Excel file.  
- **Which library version is required?** Aspose.Slides for Java 25.4 or later.  
- **Do I need a license?** A free trial works for evaluation; a commercial license is required for production.  
- **Can I add a pie chart slide?** Yes – the tutorial shows how to add a Pie chart.  
- **Is Java 16 minimum?** Yes, JDK 16 or higher is recommended.

## How to export chart to excel using Aspose.Slides?
Exporting chart data to Excel is as simple as loading a presentation, creating a chart, and then writing the chart’s workbook stream to a file. The steps below walk you through the entire process, from project setup to final verification.

## Prerequisites
Before we begin, ensure you have the following ready:

### Required Libraries and Versions
- **Aspose.Slides for Java** version 25.4 or later

### Environment Setup Requirements
- Java Development Kit (JDK) 16 or higher
- A code editor or IDE such as IntelliJ IDEA or Eclipse

### Knowledge Prerequisites
- Basic Java programming skills
- Familiarity with Maven or Gradle build systems

## Setting Up Aspose.Slides for Java
To start using Aspose.Slides, include it in your project using Maven or Gradle.

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

## Implementation Guide

### Feature 1: Load Presentation
Loading a presentation is the first step to any manipulation task.

#### Overview
This feature demonstrates how to load an existing PowerPoint file using Aspose.Slides for Java.

#### Step‑by‑Step Implementation
**Load Presentation**
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
- `Presentation` is initialized with the path to your `.pptx` file.  
- Always dispose of the `Presentation` object to free native resources.

### Feature 2: Add Pie Chart Slide
Adding a chart can significantly enhance data presentation, and many developers ask **how to add chart slide** in Java.

#### Overview
This feature shows how to add a **pie chart slide** (the classic “add pie chart slide” scenario) to the first slide of a presentation.

#### Step‑by‑Step Implementation
**Add Pie Chart**
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
- `addChart` inserts a Pie chart.  
- The parameters define the chart type and its position/size on the slide.

### Feature 3: Generate Excel from Chart
Exporting the chart data lets you **generate excel from chart** for deeper analysis.

#### Overview
This feature demonstrates exporting chart data from a presentation to an external Excel workbook.

#### Step‑by‑Step Implementation
**Export Data**
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
- `readWorkbookStream` extracts the chart’s workbook data.  
- The byte array is written to an `.xlsx` file using `FileOutputStream`.

### Feature 4: Embed Chart in Presentation with External Workbook
Linking a chart to an external workbook helps you **embed chart in presentation** and keep data synchronized.

#### Overview
This feature demonstrates setting an external workbook path so the chart can read/write data directly from Excel.

#### Step‑by‑Step Implementation
**Set External Workbook Path**
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
- `setExternalWorkbook` links the chart to an Excel file, allowing dynamic updates without rebuilding the slide.

## Practical Applications
Aspose.Slides offers versatile solutions for various scenarios:

1. **Business Reports:** Create detailed reports with charts directly from Java applications.  
2. **Academic Presentations:** Enhance lectures with interactive pie chart slides.  
3. **Financial Analysis:** **Export chart to excel** for in‑depth financial modeling.  
4. **Marketing Analytics:** Visualize campaign performance and **generate excel from chart** for the analytics team.

## Frequently Asked Questions

**Q: Can I use this approach with other chart types (e.g., Bar, Line)?**  
A: Absolutely. Replace `ChartType.Pie` with any other `ChartType` enum value.

**Q: Do I need a separate Excel library to read the exported file?**  
A: No. The exported `.xlsx` file is a standard Excel workbook that can be opened with any spreadsheet application.

**Q: How does the external workbook affect slide size?**  
A: Linking to an external workbook does not increase the PPTX file size significantly; the chart references the workbook at runtime.

**Q: Is it possible to update the Excel data and have the slide reflect changes automatically?**  
A: Yes. After calling `setExternalWorkbook`, any changes saved to the workbook will be reflected the next time the presentation is opened.

**Q: What if I need to export multiple charts from the same presentation?**  
A: Iterate over each slide’s chart collection, call `readWorkbookStream()` for each, and write to separate workbook files.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}