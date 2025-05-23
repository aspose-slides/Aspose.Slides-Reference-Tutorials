---
"date": "2025-04-17"
"description": "Tìm hiểu cách tùy chỉnh định dạng ngày cho trục danh mục bằng Aspose.Slides for Java. Nâng cao biểu đồ của bạn với cách trình bày dữ liệu tùy chỉnh, hoàn hảo cho báo cáo thường niên và nhiều hơn nữa."
"title": "Cách thiết lập định dạng ngày tùy chỉnh trên trục danh mục trong Aspose.Slides Java | Hướng dẫn trực quan hóa dữ liệu"
"url": "/vi/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thiết lập định dạng ngày tùy chỉnh trên trục danh mục trong Aspose.Slides Java | Hướng dẫn trực quan hóa dữ liệu

Trong thế giới dữ liệu ngày nay, việc trình bày thông tin rõ ràng là rất quan trọng để đưa ra quyết định có tác động. Khi tạo biểu đồ bằng Aspose.Slides cho Java, việc tùy chỉnh định dạng ngày trên trục danh mục có thể cải thiện đáng kể cả khả năng hiểu và chất lượng trình bày. Hướng dẫn này sẽ hướng dẫn bạn cách thiết lập định dạng ngày tùy chỉnh trong Aspose.Slides để tăng cường sức hấp dẫn trực quan và độ rõ ràng của dữ liệu cho slide của bạn.

**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho Java
- Triển khai định dạng ngày tùy chỉnh trên trục danh mục
- Chuyển đổi ngày GregorianCalendar sang Định dạng ngày OLE Automation
- Ứng dụng thực tế của các tính năng này trong các tình huống thực tế

Hãy cùng tìm hiểu cách bạn có thể đạt được điều này một cách dễ dàng!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn đã đáp ứng các điều kiện tiên quyết sau:

### Thư viện và phiên bản bắt buộc:
- **Aspose.Slides cho Java**: Bạn sẽ cần phiên bản 25.4 trở lên.

### Yêu cầu thiết lập môi trường:
- Môi trường phát triển có khả năng chạy mã Java (như IntelliJ IDEA, Eclipse hoặc NetBeans).
- Maven hoặc Gradle được cấu hình trong dự án của bạn để quản lý các phụ thuộc.

### Điều kiện tiên quyết về kiến thức:
- Hiểu biết cơ bản về lập trình Java.
- Quen thuộc với việc sử dụng các thành phần biểu đồ trong bài thuyết trình.

## Thiết lập Aspose.Slides cho Java

Để làm việc với Aspose.Slides for Java, hãy đưa nó vào như một dependency trong dự án của bạn. Dưới đây là hướng dẫn cài đặt:

**Chuyên gia:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Cấp độ:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ngoài ra, bạn có thể [tải xuống bản phát hành mới nhất](https://releases.aspose.com/slides/java/) trực tiếp từ trang web chính thức của Aspose.

### Mua giấy phép:
- **Dùng thử miễn phí**: Bắt đầu bằng bản dùng thử miễn phí để khám phá các tính năng.
- **Giấy phép tạm thời**: Yêu cầu cấp giấy phép tạm thời để thử nghiệm kéo dài.
- **Mua**: Để sử dụng lâu dài, hãy cân nhắc mua đăng ký. Truy cập [Mua Aspose](https://purchase.aspose.com/buy) để biết thêm chi tiết.

### Khởi tạo cơ bản:

Sau đây là cách bạn có thể khởi tạo Aspose.Slides trong dự án của mình:
```java
import com.aspose.slides.Presentation;
// Khởi tạo một đối tượng Presentation biểu diễn một tệp trình bày
Presentation pres = new Presentation();
```

Bây giờ, chúng ta hãy đi vào nội dung chính của hướng dẫn này!

## Hướng dẫn thực hiện

### Thiết lập Định dạng Ngày cho Trục Danh mục

Tính năng này cho phép bạn tùy chỉnh cách hiển thị ngày trên trục danh mục của biểu đồ. Dưới đây là hướng dẫn chi tiết:

#### 1. Tạo một bài thuyết trình và biểu đồ mới
Bắt đầu bằng cách tạo một phiên bản của `Presentation` và thêm một biểu đồ diện tích mới.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // Khởi tạo bài thuyết trình
        Presentation pres = new Presentation();
        
        try {
            // Thêm Biểu đồ diện tích vào trang chiếu đầu tiên ở vị trí và kích thước đã chỉ định
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // Truy cập bảng tính dữ liệu biểu đồ để thao tác dữ liệu biểu đồ
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // Xóa bất kỳ dữ liệu hiện có nào trong biểu đồ

            // Xóa bất kỳ danh mục và chuỗi nào đã tồn tại trước đó
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // Thêm ngày vào trục danh mục bằng cách sử dụng ngày OLE Automation đã chuyển đổi
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // Tạo một chuỗi mới và thêm các điểm dữ liệu vào đó
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // Đặt loại trục danh mục thành Ngày và cấu hình định dạng số của nó
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // Định dạng ngày tháng chỉ theo năm

            // Lưu bài thuyết trình vào một thư mục đã chỉ định
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Ngày cơ sở cho chuyển đổi OLE Automation
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // Chuyển đổi sang ngày Tự động hóa OLE
        return String.valueOf(oaDate);
    }
}
```

#### 2. Chuyển đổi Ngày GregorianCalendar sang Định dạng Ngày OLE Automation

Aspose.Slides yêu cầu ngày tháng theo định dạng OLE Automation, đây là định dạng ngày tháng chuẩn của Excel. Sau đây là cách bạn chuyển đổi Java của mình `GregorianCalendar` ngày tháng:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // Ngày 15 tháng 1 năm 2021
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Ngày cơ sở của Excel cho OLE Automation
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### Mẹo khắc phục sự cố:
- Đảm bảo ngày cơ sở để chuyển đổi (`30 Dec 1899`) được phân tích cú pháp chính xác.
- Xác minh rằng môi trường Java của bạn hỗ trợ các thư viện và lớp cần thiết.
- Nếu có vấn đề phát sinh, hãy kiểm tra xem có bản cập nhật hoặc bản vá nào dành cho Aspose.Slides không.

### Ứng dụng thực tế

Việc tùy chỉnh định dạng ngày tháng có thể đặc biệt hữu ích trong các trường hợp như:
- **Báo cáo thường niên:** Hiển thị rõ ràng xu hướng dữ liệu hàng năm.
- **Biểu đồ tài chính:** Trình bày chính xác các kỳ tài chính.
- **Tiến độ dự án:** Làm nổi bật các khung thời gian hoặc cột mốc cụ thể.

Bằng cách làm theo hướng dẫn này, bạn sẽ có thể cải thiện bài thuyết trình của mình với các định dạng ngày tháng chính xác và hấp dẫn về mặt hình ảnh bằng Aspose.Slides for Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}