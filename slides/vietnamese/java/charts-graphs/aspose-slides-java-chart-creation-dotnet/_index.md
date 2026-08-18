---
date: '2026-06-03'
description: Tìm hiểu cách tạo biểu đồ trong các bản trình chiếu .NET và thêm biểu
  đồ vào slide bằng Aspose.Slides for Java. Thực hiện theo hướng dẫn từng bước này
  để trực quan hoá dữ liệu.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Tạo biểu đồ trong .NET bằng Aspose.Slides for Java
url: /vi/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ trong .NET bằng Aspose.Slides cho Java

## Giới thiệu
Creating compelling presentations often involves integrating visual data representations like charts to enhance audience understanding and engagement. **If you want to create charts in .NET**, Aspose.Slides for Java gives you a powerful, language‑agnostic API that works seamlessly inside .NET applications. In this tutorial you’ll learn how to initialize a presentation, add a variety of chart types, manage the chart data workbook, and format series data—including handling negative values. By the end you’ll be able to generate chart in presentation files programmatically and add chart to slide with just a few lines of code.

## Câu trả lời nhanh
- **Mục tiêu chính là gì?** Create charts in .NET presentations using Aspose.Slides for Java.  
- **Phiên bản thư viện nào được yêu cầu?** Aspose.Slides for Java 25.4 or later.  
- **Tôi có cần giấy phép không?** A free trial works for development; a commercial license is required for production.  
- **Tôi có thể sử dụng Maven hoặc Gradle không?** Yes—both build systems are supported.  
- **Các loại biểu đồ nào có sẵn?** Clustered column, line, pie, bar, area, and more.

## Cách tạo biểu đồ trong các bản trình bày .NET bằng Aspose.Slides cho Java?
The `Presentation` class represents a PowerPoint file and provides methods to manipulate its slides. Load a new `Presentation` object, call `slides.addEmptySlide()` to obtain a slide, then use `slide.getShapes().addChart()` to insert the desired chart type at the coordinates you specify. After the chart is added, populate its data workbook with series and categories, apply any formatting (such as colors for negative values), and finally save the presentation to a .pptx file. This flow lets you **create charts in .NET** with a concise set of API calls.

## Aspose.Slides cho Java là gì?
Aspose.Slides for Java is a cross‑platform API that enables developers to create, modify, and render PowerPoint files without Microsoft Office. It supports **50+ input and output formats** and can process presentations with thousands of slides while keeping memory usage under 200 MB.

## Tại sao sử dụng Aspose.Slides cho Java trong dự án .NET?
Aspose.Slides for Java runs on the Java Virtual Machine and can be called from .NET through a native wrapper, giving .NET developers access to a mature chart engine, high‑performance processing of large data sets, and full compatibility with existing Java code without rewriting logic.

## Yêu cầu trước
Before diving into creating charts with Aspose.Slides for Java, let's outline what you need:

### Thư viện và Phiên bản yêu cầu
- **Aspose.Slides cho Java**: Version 25.4 or later.

### Yêu cầu thiết lập môi trường
- A development environment supporting .NET applications.  
- Basic understanding of Java programming concepts.

### Kiến thức tiên quyết
- Familiarity with creating presentations in a .NET application context.  
- Understanding Java dependencies and their management (Maven/Gradle).

## Cài đặt Aspose.Slides cho Java
To start using Aspose.Slides, you need to include it as a dependency in your project. Here’s how you can do that:

### Maven
The Maven dependency snippet adds Aspose.Slides for Java to your project.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file to pull the library from Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Alternatively, you can download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Các bước lấy giấy phép
- **Dùng thử miễn phí**: Start with a temporary license to explore features.  
- **Mua**: Buy a license for unrestricted production use.

#### Khởi tạo và Cài đặt Cơ bản
`Slides` initialization requires setting the license and creating a `Presentation` instance.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

This setup ensures resource management is handled effectively.

## Hướng dẫn triển khai
We'll walk you through implementing the features step‑by‑step.

### Khởi tạo Presentation
**Tổng quan:**  
Creating a presentation instance sets the stage for all subsequent operations. This feature shows how to start from scratch using Aspose.Slides.

#### Bước 1: Nhập các gói cần thiết
`Presentation` and related classes are part of the `com.aspose.slides` namespace.

```java
import com.aspose.slides.Presentation;
```

#### Bước 2: Tạo đối tượng Presentation mới
Instantiate a `Presentation` object and wrap it in a try‑with‑resources block to guarantee disposal.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*This ensures that the presentation object is properly disposed of after use, preventing memory leaks.*

### Thêm biểu đồ vào Slide
**Tổng quan:**  
Adding a chart to your slide can make data visualization more effective and engaging.

#### Bước 1: Nhập các gói cần thiết
The `Chart` class represents a chart shape that can be placed on a slide and customized.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Bước 2: Khởi tạo Presentation và Thêm biểu đồ
Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and the desired position and size.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Here, we add a clustered column chart to the first slide at specified coordinates and dimensions.*

### Quản lý Workbook dữ liệu biểu đồ
**Tổng quan:**  
Efficiently managing your chart's data workbook allows you to manipulate series and categories seamlessly.

#### Bước 1: Nhập các gói cần thiết
`IChartDataWorkbook` provides access to the underlying Excel‑like workbook used by charts.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Bước 2: Truy cập và Xóa Workbook dữ liệu
Retrieve the workbook from the chart and clear any existing data to start fresh.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Clearing the workbook is crucial for starting with a clean slate when adding new series and categories.*

### Thêm Series và Categories vào Biểu đồ
**Tổng quan:**  
This feature shows how you can add meaningful data points by managing series and categories.

#### Bước 1: Thêm Series và Categories
Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()` to define structure.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Adding series and categories allows for a more organized data presentation.*

### Điền dữ liệu Series và Định dạng
**Tổng quan:**  
Populate your chart with data points and format the appearance to enhance readability, especially when dealing with negative values.

#### Bước 1: Điền dữ liệu Series
Assign numeric values to each cell in the workbook and apply a red fill for negative numbers.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*This section demonstrates how to populate data and apply color formatting for better visualization.*

## Các vấn đề thường gặp và giải pháp
- **LicenseNotFoundException** – Ensure the license file path is correct and the file is accessible at runtime.  
- **NullPointerException trên dữ liệu biểu đồ** – Always clear the workbook before adding new series to avoid residual data.  
- **Chart not rendering in .NET** – Verify that you are using the .NET compatible version of the Aspose.Slides JAR and that the Java runtime is correctly configured in your .NET project.

## Câu hỏi thường gặp

**Q: Có thể tạo biểu đồ trong tệp trình bày mà không cần giao diện người dùng không?**  
A: Yes, Aspose.Slides for Java is fully headless and works on servers without any graphical components.

**Q: Các phiên bản .NET nào được hỗ trợ?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.

**Q: Có thể thêm bao nhiêu loại biểu đồ?**  
A: Over 20 chart types are available, including column, line, pie, area, and radar charts.

**Q: Có thể định dạng từng điểm dữ liệu riêng lẻ không?**  
A: Absolutely – you can set fill colors, borders, and markers for each data point via the `IDataPoint` API.

**Q: Cần phải chuyển đổi các đối tượng Java sang kiểu .NET một cách thủ công không?**  
A: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách Nhúng Biểu Đồ vào Bản Trình Bày .NET Sử Dụng Aspose.Slides để Trực Quan Hóa Dữ Liệu](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Cách Lấy Loại Nguồn Dữ Liệu Biểu Đồ Sử Dụng Aspose.Slides cho .NET - Charts & Graphs](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Tạo và Quản Lý Series Biểu Đồ với Aspose.Slides .NET để Trực Quan Hóa Dữ Liệu Hiệu Quả](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}