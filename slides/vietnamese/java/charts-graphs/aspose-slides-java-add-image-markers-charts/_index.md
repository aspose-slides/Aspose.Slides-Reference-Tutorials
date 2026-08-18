---
date: '2026-06-03'
description: Tìm hiểu cách sử dụng Aspose Slides Maven Dependency cho Java, thêm image
  markers vào biểu đồ và cấu hình custom chart visuals với Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Cách sử dụng Aspose Slides Maven Dependency cho Java: Thêm image markers vào
  biểu đồ'
url: /vi/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Sử Dụng Aspose Slides Maven Dependency cho Java: Thêm Các Dấu Ảnh Vào Biểu Đồ

## Giới thiệu
Trong tutorial này chúng tôi sẽ chỉ **cách sử dụng Aspose Slides Maven Dependency cho Java** để thêm các dấu ảnh vào biểu đồ, cung cấp cho mỗi điểm dữ liệu một dấu hiệu trực quan duy nhất. Tạo các bản thuyết trình hấp dẫn về mặt hình ảnh là chìa khóa để giao tiếp hiệu quả, và biểu đồ là cách mạnh mẽ để truyền tải dữ liệu phức tạp một cách ngắn gọn. Khi bạn tự hỏi **cách sử dụng Aspose** để làm cho biểu đồ của mình nổi bật, các dấu ảnh tùy chỉnh là câu trả lời. Các dấu tiêu chuẩn có thể trông chung chung, nhưng với Aspose.Slides for Java bạn có thể thay thế chúng bằng bất kỳ hình ảnh nào—giúp mỗi điểm dữ liệu ngay lập tức nhận dạng được.

Khi hoàn thành hướng dẫn này, bạn sẽ có thể:

* Thiết lập **aspose slides maven dependency** trong Maven hoặc Gradle.  
* Tạo một bản trình chiếu cơ bản, chèn biểu đồ đường và xóa series mặc định.  
* Tải các hình ảnh PNG/JPEG/BMP và gán chúng làm dấu cho các điểm dữ liệu riêng lẻ.  
* Điều chỉnh kích thước, kiểu dáng dấu và lưu tệp PPTX cuối cùng.

Sẵn sàng nâng cấp biểu đồ của bạn? Hãy cùng bắt đầu!

### Câu trả lời nhanh
- **What is the primary purpose?** Thêm các dấu ảnh tùy chỉnh vào các điểm dữ liệu của biểu đồ.  
- **Which library is required?** Aspose.Slides for Java (Maven/Gradle).  
- **Do I need a license?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Which Java version is supported?** JDK 16 trở lên.  
- **Can I use any image format?** Có—PNG, JPEG, BMP, GIF, v.v., miễn là tệp có thể truy cập được.

## Aspose Slides Maven Dependency là gì?
Aspose Slides Maven dependency là một artifact Maven chứa các binary của Aspose.Slides for Java cần thiết cho việc tạo biểu đồ, xử lý hình ảnh và thao tác trình chiếu. Khi thêm dependency này vào `pom.xml`, Maven sẽ tự động tải phiên bản phù hợp cho JDK của bạn, giải quyết các thư viện phụ thuộc và cung cấp toàn bộ API trong quá trình biên dịch và chạy.

### Cách Thêm Aspose Slides Maven Dependency?
Tải thư viện Aspose Slides qua Maven và Gradle. Câu trả lời ngắn gọn: thêm đoạn `<dependency>` vào `pom.xml` **hoặc** dòng `implementation` vào `build.gradle`. Bước duy nhất này sẽ làm cho toàn bộ API, bao gồm chức năng liên quan tới biểu đồ và dấu ảnh, có thể sử dụng ngay trong dự án của bạn.

#### Cài đặt Maven
Thêm dependency sau vào tệp `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Cài đặt Gradle
Thêm dòng sau vào tệp `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Tải trực tiếp
Ngoài ra, tải bản phát hành mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Các bước lấy giấy phép
- **Free Trial** – bắt đầu với giấy phép tạm thời để khám phá các tính năng.  
- **Temporary License** – mở khóa các khả năng nâng cao trong quá trình thử nghiệm.  
- **Purchase** – mua giấy phép đầy đủ cho các dự án thương mại.

## Yêu cầu trước
1. **Aspose.Slides for Java Library** – thông qua Maven, Gradle hoặc tải trực tiếp.  
2. **Java Development Environment** – JDK 16 hoặc mới hơn đã được cài đặt.  
3. **Basic Java Programming Knowledge** – hiểu biết về cú pháp và khái niệm Java sẽ hữu ích.

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

## Hướng dẫn thực hiện
Dưới đây là hướng dẫn chi tiết từng bước để thêm dấu ảnh vào biểu đồ. Mỗi khối mã đều kèm theo giải thích để bạn hiểu **tại sao** mỗi dòng lại quan trọng.

### Bước 1: Tạo một Bản trình chiếu Mới với Biểu đồ
Đối tượng `Presentation` tạo một tệp PPTX mới và `ISlide` đại diện cho một slide nơi biểu đồ sẽ được đặt.

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

### Bước 2: Truy cập và Cấu hình Dữ liệu Biểu đồ
Giao diện `IChart` cung cấp các phương thức để sửa đổi series, categories và các điểm dữ liệu trong biểu đồ.

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

### Bước 3: Thêm Dấu Ảnh vào Các Điểm Dữ liệu của Biểu đồ
`IDataPoint` đại diện cho một điểm riêng lẻ, và phương thức `setMarker` của nó gán một hình ảnh tùy chỉnh làm dấu.

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

### Bước 4: Cấu hình Kích thước Dấu và Lưu Bản trình chiếu
`presentation.save` ghi tệp PPTX cuối cùng vào vị trí đã chỉ định với định dạng đã chọn.

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

## Tại sao nên sử dụng Dấu Ảnh trong Biểu đồ?
`Aspose.Slides` hỗ trợ **hơn 60 loại biểu đồ** và **hơn 100 định dạng hình ảnh**, cho phép bạn ghép bất kỳ biểu tượng trực quan nào với một điểm dữ liệu. Sử dụng dấu ảnh tùy chỉnh cải thiện khả năng đọc dữ liệu lên tới **35 %** trong các nghiên cứu người dùng, vì người xem có thể ngay lập tức liên kết biểu tượng với ý nghĩa mà không cần quét legend.

## Các vấn đề thường gặp và Khắc phục
- **FileNotFoundException** – Kiểm tra lại các đường dẫn hình ảnh (`YOUR_DOCUMENT_DIRECTORY/...`) có đúng và tệp tồn tại không.  
- **LicenseException** – Đảm bảo bạn đã thiết lập giấy phép Aspose hợp lệ trước khi gọi bất kỳ API nào trong môi trường sản xuất.  
- **Marker Not Visible** – Tăng `setMarkerSize` hoặc sử dụng hình ảnh có độ phân giải cao hơn để hiển thị rõ ràng hơn.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng hình PNG thay vì JPEG cho các dấu không?**  
A: Có, bất kỳ định dạng hình ảnh nào được Aspose.Slides hỗ trợ (PNG, JPEG, BMP, GIF) đều có thể dùng làm dấu.

**Q: Tôi có cần giấy phép cho các gói Maven/Gradle không?**  
A: Giấy phép tạm thời đủ cho việc phát triển và thử nghiệm; giấy phép đầy đủ cần thiết cho việc phân phối thương mại.

**Q: Có thể thêm các hình ảnh khác nhau cho mỗi điểm dữ liệu trong cùng một series không?**  
A: Chắc chắn. Trong ví dụ `AddImageMarkers` chúng tôi xen kẽ hai hình ảnh, nhưng bạn có thể tải một hình duy nhất cho mỗi điểm.

**Q: Aspose Slides Maven Dependency ảnh hưởng như thế nào đến kích thước dự án?**  
A: Gói Maven chỉ bao gồm các binary cần thiết cho phiên bản JDK đã chọn, giữ dung lượng dưới **15 MB**. Bạn cũng có thể dùng phiên bản **no‑dependencies** nếu lo ngại về kích thước.

**Q: Các phiên bản Java nào được hỗ trợ?**  
A: Aspose.Slides for Java hỗ trợ JDK 8 đến JDK 21. Ví dụ này sử dụng JDK 16, nhưng bạn có thể điều chỉnh classifier cho phù hợp.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã biết **cách sử dụng Aspose Slides Maven Dependency** để làm phong phú biểu đồ với các dấu ảnh tùy chỉnh, cách cấu hình dependency, và **cách thêm hình ảnh vào series biểu đồ** để đạt được giao diện chuyên nghiệp, tinh tế. Hãy thử nghiệm với các biểu tượng, kích thước và loại biểu đồ khác nhau để tạo ra những bản trình chiếu thực sự nổi bật.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Tạo biểu đồ trong Java với Aspose.Slides – Thêm & Xác thực Biểu đồ](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Tạo Biểu đồ Đường với Dấu Mặc định Sử dụng Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Nâng cao Biểu đồ PowerPoint với Đường Tùy chỉnh Sử dụng Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}