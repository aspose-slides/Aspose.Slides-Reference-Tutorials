---
date: '2026-03-02'
description: Aspose.Slides for Java를 사용하여 동적 파이 차트를 만들면서 Excel을 PowerPoint에 추가하고 Excel에서
  PowerPoint를 생성하는 방법을 배워보세요.
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 'Excel을 PowerPoint에 추가: Aspose.Slides for Java를 사용한 파이 차트 동적 프레젠테이션'
url: /ko/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Excel을 PowerPoint에 추가하기: Aspose.Slides for Java를 사용한 파이 차트 동적 프레젠테이션

오늘날 데이터‑드리븐 환경에서 **add Excel to PowerPoint**를 빠르고 안정적으로 수행하여 청중이 숫자를 시각적인 형식으로 볼 수 있도록 합니다. 이 튜토리얼에서는 Excel에서 PowerPoint를 생성하고, Java로 파이 차트를 만들며, 차트 데이터 범위를 구성하는 과정을 Aspose.Slides for Java와 함께 안내합니다. 최종적으로 Excel 워크북에서 실시간 데이터를 직접 가져오는 사용 가능한 프레젠테이션을 얻게 됩니다.

## Quick Answers
- **What library creates charts in Java?** Aspose.Slides for Java.
- **Can I pull Excel data directly into a PowerPoint chart?** Yes – use Aspose.Cells to read the workbook and feed it to the chart.
- **Which chart type is demonstrated?** A pie chart.
- **How do I set the data range for the chart?** By calling `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.
- **What is the primary benefit of this approach?** Automates the “add Excel to PowerPoint” workflow, eliminating manual copy‑paste.

## What is **add Excel to PowerPoint**?
Excel을 PowerPoint에 추가한다는 것은 스프레드시트 데이터를 프로그래밍 방식으로 가져와 슬라이드 데크 안에 시각화하는 것을 의미합니다. Aspose.Slides와 Aspose.Cells를 사용하면 모든 Excel 파일을 읽고, 셀을 차트 시리즈에 매핑하며, PowerPoint를 수동으로 열지 않고도 깔끔한 프레젠테이션을 만들 수 있습니다.

## Why generate PowerPoint from Excel with Aspose.Slides for Java?
- **Speed:** Build reports in seconds, not minutes.
- **Accuracy:** Data is read directly from the source workbook, removing transcription errors.
- **Flexibility:** Customize chart colors, styles, and data ranges on the fly.
- **Scalability:** Integrate into batch jobs, web services, or scheduled reporting pipelines.

## Prerequisites

시작하기 전에 다음이 설치되어 있는지 확인하십시오:

- **Java Development Kit (JDK) 1.8+** installed.
- **Aspose.Slides for Java** and **Aspose.Cells for Java** libraries (Maven, Gradle, or direct JAR download).
- An Excel workbook (`book1.xlsx`) containing the data you want to visualize.
- A valid Aspose license (free trial works for evaluation).

### Required Libraries
You’ll need Aspose.Slides and Aspose.Cells. Use one of these dependency management tools:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatively, download the JARs directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
- **Free Trial:** Available on the [Aspose download page](https://releases.aspose.com/slides/java/).  
- **Temporary License:** For testing without evaluation limitations, apply for one at [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).  
- **Purchase License:** To use Aspose products in production, purchase the full license.

## Setting Up Aspose.Slides for Java

Add the Aspose.Slides dependency to your project (see the Maven/Gradle snippets above) and place the JAR files on your classpath if you’re not using a build tool.

### Basic Initialization and Setup
Import the core class that represents a PowerPoint file:

```java
import com.aspose.slides.Presentation;
```

## Implementation Guide

Below is a step‑by‑step walkthrough that covers **create pie chart java**, **set chart data range**, and **add Excel to PowerPoint** in a single flow.

### Create and Add Chart to Presentation

**Overview:** Initialize a new presentation, grab the first slide, and insert a pie chart.

#### Step 1: Initialize Presentation
```java
Presentation pres = new Presentation();
```
- **Purpose:** Creates an empty PowerPoint file in memory.

#### Step 2: Access First Slide
```java
ISlide slide = pres.getSlides().get_Item(0);
```
- **Explanation:** Retrieves the automatically created first slide.

#### Step 3: Add Pie Chart to Slide
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **Parameters:** Position (`x`, `y`) and size (`width`, `height`).  
- **Purpose:** Places a pie chart shape on the slide.

### Load Workbook from File

**Overview:** Load the Excel workbook that holds the data for the chart.

#### Step 1: Define Document Directory
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- Set this to the folder containing `book1.xlsx`.

#### Step 2: Open Workbook
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **Purpose:** Reads the Excel file into memory.

### Save Workbook to ByteArrayOutputStream

**Overview:** Convert the workbook into a byte array so Aspose.Slides can consume it.

#### Step 1: Create ByteArrayOutputStream
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```
- **Purpose:** Provides an in‑memory stream for temporary storage.

#### Step 2: Save Workbook to Stream
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```
- **Explanation:** Writes the workbook as an XLSX byte stream.

### Write Workbook Data to Chart

**Overview:** Feed the Excel byte array into the chart as its data source.

#### Step 1: Feed Data into Chart
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **Purpose:** Links the chart to the Excel data.

### Set Chart Data Range and Configure Series

**Overview:** Define which cells the chart should read and enhance visual styling.

#### Step 1: Define Data Range
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```
- **Explanation:** Points the chart to the exact range on *Sheet2*.

#### Step 2: Configure Series Properties
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```
- **Purpose:** Enables varied colors for each slice of the pie chart.

### Save Presentation to File

**Overview:** Persist the completed presentation to disk.

#### Step 1: Define Output Path
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```
- Choose a folder where you want the final PowerPoint file.

#### Step 2: Save Presentation
```java
pres.save(outPath, SaveFormat.Pptx);
```
- **Explanation:** Writes the presentation as a `.pptx` file.

## Practical Applications

1. **Business Reporting:** Turn monthly sales spreadsheets into polished slide decks with a single command.  
2. **Educational Tools:** Show statistical breakdowns for classroom presentations without manual chart creation.  
3. **Dashboard Integration:** Automate the generation of slide‑based dashboards that pull live data from Excel workbooks.

## Performance Considerations

- **Memory Management:** Wrap streams in try‑with‑resources or close them in a `finally` block to avoid leaks.  
- **Large Datasets:** Process data in chunks or use `Workbook.getWorksheets().clear()` after extracting needed values.  
- **Lazy Loading:** Load the workbook only when you need to populate the chart, not at application startup.

## Common Issues and Solutions

| 문제 | 해결책 |
|-------|----------|
| **Chart shows no data** | Verify the range string matches the sheet name and cell addresses exactly (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | Use `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` to ensure the stream is released promptly. |
| **License not applied** | Load the license before any Aspose class is instantiated: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Frequently Asked Questions

**Q: Can I use Aspose.Slides without a license?**  
A: Yes, but evaluation mode adds watermarks and limits some features. For production, obtain a temporary or full license.

**Q: How do I handle large presentations in Aspose.Slides?**  
A: Use efficient resource management, split the presentation into smaller parts, and dispose of unused objects promptly.

**Q: What file formats can Aspose.Slides export to?**  
A: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.

**Q: Is it possible to update an existing PowerPoint file instead of creating a new one?**  
A: Absolutely. Load an existing file with `new Presentation("existing.pptx")`, modify slides/charts, then save.

**Q: Does the library support setting custom colors for individual pie slices?**  
A: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` and assign a `Color`.

## Resources
- **Documentation:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)
- **Purchase License:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Free Trial:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Temporary License:** [Get a Temporary License](https://purchase.aspose.com/temporary-license)

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}