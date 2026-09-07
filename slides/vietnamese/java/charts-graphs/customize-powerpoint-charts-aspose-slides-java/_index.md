---
date: '2026-09-07'
description: Tìm hiểu cách thêm custom lines vào biểu đồ Aspose Slides bằng Java.
  Hướng dẫn step‑by‑step nâng cao biểu đồ PowerPoint để clearer data visualization.
keywords:
- aspose slides chart
- customize PowerPoint charts
- add custom lines to charts Java
lastmod: '2026-09-07'
og_description: Tìm hiểu cách thêm custom lines vào biểu đồ Aspose Slides bằng Java.
  Hướng dẫn step‑by‑step nâng cao biểu đồ PowerPoint để clearer data visualization.
og_image_alt: Developer guide showing custom line addition to an Aspose Slides chart
  in Java
og_title: Cách thêm custom lines vào biểu đồ Aspose Slides trong Java
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  headline: How to add custom lines to an Aspose Slides chart in Java
  type: TechArticle
- description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  name: How to add custom lines to an Aspose Slides chart in Java
  steps:
  - name: create a presentation object
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a single PowerPoint file in memory.
  - name: add a clustered column chart
    text: Insert a clustered column chart on the first slide at coordinates (100,
      100) with a width of 500 px and a height of 400 px.
  - name: add an auto‑shape line to the chart
    text: Add a line shape to the chart’s `userShapes` collection, which stores custom
      drawing objects. `userShapes` is a collection that holds custom shapes drawn
      directly on a chart, allowing you to overlay lines, arrows, or other annotations.
  - name: customize line properties
    text: Set the line’s fill type to solid, change its color to red, and optionally
      adjust thickness or dash style.
  - name: save the presentation
    text: Persist the modified presentation to disk.
  type: HowTo
- questions:
  - answer: '`Presentation` represents a PowerPoint file in memory.'
    question: What is the main class for creating a presentation?
  - answer: '`slide.getShapes().addChart(...)` creates a chart object.'
    question: Which method adds a chart to a slide?
  - answer: Use `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.
    question: How do you draw a line on a chart?
  - answer: Yes—set the line’s fill to a solid red `Color.RED`.
    question: Can I set the line color to red?
  - answer: A full license removes evaluation limits; a trial works for testing.
    question: Do I need a license for production use?
  type: FAQPage
tags:
- aspose slides
- chart customization
- java presentation
title: Cách thêm custom lines vào biểu đồ Aspose Slides trong Java
url: /vi/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm các đường tùy chỉnh vào biểu đồ Aspose Slides trong Java

## Giới thiệu

Trong tutorial này, bạn sẽ khám phá cách thêm các đường tùy chỉnh vào một **aspose slides chart** bằng Java. Các đường tùy chỉnh giúp bạn làm nổi bật các ngưỡng, xu hướng hoặc các điểm dữ liệu quan trọng, biến một biểu đồ đơn giản thành một câu chuyện trực quan mạnh mẽ. Khi kết thúc hướng dẫn, bạn sẽ có thể tích hợp Aspose.Slides vào dự án của mình, vẽ các đường trên biểu đồ và tinh chỉnh giao diện của chúng để đạt hiệu quả tối đa.

**Bạn sẽ học được**
- Cách cài đặt và cấp phép Aspose.Slides cho Java
- Các bước chính xác để vẽ một đường tùy chỉnh trên biểu đồ
- Các cách để tạo kiểu cho đường (màu, độ dày, kiểu gạch)
- Các kịch bản thực tế nơi các đường tùy chỉnh cải thiện việc truyền đạt dữ liệu

## Câu trả lời nhanh
- **Lớp chính để tạo một bản trình chiếu là gì?** `Presentation` đại diện cho một tệp PowerPoint trong bộ nhớ.  
- **Phương thức nào thêm biểu đồ vào một slide?** `slide.getShapes().addChart(...)` tạo một đối tượng biểu đồ.  
- **Làm thế nào để vẽ một đường trên biểu đồ?** Sử dụng `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.  
- **Có thể đặt màu đường thành màu đỏ không?** Có — đặt màu nền của đường thành màu đỏ đặc `Color.RED`.  
- **Có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Giấy phép đầy đủ loại bỏ các giới hạn đánh giá; bản dùng thử hoạt động cho việc thử nghiệm.  

`ShapeType.Line` là một giá trị enum cho biết Aspose.Slides tạo một auto‑shape dạng đường.

## Biểu đồ Aspose Slides là gì?

Một **Aspose Slides chart** là một đối tượng biểu đồ có thể lập trình, tồn tại bên trong một slide PowerPoint, cho phép bạn tạo, chỉnh sửa và tạo kiểu cho các biểu đồ hoàn toàn bằng mã Java. Nó hỗ trợ nhiều loại biểu đồ (cột, thanh, đường, tròn, v.v.), cung cấp quyền kiểm soát đầy đủ đối với các series, trục, chú giải, và có thể kết hợp với các yếu tố slide khác như hình ảnh và hình dạng tùy chỉnh, làm cho nó phù hợp cho báo cáo tự động và các bài thuyết trình động.

## Tại sao nên thêm các đường tùy chỉnh vào biểu đồ Aspose Slides?

Các đường tùy chỉnh cho phép bạn chú thích biểu đồ bằng các dấu hiệu trực quan chính xác. Aspose.Slides hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý các bản trình chiếu với **hàng trăm slide** trong khi sử dụng ít hơn **150 MB RAM** trên một máy phát triển tiêu chuẩn, làm cho nó trở nên lý tưởng cho báo cáo quy mô lớn.

## Yêu cầu trước

- **Aspose.Slides for Java** – phiên bản 25.4 (hoặc mới hơn)  
- **JDK 16+** – bất kỳ môi trường chạy Java mới nào  
- IDE như IntelliJ IDEA hoặc Eclipse  
- Kiến thức cơ bản về Java và hiểu biết về các khái niệm PowerPoint  

### Thư viện cần thiết
- Aspose.Slides for Java (Phiên bản 25.4)

### Cấu hình môi trường
- Cài đặt JDK 16 hoặc mới hơn  
- Sử dụng Maven hoặc Gradle để quản lý các phụ thuộc (các ví dụ dưới đây)  

## Cài đặt Aspose.Slides cho Java

Thêm thư viện vào dự án của bạn bằng một trong các công cụ xây dựng sau.

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

Để tải xuống thủ công, truy cập [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) để lấy gói mới nhất.

### Nhận giấy phép
- **Free trial:** bắt đầu thử nghiệm mà không cần mua.  
- **Temporary license:** sử dụng để đánh giá mở rộng mà không có watermark.  
- **Full license:** mở khóa tất cả tính năng cho các công việc sản xuất.  

Khởi tạo giấy phép trong mã của bạn như sau:
```java
License license = new License();
license.setLicense("path_to_license.lic");
```  

`License` là lớp dùng để tải và áp dụng tệp giấy phép Aspose.Slides của bạn vào ứng dụng.

## Làm thế nào để thêm các đường tùy chỉnh vào biểu đồ Aspose Slides?

Load hoặc tạo một bản trình chiếu, chèn một biểu đồ, sau đó thêm một hình dạng đường vào bộ sưu tập user‑shapes của biểu đồ. Đường có thể được định vị, thay đổi kích thước và tạo kiểu để phù hợp với nhu cầu báo cáo của bạn. Cách tiếp cận này hoạt động cho các biểu đồ cột nhóm, thanh, đường và khu vực.

## Hướng dẫn triển khai

### Thêm các đường tùy chỉnh vào biểu đồ

#### Tổng quan
Các đường tùy chỉnh thu hút sự chú ý đến các giá trị cụ thể — chẳng hạn như giới hạn ngân sách hoặc đường mục tiêu — làm cho biểu đồ của bạn trở nên sâu sắc hơn.

#### Bước 1: tạo đối tượng presentation
Lớp `Presentation` là đối tượng cấp cao nhất của Aspose.Slides, đại diện cho một tệp PowerPoint duy nhất trong bộ nhớ.  
```java
Presentation pres = new Presentation();
```  

#### Bước 2: thêm biểu đồ cột nhóm
Chèn một biểu đồ cột nhóm vào slide đầu tiên tại tọa độ (100, 100) với chiều rộng 500 px và chiều cao 400 px.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 400);
```  

#### Bước 3: thêm một auto‑shape dạng đường vào biểu đồ
Thêm một hình dạng đường vào bộ sưu tập `userShapes` của biểu đồ, nơi lưu trữ các đối tượng vẽ tùy chỉnh.  
```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(
    ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```  

`userShapes` là một bộ sưu tập chứa các hình dạng tùy chỉnh được vẽ trực tiếp trên biểu đồ, cho phép bạn phủ lên các đường, mũi tên hoặc các chú thích khác.

#### Bước 4: tùy chỉnh thuộc tính đường
Đặt kiểu nền của đường thành dạng đặc, thay đổi màu thành đỏ, và tùy chọn điều chỉnh độ dày hoặc kiểu gạch.  
```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```  

#### Bước 5: lưu bản trình chiếu
Lưu bản trình chiếu đã chỉnh sửa vào đĩa.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/" + "AddCustomLines.pptx", SaveFormat.Pptx);
```  

### Làm việc với lớp Presentation
Lớp `Presentation` cung cấp các phương thức để tải, tạo và lưu các tệp PowerPoint, cũng như truy cập các slide và hình dạng riêng lẻ.

### Mẹo khắc phục sự cố
- Xác minh rằng đường dẫn tệp được sử dụng trong `save` có thể ghi được; sử dụng đường dẫn tuyệt đối để đảm bảo độ tin cậy.  
- Nếu biểu đồ không hiển thị, kiểm tra lại tọa độ X/Y và đảm bảo chỉ số slide là chính xác.  

## Ứng dụng thực tiễn

Các đường tùy chỉnh đặc biệt hữu ích trong:
1. **Báo cáo tài chính** – làm nổi bật giới hạn ngân sách hoặc mục tiêu lợi nhuận.  
2. **Bảng điều khiển bán hàng** – vẽ một đường cho mục tiêu doanh số quý.  
3. **Phân tích y tế** – đánh dấu các ngưỡng quan trọng trong xu hướng dấu hiệu sinh tồn của bệnh nhân.  

Bạn cũng có thể tự động đặt vị trí đường bằng cách lấy giá trị ngưỡng từ cơ sở dữ liệu hoặc API, cho phép báo cáo thời gian thực.

## Các cân nhắc về hiệu năng

- Giải phóng các đối tượng `Presentation` bằng `presentation.dispose()` khi hoàn thành để giải phóng bộ nhớ gốc.  
- Sử dụng độ phân giải ảnh và biểu đồ vừa phải (ví dụ, 150 dpi) để giữ kích thước tệp trong tầm kiểm soát.  
- Trong quá trình phát triển, giấy phép tạm thời tránh các watermark đánh giá đồng thời vẫn cung cấp quyền truy cập đầy đủ API.  

## Kết luận

Bây giờ bạn đã biết cách thêm các đường tùy chỉnh vào một **aspose slides chart** trong Java, cho phép bạn kiểm soát hoàn toàn việc chú thích biểu đồ và nhấn mạnh trực quan. Hãy thử nghiệm với các kiểu đường, vị trí và loại biểu đồ khác nhau để tạo ra các báo cáo truyền tải dữ liệu ngay lập tức.

## Phần Câu hỏi thường gặp

**Q1: Tôi có thể thay đổi màu của các đường tùy chỉnh không?**  
A1: Có, tùy chỉnh màu đường bằng cách đặt thuộc tính `SolidFillColor` thành bất kỳ `java.awt.Color` nào mong muốn.

**Q2: Aspose.Slides có tương thích với mọi IDE Java không?**  
A2: Có, miễn là IDE của bạn hỗ trợ Maven hoặc Gradle, bạn có thể tích hợp Aspose.Slides mà không gặp vấn đề.

**Q3: Những loại biểu đồ nào được hỗ trợ để thêm các đường tùy chỉnh?**  
A3: Các đường tùy chỉnh có thể được thêm vào biểu đồ cột nhóm, thanh, đường, khu vực và tròn, cùng các loại khác.

**Q4: Làm thế nào để khắc phục sự cố khi lưu bản trình chiếu?**  
A4: Đảm bảo thư mục đầu ra tồn tại, đường dẫn tệp đúng và ứng dụng có quyền ghi.

**Q5: Có bất kỳ hạn chế nào khi sử dụng giấy phép dùng thử không?**  
A5: Bản dùng thử có thể thêm watermark và giới hạn một số tính năng cao cấp; giấy phép tạm thời hoặc đầy đủ sẽ loại bỏ các ràng buộc này.

## Tài nguyên
- **Tài liệu**: [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)  
- **Tải xuống**: [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)  
- **Mua**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Dùng thử miễn phí**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **Giấy phép tạm thời**: [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Hỗ trợ**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Cập nhật lần cuối:** 2026-09-07  
**Kiểm tra với:** Aspose.Slides for Java 25.4  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo và Tùy chỉnh Đường xu hướng cho Biểu đồ Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)
- [Cách chỉnh sửa dữ liệu biểu đồ PowerPoint bằng Aspose.Slides cho Java: Hướng dẫn toàn diện](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Cách xoay tiêu đề trục biểu đồ trong PowerPoint bằng Aspose.Slides cho Java: Hướng dẫn từng bước](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}