---
date: '2026-09-17'
description: Tìm hiểu cách tạo bubble chart PowerPoint bằng Aspose.Slides for Java.
  Hướng dẫn này chỉ cho bạn cách thêm chart vào slide, cấu hình bubble size, và lưu
  PPTX một cách hiệu quả.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Tìm hiểu cách tạo bubble chart PowerPoint bằng Aspose.Slides for Java.
  Bài hướng dẫn này giải thích cách thêm chart vào slide, điều chỉnh bubble sizes,
  và lưu presentation một cách hiệu quả.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Tạo bubble chart PowerPoint với Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Tạo bubble chart PowerPoint với Aspose.Slides for Java
url: /vi/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo biểu đồ bong bóng PowerPoint với Aspose.Slides cho Java

## Giới thiệu
Nếu bạn cần **tạo biểu đồ bong bóng PowerPoint** một cách lập trình, Aspose.Slides cho Java cung cấp cho bạn một API sạch, chạy phía máy chủ mà không cần Microsoft Office. Trong hướng dẫn này, bạn sẽ học cách thêm biểu đồ vào một slide, kiểm soát kích thước bong bóng và lưu file PPTX cuối cùng trong khi quản lý tài nguyên một cách hiệu quả. Các bước được chia nhỏ để bạn có thể sao chép‑dán mã vào bất kỳ dự án Java nào và thấy kết quả ngay lập tức.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Slides for Java
- **Phiên bản Java yêu cầu là gì?** JDK 16 hoặc cao hơn
- **Làm thế nào để thêm biểu đồ bong bóng?** Gọi `addChart(ChartType.Bubble, …)` trên một slide
- **Tôi có thể thay đổi kích thước bong bóng không?** Có, thông qua `setBubbleSizeScale()`
- **Làm thế nào để lưu file?** Sử dụng `pres.save("Result.pptx", SaveFormat.Pptx)`

## Tạo biểu đồ bong bóng PowerPoint là gì?
Tạo một biểu đồ bong bóng trong PowerPoint có nghĩa là lập trình tạo ra một biểu đồ trong đó mỗi điểm dữ liệu được biểu diễn bằng một bong bóng, vị trí X, vị trí Y và kích thước của nó mã hoá ba chiều dữ liệu. Aspose.Slides cho Java xử lý việc render, vì vậy bạn không cần cài đặt PowerPoint.

## Tại sao nên sử dụng Aspose.Slides cho Java?
Aspose.Slides hỗ trợ **hơn 50 loại biểu đồ**, có thể xử lý các bản trình bày lên tới **2 GB** mà không cần tải toàn bộ file vào bộ nhớ, và chạy trên bất kỳ nền tảng nào hỗ trợ Java 16+. Những khả năng được định lượng này khiến nó trở thành lựa chọn đáng tin cậy cho báo cáo cấp doanh nghiệp.

## Yêu cầu trước
- **Java Development Kit** 16 hoặc mới hơn đã được cài đặt.
- **Thư viện Aspose.Slides cho Java** (thêm qua Maven, Gradle, hoặc tải JAR trực tiếp).
- Kiến thức cơ bản về cú pháp Java và lập trình hướng đối tượng.

## Cài đặt Aspose.Slides cho Java
Để bắt đầu sử dụng Aspose.Slides, bao gồm thư viện vào hệ thống build của bạn.

### Maven
Thêm phụ thuộc sau vào `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Bao gồm đoạn này trong `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Bạn cũng có thể lấy JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Nhận giấy phép
- **Dùng thử miễn phí** – khám phá tất cả tính năng mà không tốn phí.  
- **Giấy phép tạm thời** – đánh giá mở rộng cho các dự án lớn hơn.  
- **Giấy phép đầy đủ** – cần thiết cho triển khai sản xuất.

### Khởi tạo và cấu hình cơ bản
Lớp `Presentation` là điểm vào để tạo hoặc tải các file PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Hướng dẫn triển khai
Dưới đây là hướng dẫn chi tiết từng bước để tạo biểu đồ bong bóng và quản lý tài nguyên.

## Cách tạo biểu đồ bong bóng PowerPoint
Trong phần này, bạn sẽ học chuỗi lệnh API chính xác cần thiết để tạo biểu đồ bong bóng, cấu hình các thuộc tính hiển thị, và lưu kết quả dưới dạng file PPTX. Cách tiếp cận này hoạt động cho bất kỳ dự án Java nào có Aspose.Slides và tuân theo thực hành quản lý tài nguyên tốt nhất.

Tải bản trình bày, thêm biểu đồ bong bóng, cấu hình giao diện, và lưu file.

### Trả lời trực tiếp
Tạo một `Presentation` mới, gọi `addChart(ChartType.Bubble, …)` trên slide mong muốn, điều chỉnh tỷ lệ kích thước bong bóng bằng `setBubbleSizeScale(150)`, sau đó lưu bằng `pres.save("Result.pptx", SaveFormat.Pptx)`. Chuỗi lệnh này thêm một biểu đồ bong bóng hoàn chỉnh chỉ trong vài dòng Java.

- **`ChartType.Bubble`** đại diện cho loại biểu đồ bong bóng.  
- **`addChart`** chèn một biểu đồ mới loại đã chỉ định vào một slide.  
- **`setBubbleSizeScale`** điều chỉnh kích thước tổng thể của các bong bóng trong biểu đồ.  
- **`SaveFormat.Pptx`** chỉ định định dạng file PPTX để lưu.  

#### Triển khai từng bước
**1. Khởi tạo bản trình bày** – tạo một đối tượng `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Thêm biểu đồ bong bóng** – chèn biểu đồ tại tọa độ đã chọn.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` cho Aspose.Slides biết tạo biểu đồ bong bóng.  
- Các tham số số xác định vị trí X/Y và chiều rộng/chiều cao tính bằng điểm.

**3. Cấu hình tỷ lệ kích thước bong bóng** – phóng to bong bóng để có ảnh hưởng hình ảnh tốt hơn.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Đặt tỷ lệ thành **150 %** làm mỗi bong bóng lớn hơn 1.5 × so với mặc định.

**4. Lưu bản trình bày** – ghi file PPTX ra đĩa.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Mẹo khắc phục sự cố
- Kiểm tra quyền ghi cho thư mục đầu ra.  
- Xác nhận JAR Aspose.Slides phù hợp với phiên bản JDK bạn đang sử dụng.

## Cách quản lý tài nguyên PowerPoint hiệu quả
Quản lý tài nguyên hiệu quả ngăn ngừa rò rỉ bộ nhớ và giữ dung lượng JVM thấp, đặc biệt khi xử lý các bộ slide lớn hoặc chạy trong môi trường server. Thực hiện mẫu dưới đây để đảm bảo tài nguyên gốc được giải phóng ngay cả khi xảy ra ngoại lệ.

Quản lý tài nguyên hiệu quả ngăn ngừa rò rỉ bộ nhớ, đặc biệt khi xử lý các bộ slide lớn.

### Trả lời trực tiếp
Sau khi hoàn thành công việc với một `Presentation`, luôn gọi `pres.dispose()` trong khối `try‑finally`; điều này giải phóng tài nguyên gốc và cho phép JVM thu hồi bộ nhớ kịp thời.

- **`pres.dispose()`** giải phóng tài nguyên gốc được sử dụng bởi bản trình bày.

**1. Tạo và chỉnh sửa** – làm việc với bản trình bày theo nhu cầu.  
```java
Presentation pres = new Presentation();
```

**2. Giải phóng tài nguyên** – giải phóng bộ nhớ sau khi xử lý hoàn tất.  
```java
if (pres != null) pres.dispose();
```

## Ứng dụng thực tiễn
Biểu đồ bong bóng xuất sắc trong các kịch bản cần trực quan hoá đồng thời ba chiều dữ liệu:

1. **Phân tích thị trường** – kích thước bong bóng đại diện doanh thu trong khi các trục X/Y hiển thị tăng trưởng và thị phần.  
2. **Chỉ số hiệu suất** – so sánh năng suất nhân viên (X), mức độ hài lòng (Y), và tác động (kích thước).  
3. **Dữ liệu địa lý** – vẽ các thành phố với dân số được mã hoá trong kích thước bong bóng.  
4. **Quản lý dự án** – trực quan hoá thời gian (X), chi phí (Y), và rủi ro (kích thước) trên một slide duy nhất.

## Các cân nhắc về hiệu năng
- **Sử dụng tài nguyên** – giải phóng bản trình bày kịp thời để giữ mức sử dụng heap thấp.  
- **Quản lý bộ nhớ Java** – bọc công việc với bản trình bày trong `try‑finally` để đảm bảo giải phóng ngay cả khi có ngoại lệ.  
- **Cập nhật** – nâng cấp lên phiên bản mới nhất của Aspose.Slides để hưởng lợi từ tối ưu hoá hiệu năng và sửa lỗi.

## Câu hỏi thường gặp

**Q: Aspose.Slides cho Java là gì?**  
A: Aspose.Slides cho Java là một thư viện độc lập cho phép bạn tạo, chỉnh sửa và chuyển đổi các file PowerPoint mà không cần Microsoft Office.

**Q: Làm thế nào để tích hợp Aspose.Slides vào dự án Java hiện có của tôi?**  
A: Thêm phụ thuộc Maven hoặc Gradle như đã trình bày ở trên, hoặc đặt JAR vào classpath, sau đó import `com.aspose.slides.*`.

**Q: Tôi có thể sử dụng Aspose.Slides cho các bản trình bày lớn không?**  
A: Có, thư viện xử lý hiệu quả các bản trình bày lên tới **2 GB** và hỗ trợ streaming để tránh tải toàn bộ file vào bộ nhớ.

**Q: Có những loại biểu đồ nào ngoài biểu đồ bong bóng?**  
A: Hơn **50 loại biểu đồ** được hỗ trợ, bao gồm biểu đồ cột, đường, tròn, radar và thác nước.

**Q: Có hỗ trợ tích hợp cho việc tạo kiểu các thành phần biểu đồ không?**  
A: Chắc chắn. Bạn có thể tùy chỉnh màu sắc, phông chữ, viền và nhãn dữ liệu thông qua các đối tượng `ChartSeries` và `ChartTitle` của biểu đồ.

## Tài nguyên
- **Tài liệu**: [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Tải xuống**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Mua**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Dùng thử miễn phí**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Giấy phép tạm thời**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Hỗ trợ**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Cập nhật lần cuối:** 2026-09-17  
**Kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách Thêm Biểu Đồ vào PowerPoint Sử dụng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java tạo biểu đồ PowerPoint bằng Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Tạo Biểu Đồ PowerPoint Java – Lưu Bản Trình Bày với Biểu Đồ Sử dụng Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}