---
date: '2026-03-04'
description: Tìm hiểu cách thêm các thanh lỗi tùy chỉnh vào biểu đồ bong bóng bằng
  Aspose.Slides cho Java. Hướng dẫn này bao gồm việc tạo biểu đồ, cấu hình thanh lỗi
  cho từng điểm và lưu bản trình bày.
keywords:
- Bubble Chart Java
- Custom Error Bars Aspose.Slides
- Java Data Visualization
title: Cách Thêm Thanh Lỗi Tùy Chỉnh vào Biểu Đồ Bọt trong Java bằng Aspose.Slides
url: /vi/java/charts-graphs/create-bubble-chart-error-bars-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Thêm Thanh Lỗi Tùy Chỉnh vào Biểu Đồ Bong Bóng trong Java Sử Dụng Aspose.Slides

Tạo ra các bản thuyết trình rõ ràng, dựa trên dữ liệu thường đòi hỏi phải vượt ra ngoài các biểu đồ đơn giản. Bằng cách học **cách thêm thanh lỗi tùy chỉnh** vào biểu đồ bong bóng, bạn cung cấp cho khán giả cái nhìn về độ biến đổi và mức độ tin cậy cho mỗi điểm dữ liệu. Trong hướng dẫn này, bạn sẽ thấy cách thiết lập dự án Java với Aspose.Slides, thêm biểu đồ bong bóng vào một slide, cấu hình thanh lỗi cho từng điểm, và cuối cùng lưu kết quả dưới dạng tệp PowerPoint.

## Câu trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.Slides for Java (phiên bản mới nhất).  
- **Loại biểu đồ nào hỗ trợ thanh lỗi tùy chỉnh?** Biểu đồ bong bóng (`ChartType.Bubble`).  
- **Có thể đặt thanh lỗi cho từng điểm dữ liệu không?** Có – sử dụng `ErrorBarsCustomValues` cho các giá trị cộng/trừ X/Y.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; giấy phép đầy đủ loại bỏ các giới hạn đánh giá.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một ví dụ cơ bản.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- **Java Development Kit (JDK):** Phiên bản 8 hoặc cao hơn.  
- **Aspose.Slides for Java:** Thêm thư viện vào dự án của bạn (xem các đoạn mã Maven/Gradle bên dưới).  
- **IDE:** IntelliJ IDEA, Eclipse, NetBeans, hoặc bất kỳ trình soạn thảo nào bạn thích.

### Thư viện và phụ thuộc cần thiết

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

Bạn cũng có thể tải JAR mới nhất từ trang phát hành chính thức: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Nhận giấy phép

- Bắt đầu với bản dùng thử miễn phí để khám phá tất cả các tính năng.  
- Yêu cầu giấy phép tạm thời để thử nghiệm không giới hạn.  
- Mua giấy phép chạy đầy đủ cho môi trường sản xuất.

## Cài đặt Aspose.Slides cho Java

Khi thư viện đã có trong classpath, khởi tạo một đối tượng presentation. Khối này tạo một canvas sạch sẽ cho biểu đồ.

```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Hướng dẫn triển khai

### Tính năng 1: Thêm biểu đồ vào slide và tạo biểu đồ bong bóng

**Tại sao lại thêm biểu đồ vào slide?**  
Nhúng một biểu đồ trực tiếp vào slide cho phép bạn giữ ngữ cảnh hình ảnh cùng với bất kỳ văn bản hoặc hình ảnh xung quanh nào, làm cho bản thuyết trình trở nên gắn kết hơn.

#### Step 1: Import Required Classes
```java
import com.aspose.slides.*;
```

#### Step 2: Add Bubble Chart to the First Slide
```java
// Access the first slide
ISlide slide = presentation.getSlides().get_Item(0);

// Create a bubble chart on the slide
IChart chart = slide.getShapes().addChart(
    ChartType.Bubble, 50, 50, 400, 300, true);
```
- `ChartType.Bubble` cho Aspose biết chúng ta muốn một biểu đồ bong bóng.  
- Các tọa độ `(50, 50)` và kích thước `(400, 300)` đặt biểu đồ một cách hợp lý trên slide.

### Tính năng 2: Cấu hình thanh lỗi

Thanh lỗi cung cấp cho người xem một dấu hiệu trực quan về độ tin cậy của mỗi điểm. Chúng ta sẽ làm cho chúng hiển thị và thiết lập chúng sử dụng các giá trị tùy chỉnh.

#### Step 3: Access the First Series
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Step 4: Enable and Set Custom Error Bars
```java
// Accessing error bar formats
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();

// Making error bars visible
errBarX.setVisible(true);
errBarY.setVisible(true);

// Setting custom value types for more detailed control
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

### Tính năng 3: Đặt thanh lỗi cho các điểm dữ liệu (Thanh lỗi cho mỗi điểm)

Bây giờ chúng ta sẽ gán các giá trị biên độ lỗi duy nhất cho mỗi bong bóng, minh họa **thanh lỗi cho mỗi điểm**.

#### Step 5: Configure Data Point Collection
```java
IChartDataPointCollection points = series.getDataPoints();

// Configuring custom values for error bars
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Loop through each data point
for (int i = 0; i < points.size(); i++) {
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```
*​Sử dụng các giá trị tùy chỉnh cho phép bạn xác định chính xác phạm vi lỗi cho mỗi bong bóng, điều này rất quan trọng cho các phân tích khoa học hoặc tài chính.*​

### Tính năng 4: Lưu bản trình bày

```java
String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";

// Saving the presentation
presentation.save(YOUR_DOCUMENT_DIRECTORY + "/ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

## Ứng dụng thực tiễn

Thêm thanh lỗi tùy chỉnh vào biểu đồ bong bóng có giá trị trong nhiều tình huống thực tế:

1. **Nghiên cứu khoa học:** Hiển thị độ không chắc chắn của đo lường cho mỗi kết quả thí nghiệm.  
2. **Phân tích kinh doanh:** Trực quan hóa phạm vi dự báo cho doanh số hoặc thị phần.  
3. **Giáo dục:** Minh họa các khái niệm thống kê như khoảng tin cậy.

## Các lưu ý về hiệu suất

- Giải phóng đối tượng `Presentation` kịp thời để giải phóng tài nguyên gốc.  
- Giới hạn số lượng điểm dữ liệu nếu bạn tạo biểu đồ hàng loạt; tập dữ liệu rất lớn có thể làm tăng thời gian render.  
- Tái sử dụng các đối tượng biểu đồ khi tạo nhiều slide để giảm tải.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **ErrorBarsCustomValues trả về `null`** | Series chưa có điểm dữ liệu nào. | Thêm điểm dữ liệu trước hoặc đảm bảo series đã được điền dữ liệu trước khi cấu hình thanh lỗi. |
| **Biểu đồ không hiển thị trên slide** | Kích thước biểu đồ được đặt ngoài giới hạn slide. | Điều chỉnh tọa độ X/Y và chiều rộng/chiều cao để phù hợp với kích thước slide. |
| **Lỗi giấy phép** | Sử dụng phiên bản dùng thử mà không có giấy phép hợp lệ. | Áp dụng giấy phép tạm thời hoặc đầy đủ trước khi lưu bản trình bày. |

## Câu hỏi thường gặp

**Hỏi: Aspose.Slides for Java là gì?**  
**Đáp:** Đó là một API mạnh mẽ cho phép bạn tạo, chỉnh sửa và chuyển đổi tệp PowerPoint một cách lập trình mà không cần Microsoft Office.

**Hỏi: Tôi có thể sử dụng Aspose.Slides mà không có giấy phép không?**  
**Đáp:** Có, bản dùng thử miễn phí hoạt động cho việc phát triển và thử nghiệm, nhưng nó sẽ thêm watermark đánh giá và giới hạn một số tính năng.

**Hỏi: Làm thế nào để cập nhật lên phiên bản mới nhất của Aspose.Slides?**  
**Đáp:** Kiểm tra trang phát hành chính thức của [Aspose](https://releases.aspose.com/slides/java/) và cập nhật phụ thuộc Maven/Gradle của bạn cho phù hợp.

**Hỏi: Tại sao lại thêm thanh lỗi tùy chỉnh vào biểu đồ bong bóng?**  
**Đáp:** Chúng truyền tải độ biến đổi hoặc mức độ tin cậy cho mỗi điểm dữ liệu, biến một biểu đồ phân tán đơn giản thành một câu chuyện phong phú và thông tin hơn.

**Hỏi: Tôi có thể tùy chỉnh các loại biểu đồ khác với thanh lỗi không?**  
**Đáp:** Chắc chắn. Aspose.Slides hỗ trợ thanh lỗi cho biểu đồ đường, cột, thanh và nhiều loại biểu đồ khác.

---

**Cập nhật lần cuối:** 2026-03-04  
**Kiểm thử với:** Aspose.Slides for Java 25.4 (jdk16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}