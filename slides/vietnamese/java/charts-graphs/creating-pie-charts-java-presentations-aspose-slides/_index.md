---
date: '2026-08-01'
description: Tìm hiểu cách sử dụng giấy phép Aspose Slides để tạo và tùy chỉnh pie
  charts trong các bản trình bày Java. Thực hiện các hướng dẫn step‑by‑step để cấu
  hình dữ liệu pie chart và thêm chart slides một cách hiệu quả.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Tìm hiểu cách sử dụng giấy phép Aspose Slides để tạo và tùy chỉnh
  pie charts trong các bản trình bày Java. Thực hiện các hướng dẫn step‑by‑step để
  cấu hình dữ liệu pie chart và thêm chart slides một cách hiệu quả.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Tạo Pie Charts trong Java với giấy phép Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Tạo Pie Charts trong Java với giấy phép Aspose Slides
url: /vi/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Tạo Biểu Đồ Tròn trong Bài Thuyết Trình Java Sử Dụng Aspose.Slides

## Giới thiệu

Nếu bạn cần tạo các bài thuyết trình chuyên nghiệp, **một giấy phép Aspose Slides** cho phép bạn tạo và định dạng biểu đồ một cách lập trình. Trong hướng dẫn này, bạn sẽ học cách tạo biểu đồ tròn, cấu hình dữ liệu của nó và nhúng vào bộ slide Java — mà không cần dựa vào Microsoft PowerPoint. Chúng tôi sẽ hướng dẫn qua quá trình cài đặt, luồng mã và các mẹo thực hành tốt nhất để bạn có thể cung cấp các báo cáo hình ảnh hoàn chỉnh trong vài phút.

**Bạn sẽ học:**
- Cài đặt Aspose.Slides cho Java với giấy phép hợp lệ
- Các bước tạo và tùy chỉnh biểu đồ tròn
- Cách cấu hình dữ liệu biểu đồ tròn và thêm các slide biểu đồ
- Những lỗi thường gặp và mẹo tối ưu hiệu năng

Hãy bắt đầu bằng cách xác nhận môi trường của bạn đã sẵn sàng.

## Câu trả lời nhanh
- **Giấy phép Aspose Slides cho phép gì?** Tạo biểu đồ đầy đủ tính năng, xuất ra PDF/HTML và loại bỏ watermark.  
- **Phiên bản Java nào được yêu cầu?** JDK 16 hoặc mới hơn.  
- **Tôi có cần Maven hoặc Gradle không?** Cả hai đều hoạt động; thư viện có sẵn qua cả hai.  
- **Biểu đồ tròn có thể chứa bao nhiêu điểm dữ liệu?** Lên tới 10 000 điểm mà không gặp vấn đề bộ nhớ.  
- **Tôi có thể xuất slide dưới dạng hình ảnh không?** Có – PNG, JPEG, SVG và nhiều định dạng khác được hỗ trợ.  

## Yêu cầu trước
Trước khi bắt đầu, hãy xác nhận rằng bạn có:
- **Thư viện yêu cầu:** Aspose.Slides for Java (phiên bản 25.4 hoặc mới hơn) – phiên bản này hỗ trợ các định dạng tệp mới nhất và tối ưu hiệu năng.  
- **Cài đặt môi trường:** JDK 16+ đã được cài đặt và cấu hình trong IDE hoặc hệ thống build của bạn.  
- **Kiến thức cơ bản:** Quen thuộc với Java, Maven hoặc Gradle, và các khái niệm lập trình hướng đối tượng.  

## Cài đặt Aspose.Slides cho Java
Để sử dụng Aspose.Slides cho Java, bao gồm nó trong dự án của bạn. Dưới đây là cách thêm phụ thuộc với các công cụ build phổ biến nhất:

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

**Tải trực tiếp:** Bạn cũng có thể tải JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Nhận Giấy phép
Aspose cung cấp bản dùng thử miễn phí mở khóa tất cả tính năng, nhưng **giấy phép Aspose Slides hợp lệ** là cần thiết cho môi trường sản xuất để loại bỏ watermark đánh giá và nhận được lợi ích về hiệu năng. Các tùy chọn mua được liệt kê trên [trang mua](https://purchase.aspose.com/buy). Sau khi có file giấy phép, tải nó một lần khi khởi động ứng dụng:

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Hướng dẫn triển khai

### Tạo và Thêm Biểu Đồ Tròn vào Bài Thuyết Trình

#### Tổng quan
Phần này giải thích cách tạo biểu đồ tròn, cấu hình chuỗi dữ liệu của nó và nhúng biểu đồ vào một slide. Bạn sẽ thấy quy trình đầy đủ từ khởi tạo đối tượng presentation đến lưu file cuối cùng.

#### Bước 1: Khởi tạo Presentation  
`Presentation` là đối tượng cấp cao nhất của Aspose.Slides đại diện cho một tệp PowerPoint trong bộ nhớ. Tạo một thể hiện sẽ cung cấp cho bạn một bộ slide trống sẵn sàng để chỉnh sửa.

```java
demo.Presentation pres = new demo.Presentation();
```  
Dòng này tạo một presentation mới, nơi tất cả các thay đổi tiếp theo sẽ được áp dụng.

#### Bước 2: Thêm Biểu Đồ Tròn vào Slide  
`Chart` là lớp bao bọc các đối tượng biểu đồ, bao gồm cả biểu đồ tròn. Thêm một biểu đồ vào slide chỉ cần một lời gọi phương thức duy nhất, chỉ định vị trí và kích thước.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` và `yPosition` đặt góc trên‑trái của biểu đồ.  
- `width` và `height` xác định kích thước hiển thị của biểu đồ trên slide.

#### Bước 3: Cấu hình Dữ liệu Biểu Đồ Tròn  
`ChartData` chứa chuỗi dữ liệu cho một biểu đồ.  
**Làm thế nào để cấu hình dữ liệu biểu đồ tròn?**  
Cung cấp câu trả lời ngắn gọn đầu tiên: Sử dụng bộ sưu tập `ChartData` để thêm một series, sau đó điền các đối tượng `ChartDataPoint` với giá trị số và tên danh mục. Cách tiếp cận này cho phép bạn hiển thị lên tới 10 000 lát bánh mà vẫn giữ định dạng nhãn. Sau khi thiết lập dữ liệu, bạn có thể tùy chỉnh màu sắc, chú giải và nhãn dữ liệu để phù hợp với hướng dẫn phong cách công ty của bạn.

Bây giờ, đây là đoạn mã thêm hai danh mục và hiển thị nhãn của chúng:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Đoạn mã này tạo một series dữ liệu, chèn hai điểm, và bật nhãn danh mục trên biểu đồ.

#### Bước 4: Lưu Presentation  
Cuối cùng, lưu presentation vào định dạng tệp mà bạn chọn (PPTX, PDF hoặc PNG). Phương thức `save` tuân theo giấy phép đang hoạt động, đảm bảo không xuất hiện watermark bản dùng thử.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Các vấn đề thường gặp và giải pháp
- **Lỗi thiếu giấy phép:** Đảm bảo đường dẫn file giấy phép đúng và đối tượng `License` được khởi tạo trước bất kỳ lời gọi Aspose.Slides nào.  
- **Biểu đồ trống:** Kiểm tra rằng series `ChartData` chứa ít nhất một `ChartDataPoint`. Series rỗng sẽ dẫn đến khu vực biểu đồ trống.  
- **Độ trễ hiệu năng với bộ dữ liệu lớn:** Sử dụng `presentation.getSlides().removeAt(index)` để loại bỏ các slide không dùng và gọi `System.gc()` sau khi xử lý nặng.  

## Ứng dụng thực tiễn
1. **Báo cáo kinh doanh:** Trực quan hóa thị phần hoặc phân phối doanh thu theo khu vực bằng một biểu đồ tròn duy nhất.  
2. **Bài thuyết trình học thuật:** Hiển thị kết quả khảo sát hoặc kết quả thí nghiệm một cách rõ ràng, dễ hiểu.  
3. **Bảng điều khiển dự án:** Đại diện phần trăm hoàn thành nhiệm vụ hoặc phân bổ nguồn lực ngay trên slide.  

Bạn cũng có thể kết hợp Aspose.Slides với JDBC để lấy dữ liệu trực tiếp từ cơ sở dữ liệu, tạo biểu đồ cập nhật cho các buổi tóm tắt hàng tuần cho lãnh đạo.

## Cân nhắc về hiệu năng
Khi làm việc với các bài thuyết trình chứa nhiều hình ảnh độ phân giải cao hoặc bộ dữ liệu lớn:
- Giải phóng các đối tượng kịp thời bằng cách sử dụng `try‑with‑resources` hoặc gọi `dispose()` một cách rõ ràng.  
- Bật tải lười (lazy loading) các tài nguyên slide để giảm mức sử dụng bộ nhớ.  
- Đối với xử lý hàng loạt, tái sử dụng một thể hiện `Presentation` duy nhất khi có thể để giảm tải JVM.  

## Kết luận
Bạn giờ đã có quy trình hoàn chỉnh, sẵn sàng cho sản xuất để tạo biểu đồ tròn trong Java sử dụng **giấy phép Aspose Slides**. Thử nghiệm các loại biểu đồ khác — cột, đường, hoặc vòng donut — để làm phong phú hơn các slide của bạn. Tiếp theo, khám phá khả năng xuất của API để tự động tạo báo cáo PDF hoặc hình ảnh PNG.

## Câu hỏi thường gặp

**Q: Làm thế nào để thêm nhiều biểu đồ vào một slide duy nhất?**  
A: Gọi `slide.getShapes().addChart()` cho mỗi biểu đồ, cung cấp tọa độ và kích thước riêng cho mỗi thể hiện.

**Q: Một số lựa chọn thay thế cho Aspose.Slides cho Java là gì?**  
A: Apache POI và JFreeChart là các lựa chọn phổ biến, nhưng chúng thiếu các tùy chọn xuất toàn diện và mô hình cấp phép của Aspose.

**Q: Tôi có thể chuyển đổi bài thuyết trình sang các định dạng khác bằng Aspose.Slides không?**  
A: Có — xuất ra PDF, XPS, HTML, PNG, JPEG, SVG và nhiều định dạng khác chỉ bằng một lời gọi `save`.

**Q: Làm sao quản lý giấy phép cho một đội phát triển lớn?**  
A: Mua giấy phép doanh nghiệp bao phủ nhiều nhà phát triển và máy chủ; liên hệ bộ phận bán hàng của Aspose để được giảm giá theo khối lượng.

**Q: Nếu dữ liệu biểu đồ của tôi thường xuyên cập nhật thì sao?**  
A: Tích hợp Aspose.Slides với nguồn dữ liệu (ví dụ, truy vấn SQL) và xây dựng lại biểu đồ tại thời gian chạy; API hỗ trợ ràng buộc dữ liệu động.

## Tài nguyên
- **Tài liệu:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **Tải xuống:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Mua:** [Buy a License](https://purchase.aspose.com/buy)
- **Dùng thử miễn phí:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Giấy phép tạm thời:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Hỗ trợ:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Cập nhật lần cuối:** 2026-08-01  
**Kiểm tra với:** Aspose.Slides for Java 25.4  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách Thêm và Cấu hình Biểu đồ trong Bài Thuyết Trình Sử Dụng Aspose.Slides cho Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Tạo và Tùy chỉnh Biểu đồ trong Bài Thuyết Trình Java Sử Dụng Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Cách Tạo và Cấu hình Bài Thuyết Trình với Aspose.Slides Java: Hướng Dẫn Từng Bước](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}