---
"date": "2025-04-17"
"description": "Tìm hiểu cách tạo và cấu hình các bài thuyết trình động với biểu đồ trong Java bằng Aspose.Slides. Làm chủ việc thêm, tùy chỉnh và lưu các bài thuyết trình hiệu quả."
"title": "Tạo bài thuyết trình Java có biểu đồ bằng Aspose.Slides cho Java"
"url": "/vi/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo và cấu hình bản trình bày có biểu đồ bằng Aspose.Slides cho Java

## Giới thiệu

Tạo các bài thuyết trình động truyền tải dữ liệu hiệu quả là điều cần thiết trong môi trường kinh doanh phát triển nhanh như hiện nay. Cho dù bạn đang chuẩn bị báo cáo tài chính hay trình bày số liệu dự án, việc thêm biểu đồ có thể tăng đáng kể tác động của bài thuyết trình. Hướng dẫn này hướng dẫn bạn cách tạo và cấu hình bài thuyết trình bằng biểu đồ cột xếp chồng 3D bằng Aspose.Slides for Java, một thư viện mạnh mẽ được thiết kế để xử lý các bài thuyết trình theo chương trình.

**Những gì bạn sẽ học được:**
- Cách tạo bài thuyết trình mới
- Thêm và cấu hình biểu đồ trong slide
- Tùy chỉnh dữ liệu biểu đồ và giao diện
- Lưu bài thuyết trình của bạn một cách hiệu quả

Bạn đã sẵn sàng để thành thạo việc tạo các bài thuyết trình hấp dẫn bằng Java chưa? Hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã nắm được những điều kiện tiên quyết sau:

- **Thư viện và các phụ thuộc**: Aspose.Slides cho Java phải được cài đặt.
- **Thiết lập môi trường**: Làm việc trong môi trường Java (khuyến khích sử dụng JDK 16 trở lên).
- **Cơ sở tri thức**: Việc quen thuộc với các khái niệm lập trình Java cơ bản sẽ rất có lợi.

## Thiết lập Aspose.Slides cho Java

### Cài đặt

Để tích hợp Aspose.Slides vào dự án của bạn, hãy làm theo các bước sau:

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Tốt nghiệp**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải xuống trực tiếp**: Hoặc tải xuống phiên bản mới nhất từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

### Mua lại giấy phép
- **Dùng thử miễn phí**: Bắt đầu bằng bản dùng thử miễn phí để khám phá các tính năng.
- **Giấy phép tạm thời**: Xin giấy phép tạm thời để thử nghiệm mở rộng.
- **Mua**: Có được giấy phép đầy đủ để sử dụng cho mục đích thương mại.

Sau khi cài đặt, hãy khởi tạo thư viện trong môi trường Java của bạn bằng cách tạo một phiên bản của `Presentation` lớp. Điều này thiết lập nền tảng để thêm biểu đồ và các yếu tố khác vào bài thuyết trình của bạn.

## Hướng dẫn thực hiện

### Tạo và cấu hình bài thuyết trình bằng biểu đồ

#### Tổng quan
Tạo bài thuyết trình từ đầu thật đơn giản với Aspose.Slides. Trong phần này, chúng ta sẽ thêm biểu đồ cột xếp chồng 3D vào slide đầu tiên của bài thuyết trình.

**Các bước thực hiện:**

1. **Khởi tạo đối tượng trình bày**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Khởi tạo một đối tượng Presentation mới
           Presentation presentation = new Presentation();
           
           // Truy cập trang chiếu đầu tiên trong bài thuyết trình
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Thêm biểu đồ cột xếp chồng 3D vào trang chiếu ở vị trí (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Giải thích các tham số**:
   - `ChartType.StackedColumn3D`: Chỉ định loại biểu đồ.
   - Vị trí và kích thước `(0, 0, 500, 500)`: Xác định vị trí biểu đồ xuất hiện trên trang chiếu.

### Cấu hình dữ liệu biểu đồ

#### Tổng quan
Để làm cho biểu đồ của bạn có ý nghĩa, hãy định cấu hình chuỗi dữ liệu và danh mục của nó. Phần này trình bày cách thêm các điểm dữ liệu cụ thể vào biểu đồ của bạn.

**Các bước thực hiện:**

1. **Sổ làm việc dữ liệu của Access Chart**

   ```java
   public static void configureChartData(IChart chart) {
       // Đặt chỉ mục của bảng tính có chứa dữ liệu biểu đồ
       int defaultWorksheetIndex = 0;
       
       // Truy cập vào sổ làm việc dữ liệu của biểu đồ
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Thêm hai chuỗi có tên
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Thêm ba danh mục
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Đặt Thuộc tính Rotation3D cho Biểu đồ

#### Tổng quan
Tăng cường sức hấp dẫn trực quan của biểu đồ của bạn với các thuộc tính xoay 3D. Tùy chỉnh này cho phép bạn điều chỉnh góc nhìn và độ sâu.

**Các bước thực hiện:**

1. **Cấu hình Xoay 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Kích hoạt trục góc vuông và cấu hình phép quay theo hướng X, Y và phần trăm độ sâu
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Giải thích các tham số**:
   - `setRightAngleAxes(true)`: Đảm bảo các trục vuông góc.
   - Giá trị xoay: Điều chỉnh góc và độ sâu của chế độ xem 3D.

### Điền dữ liệu chuỗi vào biểu đồ

#### Tổng quan
Việc điền các điểm dữ liệu vào biểu đồ của bạn là rất quan trọng để phân tích. Ở đây, chúng ta sẽ thêm các giá trị cụ thể vào một chuỗi trong biểu đồ của mình.

**Các bước thực hiện:**

1. **Thêm Điểm Dữ Liệu**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Truy cập chuỗi biểu đồ thứ hai
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Thêm điểm dữ liệu cho chuỗi thanh với các giá trị được chỉ định
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Điều chỉnh sự chồng chéo của chuỗi trong biểu đồ

#### Tổng quan
Tinh chỉnh giao diện biểu đồ của bạn có thể cải thiện khả năng đọc. Phần này đề cập đến cách điều chỉnh thuộc tính chồng chéo để trực quan hóa dữ liệu tốt hơn.

**Các bước thực hiện:**

1. **Đặt chồng chéo chuỗi**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Lấy chuỗi thứ hai từ biểu đồ và đặt độ chồng chéo của nó thành 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Lưu bài thuyết trình

#### Tổng quan
Sau khi cấu hình xong bản trình bày, hãy lưu vào đĩa theo định dạng mong muốn. Bước này đảm bảo rằng mọi thay đổi đều được giữ nguyên.

**Các bước thực hiện:**

1. **Lưu bài thuyết trình**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Lưu bản trình bày đã sửa đổi vào một tập tin
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Phần kết luận

Bây giờ bạn đã học cách tạo và cấu hình bài thuyết trình với biểu đồ bằng Aspose.Slides for Java. Hướng dẫn này bao gồm khởi tạo bài thuyết trình, thêm biểu đồ cột xếp chồng 3D, cấu hình chuỗi dữ liệu và danh mục, thiết lập thuộc tính xoay, điền dữ liệu chuỗi, điều chỉnh chồng chéo chuỗi và lưu bài thuyết trình cuối cùng.

Để biết thêm các tính năng nâng cao và tùy chọn tùy chỉnh, hãy tham khảo [Tài liệu Aspose.Slides cho Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}