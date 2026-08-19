---
date: '2026-07-17'
description: Tìm hiểu cách thêm chart vào PowerPoint bằng cách tạo Pie of Pie chart
  sử dụng Aspose.Slides for Java. Bao gồm setup, code, customization và saving dưới
  dạng PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Thêm chart vào PowerPoint với Aspose.Slides for Java. Hướng dẫn này
  chỉ ra cách tạo, customize và save Pie of Pie chart dưới dạng PPTX trong vài phút.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Thêm Chart vào PowerPoint – Tạo Pie of Pie Chart trong Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Thêm Chart vào PowerPoint – Tạo Pie of Pie Chart trong Java với Aspose.Slides
url: /vi/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thêm Biểu Đồ vào PowerPoint – Tạo Biểu Đồ Pie of Pie trong Java với Aspose.Slides

## Biểu Đồ & Đồ Thị

### Giới Thiệu

Trong các bài thuyết trình dựa trên dữ liệu hiện đại, **thêm biểu đồ vào PowerPoint** thường là cách nhanh nhất để biến các con số thô thành cái nhìn trực quan. Một biểu đồ tròn thông thường hoạt động tốt cho một vài danh mục, nhưng khi một số lát bánh quá nhỏ chúng trở nên khó đọc. Biểu đồ *Pie of Pie* giải quyết vấn đề này bằng cách tách các lát bánh nhỏ ra thành một biểu đồ tròn phụ, giữ cho biểu đồ chính sạch sẽ và chi tiết dễ tiếp cận.

Trong tutorial này, bạn sẽ học cách **thêm biểu đồ vào PowerPoint** bằng cách tạo một biểu đồ Pie of Pie với Aspose.Slides cho Java. Chúng tôi sẽ hướng dẫn cài đặt môi trường, tạo biểu đồ, tùy chỉnh nhãn, điều chỉnh vị trí tách, và cuối cùng lưu bản trình chiếu dưới dạng tệp PPTX. Khi hoàn thành, bạn sẽ sẵn sàng nhúng các biểu đồ tinh vi vào bất kỳ bộ slide nào.

## Câu Trả Lời Nhanh
Trong Aspose.Slides, `Presentation` đại diện cho một tệp PPTX, `ChartType.PieOfPie` chọn biểu đồ Pie of Pie, `setShowValue(true)` hiển thị giá trị trên nhãn, và `save` ghi tệp.

- **Lớp chính để thao tác PowerPoint là gì?** `Presentation` – nó đại diện cho toàn bộ tệp PPTX trong bộ nhớ.  
- **Loại biểu đồ nào tạo một biểu đồ tròn phụ cho các lát bánh nhỏ?** `ChartType.PieOfPie`.  
- **Làm thế nào để hiển thị giá trị trên mỗi lát bánh?** Đặt `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Bạn có thể lưu tệp trực tiếp dưới dạng PPTX không?** Có – gọi `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Bạn có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí 30 ngày đủ cho việc thử nghiệm; giấy phép vĩnh viễn sẽ loại bỏ watermark đánh giá.

## Biểu Đồ Pie of Pie là gì?
**Biểu Đồ Pie of Pie** là một dạng biểu đồ tròn hai cấp mà tách một hoặc nhiều lát bánh nhỏ vào một biểu đồ tròn riêng, giúp chúng dễ đọc hơn. Aspose.Slides hỗ trợ loại biểu đồ này ngay từ đầu, cho phép bạn kiểm soát kích thước tách, vị trí và định dạng nhãn.

## Tại sao thêm biểu đồ vào PowerPoint với Aspose.Slides?
Aspose.Slides có thể tạo, chỉnh sửa và render các tệp PowerPoint mà không cần cài đặt Microsoft Office. Nó hỗ trợ **hơn 50 định dạng nhập và xuất**, xử lý các bản trình chiếu **lên tới 500 slide** trong vòng chưa đầy một giây trên phần cứng máy chủ tiêu chuẩn, và cung cấp **điều khiển API đầy đủ** cho việc định dạng biểu đồ, nhãn dữ liệu và bố cục—lý tưởng cho các quy trình báo cáo tự động.

## Yêu Cầu Trước

- **Java Development Kit (JDK) 16+** đã được cài đặt.  
- Một IDE như **IntelliJ IDEA**, **Eclipse**, hoặc **NetBeans**.  
- Maven hoặc Gradle để quản lý phụ thuộc (xem các phần bên dưới).  
- Kiến thức cơ bản về Java và quen thuộc với việc xây dựng dự án.

## Cài Đặt Aspose.Slides cho Java

### Thông Tin Cài Đặt

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

**Direct Download:** Bạn có thể tải xuống phiên bản mới nhất từ [bản phát hành Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).

### Các Bước Nhận Giấy Phép
- **Free Trial:** Bắt đầu với bản dùng thử 30 ngày để khám phá mọi tính năng.  
- **Temporary License:** Yêu cầu một khóa tạm thời để kéo dài thời gian đánh giá.  
- **Purchase:** Mua giấy phép vĩnh viễn để sử dụng trong môi trường sản xuất và loại bỏ watermark đánh giá.

### Khởi Tạo và Cấu Hình Cơ Bản
`Presentation` là đối tượng chính để tạo tệp PowerPoint, và `Chart` đại diện cho một hình dạng biểu đồ trong slide.

```java
Presentation presentation = new Presentation();
```  

Điều này tạo ra một bản trình chiếu trống sẵn sàng cho các slide và biểu đồ.

## Hướng Dẫn Thực Hiện

### Làm thế nào để thêm biểu đồ vào PowerPoint bằng Aspose.Slides cho Java?
Tải một `Presentation` mới, thêm một slide, và chèn một `Chart` loại `PieOfPie`. Chuỗi lệnh API ngắn gọn: tạo biểu đồ, điền dữ liệu cho series, điều chỉnh hiển thị nhãn, cấu hình kích thước biểu đồ tròn phụ, và cuối cùng lưu. Toàn bộ quy trình thường chỉ dưới 20 dòng code, rất thích hợp cho việc tạo báo cáo tự động.

### Tạo Biểu Đồ 'Pie of Pie'

#### Tổng Quan
Chúng ta sẽ xây dựng một biểu đồ Pie of Pie trên slide đầu tiên, tách các lát bánh nhỏ nhất, và gắn nhãn giá trị cho mỗi phần.

#### Bước 1: Tạo một Instance của Lớp Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Điều này khởi tạo container cho tất cả các slide và biểu đồ tiếp theo.

#### Bước 2: Thêm Biểu Đồ 'Pie of Pie' trên Slide Đầu Tiên
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Ở đây chúng ta chỉ định `ChartType.PieOfPie` và định nghĩa vị trí (X, Y) và kích thước (width, height) của biểu đồ trên canvas slide.

#### Bước 3: Đặt Nhãn Dữ Liệu để Hiển Thị Giá Trị cho Series
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Kích hoạt `showValue` khiến mỗi lát bánh hiển thị giá trị số, rất cần thiết cho việc diễn giải nhanh dữ liệu.

#### Bước 4: Cấu Hình Kích Thước Pie Thứ Hai và Tách Theo Phần Trăm
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Các tùy chọn này cho phép bạn quyết định bao nhiêu phần của biểu đồ được phân bổ cho pie phụ và các lát bánh nào sẽ được di chuyển dựa trên ngưỡng phần trăm.

#### Bước 5: Lưu Bản Trình Chiếu vào Đĩa ở Định Dạng PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** Sử dụng đường dẫn tuyệt đối hoặc `Paths.get()` của Java để tránh các ký tự phân tách đặc thù của nền tảng.

## Các Vấn Đề Thường Gặp và Giải Pháp

Lớp `License` tải tệp giấy phép để loại bỏ các hạn chế đánh giá.

- **Missing license warning:** Nếu bạn thấy “Evaluation Only” trên biểu đồ, hãy chắc chắn rằng bạn đã áp dụng tệp giấy phép hợp lệ bằng `License license = new License(); license.setLicense("Aspose.Slides.lic");`.  
- **Incorrect slice split:** Kiểm tra thuộc tính `splitBy` đã được đặt thành `SplitBy.Percentage` và `secondPieSize` có giá trị từ 0 đến 100.  
- **Data not displaying:** Xác nhận rằng series của biểu đồ chứa ít nhất một điểm dữ liệu; nếu không biểu đồ sẽ hiển thị trống.

## Câu Hỏi Thường Gặp

`IChart` đại diện cho một đối tượng biểu đồ có thể được thêm vào slide.

**Q: Tôi có thể tạo nhiều biểu đồ trong một bản trình chiếu không?**  
A: Có, khởi tạo một `IChart` mới cho mỗi slide hoặc vị trí; API cho phép không giới hạn số đối tượng biểu đồ trong mỗi tệp.

`SaveFormat.Pdf` chỉ định định dạng xuất PDF cho việc lưu.

**Q: Aspose.Slides có hỗ trợ lưu dưới dạng PDF không?**  
A: Chắc chắn – gọi `presentation.save("output.pdf", SaveFormat.Pdf)` để xuất cùng một bộ slide sang PDF.

`IPortion` đại diện cho một lát bánh riêng lẻ của biểu đồ tròn.

**Q: Số điểm dữ liệu tối đa mà một biểu đồ Pie of Pie có thể xử lý là bao nhiêu?**  
A: Thư viện hỗ trợ tới **10.000** điểm dữ liệu cho mỗi series, chỉ bị giới hạn bởi bộ nhớ khả dụng.

**Q: Có thể tùy chỉnh màu sắc cho từng lát bánh không?**  
A: Có, truy cập mỗi `IPortion` qua `chart.getChartData().getSeries().get_Item(0).getPortions()` và đặt `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: Làm sao để nhúng PPTX đã tạo vào một ứng dụng web?**  
A: Sau khi lưu tệp, truyền trực tiếp nó tới client bằng `HttpServletResponse` với `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Kết Luận

Bạn giờ đã có một công thức hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **thêm biểu đồ vào PowerPoint** bằng cách tạo biểu đồ Pie of Pie với Aspose.Slides cho Java. Hãy thử nghiệm các ngưỡng tách khác nhau, định dạng nhãn và bảng màu để phù hợp với hướng dẫn thương hiệu của bạn. Tiếp theo, khám phá các loại biểu đồ khác—như cột chồng hoặc radar—để làm phong phú hơn bộ slide tự động của bạn.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Các Hướng Dẫn Liên Quan

- [Create Dynamic Chart Java – PowerPoint Charts Tutorials for Aspose.Slides](/slides/java/charts-graphs/)
- [How to add pie chart PowerPoint with Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑by‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}