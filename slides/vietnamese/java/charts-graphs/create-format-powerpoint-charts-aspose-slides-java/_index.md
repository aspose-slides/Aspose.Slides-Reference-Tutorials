---
date: '2026-03-15'
description: Tìm hiểu cách thêm biểu đồ cột nhóm vào một slide PowerPoint bằng Aspose.Slides
  for Java, bao gồm các bước để chèn biểu đồ vào slide và tạo slide PowerPoint bằng
  Java một cách hiệu quả.
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: Thêm biểu đồ cột nhóm vào PPT bằng Aspose.Slides Java
url: /vi/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

Make sure we keep code block placeholders unchanged.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thêm Biểu Đồ Cột Nhóm vào PPT bằng Aspose.Slides Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **thêm biểu đồ cột nhóm** vào một bản trình bày PowerPoint một cách lập trình bằng Aspose.Slides cho Java. Cho dù bạn đang xây dựng báo cáo kinh doanh, bộ slide giáo dục hay bộ slide marketing, việc tự động tạo biểu đồ giúp tiết kiệm thời gian và đảm bảo tính nhất quán. Chúng tôi sẽ hướng dẫn cách cài đặt thư viện, tạo slide, thêm biểu đồ, áp dụng kiểu đường viền và góc bo tròn, và cuối cùng lưu tệp. Khi hoàn thành, bạn sẽ nắm vững quy trình **thêm biểu đồ vào slide** và thậm chí **tạo slide PowerPoint bằng Java**‑based solutions.

### Câu trả lời nhanh
- **Lớp chính để bắt đầu là gì?** `Presentation`
- **Loại biểu đồ nào được sử dụng?** `ChartType.ClusteredColumn`
- **Làm thế nào để bật góc bo tròn?** `chart.setRoundedCorners(true);`
- **Định dạng nào được khuyến nghị để lưu?** `SaveFormat.Pptx`
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí hoạt động cho việc kiểm tra; giấy phép mua phải được sử dụng cho môi trường sản xuất.

## Biểu đồ cột nhóm là gì?
Biểu đồ cột nhóm nhóm các chuỗi dữ liệu nhiều phía nhau cho mỗi danh mục, giúp so sánh giá trị giữa các nhóm khác nhau. Aspose.Slides cho phép bạn tạo loại biểu đồ này hoàn toàn bằng mã mà không cần mở PowerPoint.

## Tại sao nên sử dụng Aspose.Slides cho Java để thêm biểu đồ cột nhóm?
- **Tự động hoàn toàn** – Không cần tương tác UI thủ công.  
- **Đa nền tảng** – Hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **Định dạng phong phú** – Kiểm soát kiểu đường viền, màu nền, góc bo tròn và hơn thế nữa.  
- **Không phụ thuộc COM** – Không giống như Office Interop, nó chạy an toàn trên máy chủ.

## Yêu cầu trước
- **Aspose.Slides cho Java** (v25.4 hoặc mới hơn)  
- **JDK 16** (hoặc mới hơn)  
- Một IDE như IntelliJ IDEA, Eclipse hoặc NetBeans  

## Cài đặt Aspose.Slides cho Java
Bạn có thể thêm thư viện qua Maven, Gradle hoặc tải trực tiếp.

### Sử dụng Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Sử dụng Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Các bước nhận giấy phép
- **Dùng thử miễn phí** – Kiểm tra tất cả tính năng không giới hạn thời gian.  
- **Giấy phép tạm thời** – Yêu cầu từ cổng Aspose để đánh giá đầy đủ tính năng.  
- **Mua** – Nhận giấy phép vĩnh viễn cho việc sử dụng trong môi trường sản xuất.

## Hướng dẫn thực hiện

### Tạo bản trình bày và thêm slide
#### Tổng quan
Đầu tiên, chúng ta tạo một đối tượng `Presentation` mới và lấy slide mặc định đi kèm với tệp mới.

#### Các bước thực hiện
**1. Khởi tạo đối tượng Presentation**
```java
Presentation presentation = new Presentation();
```

**2. Truy cập slide đầu tiên**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Giải phóng tài nguyên**
```java
if (presentation != null) presentation.dispose();
```

### Thêm biểu đồ vào slide
#### Tổng quan
Bây giờ chúng ta nhúng một **biểu đồ cột nhóm** vào slide vừa chuẩn bị.

#### Các bước thực hiện
**1. Khởi tạo đối tượng Presentation**
```java
Presentation presentation = new Presentation();
```

**2. Truy cập slide đầu tiên**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Thêm biểu đồ cột nhóm**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Giải phóng tài nguyên**
```java
if (presentation != null) presentation.dispose();
```

### Định dạng kiểu đường viền biểu đồ và thiết lập góc bo tròn
#### Tổng quan
Cải thiện giao diện bằng cách áp dụng màu nền đường viền đặc, kiểu đường viền đơn và góc bo tròn.

#### Các bước thực hiện
**1. Khởi tạo đối tượng Presentation**
```java
Presentation presentation = new Presentation();
```

**2. Truy cập slide đầu tiên**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Thêm biểu đồ cột nhóm**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Đặt định dạng đường viền thành loại nền đặc**
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. Áp dụng kiểu đường viền đơn**
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. Bật góc bo tròn cho vùng biểu đồ**
```java
chart.setRoundedCorners(true);
```

**7. Giải phóng tài nguyên**
```java
if (presentation != null) presentation.dispose();
```

### Lưu bản trình bày
#### Tổng quan
Cuối cùng, chúng ta ghi bản trình bày ra đĩa ở định dạng PPTX.

#### Các bước thực hiện
**1. Khởi tạo đối tượng Presentation**
```java
Presentation presentation = new Presentation();
```

**2. Xác định thư mục đầu ra và tên tệp**
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. Lưu bản trình bày ở định dạng PPTX**
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. Giải phóng tài nguyên**
```java
if (presentation != null) presentation.dispose();
```

## Ứng dụng thực tiễn
- **Báo cáo kinh doanh** – Tự động tạo các bộ slide tài chính quý với biểu đồ động.  
- **Nội dung giáo dục** – Tạo slide bài giảng lấy dữ liệu từ cơ sở dữ liệu.  
- **Bài thuyết trình marketing** – Trực quan hoá xu hướng sản phẩm bằng các biểu đồ tinh tế.

## Các cân nhắc về hiệu năng
- **Quản lý tài nguyên** – Luôn gọi `dispose()` hoặc sử dụng try‑with‑resources.  
- **Tối ưu bộ nhớ** – Xử lý các bộ dữ liệu lớn theo các lô nhỏ hơn.  
- **Thực hành tốt** – Ưu tiên cấu trúc dữ liệu bất biến cho các series biểu đồ khi có thể.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **`NullPointerException` on `getSlides()`** | Đảm bảo đối tượng `Presentation` được khởi tạo thành công trước khi truy cập slide. |
| **Chart not appearing** | Kiểm tra kích thước biểu đồ (x, y, width, height) nằm trong giới hạn của slide. |
| **License not applied** | Tải tệp giấy phép của bạn trước khi tạo đối tượng `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Câu hỏi thường gặp

**Q: Làm thế nào để thêm các loại biểu đồ khác nhau bằng Aspose.Slides?**  
A: Thay thế `ChartType.ClusteredColumn` bằng bất kỳ giá trị enum nào khác như `ChartType.Pie`, `ChartType.Line` hoặc `ChartType.Bar`.

**Q: Tôi nên làm gì nếu gặp lỗi biên dịch?**  
A: Kiểm tra lại rằng bạn đang sử dụng JDK 16 hoặc mới hơn và phụ thuộc Maven/Gradle khớp với phiên bản được hiển thị ở trên.

**Q: Tôi có thể điền dữ liệu cho biểu đồ từ cơ sở dữ liệu không?**  
A: Có. Truy cập bộ sưu tập `getChartData()` của biểu đồ, tạo series và categories, và điền chúng bằng các giá trị lấy từ runtime.

**Q: Làm thế nào để cải thiện hiệu năng cho các bản trình bày rất lớn?**  
A: Chia công việc thành nhiều đối tượng `Presentation`, tái sử dụng mẫu biểu đồ và luôn giải phóng các đối tượng kịp thời.

## Kết luận
Bây giờ bạn đã có một quy trình hoàn chỉnh, từ đầu đến cuối để **thêm biểu đồ cột nhóm** vào slide PowerPoint bằng Aspose.Slides cho Java. Thử nghiệm các loại biểu đồ khác, kết nối nguồn dữ liệu trực tiếp, và tích hợp logic này vào các pipeline báo cáo lớn hơn để tự động hoá quy trình tạo slide của bạn.

---

**Last Updated:** 2026-03-15  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}