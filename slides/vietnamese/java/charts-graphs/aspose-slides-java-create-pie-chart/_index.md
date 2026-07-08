---
date: '2026-07-08'
description: Tìm hiểu cách thêm pie chart PowerPoint vào các bản trình chiếu bằng
  Aspose.Slides for Java. Hãy làm theo hướng dẫn từng bước này để tạo và tùy chỉnh
  các pie chart chuyên nghiệp.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Thêm pie chart PowerPoint bằng Aspose.Slides for Java. Hướng dẫn này
  chỉ cách tạo và tùy chỉnh pie chart một cách lập trình, lý tưởng cho các báo cáo
  tự động.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Thêm Pie Chart PowerPoint với Aspose.Slides for Java – Hướng dẫn nhanh
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Cách thêm pie chart PowerPoint với Aspose.Slides for Java
url: /vi/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thêm biểu đồ tròn PowerPoint với Aspose.Slides cho Java

## Giới thiệu

Nếu bạn cần **thêm biểu đồ tròn PowerPoint** mà không phải mở PowerPoint thủ công, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách thiết lập Aspose.Slides cho Java, tạo biểu đồ tròn và tùy chỉnh từng lát—hoàn hảo cho báo cáo tự động, bảng điều khiển hoặc bài thuyết trình cá nhân hoá. Khi kết thúc, bạn sẽ có một đoạn mã Java có thể tái sử dụng để tạo tệp PowerPoint biểu đồ tròn chuyên nghiệp trong vài giây.

### Câu trả lời nhanh
- **Thư viện nào tạo biểu đồ?** Aspose.Slides cho Java (phiên bản mới nhất).  
- **Tôi có thể chạy mà không có giao diện không?** Có—không cần cài đặt Office.  
- **Phiên bản Java nào tối ưu?** JDK 16+ để có hiệu năng tốt nhất và cải tiến GC.  
- **Làm sao để tách một lát?** Gọi `setExplosion` trên `IDataPoint` và đặt độ lệch tính bằng pixel.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Bản dùng thử hoạt động cho phát triển; giấy phép vĩnh viễn loại bỏ mọi giới hạn đánh giá.

## Tại sao thêm biểu đồ tròn PowerPoint bằng Aspose.Slides cho Java?

Bạn có thể tạo các báo cáo hình ảnh cập nhật trực tiếp từ các dịch vụ back‑end của mình, loại bỏ lỗi sao chép‑dán thủ công và đảm bảo phong cách nhất quán với thương hiệu. Aspose.Slides hỗ trợ **hơn 70 loại biểu đồ** và có thể xử lý các bài thuyết trình với **hơn 10.000 slide** mà không cần tải toàn bộ tệp vào bộ nhớ, làm cho nó trở thành lựa chọn lý tưởng cho tự động hoá quy mô lớn.

## Yêu cầu trước

- **Aspose.Slides cho Java** – hướng dẫn tham chiếu phiên bản 25.4 (phiên bản mới nhất tại thời điểm viết).  
- **Bộ công cụ phát triển Java** – JDK 16 hoặc mới hơn được khuyến nghị.  
- **Maven** hoặc **Gradle** để quản lý phụ thuộc.  

## Cài đặt Aspose.Slides cho Java

### Maven
Thêm phụ thuộc này vào tệp `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Bao gồm các dòng sau trong tệp `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Hoặc, tải phiên bản mới nhất trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Cấp phép
Để sử dụng Aspose.Slides không bị giới hạn:

- Bắt đầu với **bản dùng thử miễn phí** để đánh giá API.  
- Yêu cầu **giấy phép tạm thời** để thử nghiệm kéo dài tại trang [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Mua gói đăng ký đầy đủ qua [Purchase page](https://purchase.aspose.com/buy).

## Cách thêm biểu đồ tròn PowerPoint bằng Aspose.Slides cho Java

Tải một bản thuyết trình mới, chèn biểu đồ tròn và lưu tệp—tất cả trong ba bước ngắn gọn. Mẫu này hoạt động với bất kỳ bộ dữ liệu nào và có thể được đặt trong vòng lặp để tự động tạo hàng chục slide. Cách tiếp cận này nhẹ, chỉ cần vài dòng mã và không cần tài nguyên bên ngoài, phù hợp cho cả tiện ích nhỏ và công việc batch lớn.

### Bước 1: Khởi tạo Presentation
Lớp `Presentation` đại diện cho một tệp PowerPoint duy nhất trong bộ nhớ. Tạo một thể hiện sẽ cung cấp cho bạn một bộ slide trống, mới để làm việc với.
```java
Presentation pres = new Presentation();
```

### Bước 2: Thêm biểu đồ tròn
Chèn biểu đồ tròn vào slide đầu tiên. Tọa độ (50, 50) và kích thước (600 × 400) phù hợp với bố cục tiêu chuẩn 16:9 và để chỗ cho tiêu đề.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Bước 3: Lưu Presentation
Ghi bản thuyết trình ra đĩa. Thay thế `YOUR_OUTPUT_DIRECTORY` bằng thư mục bạn muốn lưu tệp.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Bước 4: Dọn dẹp tài nguyên
Giải phóng đối tượng `Presentation` để giải phóng tài nguyên gốc và tránh rò rỉ bộ nhớ.
```java
if (pres != null) pres.dispose();
```

## Cách tùy chỉnh việc tách điểm dữ liệu và màu sắc?

Tải biểu đồ, xác định điểm dữ liệu mục tiêu, sau đó áp dụng độ lệch tách và màu nền đặc. Điều này làm cho lát nổi bật để nhấn mạnh. Những điều chỉnh này giúp thu hút sự chú ý của khán giả đến các giá trị quan trọng và cải thiện khả năng đọc tổng thể của biểu đồ.

### Bước 1: Tải một Presentation hiện có (hoặc sử dụng lại cái vừa tạo)
Đối tượng `Presentation` tải một tệp PowerPoint hiện có vào bộ nhớ, cho phép bạn chỉnh sửa nội dung của nó.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Bước 2: Truy cập biểu đồ và điểm dữ liệu mục tiêu
Giao diện `IDataPoint` đại diện cho một điểm dữ liệu riêng lẻ (lát) trong một chuỗi biểu đồ.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Bước 3: Áp dụng tách và màu
`setExplosion(int)` đặt khoảng cách, tính bằng pixel, mà một lát được dịch ra khỏi trung tâm biểu đồ. Tách lát ra bằng cách sử dụng `setExplosion(20)` và thay đổi màu nền thành xanh dương bằng `setFillType(FillType.Solid)` và `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Bước 4: Lưu và giải phóng
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Ứng dụng thực tiễn
- **Báo cáo bán hàng:** Làm nổi bật các sản phẩm bán chạy nhất bằng các lát tách.  
- **Phân tích ngân sách:** Gán màu sắc riêng cho các phòng ban để so sánh nhanh bằng hình ảnh.  
- **Slide giáo dục:** Phân tách các khái niệm phức tạp thành các phần biểu đồ dễ hiểu.  

## Các cân nhắc về hiệu năng
- **Giải phóng đối tượng** kịp thời để tránh rò rỉ bộ nhớ, đặc biệt khi tạo nhiều slide trong vòng lặp.  
- **Giám sát việc sử dụng heap** cho các bản thuyết trình lớn; sử dụng phương thức `Save` nhận `OutputStream` để truyền dữ liệu và giữ dung lượng bộ nhớ thấp.  
- Tuân thủ **JDK 16+** để tận dụng các cải tiến thu gom rác mới nhất, có thể giảm thời gian xử lý tới 30 % cho bộ slide 1.000 slide.

## Kết luận
Bây giờ bạn đã có quy trình hoàn chỉnh, sẵn sàng cho sản xuất để **thêm biểu đồ tròn PowerPoint** bằng Aspose.Slides cho Java. Thử nghiệm với các khoảng cách tách, màu sắc và bộ dữ liệu khác nhau để phù hợp với thương hiệu của bạn. Khi đã sẵn sàng, khám phá các loại biểu đồ khác—cột, đường, hoặc scatter—to xây dựng một bảng điều khiển phân tích đầy đủ trong PowerPoint.

## Câu hỏi thường gặp

**Q: Lợi thế lớn nhất của việc sử dụng Aspose.Slides cho Java là gì?**  
A: Nó cho phép bạn tạo, chỉnh sửa và render tệp PowerPoint bằng lập trình mà không cần cài đặt Microsoft Office, hỗ trợ hơn 70 loại biểu đồ và hơn 100 định dạng tệp.

**Q: Tôi có thể tạo tệp PowerPoint từ đầu không?**  
A: Có, khởi tạo một đối tượng `Presentation`, thêm slide, biểu đồ hoặc hình dạng, sau đó gọi `save`—tất cả bằng mã Java thuần.

**Q: Làm sao để tách một lát bánh tròn cụ thể?**  
A: Lấy `IDataPoint` cho lát đó và gọi `setExplosion(pixelOffset)`. Độ lệch xác định khoảng cách lát di chuyển ra ngoài.

**Q: Có giới hạn về số slide tôi có thể tạo không?**  
A: Aspose.Slides có thể xử lý các bản thuyết trình lên tới **10.000 slide** trong một tệp, với điều kiện bạn stream đầu ra để tránh tải toàn bộ vào bộ nhớ.

**Q: Tôi có thể tìm các ví dụ tùy chỉnh biểu đồ nâng cao ở đâu?**  
A: Kiểm tra [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) chính thức để xem tài liệu API chi tiết và các dự án mẫu.

## Tài nguyên
- **Tài liệu:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Tải thư viện:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Mua giấy phép:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Dùng thử miễn phí:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Giấy phép tạm thời:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Diễn đàn hỗ trợ:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Cập nhật lần cuối:** 2026-07-08  
**Kiểm tra với:** Aspose.Slides cho Java 25.4 (phân loại JDK 16)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách Thêm Biểu Đồ vào PowerPoint Sử dụng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hoạt Họa Biểu Đồ PowerPoint Sử dụng Aspose.Slides cho Java – Hướng Dẫn Từng Bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Tạo và Xác Thực Bố Cục Biểu Đồ trong PowerPoint Sử dụng Aspose.Slides cho Java | Hướng Dẫn Tối Ưu SEO](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}