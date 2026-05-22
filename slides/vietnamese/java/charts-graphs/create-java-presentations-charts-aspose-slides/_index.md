---
date: '2026-03-20'
description: Tìm hiểu cách thêm biểu đồ vào các bài thuyết trình Java bằng Aspose.Slides
  và nhanh chóng tạo các tệp biểu đồ cho bài thuyết trình.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Cách Thêm Biểu Đồ vào Bài Thuyết Trình Java với Aspose.Slides
url: /vi/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Thêm Biểu Đồ Vào Bản Trình Chiếu Sử Dụng Aspose.Slides cho Java

## Giới thiệu

Việc tạo các bản trình chiếu động, truyền tải dữ liệu một cách hiệu quả là rất quan trọng trong môi trường kinh doanh nhanh chóng ngày nay. Dù bạn đang chuẩn bị báo cáo tài chính, bộ tài liệu marketing, hay bản cập nhật trạng thái dự án, **biết cách thêm biểu đồ** vào các slide có thể nâng cao đáng kể mức độ tương tác của khán giả. Trong hướng dẫn này, bạn sẽ học từng bước cách thêm biểu đồ cột chồng 3D, cấu hình dữ liệu và lưu file cuối cùng — tất cả đều sử dụng Aspose.Slides cho Java.

### Trả lời nhanh
- **Thư viện chính là gì?** Aspose.Slides cho Java  
- **Loại biểu đồ được minh họa là gì?** Cột chồng 3D  
- **Tôi có thể tạo file biểu đồ trình chiếu một cách lập trình không?** Có, bằng các phương thức API được trình bày bên dưới  
- **Phiên bản Java nào được khuyến nghị?** JDK 16 hoặc mới hơn  
- **Có cần giấy phép cho môi trường sản xuất không?** Cần giấy phép Aspose.Slides hợp lệ cho việc sử dụng thương mại  

## “how to add chart” trong Aspose.Slides là gì?

Aspose.Slides cho Java cung cấp một bộ đối tượng phong phú cho phép bạn tạo, chỉnh sửa và xuất file PowerPoint mà không cần Microsoft Office. Thêm một biểu đồ chỉ đơn giản là tạo một đối tượng `Presentation`, chèn một shape biểu đồ, và cung cấp dữ liệu qua workbook tích hợp.

## Tại sao cần thêm biểu đồ vào bản trình chiếu Java?

- **Tác động trực quan:** Biểu đồ biến các con số thô thành hình ảnh dễ hiểu ngay lập tức.  
- **Tự động hoá:** Tạo báo cáo nhanh chóng — lý tưởng cho các bản tóm tắt email định kỳ hoặc dashboard.  
- **Nhất quán:** Sử dụng cùng một phong cách và thương hiệu cho tất cả các bản trình chiếu được tạo tự động.  
- **Di động:** Xuất ra PPTX, PDF hoặc hình ảnh chỉ với một lời gọi phương thức.

## Yêu cầu trước

- **Thư viện và phụ thuộc:** Cần cài đặt Aspose.Slides cho Java.  
- **Cài đặt môi trường:** Làm việc trong môi trường Java (khuyến nghị JDK 16 hoặc mới hơn).  
- **Kiến thức nền:** Hiểu biết cơ bản về lập trình Java sẽ hữu ích.

## Cài đặt Aspose.Slides cho Java

### Cài đặt

Để tích hợp Aspose.Slides vào dự án, làm theo một trong các tùy chọn dưới đây.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải trực tiếp**: Hoặc tải phiên bản mới nhất từ [Aspose.Slides cho Java releases](https://releases.aspose.com/slides/java/).

### Nhận giấy phép
- **Dùng thử miễn phí:** Bắt đầu với bản dùng thử để khám phá các tính năng.  
- **Giấy phép tạm thời:** Nhận giấy phép tạm thời để thử nghiệm kéo dài hơn.  
- **Mua bản đầy đủ:** Mua giấy phép đầy đủ cho việc sử dụng thương mại.

Sau khi cài đặt, bạn có thể khởi tạo lớp `Presentation`, lớp này là điểm vào cho mọi thao tác liên quan đến biểu đồ.

## Hướng dẫn triển khai

### Cách thêm biểu đồ vào bản trình chiếu với cột chồng 3D

#### Tổng quan
Tạo một bản trình chiếu từ đầu rất đơn giản với Aspose.Slides. Trong phần này, chúng ta sẽ thêm một biểu đồ cột chồng 3D vào slide đầu tiên của bản trình chiếu.

**Các bước:**

1. **Khởi tạo đối tượng Presentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
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

2. **Giải thích các tham số**  
   - `ChartType.StackedColumn3D`: Xác định loại biểu đồ.  
   - Vị trí và kích thước `(0, 0, 500, 500)`: Xác định nơi biểu đồ sẽ xuất hiện trên slide.

### Cấu hình dữ liệu biểu đồ

#### Tổng quan
Để biểu đồ có ý nghĩa, cần cấu hình các series dữ liệu và danh mục. Phần này minh họa cách thêm các điểm dữ liệu cụ thể vào biểu đồ.

**Các bước:**

1. **Truy cập Workbook dữ liệu của biểu đồ**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Đặt thuộc tính Rotation3D cho biểu đồ

#### Tổng quan
Nâng cao tính thẩm mỹ của biểu đồ bằng các thuộc tính xoay 3D. Tùy chỉnh này cho phép bạn điều chỉnh góc nhìn và độ sâu.

**Các bước:**

1. **Cấu hình xoay 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Giải thích các tham số**  
   - `setRightAngleAxes(true)`: Đảm bảo các trục vuông góc nhau.  
   - Giá trị xoay: Điều chỉnh góc và độ sâu của góc nhìn 3D.

### Điền dữ liệu series vào biểu đồ

#### Tổng quan
Điền dữ liệu vào biểu đồ là yếu tố then chốt cho việc phân tích. Ở đây, chúng ta sẽ thêm các giá trị cụ thể vào một series trong biểu đồ.

**Các bước:**

1. **Thêm các điểm dữ liệu**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
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

### Điều chỉnh độ chồng series trong biểu đồ

#### Tổng quan
Tinh chỉnh giao diện biểu đồ có thể cải thiện khả năng đọc. Phần này hướng dẫn cách điều chỉnh thuộc tính overlap để hiển thị dữ liệu tốt hơn.

**Các bước:**

1. **Đặt độ chồng series**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Lưu bản trình chiếu

#### Tổng quan
Khi bản trình chiếu đã được cấu hình, lưu nó vào đĩa ở định dạng mong muốn. Bước này đảm bảo mọi thay đổi được lưu lại.

**Các bước:**

1. **Lưu bản trình chiếu**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| **Biểu đồ xuất hiện phẳng** | Chưa đặt xoay 3D | Gọi `setRotation3D` với các giá trị X/Y thích hợp. |
| **Dữ liệu không hiển thị** | Các ô workbook chưa được liên kết | Đảm bảo `fact.getCell` tham chiếu đúng chỉ số hàng/cột. |
| **File không được lưu** | Đường dẫn không đúng hoặc thiếu quyền | Kiểm tra `outputFilePath` có quyền ghi và thư mục tồn tại. |

## Câu hỏi thường gặp

**H: Tôi có thể tạo file biểu đồ trình chiếu ở các định dạng khác ngoài PPTX không?**  
Đ: Có, Aspose.Slides hỗ trợ PDF, ODP và các định dạng hình ảnh thông qua enum `SaveFormat`.

**H: Tôi có cần giấy phép để chạy mã trong môi trường phát triển không?**  
Đ: Giấy phép tạm thời hoặc bản dùng thử đủ cho phát triển, nhưng cần giấy phép đầy đủ cho triển khai sản xuất.

**H: Có thể thêm nhiều biểu đồ vào cùng một slide không?**  
Đ: Chắc chắn. Gọi `slide.getShapes().addChart` nhiều lần với các vị trí hoặc kích thước khác nhau.

**H: Làm sao thay đổi bảng màu của biểu đồ?**  
Đ: Sử dụng `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` và đặt màu `SolidFillColor`.

**H: Tôi có thể liên kết biểu đồ với nguồn dữ liệu bên ngoài như cơ sở dữ liệu không?**  
Đ: Có. Lấy dữ liệu bằng JDBC, sau đó điền các ô workbook một cách lập trình trước khi lưu.

## Kết luận

Bạn đã học **cách thêm biểu đồ** vào bản trình chiếu Java, cấu hình dữ liệu, tùy chỉnh xoay 3D, điều chỉnh độ chồng series và lưu file cuối cùng. Kiến thức này cho phép bạn tự động hoá việc tạo báo cáo, duy trì thương hiệu nhất quán và truyền tải dữ liệu qua các bản trình chiếu mà không cần thao tác thủ công. Để tùy chỉnh sâu hơn — như định dạng legend, trục, hoặc áp dụng theme — hãy khám phá toàn bộ khả năng trong tài liệu chính thức.

Đối với các tính năng nâng cao và tùy chọn tùy chỉnh, tham khảo [tài liệu Aspose.Slides cho Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-03-20  
**Kiểm tra với:** Aspose.Slides cho Java 25.4 (JDK 16)  
**Tác giả:** Aspose