---
date: '2026-02-17'
description: Tìm hiểu cách thêm biểu đồ tròn vào bản trình bày PowerPoint bằng Aspose.Slides
  cho Java. Hãy làm theo hướng dẫn từng bước này để tạo và tùy chỉnh các biểu đồ tròn
  chuyên nghiệp.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Cách thêm biểu đồ tròn vào PowerPoint với Aspose.Slides cho Java
url: /vi/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo và Tùy chỉnh Biểu đồ Tròn trong PowerPoint bằng Aspose.Slides cho Java

## Giới thiệu

Bạn đang gặp khó khăn trong việc trực quan hoá dữ liệu một cách hiệu quả trong các bài thuyết trình PowerPoint? **Thêm biểu đồ tròn PowerPoint** có thể ngay lập tức biến các con số thô thành một câu chuyện hình ảnh rõ ràng. Với Aspose.Slides cho Java, bạn có thể **thêm biểu đồ tròn PowerPoint** một cách lập trình, cho phép bạn kiểm soát toàn bộ thiết kế và dữ liệu mà không cần mở PowerPoint thủ công. Trong hướng dẫn này, chúng tôi sẽ đi qua toàn bộ quy trình — từ cài đặt thư viện đến tùy chỉnh các điểm dữ liệu cá nhân — để bạn có thể tạo ra các slide dữ liệu‑định dạng chuyên nghiệp chỉ trong vài phút.

### Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Slides cho Java (phiên bản mới nhất).  
- **Có thể tạo biểu đồ mà không cài đặt PowerPoint không?** Có, API hoạt động hoàn toàn offline.  
- **Yêu cầu phiên bản Java nào?** JDK 16 hoặc mới hơn được khuyến nghị.  
- **Làm sao để thay đổi màu của một lát?** Sử dụng các phương thức `setFillType` và `setSolidFillColor` trên điểm dữ liệu.  
- **Có cần giấy phép bắt buộc không?** Bản dùng thử hoạt động cho phát triển; giấy phép chính thức sẽ loại bỏ các giới hạn đánh giá.

### Những gì bạn sẽ học
- Cách **thêm biểu đồ tròn PowerPoint** một cách lập trình bằng Java.  
- Các cách tùy chỉnh việc nổ (explosion) các lát, màu sắc và các thuộc tính hiển thị khác.  
- Các thực tiễn tốt nhất về quản lý tài nguyên và hiệu năng khi xử lý các bản trình bày lớn.

## Tại sao nên thêm biểu đồ tròn PowerPoint bằng Aspose.Slides cho Java?
Việc nhúng biểu đồ tròn trực tiếp từ mã nguồn cho phép bạn tạo các báo cáo luôn cập nhật, tự động hoá các bảng điều khiển hàng tháng, hoặc tạo các bộ slide cá nhân hoá ngay lập tức. Nó loại bỏ các lỗi sao chép‑dán thủ công, đảm bảo tính nhất quán giữa các bản trình bày, và tích hợp mượt mà với các back‑end Java hiện có.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- **Thư viện Aspose.Slides cho Java** – hướng dẫn này tham chiếu phiên bản 25.4 (phiên bản mới nhất tại thời điểm viết).  
- **Bộ công cụ phát triển Java (JDK)** tương thích – ưu tiên JDK 16+.  
- Kiến thức cơ bản về **Maven** hoặc **Gradle** để quản lý phụ thuộc.  

## Cài đặt Aspose.Slides cho Java

Để bắt đầu, hãy thêm thư viện Aspose.Slides vào dự án của bạn.

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
Bao gồm đoạn sau trong tệp `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Hoặc tải phiên bản mới nhất trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Cấp phép
Để sử dụng Aspose.Slides không bị giới hạn:

- Bắt đầu với **bản dùng thử miễn phí** để đánh giá API.  
- Yêu cầu **giấy phép tạm thời** để thử nghiệm kéo dài hơn tại trang [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Mua gói đăng ký đầy đủ qua [Purchase page](https://purchase.aspose.com/buy).

## Cách thêm biểu đồ tròn PowerPoint bằng Aspose.Slides cho Java

Dưới đây là hướng dẫn từng bước cho thấy cách tạo và tùy chỉnh một biểu đồ tròn.

### Bước 1: Khởi tạo Presentation
Đầu tiên, tạo một đối tượng `Presentation` mới. Đối tượng này đại diện cho một tệp PowerPoint trống.
```java
Presentation pres = new Presentation();
```

### Bước 2: Thêm biểu đồ tròn
Chèn một biểu đồ tròn vào slide đầu tiên. Tọa độ (50, 50) và kích thước (600 × 400) phù hợp với slide tiêu chuẩn 16:9.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Bước 3: Lưu Presentation
Ghi bản trình bày ra đĩa. Thay thế `YOUR_OUTPUT_DIRECTORY` bằng thư mục bạn muốn lưu tệp.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Bước 4: Dọn dẹp tài nguyên
Giải phóng đối tượng `Presentation` để giải phóng tài nguyên gốc.
```java
if (pres != null) pres.dispose();
```

## Tùy chỉnh Nổ (Explosion) và Màu của Điểm Dữ liệu

Việc tùy chỉnh các lát riêng lẻ giúp biểu đồ của bạn dễ đọc hơn, đặc biệt khi muốn làm nổi bật một giá trị cụ thể.

### Bước 1: Tải một Presentation hiện có (hoặc sử dụng lại cái vừa tạo)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Bước 2: Truy cập biểu đồ và điểm dữ liệu mục tiêu
Ở đây chúng ta lấy điểm dữ liệu thứ hai (chỉ số 1) từ series đầu tiên.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Bước 3: Áp dụng Explosion và Màu
Tách lát ra một cách trực quan và thay đổi màu nền thành màu xanh.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Bước 4: Lưu và Giải phóng
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Ứng dụng thực tế
- **Báo cáo bán hàng:** Làm nổi bật các sản phẩm bán chạy nhất bằng các lát nổ.  
- **Phân tích ngân sách:** Gán màu sắc riêng cho các phòng ban để so sánh nhanh.  
- **Slide giáo dục:** Phân tách các khái niệm phức tạp thành các phần biểu đồ dễ tiêu hoá.

## Các lưu ý về hiệu năng
- **Giải phóng đối tượng** kịp thời để tránh rò rỉ bộ nhớ, đặc biệt khi tạo nhiều slide trong vòng lặp.  
- **Giám sát mức sử dụng heap** cho các bản trình bày lớn; cân nhắc streaming đầu ra bằng các overload của `Save` chấp nhận `OutputStream`.  
- Sử dụng **JDK 16+** để hưởng lợi từ các cải tiến mới nhất của garbage‑collection.

## Kết luận
Bạn đã có một quy trình hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **thêm biểu đồ tròn PowerPoint** bằng Aspose.Slides cho Java. Hãy thử nghiệm các khoảng cách nổ khác nhau, màu sắc và bộ dữ liệu để phù hợp với thương hiệu của bạn. Khi đã sẵn sàng, khám phá các loại biểu đồ khác — cột, đường, hoặc scatter — để xây dựng một bảng điều khiển phân tích đầy đủ trong PowerPoint.

## Phần Câu hỏi thường gặp
1. **Lợi thế chính của việc sử dụng Aspose.Slides cho Java là gì?**  
   - Nó đơn giản hoá việc tạo và thao tác các tệp PowerPoint một cách lập trình, cung cấp một loạt các tính năng phong phú.  
2. **Tôi có thể tùy chỉnh các loại biểu đồ khác với Aspose.Slides không?**  
   - Chắc chắn! Aspose.Slides hỗ trợ nhiều loại biểu đồ như cột, đường và scatter.  
3. **Làm sao để xử lý nhiều slide khi tạo biểu đồ?**  
   - Truy cập từng slide bằng chỉ số thông qua phương thức `get_Item()` để áp dụng thay đổi trên các slide khác nhau.  
4. **Nếu biểu đồ tròn của tôi không hiển thị đúng sau khi tùy chỉnh thì sao?**  
   - Kiểm tra lại tọa độ và kích thước được sử dụng trong `addChart()`, đảm bảo chúng nằm trong bố cục slide của bạn.  
5. **Tôi có thể tìm các tính năng nâng cao của Aspose.Slides ở đâu?**  
   - Khám phá [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) để tìm hiểu thêm về các chức năng và tùy chọn bổ sung.

## Tài nguyên
- **Tài liệu:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Tải thư viện:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Mua giấy phép:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Dùng thử miễn phí:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Giấy phép tạm thời:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Diễn đàn hỗ trợ:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Cập nhật lần cuối:** 2026-02-17  
**Đã kiểm tra với:** Aspose.Slides cho Java 25.4 (JDK 16 classifier)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}