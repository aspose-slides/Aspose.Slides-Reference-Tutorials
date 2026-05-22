---
date: '2026-03-23'
description: Tìm hiểu cách sử dụng Aspose.Slides cho Java để tạo biểu đồ đường có
  dấu đánh dấu, thêm một chuỗi thứ hai và xử lý dữ liệu null trong các bản trình bày
  PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Cách sử dụng Aspose.Slides cho Java: Tạo biểu đồ đường với các dấu đánh dấu
  mặc định'
url: /vi/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ đường với các điểm đánh dấu mặc định bằng Aspose.Slides cho Java

## Giới thiệu
Nếu bạn đang tự hỏi **cách sử dụng Aspose** để tự động tạo PowerPoint, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng ta sẽ đi qua cách xây dựng một **biểu đồ đường có điểm đánh dấu**, thêm một chuỗi thứ hai và xử lý dữ liệu null — tất cả đều bằng Aspose.Slides cho Java. Khi kết thúc, bạn sẽ có một đoạn mã sẵn sàng chạy, tạo ra một biểu đồ chuyên nghiệp mà không cần mở PowerPoint thủ công.

### Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Slides cho Java (khuyến nghị phiên bản mới nhất)  
- **Tôi có thể thêm chuỗi thứ hai không?** Có – API cho phép bạn dễ dàng thêm nhiều chuỗi.  
- **Các điểm dữ liệu null được xử lý như thế nào?** Sử dụng `null` trong giá trị ô; biểu đồ sẽ bỏ qua điểm đó.  
- **Có cần Maven không?** Maven hoặc Gradle đều hoạt động; xem phần *aspose slides maven* bên dưới.  
- **Cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần cho môi trường sản xuất.

## Cách sử dụng Aspose.Slides cho Java để tạo biểu đồ đường
Việc tạo biểu đồ bằng mã giúp bạn tiết kiệm hàng giờ định dạng thủ công và đảm bảo tính nhất quán trong các bài thuyết trình. Dù bạn đang xây dựng tính năng **tạo biểu đồ PowerPoint** trong công cụ báo cáo hay tạo slide nhanh chóng, Aspose.Slides cho phép bạn kiểm soát toàn bộ từ mã Java.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo môi trường phát triển của bạn đã sẵn sàng:

1. **Thư viện & Phụ thuộc**
   - Thư viện Aspose.Slides cho Java (phiên bản 25.4 được khuyến nghị) – đáp ứng kịch bản *aspose slides maven*.
   - Java Development Kit (JDK) phiên bản 16 trở lên.
2. **Cài đặt môi trường**
   - IDE hỗ trợ Maven hoặc Gradle.
   - Tệp giấy phép Aspose hợp lệ nếu bạn chạy mã ngoài thời gian dùng thử.
3. **Kiến thức nền**
   - Lập trình Java cơ bản.
   - Quen thuộc với các tệp cấu hình Maven hoặc Gradle.

## Cài đặt Aspose.Slides cho Java
### Maven
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Thêm đoạn này vào tệp `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Tải trực tiếp
Hoặc bạn có thể tải phiên bản mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Các bước lấy giấy phép:**
- Đối với bản dùng thử miễn phí, truy cập [trang dùng thử miễn phí](https://releases.aspose.com/slides/java/).
- Để nhận giấy phép tạm thời, vào [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
- Mua giấy phép đầy đủ qua [cổng mua hàng](https://purchase.aspose.com/buy).

**Khởi tạo cơ bản:**
Dưới đây là cách khởi tạo Aspose.Slides trong ứng dụng Java của bạn:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Bây giờ, chúng ta cùng bắt đầu tạo biểu đồ!

## Hướng dẫn triển khai
### Tính năng 1: Tạo biểu đồ với các điểm đánh dấu mặc định
Phần này minh họa cách tạo một **biểu đồ đường có điểm đánh dấu**, lý tưởng để làm nổi bật các điểm dữ liệu riêng lẻ trên đường xu hướng.

#### Thêm biểu đồ đường
Để thêm một biểu đồ đường có điểm đánh dấu:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Xóa chuỗi và danh mục
Để bắt đầu lại từ đầu:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Tính năng 2: Thêm chuỗi và danh mục
Thêm chuỗi và danh mục là bước quan trọng để cung cấp dữ liệu có ý nghĩa cho biểu đồ.

#### Tạo chuỗi mới
Để thêm một chuỗi mới có tên "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Điền danh mục và điểm dữ liệu
Để thêm danh mục và các điểm dữ liệu tương ứng:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Tính năng 3: Thêm chuỗi thứ hai và điền dữ liệu
Thêm chuỗi bổ sung giúp phân tích trực quan sâu hơn.

#### Tạo và điền dữ liệu cho chuỗi thứ hai
Để thêm "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Tính năng 4: Cấu hình chú giải biểu đồ
Cấu hình chú giải giúp biểu đồ dễ đọc hơn, đặc biệt khi bạn **thêm chuỗi thứ hai**.

#### Điều chỉnh cài đặt chú giải
Để cấu hình:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Tính năng 5: Lưu bản trình chiếu
Khi biểu đồ đã sẵn sàng, bạn sẽ muốn **tạo file biểu đồ PowerPoint** để chia sẻ hoặc chỉnh sửa thêm.

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Ứng dụng thực tiễn
1. **Báo cáo doanh nghiệp:** Sử dụng biểu đồ đường có điểm đánh dấu để minh họa xu hướng tài chính qua các quý.  
2. **Phân tích dữ liệu:** Trực quan hoá dữ liệu thí nghiệm, mỗi điểm đánh dấu nhấn mạnh một phép đo.  
3. **Tài liệu giáo dục:** Xây dựng slide giảng dạy thể hiện các thay đổi từng bước trong một quy trình.  
4. **Quản lý dự án:** Theo dõi các mốc quan trọng trên dòng thời gian với các điểm đánh dấu riêng cho các ngày trọng yếu.  
5. **Bài thuyết trình marketing:** Hiển thị các đỉnh hiệu suất chiến dịch bằng các ký hiệu điểm đánh dấu rõ ràng.

## Các vấn đề thường gặp và giải pháp
- **Điểm dữ liệu null gây lỗi:** Truyền `null` làm giá trị ô (như ví dụ) – Aspose sẽ tự động bỏ qua điểm đó.  
- **Biểu đồ hiển thị mà không có điểm đánh dấu:** Đảm bảo bạn dùng `ChartType.LineWithMarkers` thay vì `ChartType.Line`.  
- **Chú giải chồng lên dữ liệu:** Đặt `chart.getLegend().setOverlay(false)` để giữ chú giải riêng biệt.

## Câu hỏi thường gặp

**H: Tôi có thể dùng cách này để tạo biểu đồ trong dịch vụ web không?**  
Đ: Hoàn toàn có thể. Thư viện hoạt động trong bất kỳ môi trường Java nào, kể cả các ứng dụng phía máy chủ.

**H: Tôi có cần giấy phép cho bản dựng phát triển không?**  
Đ: Bản dùng thử miễn phí đủ cho phát triển và kiểm thử. Giấy phép thương mại cần cho môi trường sản xuất.

**H: Aspose xử lý tập dữ liệu lớn như thế nào?**  
Đ: API truyền dữ liệu một cách hiệu quả; tuy nhiên, nên giữ số lượng điểm dữ liệu ở mức hợp lý để tránh kích thước tệp quá lớn.

**H: Có hỗ trợ các loại biểu đồ khác không?**  
Đ: Có – Aspose.Slides hỗ trợ biểu đồ cột, bánh, scatter và nhiều loại khác.

**H: Tôi có thể tùy chỉnh hình dạng và màu sắc của điểm đánh dấu không?**  
Đ: Bạn có thể thay đổi định dạng điểm đánh dấu qua thuộc tính `Marker` của mỗi điểm dữ liệu.

## Kết luận
Bây giờ bạn đã biết **cách sử dụng Aspose** để tạo một biểu đồ đường với các điểm đánh dấu mặc định, thêm chuỗi thứ hai, xử lý dữ liệu null và lưu kết quả dưới dạng tệp PowerPoint. Những kỹ thuật này giúp bạn tự động hoá việc tạo báo cáo, nâng cao khả năng kể chuyện dữ liệu và duy trì tính nhất quán cho các bài thuyết trình.

Để tìm hiểu sâu hơn, hãy khám phá [tài liệu chính thức](https://docs.aspose.com/slides/java/) hoặc tham gia các diễn đàn cộng đồng như Stack Overflow.

---

**Cập nhật lần cuối:** 2026-03-23  
**Kiểm thử với:** Aspose.Slides cho Java 25.4 (jdk16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}