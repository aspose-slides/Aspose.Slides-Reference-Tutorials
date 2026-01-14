---
date: '2026-01-14'
description: Tìm hiểu cách tạo biểu đồ cột nhóm trong Java bằng Aspose.Slides. Hướng
  dẫn từng bước bao gồm tạo bản trình bày trống, thêm biểu đồ vào bản trình bày và
  quản lý các chuỗi.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Cách tạo biểu đồ cột nhóm trong Java với Aspose.Slides
url: /vi/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Làm Chủ Việc Tạo Biểu Đồ trong Java với Aspose.Slides

## Cách Tạo và Quản Lý Biểu Đồ Sử Dụng Aspose.Slides cho Java

### Giới thiệu
Việc tạo các bản trình bày động thường đòi hỏi việc trực quan hoá dữ liệu bằng biểu đồ. Với **Aspose.Slides for Java**, bạn có thể dễ dàng **tạo biểu đồ cột nhóm** và quản lý nhiều loại biểu đồ, nâng cao cả độ rõ ràng và tác động. Tutorial này sẽ hướng dẫn bạn tạo một bản trình bày trống, thêm một biểu đồ cột nhóm, quản lý series, và tùy chỉnh việc đảo ngược các điểm dữ liệu — tất cả đều sử dụng Aspose.Slides for Java.

**Bạn sẽ học được:**
- Cách thiết lập Aspose.Slides cho Java.
- Các bước **tạo bản trình bày trống** và thêm biểu đồ vào bản trình bày.
- Kỹ thuật quản lý series biểu đồ và các điểm dữ liệu một cách hiệu quả.
- Phương pháp đảo ngược có điều kiện các điểm dữ liệu âm để cải thiện việc hiển thị.
- Cách lưu bản trình bày một cách an toàn.

Hãy bắt đầu với các yêu cầu trước khi tiến hành.

## Câu trả lời nhanh
- **Lớp chính để bắt đầu là gì?** `Presentation` từ `com.aspose.slides`.
- **Kiểu biểu đồ nào tạo biểu đồ cột nhóm?** `ChartType.ClusteredColumn`.
- **Làm thế nào để thêm biểu đồ vào một slide?** Sử dụng `addChart()` trên bộ sưu tập shape của slide.
- **Bạn có thể đảo ngược các giá trị âm không?** Có, bằng cách dùng `invertIfNegative(true)` trên một data point.
- **Phiên bản yêu cầu là gì?** Aspose.Slides cho Java 25.4 hoặc mới hơn.

## Biểu đồ cột nhóm là gì?
Biểu đồ cột nhóm hiển thị nhiều series dữ liệu cạnh nhau cho mỗi danh mục, giúp so sánh giá trị giữa các nhóm một cách lý tưởng. Aspose.Slides cho phép bạn tạo biểu đồ này bằng lập trình mà không cần mở PowerPoint.

## Tại sao nên sử dụng Aspose.Slides cho Java để thêm biểu đồ vào bản trình bày?
- **Kiểm soát toàn diện** dữ liệu biểu đồ, giao diện và bố cục.
- **Không cần cài đặt Office** trên máy chủ.
- **Hỗ trợ tất cả các loại biểu đồ chính**, bao gồm biểu đồ cột nhóm.
- **Dễ dàng tích hợp** với các dự án Maven/Gradle.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn có những thứ sau:

1. **Thư viện cần thiết:**  
   - Aspose.Slides cho Java (phiên bản 25.4 hoặc mới hơn).

2. **Yêu cầu thiết lập môi trường:**  
   - Phiên bản JDK tương thích (ví dụ, JDK 16).  
   - Maven hoặc Gradle đã được cài đặt nếu bạn muốn quản lý phụ thuộc.

3. **Kiến thức nền:**  
   - Hiểu biết cơ bản về lập trình Java.  
   - Quen thuộc với việc quản lý phụ thuộc trong môi trường phát triển của bạn.

## Cài đặt Aspose.Slides cho Java
Để bắt đầu sử dụng Aspose.Slides, thực hiện các bước sau:

**Cài đặt Maven:**  
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Cài đặt Gradle:**  
Thêm dòng sau vào tệp `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải trực tiếp:**  
Hoặc, tải phiên bản mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Mua giấy phép
- **Dùng thử miễn phí:** Bạn có thể bắt đầu với bản dùng thử miễn phí để khám phá các tính năng.  
- **Giấy phép tạm thời:** Nhận giấy phép tạm thời để có quyền truy cập đầy đủ trong thời gian đánh giá.  
- **Mua bản quyền:** Xem xét mua nếu bạn thấy nó phù hợp với nhu cầu lâu dài của mình.

### Khởi tạo cơ bản
Dưới đây là đoạn mã tối thiểu cần thiết để tạo một thể hiện của bản trình bày mới:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Hướng dẫn triển khai
Bây giờ, chúng ta sẽ chia nhỏ mỗi tính năng thành các bước dễ quản lý.

### Tạo bản trình bày với biểu đồ cột nhóm
#### Tổng quan
Phần này trình bày cách **tạo bản trình bày trống**, thêm một **biểu đồ cột nhóm**, và đặt nó trên slide đầu tiên.

**Các bước:**
1. **Khởi tạo đối tượng Presentation** – tạo một `Presentation` mới.
2. **Thêm biểu đồ cột nhóm** – gọi `addChart()` với kiểu và kích thước phù hợp.

**Ví dụ mã:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Quản lý series biểu đồ
#### Tổng quan
Tìm hiểu cách xóa bất kỳ series mặc định nào, thêm một series mới và điền dữ liệu với cả giá trị dương và âm.

**Các bước:**
1. **Xóa series hiện có** – loại bỏ bất kỳ dữ liệu đã được điền sẵn.
2. **Thêm series mới** – sử dụng ô trong workbook làm tên series.
3. **Chèn các điểm dữ liệu** – thêm các giá trị, bao gồm cả âm, để minh họa việc đảo ngược sau này.

**Ví dụ mã:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Đảo ngược các điểm dữ liệu của series dựa trên điều kiện
#### Tổng quan
Mặc định, Aspose.Slides có thể đảo ngược các giá trị âm. Bạn có thể kiểm soát hành vi này toàn cục và từng điểm dữ liệu.

**Các bước:**
1. **Thiết lập đảo ngược toàn cục** – tắt việc tự động đảo ngược cho toàn bộ series.
2. **Áp dụng đảo ngược có điều kiện** – bật đảo ngược chỉ cho các điểm âm cụ thể.

**Ví dụ mã:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| Biểu đồ hiển thị trống | Đảm bảo chỉ số slide (`0`) tồn tại và kích thước biểu đồ nằm trong giới hạn slide. |
| Giá trị âm không được đảo ngược | Kiểm tra `invertIfNegative(false)` đã được đặt trên series và `invertIfNegative(true)` trên điểm dữ liệu cụ thể. |
| Lỗi giấy phép | Áp dụng giấy phép Aspose hợp lệ trước khi tạo đối tượng `Presentation`. |

## Câu hỏi thường gặp

**Hỏi: Tôi có thể thêm các loại biểu đồ khác ngoài cột nhóm không?**  
**Đáp:** Có, Aspose.Slides hỗ trợ các loại biểu đồ đường, tròn, thanh, khu vực và nhiều loại biểu đồ khác.

**Hỏi: Tôi có cần giấy phép cho việc phát triển không?**  
**Đáp:** Bản dùng thử miễn phí đủ cho việc đánh giá, nhưng cần giấy phép thương mại cho việc sử dụng trong môi trường sản xuất.

**Hỏi: Làm sao để xuất biểu đồ dưới dạng hình ảnh?**  
**Đáp:** Sử dụng `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` sau khi render.

**Hỏi: Có thể tùy chỉnh kiểu dáng biểu đồ (màu sắc, phông chữ) không?**  
**Đáp:** Chắc chắn. Mỗi `IChartSeries` và `IChartDataPoint` đều cung cấp các thuộc tính kiểu dáng.

**Hỏi: Nếu tôi muốn thêm biểu đồ vào một tệp PPTX đã tồn tại thì sao?**  
**Đáp:** Tải tệp bằng `new Presentation("existing.pptx")`, sau đó thêm biểu đồ vào slide mong muốn.

## Kết luận
Trong tutorial này, bạn đã học cách **tạo biểu đồ cột nhóm** trong Java, quản lý series và đảo ngược có điều kiện các điểm dữ liệu âm bằng Aspose.Slides. Với những kỹ thuật này, bạn có thể xây dựng các bản trình bày hấp dẫn, dựa trên dữ liệu một cách lập trình.

**Bước tiếp theo:**
- Thử nghiệm các loại biểu đồ khác do Aspose.Slides cho Java cung cấp.  
- Tìm hiểu các tùy chọn kiểu dáng nâng cao như màu tùy chỉnh, nhãn dữ liệu và định dạng trục.  
- Tích hợp việc tạo biểu đồ vào quy trình báo cáo hoặc phân tích của bạn.

---

Cập nhật lần cuối: 2026-01-14  
Kiểm tra với: Aspose.Slides cho Java 25.4 (jdk16 classifier)  
Tác giả: Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}