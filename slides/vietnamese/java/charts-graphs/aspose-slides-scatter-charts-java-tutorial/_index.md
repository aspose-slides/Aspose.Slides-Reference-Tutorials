---
"date": "2025-04-17"
"description": "Tìm hiểu cách tạo biểu đồ phân tán động bằng Aspose.Slides for Java. Nâng cao bài thuyết trình của bạn bằng các tính năng biểu đồ có thể tùy chỉnh."
"title": "Tạo và tùy chỉnh biểu đồ phân tán trong Java với Aspose.Slides"
"url": "/vi/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo và tùy chỉnh biểu đồ phân tán trong Java với Aspose.Slides

Cải thiện bài thuyết trình của bạn bằng cách thêm biểu đồ phân tán động sử dụng Java với Aspose.Slides. Hướng dẫn toàn diện này sẽ hướng dẫn bạn thiết lập thư mục, khởi tạo bài thuyết trình, tạo biểu đồ phân tán, quản lý dữ liệu biểu đồ, tùy chỉnh loại chuỗi và điểm đánh dấu, và lưu công việc của bạn—tất cả đều dễ dàng.

**Những gì bạn sẽ học được:**
- Thiết lập thư mục để lưu trữ các tập tin trình bày
- Khởi tạo và thao tác các bài thuyết trình bằng Aspose.Slides
- Tạo biểu đồ phân tán trên slide
- Quản lý và thêm dữ liệu vào chuỗi biểu đồ
- Tùy chỉnh các loại biểu đồ và đánh dấu
- Lưu bài thuyết trình của bạn với các sửa đổi

Hãy bắt đầu bằng cách đảm bảo bạn có đủ các điều kiện tiên quyết cần thiết.

## Điều kiện tiên quyết

Để làm theo hướng dẫn này, hãy đảm bảo bạn có:
- **Aspose.Slides cho Java**: Yêu cầu phiên bản 25.4 trở lên.
- **Bộ phát triển Java (JDK)**: Cần có JDK 8 trở lên.
- Kiến thức cơ bản về lập trình Java và quen thuộc với các công cụ xây dựng Maven hoặc Gradle.

## Thiết lập Aspose.Slides cho Java

Trước khi bắt đầu viết mã, hãy tích hợp Aspose.Slides vào dự án của bạn bằng một trong các phương pháp sau:

### Maven
Bao gồm sự phụ thuộc này trong `pom.xml` tài liệu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Tốt nghiệp
Thêm dòng này vào `build.gradle` tài liệu:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ngoài ra, hãy tải xuống Aspose.Slides mới nhất cho Java từ [Aspose phát hành](https://releases.aspose.com/slides/java/).

#### Mua lại giấy phép
- **Dùng thử miễn phí**:Bắt đầu với bản dùng thử miễn phí 30 ngày để khám phá các tính năng.
- **Giấy phép tạm thời**: Xin giấy phép tạm thời để thử nghiệm mở rộng.
- **Mua**: Mua giấy phép để được truy cập và hỗ trợ đầy đủ.

Bây giờ, hãy khởi tạo Aspose.Slides trong ứng dụng Java của bạn bằng cách thêm các lệnh nhập cần thiết như được hiển thị bên dưới.

## Hướng dẫn thực hiện

### Thiết lập thư mục
Đầu tiên, hãy đảm bảo rằng thư mục của chúng tôi tồn tại để lưu trữ các tệp trình bày. Bước này ngăn ngừa lỗi trong quá trình lưu tệp.

#### Tạo thư mục nếu nó không tồn tại
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Tạo thư mục
    new File(dataDir).mkdirs();
}
```
Đoạn mã này kiểm tra thư mục được chỉ định và tạo thư mục đó nếu thư mục đó không tồn tại. Nó sử dụng `File.exists()` để xác minh sự hiện diện và `File.mkdirs()` để tạo thư mục.

### Khởi tạo trình bày

Tiếp theo, khởi tạo đối tượng trình bày nơi bạn sẽ thêm biểu đồ phân tán.

#### Khởi tạo bài thuyết trình của bạn
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Đây, `new Presentation()` tạo một bản trình bày trống. Chúng ta truy cập vào slide đầu tiên để làm việc trực tiếp với nó.

### Tạo biểu đồ
Tiếp theo là tạo biểu đồ phân tán trên trang chiếu đã khởi tạo của chúng ta.

#### Thêm biểu đồ phân tán vào trang chiếu
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Đoạn mã này thêm biểu đồ phân tán với các đường trơn vào slide đầu tiên. Các tham số xác định vị trí và kích thước của biểu đồ.

### Quản lý dữ liệu biểu đồ
Bây giờ chúng ta hãy quản lý dữ liệu biểu đồ bằng cách xóa mọi chuỗi hiện có và thêm chuỗi mới.

#### Quản lý chuỗi biểu đồ
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Thêm chuỗi mới vào biểu đồ
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Phần này xóa dữ liệu hiện có và thêm hai chuỗi mới vào biểu đồ phân tán của chúng tôi.

### Thêm Điểm Dữ Liệu cho Chuỗi Phân Tán
Để trực quan hóa dữ liệu, chúng tôi thêm điểm vào từng chuỗi trong biểu đồ phân tán.

#### Thêm Điểm Dữ Liệu
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Chúng tôi sử dụng `addDataPointForScatterSeries()` để thêm các điểm dữ liệu vào chuỗi đầu tiên của chúng tôi. Các tham số xác định giá trị X và Y.

### Loại sê-ri và sửa đổi điểm đánh dấu
Tùy chỉnh giao diện biểu đồ của bạn bằng cách thay đổi loại và kiểu đánh dấu trong mỗi chuỗi.

#### Tùy chỉnh Series
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Sửa đổi loạt thứ hai
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Những thay đổi này điều chỉnh loại chuỗi để sử dụng các đường thẳng và điểm đánh dấu. Chúng tôi cũng thiết lập kích thước điểm đánh dấu và ký hiệu để phân biệt trực quan.

### Lưu Trình Bày
Cuối cùng, hãy lưu bài thuyết trình của bạn với mọi sửa đổi đã thực hiện.

#### Lưu bài thuyết trình của bạn
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Sử dụng `SaveFormat.Pptx` để chỉ định định dạng PowerPoint để lưu tệp của bạn. Bước này rất quan trọng để giữ nguyên mọi thay đổi.

## Ứng dụng thực tế
Sau đây là một số trường hợp sử dụng thực tế:
1. **Phân tích tài chính**: Sử dụng biểu đồ phân tán để hiển thị xu hướng cổ phiếu theo thời gian.
2. **Nghiên cứu khoa học**: Biểu diễn các điểm dữ liệu thực nghiệm để phân tích.
3. **Quản lý dự án**: Trực quan hóa phân bổ tài nguyên và số liệu tiến độ.

Tích hợp Aspose.Slides vào hệ thống của bạn cho phép bạn tự động hóa việc tạo báo cáo, nâng cao năng suất và độ chính xác.

## Cân nhắc về hiệu suất
Để có hiệu suất tối ưu:
- Quản lý việc sử dụng bộ nhớ bằng cách xóa bài thuyết trình sau khi lưu.
- Sử dụng cấu trúc dữ liệu hiệu quả cho các tập dữ liệu lớn.
- Giảm thiểu các hoạt động tốn nhiều tài nguyên trong vòng lặp.

Các biện pháp tốt nhất đảm bảo thực hiện suôn sẻ ngay cả với các thao tác biểu đồ phức tạp.

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách thiết lập thư mục, khởi tạo bài thuyết trình Aspose.Slides, tạo và tùy chỉnh biểu đồ phân tán, quản lý dữ liệu chuỗi, sửa đổi điểm đánh dấu và lưu công việc của mình. Để khám phá thêm các khả năng của Aspose.Slides, hãy cân nhắc tìm hiểu sâu hơn về các tính năng nâng cao hơn như hoạt ảnh và chuyển tiếp slide.

**Các bước tiếp theo**:Thử nghiệm với các loại biểu đồ khác nhau hoặc tích hợp các kỹ thuật này vào một dự án Java lớn hơn.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi màu sắc của điểm đánh dấu?
Để thay đổi màu đánh dấu, hãy sử dụng `series.getMarker().getFillFormat().setFillColor(ColorObject)`, Ở đâu `ColorObject` là màu bạn mong muốn.

### Tôi có thể thêm nhiều hơn hai chuỗi vào biểu đồ phân tán không?
Có, bạn có thể thêm bao nhiêu chuỗi tùy ý bằng cách lặp lại quy trình thêm chuỗi và điểm dữ liệu mới.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}