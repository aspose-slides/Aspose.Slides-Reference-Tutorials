---
date: '2026-06-03'
description: Tìm hiểu cách thêm biểu đồ với aspose slides maven dependency, cấu hình
  nhãn dữ liệu và tạo biểu đồ động trong bài thuyết trình Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Thêm và cấu hình biểu đồ trong bài thuyết
  trình bằng Aspose.Slides for Java'
url: /vi/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Thêm và Cấu hình Biểu đồ trong Bài thuyết trình bằng Aspose.Slides cho Java

## Giới thiệu
The **aspose slides maven dependency** lets Java developers programmatically create, modify, and enrich PowerPoint files without ever opening PowerPoint itself. In many business and academic scenarios, manually inserting charts is time‑consuming and error‑prone. This tutorial shows you step‑by‑step how to add a Bubble Chart, bind data labels to worksheet cells, and save the result—all by leveraging the aspose slides maven dependency in a clean, repeatable way.

**Bạn sẽ học được**
- Cách thêm biểu đồ bằng aspose slides maven dependency
- Cài đặt dự án Java bằng Maven hoặc Gradle
- Tải một bài thuyết trình hiện có và chèn Biểu đồ Bubble
- Cấu hình nhãn dữ liệu bằng cách tham chiếu ô (thêm nhãn dữ liệu cho biểu đồ)
- Lưu tệp đã cập nhật để phân phối sau
- Các trường hợp sử dụng thực tế như tạo biểu đồ động và quy trình tạo biểu đồ cho bài thuyết trình

## Câu trả lời nhanh
- **Artifact Maven nào thêm khả năng biểu đồ?** `com.aspose:aspose-slides:25.4` (or latest)  
- **Có thể gắn nhãn dữ liệu vào các ô kiểu Excel không?** Yes – use `ChartDataLabel` with `setDataLabelFormat` and cell references.  
- **Có cần giấy phép cho môi trường sản xuất không?** A full license removes the evaluation watermark and unlocks all features.  
- **Liệu điều này có hoạt động trên Java 11+ không?** Absolutely; the library is compatible with Java 8 through Java 21.  
- **Có bao nhiêu loại biểu đồ được hỗ trợ?** Over 70 distinct chart types, including Bubble, Radar, and Stock charts.

## Aspose slides maven dependency là gì?
The **aspose slides maven dependency** is a Maven‑compatible package that provides a full‑featured API for creating and editing PowerPoint (PPTX, PPT, ODP) files in Java. By adding this dependency to your `pom.xml` or `build.gradle`, you gain access to over 70 chart types, 150+ slide layouts, and the ability to manipulate shapes, animations, and metadata without Office installed.

## Tại sao nên sử dụng aspose slides maven dependency cho tự động hoá biểu đồ?
Aspose.Slides processes multi‑thousand‑slide decks in under a second on standard server hardware, supports **70+ chart types**, and can render presentations up to **10,000 slides** without loading the entire file into memory. These quantified capabilities make it ideal for enterprise‑grade dynamic chart generation, where performance and scalability are non‑negotiable.

## Yêu cầu trước
- **Java Development Kit (JDK)** 8 or newer (Java 11+ recommended).  
- **Maven** 3.6+ **or** **Gradle** 6+.  
- **Aspose.Slides for Java** library (the aspose slides maven dependency, version 25.4 or later).  
- Kiến thức cơ bản về các collection của Java và I/O file.  
- Một file giấy phép đánh giá hoặc đầy đủ (`license.json`) nếu bạn dự định chạy mã vượt quá thời gian dùng thử.

## Cách thêm biểu đồ vào slide bằng Aspose.Slides?
Load the target presentation, create a new chart shape on the desired slide, and specify the chart type (Bubble in this example). The entire operation can be performed in **three concise lines of code** once the library is referenced, making it perfect for rapid prototyping and production pipelines.

### Bước 1: Thêm aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
These snippets pull the full Aspose.Slides API—including chart support—directly from Maven Central.

### Bước 2: Tải bài thuyết trình và chèn Biểu đồ Bubble
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Bước 3: Cấu hình chuỗi dữ liệu và nhãn của biểu đồ
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Bước 4: Lưu bài thuyết trình đã chỉnh sửa
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Cách cấu hình nhãn dữ liệu bằng tham chiếu ô?
Data labels can be bound to external cell values, mirroring Excel’s “Link to Cell” feature. This approach eliminates hard‑coded values and enables **dynamic chart generation** where label content updates automatically as the underlying data changes. By linking each label to a specific workbook cell, you ensure that any modification to the source data is instantly reflected in the presentation, reducing maintenance effort and minimizing the risk of outdated information.

### Câu trả lời trực tiếp
Call `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` and pass a `DataLabelFormat` that references a cell address such as `"Sheet1!A2"`. Aspose.Slides resolves the reference at runtime, inserting the cell’s current value into the chart label.

### Các bước thực hiện
1. Xác định chuỗi bạn muốn gắn nhãn.  
2. Lấy đối tượng `IDataLabel` cho mỗi điểm dữ liệu.  
3. Sử dụng `setDataLabelFormat` với `DataLabelFormat` được cấu hình cho `CellReference`.  
4. Tùy chọn tùy chỉnh phông chữ, màu sắc và các tùy chọn hiển thị.

## Cách lưu bài thuyết trình đã chỉnh sửa?
Saving is a single‑method call that writes the in‑memory `Presentation` object to a file path or output stream. You can also choose the output format (PPTX, PDF, ODP) by passing the appropriate `SaveFormat` enum. This operation streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope, which helps keep memory usage low even for large decks.

### Câu trả lời trực tiếp
Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`; the library streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope.

## Ứng dụng thực tiễn
1. **Báo cáo doanh nghiệp:** Tự động tạo biểu đồ bán hàng hàng quý từ dữ liệu xuất khẩu cơ sở dữ liệu.  
2. **Bài giảng học thuật:** Kéo dữ liệu nghiên cứu trực tiếp vào slide giảng dạy cho mỗi buổi học.  
3. **Bài thuyết trình bán hàng:** Xây dựng bảng điều khiển hiệu suất riêng cho khách hàng ngay lập tức.  
4. **Quản lý dự án:** Trực quan hoá thời gian kiểu Gantt với nhãn dữ liệu động.  
5. **Phân tích tiếp thị:** Nhúng các KPI chiến dịch vào bài thuyết trình và cập nhật khi có số liệu mới.

## Các lưu ý về hiệu năng
- **Quản lý bộ nhớ:** Use try‑with‑resources or explicit `presentation.dispose()` to free native memory promptly.  
- **Bộ dữ liệu lớn:** When handling more than 10,000 data points, populate chart data via `ChartDataWorkbook` to avoid loading the entire dataset into Java objects.  
- **An toàn đa luồng:** Each thread should work with its own `Presentation` instance; the API is not thread‑safe across shared objects.  

## Các vấn đề thường gặp và giải pháp
- **Issue:** “License file not found.”  
  **Solution:** Place `license.json` in the classpath and call `License license = new License(); license.setLicense("license.json");` before any API usage.  
- **Issue:** Chart appears blank after saving.  
  **Solution:** Ensure that the chart’s data workbook is saved with the presentation (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Issue:** Data labels show “#REF!” errors.  
  **Solution:** Verify that the cell reference string matches the exact sheet name and address, and that the referenced workbook is attached to the chart.  

## Câu hỏi thường gặp

**Q: Có thể thêm các loại biểu đồ khác ngoài Bubble không?**  
A: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock, and more than 70 additional types.

**Q: Aspose slides maven dependency có hoạt động với OpenJDK không?**  
A: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major operating systems.

**Q: Làm thế nào để nhúng biểu đồ từ một file Excel hiện có?**  
A: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell references.

**Q: Có giới hạn số lượng biểu đồ trên mỗi slide không?**  
A: Practically no—Aspose.Slides can handle dozens of charts per slide, limited only by available memory.

**Q: Tôi có thể xuất bản thuyết trình cuối cùng sang định dạng nào?**  
A: PPTX, PPT, ODP, PDF, XPS, HTML, và thậm chí các định dạng ảnh như PNG và JPEG đều được hỗ trợ.

## Tài nguyên
- [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) – tải xuống các binary thư viện mới nhất.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – tài liệu tham chiếu API toàn diện và các hướng dẫn.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – trang tải trực tiếp các gói Maven/Gradle.  
- [Purchase a License](https://purchase.aspose.com/buy) – mua giấy phép thương mại đầy đủ.  
- [Free Trial](https://releases.aspose.com/slides/java/) – bắt đầu dùng thử để đánh giá tính năng.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – yêu cầu khóa tạm thời cho thời gian đánh giá kéo dài.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – nhận trợ giúp từ cộng đồng và kỹ sư Aspose.

## Kết luận
You now have a complete, end‑to‑end guide for using the **aspose slides maven dependency** to add, configure, and persist charts in Java presentations. By following the steps above you can automate chart creation, bind data labels to live cell values, and generate professional‑grade decks at scale. Experiment with other chart types, explore animation APIs, and integrate this workflow into your reporting pipelines for maximum impact.

---  
**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Hướng dẫn liên quan

- [Cách tạo và cấu hình bài thuyết trình với Aspose.Slides Java: Hướng dẫn từng bước](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Tạo PPTX Java với Aspose.Slides Maven – Hướng dẫn tự động hoá](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Cách tạo biểu đồ trong Java với Aspose.Slides: Hướng dẫn toàn diện](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}