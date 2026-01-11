---
date: '2026-01-11'
description: Tìm hiểu cách sử dụng Aspose Slides cho Java, thêm các dấu hiệu hình
  ảnh vào biểu đồ và cấu hình phụ thuộc Maven của Aspose Slides cho hình ảnh biểu
  đồ tùy chỉnh.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Cách sử dụng Aspose Slides Java: Thêm các dấu hiệu hình ảnh vào biểu đồ'
url: /vi/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Sử Dụng Aspose Slides Java: Thêm Dấu Ảnh Vào Biểu Đồ

## Giới thiệu
Tạo các bản thuyết trình hấp dẫn về mặt hình ảnh là chìa khóa để giao tiếp hiệu quả, và biểu đồ là công cụ mạnh mẽ để truyền tải dữ liệu phức tạp một cách ngắn gọn. Khi bạn tự hỏi **cách sử dụng Aspose** để làm cho biểu đồ của mình nổi bật, các dấu ảnh tùy chỉnh là câu trả lời. Các dấu tiêu chuẩn có thể trông chung chung, nhưng với Aspose.Slides for Java bạn có thể thay thế chúng bằng bất kỳ hình ảnh nào—giúp mỗi điểm dữ liệu ngay lập tức nhận dạng được.

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn toàn bộ quy trình thêm dấu ảnh vào biểu đồ đường, từ việc thiết lập **phụ thuộc Aspose Slides Maven** đến tải hình ảnh và áp dụng chúng cho các điểm dữ liệu. Khi hoàn thành, bạn sẽ tự tin với **cách thêm dấu**, cách **thêm hình ảnh vào chuỗi biểu đồ**, và sẽ có một mẫu mã sẵn sàng chạy.

**Bạn sẽ học được**
- Cách thiết lập Aspose.Slides for Java (bao gồm Maven/Gradle)
- Tạo một bản trình bày và biểu đồ cơ bản
- Thêm dấu ảnh vào các điểm dữ liệu của biểu đồ
- Cấu hình kích thước và kiểu dấu để hiển thị tối ưu

Sẵn sàng nâng cấp biểu đồ của bạn? Hãy bắt đầu với các yêu cầu trước khi tiến hành!

### Câu trả lời nhanh
- **Mục đích chính là gì?** Thêm dấu ảnh tùy chỉnh vào các điểm dữ liệu của biểu đồ.  
- **Thư viện nào cần thiết?** Aspose.Slides for Java (Maven/Gradle).  
- **Có cần giấy phép không?** Giấy phép tạm thời đủ cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** JDK 16 trở lên.  
- **Có thể dùng bất kỳ định dạng ảnh nào không?** Có—PNG, JPEG, BMP, v.v., miễn là tệp có thể truy cập được.

### Yêu cầu trước
Để làm theo hướng dẫn này, bạn cần:
1. **Thư viện Aspose.Slides for Java** – lấy qua Maven, Gradle, hoặc tải trực tiếp.  
2. **Môi trường phát triển Java** – JDK 16 hoặc mới hơn đã được cài đặt.  
3. **Kiến thức lập trình Java cơ bản** – quen thuộc với cú pháp và các khái niệm Java sẽ rất hữu ích.

## Phụ Thuộc Aspose Slides Maven là gì?
Phụ thuộc Maven sẽ tải về các binary phù hợp cho phiên bản Java của bạn. Thêm nó vào `pom.xml` sẽ đảm bảo thư viện có sẵn ở thời điểm biên dịch và chạy.

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
Hoặc tải bản phát hành mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Các bước lấy giấy phép
- **Dùng thử miễn phí** – bắt đầu với giấy phép tạm thời để khám phá các tính năng.  
- **Giấy phép tạm thời** – mở khóa các khả năng nâng cao trong quá trình thử nghiệm.  
- **Mua bản quyền** – nhận giấy phép đầy đủ cho các dự án thương mại.

## Khởi tạo và Cấu hình Cơ bản
Đầu tiên, tạo một đối tượng `Presentation`. Đối tượng này đại diện cho toàn bộ tệp PowerPoint và sẽ chứa biểu đồ của chúng ta.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Hướng Dẫn Thực Hiện
Dưới đây là hướng dẫn từng bước để thêm dấu ảnh vào biểu đồ. Mỗi khối mã đi kèm với giải thích để bạn hiểu **tại sao** mỗi dòng lại quan trọng.

### Bước 1: Tạo Bản Trình Bày Mới với Biểu Đồ
Chúng ta thêm một biểu đồ đường với các dấu mặc định vào slide đầu tiên.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Bước 2: Truy Cập và Cấu Hình Dữ Liệu Biểu Đồ
Xóa bất kỳ chuỗi mặc định nào và thêm chuỗi của riêng bạn, chuẩn bị worksheet cho các điểm dữ liệu tùy chỉnh.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Bước 3: Thêm Dấu Ảnh vào Các Điểm Dữ Liệu của Biểu Đồ  
Ở đây chúng tôi minh họa **cách thêm dấu** bằng hình ảnh. Thay thế các đường dẫn placeholder bằng vị trí thực tế của các hình ảnh của bạn.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Bước 4: Cấu Hình Kích Thước Dấu và Lưu Bản Trình Bày  
Chúng ta điều chỉnh kiểu dấu để tăng khả năng hiển thị và ghi tệp PPTX cuối cùng.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Các Vấn Đề Thường Gặp và Khắc Phục
- **FileNotFoundException** – Kiểm tra lại các đường dẫn ảnh (`YOUR_DOCUMENT_DIRECTORY/...`) có đúng và tệp tồn tại không.  
- **LicenseException** – Đảm bảo bạn đã thiết lập giấy phép Aspose hợp lệ trước khi gọi bất kỳ API nào trong môi trường sản xuất.  
- **Dấu Không Hiển Thị** – Tăng giá trị `setMarkerSize` hoặc dùng ảnh có độ phân giải cao hơn để hiển thị rõ ràng hơn.

## Câu Hỏi Thường Gặp

**Q: Tôi có thể dùng ảnh PNG thay vì JPEG cho dấu không?**  
A: Có, bất kỳ định dạng ảnh nào được Aspose.Slides hỗ trợ (PNG, JPEG, BMP, GIF) đều có thể dùng làm dấu.

**Q: Tôi có cần giấy phép cho các gói Maven/Gradle không?**  
A: Giấy phép tạm thời đủ cho việc phát triển và thử nghiệm; giấy phép đầy đủ cần thiết cho việc phân phối thương mại.

**Q: Có thể thêm các ảnh khác nhau cho mỗi điểm dữ liệu trong cùng một chuỗi không?**  
A: Chắc chắn. Trong ví dụ `AddImageMarkers` chúng tôi xen kẽ hai hình ảnh, nhưng bạn có thể tải một ảnh duy nhất cho mỗi điểm.

**Q: Phụ thuộc `aspose slides maven dependency` ảnh hưởng như thế nào đến kích thước dự án?**  
A: Gói Maven chỉ bao gồm các binary cần thiết cho phiên bản JDK đã chọn, giúp giảm kích thước tổng thể. Bạn cũng có thể dùng phiên bản **không‑có‑phụ‑thuộc** nếu lo ngại về dung lượng.

**Q: Những phiên bản Java nào được hỗ trợ?**  
A: Aspose.Slides for Java hỗ trợ JDK 8 đến JDK 21. Ví dụ này dùng JDK 16, nhưng bạn có thể điều chỉnh classifier cho phù hợp.

## Kết Luận
Sau khi hoàn thành hướng dẫn này, bạn đã biết **cách sử dụng Aspose** để làm phong phú biểu đồ bằng các dấu ảnh tùy chỉnh, cách cấu hình **phụ thuộc Aspose Slides Maven**, và cách **thêm ảnh vào chuỗi biểu đồ** để tạo ra một bản trình bày chuyên nghiệp, tinh tế. Hãy thử nghiệm với các biểu tượng, kích thước và loại biểu đồ khác nhau để tạo ra những bản thuyết trình thực sự nổi bật.

---

**Cập nhật lần cuối:** 2026-01-11  
**Kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}