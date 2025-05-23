---
"date": "2025-04-17"
"description": "Học cách tạo bài thuyết trình chuyên nghiệp bằng Aspose.Slides for Java. Hướng dẫn này bao gồm thiết lập môi trường của bạn, thêm biểu đồ cột xếp chồng và tùy chỉnh chúng để rõ ràng hơn."
"title": "Làm chủ biểu đồ cột xếp chồng trong Java với Aspose.Slides&#58; Hướng dẫn toàn diện"
"url": "/vi/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Làm chủ biểu đồ cột xếp chồng trong Java với Aspose.Slides: Hướng dẫn toàn diện

## Giới thiệu

Nâng cao bài thuyết trình của bạn bằng cách kết hợp hình ảnh dữ liệu sâu sắc với sức mạnh của Aspose.Slides for Java. Việc tạo các slide chuyên nghiệp với biểu đồ cột xếp chồng rất đơn giản, cho dù bạn đang chuẩn bị báo cáo kinh doanh hay trình bày số liệu thống kê dự án.

Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Aspose.Slides for Java để tạo các bài thuyết trình động và thêm biểu đồ cột xếp chồng hấp dẫn về mặt hình ảnh. Đến cuối hướng dẫn này, bạn sẽ được trang bị các kỹ năng cần thiết để:
- Thiết lập môi trường của bạn để sử dụng Aspose.Slides
- Tạo một bài thuyết trình từ đầu
- Thêm và tùy chỉnh biểu đồ cột xếp chồng theo phần trăm
- Định dạng trục biểu đồ và nhãn dữ liệu để rõ ràng hơn

Hãy cùng tìm hiểu cách tạo ra những bài thuyết trình thu hút khán giả.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
- **Bộ phát triển Java (JDK):** Phiên bản 8 trở lên.
- **Ý tưởng:** Bất kỳ Môi trường phát triển tích hợp nào như IntelliJ IDEA hoặc Eclipse.
- **Maven/Gradle:** Để quản lý các phụ thuộc (tùy chọn nhưng được khuyến nghị).
- **Kiến thức Java cơ bản:** Quen thuộc với các khái niệm lập trình Java.

## Thiết lập Aspose.Slides cho Java
Để bắt đầu, bạn cần đưa thư viện Aspose.Slides vào dự án của mình. Thực hiện như sau:

**Chuyên gia:**
Thêm sự phụ thuộc này vào `pom.xml` tài liệu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Cấp độ:**
Bao gồm điều này trong của bạn `build.gradle` tài liệu:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải xuống trực tiếp:**
Ngoài ra, hãy tải xuống JAR mới nhất từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

### Mua lại giấy phép
Bạn có thể bắt đầu bằng bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides. Để xóa giới hạn đánh giá, hãy cân nhắc mua giấy phép tạm thời hoặc đã mua.
- **Dùng thử miễn phí:** Truy cập các tính năng hạn chế mà không phải trả phí ngay lập tức.
- **Giấy phép tạm thời:** Yêu cầu qua [Trang web của Aspose](https://purchase.aspose.com/temporary-license/).
- **Mua:** Truy cập trang mua hàng để có quyền truy cập đầy đủ.

### Khởi tạo cơ bản
Sau đây là cách bạn khởi tạo Aspose.Slides trong ứng dụng Java của mình:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Tạo một thể hiện của lớp Presentation
        Presentation presentation = new Presentation();
        
        // Thực hiện các thao tác trên đối tượng trình bày
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Hướng dẫn thực hiện

### Tạo bài thuyết trình và thêm slide
**Tổng quan:**
Bắt đầu bằng cách tạo một bài thuyết trình đơn giản với một slide ban đầu. Đây là nền tảng cho những cải tiến tiếp theo của bạn.

#### Bước 1: Khởi tạo đối tượng trình bày
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Tạo một phiên bản trình bày mới
        Presentation presentation = new Presentation();
        
        // Tham chiếu đến slide đầu tiên (tự động tạo)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Bước 2: Lưu bài thuyết trình
```java
// Lưu bài thuyết trình vào một tập tin
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Thêm biểu đồ cột xếp chồng phần trăm vào trang chiếu
**Tổng quan:**
Cải thiện slide của bạn bằng cách thêm biểu đồ cột xếp chồng theo phần trăm, cho phép so sánh dữ liệu dễ dàng.

#### Bước 1: Khởi tạo và truy cập Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Tiến hành thêm biểu đồ ở bước tiếp theo
    }
}
```

#### Bước 2: Thêm biểu đồ vào trang chiếu
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Tùy chỉnh Định dạng Số Trục Biểu đồ
**Tổng quan:**
Tùy chỉnh định dạng số của trục dọc biểu đồ để dễ đọc hơn.

#### Bước 1: Thêm và Truy cập Biểu đồ
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Bước 2: Thiết lập Định dạng số tùy chỉnh
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Thêm Chuỗi và Điểm Dữ liệu vào Biểu đồ
**Tổng quan:**
Điền chuỗi dữ liệu vào biểu đồ, làm cho biểu đồ mang tính thông tin và hấp dẫn về mặt thị giác.

#### Bước 1: Khởi tạo Trình bày và Biểu đồ
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Bước 2: Thêm Chuỗi Dữ liệu
```java
// Xóa các chuỗi hiện có và thêm chuỗi mới
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Thêm nhiều điểm dữ liệu hơn khi cần thiết
```

### Định dạng Chuỗi Tô Màu
**Tổng quan:**
Tăng tính thẩm mỹ cho biểu đồ của bạn bằng cách định dạng màu tô của từng chuỗi.

#### Bước 1: Khởi tạo và truy cập biểu đồ
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Bước 2: Thiết lập màu tô
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Lặp lại cho các chuỗi khác với màu sắc khác nhau
```

### Định dạng nhãn dữ liệu
**Tổng quan:**
Làm cho nhãn dữ liệu của bạn dễ đọc hơn bằng cách tùy chỉnh định dạng của chúng.

#### Bước 1: Truy cập Chuỗi biểu đồ và Điểm dữ liệu
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Bước 2: Tùy chỉnh nhãn dữ liệu
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách thiết lập Aspose.Slides for Java và tạo các bài thuyết trình động với biểu đồ cột xếp chồng theo phần trăm. Tùy chỉnh biểu đồ của bạn thêm nữa bằng cách điều chỉnh màu sắc và nhãn cho phù hợp với nhu cầu của bạn.

Chúc bạn viết mã vui vẻ!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}