---
"description": "Học cách tạo Biểu đồ phễu trong bài thuyết trình PowerPoint với Aspose.Slides for Java. Hướng dẫn từng bước với mã nguồn để trực quan hóa dữ liệu hiệu quả."
"linktitle": "Biểu đồ phễu trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ phễu trong Java Slides"
"url": "/vi/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ phễu trong Java Slides


## Giới thiệu về cách tạo biểu đồ phễu trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ phễu trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Biểu đồ phễu hữu ích để trực quan hóa dữ liệu thu hẹp dần hoặc "phễu" qua các giai đoạn hoặc danh mục khác nhau. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn để giúp bạn thực hiện việc này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:

- Thư viện Aspose.Slides cho Java đã được cài đặt và thiết lập trong dự án của bạn.
- Tệp bản trình bày PowerPoint (PPTX) mà bạn muốn chèn Biểu đồ phễu.

## Bước 1: Nhập Aspose.Slides cho Java

Đầu tiên, bạn cần nhập thư viện Aspose.Slides for Java vào dự án Java của mình. Đảm bảo bạn đã thêm các phụ thuộc cần thiết vào cấu hình bản dựng của mình.

```java
import com.aspose.slides.*;
```

## Bước 2: Khởi tạo Trình bày và Biểu đồ

Ở bước này, chúng ta khởi tạo một bản trình bày và thêm Biểu đồ phễu vào trang chiếu.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // Thêm Biểu đồ phễu vào trang chiếu đầu tiên tại tọa độ (50, 50) với kích thước (500, 400).
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Bước 3: Xác định dữ liệu biểu đồ

Tiếp theo, chúng ta định nghĩa dữ liệu cho Biểu đồ phễu của mình. Bạn có thể tùy chỉnh các danh mục và điểm dữ liệu theo yêu cầu của mình.

```java
// Xóa dữ liệu biểu đồ hiện có.
wb.clear(0);

// Xác định danh mục cho biểu đồ.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// Thêm điểm dữ liệu cho chuỗi Biểu đồ phễu.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Bước 4: Lưu bài thuyết trình

Cuối cùng, chúng ta lưu bản trình bày có Biểu đồ phễu vào một tệp được chỉ định.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã tạo thành công Biểu đồ phễu bằng Aspose.Slides cho Java và chèn vào bản trình bày PowerPoint.

## Mã nguồn đầy đủ cho biểu đồ phễu trong Java Slides

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Phần kết luận

Trong hướng dẫn từng bước này, chúng tôi đã trình bày cách tạo Biểu đồ phễu trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Biểu đồ phễu là một công cụ hữu ích để trực quan hóa dữ liệu theo mô hình tiến trình hoặc thu hẹp, giúp truyền tải thông tin hiệu quả. 

## Câu hỏi thường gặp

### Làm thế nào tôi có thể tùy chỉnh giao diện của Biểu đồ phễu?

Bạn có thể tùy chỉnh giao diện của Biểu đồ phễu bằng cách sửa đổi nhiều thuộc tính biểu đồ như màu sắc, nhãn và kiểu. Tham khảo tài liệu Aspose.Slides để biết thông tin chi tiết về các tùy chọn tùy chỉnh biểu đồ.

### Tôi có thể thêm nhiều điểm dữ liệu hoặc danh mục hơn vào Biểu đồ phễu không?

Có, bạn có thể thêm các điểm dữ liệu và danh mục bổ sung vào Biểu đồ phễu bằng cách mở rộng mã được cung cấp ở Bước 3. Chỉ cần thêm nhãn danh mục và điểm dữ liệu nếu cần.

### Làm thế nào để tôi có thể thay đổi vị trí và kích thước của Biểu đồ phễu trên trang chiếu?

Bạn có thể điều chỉnh vị trí và kích thước của Biểu đồ phễu bằng cách sửa đổi tọa độ và kích thước được cung cấp khi thêm biểu đồ vào trang chiếu ở Bước 2. Cập nhật các giá trị (50, 50, 500, 400) cho phù hợp.

### Tôi có thể xuất biểu đồ sang các định dạng khác như PDF hoặc hình ảnh không?

Có, Aspose.Slides for Java cho phép bạn xuất bản trình bày với Funnel Chart sang nhiều định dạng khác nhau, bao gồm PDF, định dạng hình ảnh, v.v. Bạn có thể sử dụng `SaveFormat` tùy chọn để chỉ định định dạng đầu ra mong muốn khi lưu bản trình bày.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}