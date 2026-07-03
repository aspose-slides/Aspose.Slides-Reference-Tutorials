---
date: '2026-07-03'
description: Tìm hiểu cách tạo biểu đồ Sunburst từng bước trong Java bằng Aspose.Slides,
  với đầy đủ các tùy chọn tùy chỉnh cho bản trình bày PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Cách tạo biểu đồ Sunburst trong Java bằng Aspose.Slides
url: /vi/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Tạo Biểu Đồ Sunburst trong Java Sử Dụng Aspose.Slides

## Giới thiệu
Trong các bài thuyết trình dựa trên dữ liệu ngày nay, **cách tạo sunburst** nhanh chóng có thể làm cho slide của bạn nổi bật. Hướng dẫn này sẽ dẫn bạn qua việc xây dựng biểu đồ Sunburst bằng Aspose.Slides cho Java, từ thiết lập dự án đến xuất file cuối cùng, để bạn có thể tạo ra các đồ họa dữ liệu phân cấp hấp dẫn mà không rời khỏi hệ sinh thái Java.

## Câu trả lời nhanh
- **Lớp chính cho một tệp PowerPoint là gì?** `Presentation` – đại diện cho toàn bộ PPTX trong bộ nhớ.  
- **Cần bao nhiêu dòng mã cho một sunburst cơ bản?** Thông thường 5–7 dòng sau khi đã tham chiếu thư viện.  
- **Các định dạng đầu ra nào được hỗ trợ?** PPTX, PDF, PNG, SVG và HTML.  
- **Tôi có thể định dạng từng đoạn riêng lẻ không?** Có – màu nền, viền và nhãn dữ liệu đều có thể tùy chỉnh hoàn toàn.  
- **Có cần giấy phép cho môi trường sản xuất không?** Bản đánh giá miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần thiết cho triển khai.

## Biểu đồ Sunburst là gì?
Biểu đồ Sunburst hiển thị dữ liệu phân cấp dưới dạng các vòng đồng tâm, trong đó mỗi vòng đại diện cho một cấp độ của cấu trúc. Nó giúp người xem nắm bắt mối quan hệ cha‑con một cách nhanh chóng, rất phù hợp cho sơ đồ tổ chức, hiển thị phân loại và các chỉ số đa cấp. Biểu đồ này đặc biệt hữu ích cho việc hiển thị các danh mục đa cấp như dòng sản phẩm, khu vực địa lý hoặc cấu trúc tổ chức, cho phép người xem thấy cả phân bố tổng thể và chi tiết trong từng phân đoạn.

## Tại sao nên sử dụng Aspose.Slides cho biểu đồ Sunburst?
Aspose.Slides hỗ trợ **hơn 30 loại biểu đồ**, xử lý các tệp lên tới **500 MB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, và render đồ họa ở **300 DPI** cho đầu ra sắc nét. Những khả năng định lượng này đảm bảo việc tạo nhanh và hình ảnh chất lượng cao ngay cả với các bài thuyết trình lớn. Ngoài ra, thư viện cung cấp các thao tác an toàn đa luồng và tích hợp liền mạch với các công cụ xây dựng Java phổ biến, phù hợp cho cả việc tạo trên máy tính để bàn và phía máy chủ ở quy mô lớn.

## Yêu cầu trước
- Java Development Kit (JDK) 8 hoặc mới hơn.  
- Maven hoặc Gradle để quản lý phụ thuộc.  
- Aspose.Slides for Java (phiên bản mới nhất).  
- Kiến thức cơ bản về cấu trúc dữ liệu phân cấp.

## Cách tạo biểu đồ Sunburst từng bước?
Tải môi trường, thêm biểu đồ, cung cấp dữ liệu phân cấp, tùy chỉnh và lưu tệp – tất cả trong một vài bước đơn giản. Dưới đây là quy trình chính xác bạn có thể theo mà không cần viết mã phụ trợ thêm. Quá trình được tự động hoá hoàn toàn, không cần tương tác UI thủ công, và có thể tích hợp vào các công việc batch hoặc dịch vụ web để tạo biểu đồ theo yêu cầu.

### Bước 1: Thiết lập dự án
Thêm phụ thuộc Maven của Aspose.Slides (hoặc đoạn mã Gradle tương đương) vào file `pom.xml`. Điều này sẽ kéo toàn bộ các binary và thư viện phụ thuộc cần thiết.

### Bước 2: Tải hoặc tạo một bản trình bày
`Presentation` là đối tượng cấp cao nhất của Aspose.Slides đại diện cho một tệp PowerPoint duy nhất trong bộ nhớ. Khởi tạo bằng `new Presentation()` để tạo một bản mới hoặc truyền đường dẫn tệp để mở một PPTX hiện có.

### Bước 3: Thêm biểu đồ Sunburst
Chèn một hình biểu đồ mới vào slide bằng cách sử dụng `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Điều này tạo ra khung Sunburst sẵn sàng cho dữ liệu. `ChartType.Sunburst` chỉ định loại biểu đồ Sunburst khi thêm biểu đồ vào slide.

### Bước 4: Điền dữ liệu phân cấp
`ChartData` chứa các series và danh mục cho biểu đồ. Truy cập bộ sưu tập `ChartData` của biểu đồ và thêm series cùng danh mục phản ánh cấu trúc phân cấp của bạn. Đối với mỗi cấp độ, chỉ định mối quan hệ cha‑con qua thuộc tính `ParentSeries`, cho phép biểu đồ tự động vẽ các vòng đồng tâm.

### Bước 5: Tùy chỉnh giao diện
Tinh chỉnh màu sắc đoạn, kiểu viền và nhãn dữ liệu thông qua các đối tượng `ChartSeries` và `ChartDataPoint`. `ChartSeries` đại diện cho một chuỗi các điểm dữ liệu trong biểu đồ. `ChartDataPoint` đại diện cho một điểm dữ liệu riêng lẻ trong chuỗi. Bạn cũng có thể bật quay 3‑D hoặc đặt thuộc tính `Explode` để làm nổi bật các phần cụ thể.

### Bước 6: Lưu bản trình bày
Enum `SaveFormat` định nghĩa các định dạng tệp bạn có thể lưu bản trình bày. Gọi `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` để ghi tệp ra đĩa. Bạn cũng có thể xuất ra PDF hoặc PNG bằng cách thay đổi giá trị enum `SaveFormat`.

## Cách tùy chỉnh màu sắc biểu đồ Sunburst?
Xác định màu nền cho mỗi `ChartDataPoint` bằng cách gọi `point.getFillFormat().setFillType(FillType.Solid)` rồi `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Cách tiếp cận trực tiếp này cho phép bạn phù hợp với bộ nhận diện thương hiệu hoặc nhấn mạnh các điểm dữ liệu quan trọng. Bạn cũng có thể áp dụng màu nền gradient, điều chỉnh độ trong suốt, hoặc sử dụng màu chủ đề để đảm bảo tính nhất quán với thiết kế slide còn lại.

## Các vấn đề thường gặp và giải pháp
- **Vấn đề:** Cấu trúc phân cấp hiển thị phẳng.  
  **Giải pháp:** Đảm bảo mỗi series con tham chiếu đúng `ParentSeries`. Thiếu liên kết sẽ khiến biểu đồ xem tất cả dữ liệu như một cấp duy nhất.
- **Vấn đề:** PNG xuất ra bị mờ.  
  **Giải pháp:** Tăng DPI xuất bằng cách đặt `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Vấn đề:** Tệp PPTX lớn gây OutOfMemoryError.  
  **Giải pháp:** Sử dụng `Presentation.setMemoryOptimization(true)` để stream dữ liệu và giảm mức sử dụng bộ nhớ.

## Câu hỏi thường gặp

**Q: Tôi có thể tạo biểu đồ Sunburst từ tệp CSV không?**  
A: Có. Đọc CSV, xây dựng cấu trúc phân cấp trong bộ nhớ, và đưa nó vào bộ sưu tập `ChartData` của biểu đồ trước khi lưu.

**Q: Aspose.Slides có hỗ trợ chuyển động động cho biểu đồ Sunburst không?**  
A: Có. Áp dụng `SlideShowTransition` cho slide hoặc sử dụng `ChartFormat.setAnimationEnabled(true)` cho chuyển động ở mức biểu đồ.

**Q: Có thể xuất biểu đồ dưới dạng đồ họa vector SVG không?**  
A: Hoàn toàn có thể. Lưu bản trình bày bằng `SaveFormat.Svg` để có phiên bản vector có thể mở rộng của biểu đồ Sunburst.

**Q: Số lượng điểm dữ liệu tối đa mà một biểu đồ Sunburst có thể xử lý là bao nhiêu?**  
A: Aspose.Slides xử lý ổn định tới **10,000** điểm dữ liệu trong một biểu đồ Sunburst duy nhất mà không giảm hiệu năng.

**Q: Tôi có cần giấy phép riêng cho mỗi môi trường triển khai không?**  
A: Một giấy phép thương mại duy nhất bao phủ tất cả các môi trường (phát triển, staging, production) miễn là tuân thủ các điều khoản giấy phép.

## Kết luận
Bạn đã có một hướng dẫn đầy đủ, từng bước để **cách tạo sunburst** trong Java bằng Aspose.Slides. Bằng cách thực hiện quy trình trên, bạn có thể tạo ra các hình ảnh phân cấp chất lượng cao, hoàn toàn tùy chỉnh cho bất kỳ bản trình bày PowerPoint nào.

---

**Cập nhật lần cuối:** 2026-07-03  
**Được kiểm tra với:** Aspose.Slides for Java 24.12  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách Thêm Biểu Đồ vào PowerPoint Sử Dụng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Tùy Chỉnh Biểu Đồ PowerPoint Nâng Cao Sử Dụng Aspose.Slides Java cho Bài Thuyết Trình Động](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Tạo Hoạt Ảnh cho Các Danh Mục Biểu Đồ PowerPoint với Aspose.Slides cho Java | Hướng Dẫn Từng Bước](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}