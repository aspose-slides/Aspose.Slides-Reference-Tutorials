---
date: '2026-03-02'
description: Tìm hiểu cách tạo biểu đồ hộp trong Java, thêm biểu đồ vào slide và tạo
  biểu đồ hộp râu trong PowerPoint bằng Aspose.Slides cho Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Tạo biểu đồ hộp Java bằng Aspose.Slides cho PowerPoint
url: /vi/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Tạo Biểu Đồ Hộp và Râu trong PowerPoint bằng Aspose.Slides cho Java

Trong hướng dẫn này, bạn sẽ **tạo box plot java** với Aspose.Slides, sau đó nhúng biểu đồ trực tiếp vào một slide PowerPoint. Việc tạo các bản trình bày dữ liệu hấp dẫn về mặt hình ảnh là rất quan trọng trong thế giới dựa trên dữ liệu ngày nay, và biểu đồ là công cụ thiết yếu cho mục đích này. Nếu bạn muốn tạo biểu đồ hộp‑râu trong PowerPoint bằng Java, thư viện Aspose.Slides cung cấp một giải pháp mạnh mẽ. Bài học này sẽ hướng dẫn bạn cách tạo và cấu hình các biểu đồ này một cách liền mạch với Aspose.Slides cho Java.

## Những Điều Bạn Sẽ Học

- Cài đặt môi trường cho Aspose.Slides cho Java  
- Các bước **thêm biểu đồ vào slide** và tạo biểu đồ hộp‑râu trong PowerPoint bằng Java  
- Các thực tiễn tốt nhất để tối ưu hiệu năng khi làm việc với Aspose.Slides  
- Ứng dụng thực tế của biểu đồ hộp‑râu  

## Câu Hỏi Nhanh
- **Thư viện nào tạo box plot trong Java?** Aspose.Slides cho Java.  
- **Loại biểu đồ nào được sử dụng?** `ChartType.BoxAndWhisker`.  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có thể thêm nhiều series không?** Có – lặp lại khối tạo series cho mỗi bộ dữ liệu.  
- **Định dạng file cuối cùng là gì?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Điều Kiện Tiên Quyết

Để làm theo hướng dẫn này, hãy đảm bảo bạn có:

- **Java Development Kit (JDK)**: JDK 8 trở lên đã được cài đặt.  
- **Thư viện Aspose.Slides cho Java**: Cần thiết để xử lý các bản trình bày PowerPoint trong Java.  
- **IDE**: Môi trường phát triển tích hợp như IntelliJ IDEA hoặc Eclipse để viết và chạy mã.  

## Cài Đặt Aspose.Slides cho Java

Để sử dụng Aspose.Slides, thêm nó như một phụ thuộc. Bạn có thể quản lý qua Maven, Gradle, hoặc tải trực tiếp.

### Maven

Thêm phụ thuộc sau vào file `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Trong file `build.gradle`, bao gồm:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải Trực Tiếp

Hoặc tải phiên bản mới nhất từ [Phiên bản Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).

#### Nhận Giấy Phép

- **Bản Dùng Thử Miễn Phí**: Bắt đầu với bản dùng thử để khám phá các tính năng.  
- **Giấy Phép Tạm Thời**: Nhận giấy phép tạm thời cho mục đích đánh giá.  
- **Mua Bản Quyền**: Để có đầy đủ chức năng, hãy cân nhắc mua giấy phép.

Để khởi tạo Aspose.Slides, đảm bảo thư viện đã nằm trong classpath và thiết lập bất kỳ yêu cầu giấy phép nào cần thiết.

## Hướng Dẫn Thực Hiện

Bây giờ chúng ta sẽ đi vào mã từng bước. Mỗi khối được giải thích trước đoạn mã để bạn biết chính xác nó làm gì.

### Box plot là gì và tại sao lại dùng trong Java?

Biểu đồ hộp‑râu (thường gọi là *box plot*) hiển thị phân bố dữ liệu — trung vị, các phần tư và các điểm ngoại lệ — trong một dạng gọn gàng. Trong Java, việc tạo biểu đồ này một cách lập trình cho phép bạn nhúng các hiểu biết thống kê trực tiếp vào các bộ slide PowerPoint, loại bỏ việc tạo biểu đồ thủ công.

### Tại sao thêm biểu đồ vào slide bằng Aspose.Slides?

Aspose.Slides trừu tượng hoá các chi tiết OpenXML mức thấp, cung cấp cho bạn một API mượt mà để tạo, định dạng và xuất biểu đồ. Điều này cho phép bạn tự động hoá việc tạo báo cáo, duy trì thương hiệu nhất quán và tích hợp biểu đồ vào các quy trình Java lớn hơn.

### Bước 1: Tạo hoặc Mở Một Bản Trình Bày

Đầu tiên, mở một file PPTX hiện có hoặc tạo mới:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Mẹo:** Nếu file không tồn tại, Aspose.Slides sẽ tự động tạo một bản trình bày trống mới cho bạn.

### Bước 2: Thêm Biểu Đồ Hộp‑Râu vào Slide

Đặt biểu đồ ở vị trí bạn muốn bằng cách chỉ định vị trí và kích thước (đơn vị là point):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Bước 3: Xóa Dữ Liệu Hiện Có

Trước khi đưa dữ liệu mới, hãy xóa bất kỳ danh mục hoặc series placeholder nào:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Bước 4: Cấu Hình Các Danh Mục

Thêm các danh mục (nhãn trục X) sẽ xuất hiện dưới mỗi hộp:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Lưu ý:** Điều chỉnh văn bản nhãn sao cho phù hợp với miền dữ liệu của bạn (ví dụ: “Q1”, “Sản phẩm A”).

### Bước 5: Tạo và Tùy Chỉnh Series

Bây giờ tạo một series, đặt các tùy chọn hiển thị, và đưa các điểm dữ liệu số:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Bạn có thể thay thế mảng `int[] data` bằng các giá trị đọc từ cơ sở dữ liệu, file CSV, hoặc bất kỳ nguồn nào khác.

### Bước 6: Lưu Bản Trình Bày

Ghi các thay đổi vào một file PPTX mới:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Bước 7: Dọn Dẹp Tài Nguyên

Luôn luôn giải phóng đối tượng `Presentation` để giải phóng tài nguyên gốc:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Ứng Dụng Thực Tiễn

Biểu đồ hộp‑râu vô giá trong phân tích thống kê và trình bày dữ liệu. Dưới đây là một vài kịch bản mà chúng tỏa sáng:

1. **Phân Tích Tài Chính** – Hiển thị phân bố doanh thu theo khu vực.  
2. **Kiểm Soát Chất Lượng** – Phát hiện ngoại lệ trong các phép đo sản xuất.  
3. **Nghiên Cứu Học Thuật** – Thể hiện độ biến thiên của kết quả thí nghiệm.  
4. **Nghiên Cứu Thị Trường** – So sánh hiệu suất sản phẩm qua các nhóm dân số.

Việc tích hợp các biểu đồ này vào các bộ slide PowerPoint giúp các bên liên quan nắm bắt dữ liệu phức tạp trong nháy mắt.

## Cân Nhắc Về Hiệu Năng

Khi làm việc với Aspose.Slides trong Java, hãy nhớ các lời khuyên sau:

- **Quản Lý Bộ Nhớ** – Giải phóng đối tượng `Presentation` kịp thời.  
- **Xử Lý Dữ Liệu** – Chỉ tải dữ liệu cần thiết; tránh đưa khối lượng dữ liệu khổng lồ trực tiếp vào workbook của biểu đồ.  
- **Tải Lười** – Nếu bạn tạo nhiều slide, hãy cân nhắc chỉ tạo biểu đồ cho những slide sẽ được hiển thị.

## Các Vấn Đề Thường Gặp và Giải Pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| **Biểu đồ hiển thị trống** | Các ô dữ liệu không được điền đúng | Kiểm tra lại tham chiếu `wb.getCell` tới đúng hàng/cột và đảm bảo giá trị không phải `null`. |
| **Không hiển thị ngoại lệ** | `setShowOutlierPoints` được đặt thành `false` | Đảm bảo gọi `series.setShowOutlierPoints(true)`. |
| **Rò rỉ bộ nhớ** | Không giải phóng Presentation | Luôn bao bọc việc sử dụng trong try/finally và gọi `dispose()`. |
| **Phần tư không đúng** | Sử dụng phương pháp `Inclusive` mặc định | Chuyển sang `Exclusive` bằng cách gọi `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Câu Hỏi Thường Gặp

**Q1: Biểu đồ hộp‑râu là gì?**  
Biểu đồ hộp‑râu, còn gọi là box plot, hiển thị phân bố dữ liệu dựa trên năm thống kê tóm tắt: giá trị tối thiểu, phần tư thứ nhất, trung vị, phần tư thứ ba, và giá trị tối đa, cùng với bất kỳ điểm ngoại lệ nào.

**Q2: Tôi có thể tùy chỉnh giao diện của biểu đồ hộp‑râu không?**  
Có. Aspose.Slides cho phép bạn thay đổi màu sắc, kiểu đường, hình dạng marker, và thậm chí thêm nhãn dữ liệu thông qua API định dạng của biểu đồ.

**Q3: Có thể xử lý nhiều series trong một biểu đồ không?**  
Chắc chắn. Lặp lại khối tạo series cho mỗi bộ dữ liệu bạn muốn hiển thị.

**Q4: Làm sao giải quyết vấn đề dữ liệu không hiển thị đúng?**  
Đảm bảo dữ liệu được ghi đúng vào các ô workbook và các thuộc tính hiển thị như `setShowMeanLine` đã được bật.

**Q5: Tôi có thể nhận hỗ trợ khi gặp vấn đề không?**  
Truy cập [diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để nhận trợ giúp từ cộng đồng, hoặc tham khảo tài liệu chính thức.

**Q6: Aspose.Slides có hỗ trợ các loại biểu đồ khác không?**  
Có, nó hỗ trợ line, bar, pie, scatter, radar và nhiều loại biểu đồ khác.

**Q7: Tôi có thể tạo biểu đồ trong môi trường server không có giao diện không?**  
Thư viện hoạt động đầy đủ trong các kịch bản server‑side; không cần UI.

## Tài Nguyên

- **Tài Liệu**: Khám phá chi tiết API tại [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Tải Về**: Truy cập các bản phát hành Aspose.Slides [tại đây](https://releases.aspose.com/slides/java/)  
- **Mua Bản Quyền**: Mua giấy phép để mở toàn bộ tính năng tại [Mua Aspose](https://purchase.aspose.com/buy)  
- **Bản Dùng Thử & Giấy Phép Tạm Thời**: Bắt đầu với bản dùng thử miễn phí hoặc yêu cầu giấy phép tạm thời [tại đây](https://releases.aspose.com/slides/java/)  

Bằng cách làm theo hướng dẫn này, bạn đã sẵn sàng để tạo các biểu đồ hộp‑râu sâu sắc trong các ứng dụng Java và nhúng chúng trực tiếp vào các bản trình bày PowerPoint. Chúc bạn lập trình vui vẻ!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-03-02  
**Đã kiểm tra với:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Tác giả:** Aspose