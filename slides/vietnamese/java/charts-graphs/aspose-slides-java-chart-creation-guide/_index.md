---
date: '2026-02-12'
description: Tìm hiểu cách tạo biểu đồ và quản lý biểu đồ bằng Aspose.Slides cho Java.
  Hướng dẫn này cho thấy cách tạo biểu đồ cột nhóm, xử lý chuỗi dữ liệu và tùy chỉnh
  trực quan hoá.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Cách tạo biểu đồ trong Java với Aspose.Slides: Hướng dẫn toàn diện'
url: /vi/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ trong Java với Aspose.Slides

## Cách tạo biểu đồ trong Java: Giới thiệu
Việc tạo các bản trình bày động thường đòi hỏi việc trực quan hoá dữ liệu bằng các biểu đồ. Với **Aspose.Slides for Java**, bạn có thể dễ dàng **tạo biểu đồ** objects, nâng cao độ rõ ràng và tạo ấn tượng mạnh hơn với khán giả. Hướng dẫn này sẽ chỉ cho bạn cách cài đặt thư viện, thêm một **create clustered column chart**, quản lý series và đảo ngược các điểm dữ liệu âm một cách có điều kiện.

**Bạn sẽ học được**
- Cách cài đặt Aspose.Slides for Java.
- Các bước **create clustered column chart** trong bản trình bày của bạn.
- Kỹ thuật quản lý series và các điểm dữ liệu của biểu đồ.
- Phương pháp đảo ngược có điều kiện các điểm dữ liệu âm để hiển thị tốt hơn.
- Cách lưu bản trình bày một cách an toàn.

### Quick Answers
- **Thư viện nào được sử dụng?** Aspose.Slides for Java.
- **Loại biểu đồ nào được minh họa?** Clustered column chart.
- **Tôi có thể đảo ngược các giá trị âm không?** Có, sử dụng `invertIfNegative`.
- **Phiên bản Java nào yêu cầu?** JDK 16 hoặc mới hơn.
- **Cần giấy phép cho môi trường sản xuất không?** Có, một giấy phép Aspose hợp lệ.

## Biểu đồ cột nhóm là gì?
Biểu đồ cột nhóm hiển thị nhiều series dữ liệu cạnh nhau cho mỗi danh mục, giúp dễ dàng so sánh các giá trị giữa các nhóm. Nó lý tưởng cho báo cáo tài chính, bảng điều khiển bán hàng và bất kỳ trường hợp nào bạn cần đối chiếu nhiều chỉ số.

## Tại sao nên sử dụng Aspose.Slides để tạo biểu đồ?
- **Kiểm soát đầy đủ** về giao diện biểu đồ mà không cần dựa vào UI của PowerPoint.
- **Tạo biểu đồ bằng mã** cho phép tự động hoá quy trình báo cáo.
- **Hỗ trợ đa nền tảng** đảm bảo mã của bạn chạy trên bất kỳ hệ thống nào hỗ trợ Java.
- **API phong phú** cho phép tùy chỉnh chi tiết (màu sắc, nhãn dữ liệu, đảo ngược, v.v.).

## Yêu cầu trước
1. **Thư viện cần thiết**
   - Aspose.Slides for Java (phiên bản 25.4 hoặc mới hơn).

2. **Môi trường**
   - JDK 16 hoặc mới hơn.
   - Maven hoặc Gradle để quản lý phụ thuộc.

3. **Kiến thức**
   - Lập trình Java cơ bản.
   - Quen thuộc với công cụ xây dựng (Maven/Gradle).

## Cài đặt Aspose.Slides cho Java
### Cài đặt Maven
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Cài đặt Gradle
Thêm dòng sau vào tệp `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Hoặc, tải phiên bản mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Mua giấy phép
- **Dùng thử miễn phí:** Khám phá các tính năng mà không cần giấy phép.
- **Giấy phép tạm thời:** Sử dụng trong quá trình đánh giá.
- **Giấy phép đầy đủ:** Mua để triển khai trong môi trường sản xuất.

### Khởi tạo cơ bản
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Hướng dẫn từng bước

### Bước 1: Tạo một Presentation và Thêm biểu đồ cột nhóm
Trong bước này, chúng ta **tạo biểu đồ** objects và đặt một **create clustered column chart** lên slide đầu tiên.

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

### Bước 2: Quản lý Series của biểu đồ
Bây giờ chúng ta sẽ xóa mọi series mặc định, thêm một series mới và điền dữ liệu cả giá trị dương và âm.

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

### Bước 3: Đảo ngược các điểm dữ liệu âm một cách có điều kiện
Mặc định, Aspose.Slides không đảo ngược các giá trị âm. Chúng ta sẽ bật tính năng đảo ngược chỉ cho những điểm cần thiết.

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

### Những lỗi thường gặp & Mẹo
- **Quên giải phóng đối tượng `Presentation`?** Luôn gọi `dispose()` trong khối `finally` để giải phóng tài nguyên gốc.
- **Giá trị âm không được đảo ngược?** Đảm bảo bạn gọi `invertIfNegative(true)` **sau** khi thêm điểm dữ liệu.
- **Vấn đề kích thước biểu đồ:** Các tọa độ (X, Y) và kích thước (width, height) tính bằng điểm; điều chỉnh chúng để phù hợp với bố cục slide.

## Câu hỏi thường gặp

**Q: Tôi có thể tạo các loại biểu đồ khác bằng cùng cách tiếp cận không?**  
A: Có, chỉ cần thay `ChartType.ClusteredColumn` bằng bất kỳ giá trị enum `ChartType` nào khác (ví dụ, `Line`, `Pie`).

**Q: Tôi có cần giấy phép cho bản dựng phát triển không?**  
A: Một giấy phép tạm thời hoặc đánh giá là bắt buộc để truy cập đầy đủ tính năng; nếu không, thư viện sẽ chạy ở chế độ dùng thử với hạn chế watermark.

**Q: Làm sao xuất bản trình bày ra PDF sau khi thêm biểu đồ?**  
A: Sử dụng `pres.save("output.pdf", SaveFormat.Pdf);` sau khi hoàn tất thao tác với biểu đồ.

**Q: Có thể định dạng riêng từng cột (màu, viền) không?**  
A: Có, mỗi `IChartDataPoint` cung cấp các tùy chọn định dạng như `getFillFormat().setFillType(FillType.Solid)` và `getLineFormat()`.

**Q: Nếu cần cập nhật dữ liệu biểu đồ sau khi đã lưu bản trình bày thì sao?**  
A: Tải lại bản trình bày bằng `new Presentation("file.pptx")`, sửa đổi dữ liệu biểu đồ và lưu lại.

**Cập nhật lần cuối:** 2026-02-12  
**Kiểm tra với:** Aspose.Slides for Java 25.4 (JDK 16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}