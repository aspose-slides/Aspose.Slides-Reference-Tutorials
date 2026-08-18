---
date: '2026-06-03'
description: Tìm hiểu cách tạo biểu đồ cột nhóm trong Java bằng cách sử dụng Aspose.Slides.
  Hướng dẫn này bao gồm phụ thuộc Maven, các bước tạo biểu đồ và xử lý dữ liệu.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Tạo biểu đồ cột nhóm trong Java với Aspose.Slides
url: /vi/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo Biểu Đồ Cột Nhóm trong Java với Aspose.Slides

## Cách Tạo Biểu Đồ trong Java: Giới Thiệu
Tạo các bản trình bày động thường đòi hỏi việc trực quan hóa dữ liệu bằng các biểu đồ. Với **Aspose.Slides for Java**, bạn có thể dễ dàng **tạo biểu đồ cột nhóm** đối tượng, nâng cao độ rõ ràng và tạo ấn tượng mạnh hơn với khán giả. Hướng dẫn này sẽ chỉ cho bạn cách thiết lập thư viện, thêm biểu đồ cột nhóm, quản lý các chuỗi, và đảo ngược các điểm dữ liệu âm một cách có điều kiện.

**Bạn sẽ học được**
- Cách thiết lập Aspose.Slides cho Java.
- Các bước **tạo biểu đồ cột nhóm** trong bản trình bày của bạn.
- Kỹ thuật quản lý chuỗi biểu đồ và các điểm dữ liệu.
- Phương pháp đảo ngược các điểm dữ liệu âm một cách có điều kiện để cải thiện việc trực quan hoá.
- Cách lưu bản trình bày một cách an toàn.

## Câu trả lời nhanh
- **Thư viện được sử dụng?** Aspose.Slides for Java.  
- **Loại biểu đồ được minh họa?** Biểu đồ cột nhóm.  
- **Tôi có thể đảo ngược giá trị âm không?** Có, sử dụng `invertIfNegative`.  
- **Phiên bản Java yêu cầu?** JDK 16 hoặc mới hơn.  
- **Cần giấy phép cho môi trường sản xuất không?** Có, một giấy phép Aspose hợp lệ.

## Biểu đồ cột nhóm là gì?
Biểu đồ cột nhóm là một dạng biểu diễn trực quan đặt nhiều chuỗi dữ liệu cạnh nhau cho mỗi danh mục, cho phép so sánh nhanh chóng giữa các nhóm. Nó hoàn hảo cho báo cáo tài chính, bảng điều khiển bán hàng, và bất kỳ trường hợp nào bạn cần đối chiếu nhiều chỉ số cùng lúc.

## Tại sao nên sử dụng Aspose.Slides để tạo biểu đồ?
Aspose.Slides cho phép bạn tạo và tùy chỉnh hoàn toàn các biểu đồ bằng lập trình, loại bỏ nhu cầu chỉnh sửa PowerPoint thủ công. Nó hỗ trợ **hơn 70 định dạng nhập và xuất** và có thể xử lý các bản trình bày với **lên tới 10.000 slide** mà không cần tải toàn bộ tệp vào bộ nhớ, đảm bảo hiệu năng cao cho các báo cáo quy mô lớn.

## Yêu cầu trước
1. **Thư viện yêu cầu**  
   - Aspose.Slides for Java (phiên bản 25.4 hoặc mới hơn).  

2. **Môi trường**  
   - JDK 16 hoặc mới hơn.  
   - Maven hoặc Gradle để quản lý phụ thuộc.  

3. **Kiến thức**  
   - Lập trình Java cơ bản.  
   - Quen thuộc với công cụ xây dựng (Maven/Gradle).  

## Cài đặt Aspose.Slides cho Java
### Cài đặt Maven
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Cài đặt Gradle
Thêm dòng sau vào tệp `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Hoặc, tải phiên bản mới nhất từ [Phiên bản Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).

### Nhận giấy phép
- **Dùng thử miễn phí:** Khám phá các tính năng mà không cần giấy phép.  
- **Giấy phép tạm thời:** Sử dụng trong quá trình đánh giá.  
- **Giấy phép đầy đủ:** Mua để triển khai trong môi trường sản xuất.

### Khởi tạo cơ bản
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Làm thế nào để thêm biểu đồ cột nhóm vào một slide?
`Presentation` là lớp cốt lõi đại diện cho một tệp PowerPoint. Tải một `Presentation` mới, thêm một slide, và gọi `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Lệnh duy nhất này tạo ra một biểu đồ cột nhóm hoạt động đầy đủ, được đặt tại tọa độ đã chỉ định. Bạn có thể truy cập đối tượng biểu đồ để chỉnh sửa chuỗi, điểm dữ liệu và kiểu dáng trực quan.

## Hướng dẫn từng bước

### Bước 1: Tạo một Presentation và Thêm biểu đồ cột nhóm
`Presentation` là lớp đại diện cho tài liệu PowerPoint và cho phép tạo các slide.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Bước 2: Quản lý chuỗi biểu đồ
Bây giờ chúng ta sẽ xóa bất kỳ chuỗi mặc định nào, thêm một chuỗi mới và điền dữ liệu cả giá trị dương và âm.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Bước 3: Đảo ngược các điểm dữ liệu âm một cách có điều kiện
Phương thức `invertIfNegative` cho phép đảo ngược các giá trị âm trong một chuỗi biểu đồ.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Những lỗi thường gặp & Mẹo
- **Quên giải phóng đối tượng `Presentation`?** Luôn gọi `dispose()` trong khối `finally` để giải phóng tài nguyên gốc.  
- **Giá trị âm không được đảo ngược?** Đảm bảo bạn gọi `invertIfNegative(true)` **sau** khi thêm điểm dữ liệu.  
- **Vấn đề kích thước biểu đồ:** Các tọa độ (X, Y) và kích thước (width, height) tính bằng điểm; điều chỉnh chúng để phù hợp với bố cục slide của bạn.  

## Câu hỏi thường gặp

**Q:** Can I create other chart types with the same approach?  
A: Yes, simply replace `ChartType.ClusteredColumn` with any other `ChartType` enum value (e.g., `Line`, `Pie`).  

**Q:** Do I need a license for development builds?  
A: A temporary or evaluation license is required for full feature access; otherwise, the library works in trial mode with watermark limitations.  

**Q:** How do I export the presentation to PDF after adding charts?  
`SaveFormat.Pdf` specifies PDF as the output format for saving a presentation. Use `pres.save("output.pdf", SaveFormat.Pdf);` after you finish chart manipulation.  

**Q:** Is it possible to style individual columns (color, border)?  
`IChartDataPoint` represents a single data point in a chart and allows formatting. Each `IChartDataPoint` provides options such as `getFillFormat().setFillType(FillType.Solid)` and `getLineFormat()`.  

**Q:** What if I need to update the chart data after the presentation is saved?  
A: Load the presentation again with `new Presentation("file.pptx")`, modify the chart data, and re‑save.  

---

**Cập nhật lần cuối:** 2026-06-03  
**Đã kiểm tra với:** Aspose.Slides for Java 25.4 (JDK 16)  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Cách tạo biểu đồ cột chồng trong Java với Aspose.Slides – Hướng dẫn toàn diện](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Cách tạo biểu đồ trong Java với Aspose.Slides – Thành thạo việc tạo và xác thực biểu đồ](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Tạo & Định dạng biểu đồ trong Java bằng Aspose.Slides: Hướng dẫn toàn diện](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}