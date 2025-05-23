---
"date": "2025-04-17"
"description": "Tìm hiểu cách sử dụng Aspose.Slides for Java để tạo biểu đồ hình tròn động trong PowerPoint. Cải thiện bài thuyết trình của bạn bằng các bước dễ làm theo và ví dụ về mã."
"title": "Tạo biểu đồ Doughnut động trong PowerPoint bằng Aspose.Slides cho Java"
"url": "/vi/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ Doughnut động trong PowerPoint bằng Aspose.Slides cho Java

## Giới thiệu
Việc tạo ra các bài thuyết trình hấp dẫn thường đòi hỏi nhiều hơn là chỉ văn bản và hình ảnh; biểu đồ có thể cải thiện đáng kể việc kể chuyện bằng cách trực quan hóa dữ liệu một cách hiệu quả. Tuy nhiên, nhiều nhà phát triển gặp khó khăn trong việc tích hợp các tính năng biểu đồ động vào các tệp PowerPoint theo chương trình. Hướng dẫn này trình bày cách sử dụng Aspose.Slides for Java để tạo biểu đồ hình bánh rán trong PowerPoint—một công cụ mạnh mẽ kết hợp tính linh hoạt và dễ sử dụng.

**Những gì bạn sẽ học được:**
- Cách khởi tạo bản trình bày bằng Aspose.Slides cho Java
- Hướng dẫn từng bước để thêm biểu đồ hình tròn vào slide của bạn
- Cấu hình điểm dữ liệu và tùy chỉnh thuộc tính nhãn
- Lưu bản trình bày đã sửa đổi với độ trung thực cao

Hãy cùng khám phá cách bạn có thể tận dụng các tính năng này để nâng cao bài thuyết trình của mình. Trước khi bắt đầu, hãy đảm bảo rằng bạn đã quen thuộc với các khái niệm lập trình Java cơ bản.

## Điều kiện tiên quyết
Để thực hiện hướng dẫn này một cách hiệu quả, hãy đảm bảo rằng bạn có:
- Kiến thức cơ bản về lập trình Java.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.
- Maven hoặc Gradle được cài đặt để quản lý sự phụ thuộc.
- Giấy phép Aspose.Slides for Java hợp lệ. Bạn có thể dùng thử miễn phí để kiểm tra các tính năng của nó.

## Thiết lập Aspose.Slides cho Java
Bắt đầu bằng cách kết hợp Aspose.Slides vào dự án của bạn. Chọn giữa Maven và Gradle, tùy thuộc vào sở thích của bạn:

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

Nếu bạn muốn tải xuống trực tiếp, hãy truy cập [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/) trang.

### Mua lại giấy phép
Bạn có thể bắt đầu bằng bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides. Để sử dụng lâu dài, hãy mua giấy phép hoặc yêu cầu giấy phép tạm thời từ [Trang web của Aspose](https://purchase.aspose.com/temporary-license/). Thực hiện theo hướng dẫn được cung cấp để thiết lập môi trường và khởi tạo Aspose.Slides trong ứng dụng của bạn.

## Hướng dẫn thực hiện
Chúng ta hãy cùng phân tích các bước cần thiết để tạo biểu đồ hình bánh rán trong PowerPoint bằng Aspose.Slides for Java. Mỗi phần dành riêng cho một tính năng cụ thể, đảm bảo tính rõ ràng và tập trung.

### Khởi tạo bài trình bày
Bắt đầu bằng cách tải hoặc tạo tệp PowerPoint mới. Bước này thiết lập môi trường trình bày của bạn.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Xác minh việc tải thành công bằng cách lưu bản trình bày ban đầu
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Thêm biểu đồ hình bánh rán
Thêm biểu đồ hình tròn vào trang chiếu của bạn, tùy chỉnh kích thước và giao diện của biểu đồ.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Cấu hình các thuộc tính của chuỗi
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Cấu hình Điểm dữ liệu và Nhãn
Tùy chỉnh giao diện của từng điểm dữ liệu và cấu hình nhãn để dễ đọc hơn.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Định dạng điểm dữ liệu
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Tùy chỉnh thuộc tính nhãn cho chuỗi cuối cùng trong mỗi danh mục
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Lưu bài thuyết trình
Sau khi cấu hình biểu đồ, hãy lưu bản trình bày để giữ lại những thay đổi.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Ứng dụng thực tế
Biểu đồ hình tròn có thể được sử dụng trong nhiều trường hợp khác nhau:
- **Báo cáo tài chính:** Hình dung phân bổ ngân sách hoặc số liệu tài chính.
- **Phân tích thị trường:** Hiển thị sự phân bổ thị phần giữa các đối thủ cạnh tranh.
- **Kết quả khảo sát:** Trình bày dữ liệu phân loại từ phản hồi khảo sát một cách hiệu quả.

Tích hợp với các hệ thống khác, như cơ sở dữ liệu và ứng dụng web, cho phép tạo biểu đồ động dựa trên dữ liệu thời gian thực.

## Cân nhắc về hiệu suất
Để có hiệu suất tối ưu:
- Quản lý việc sử dụng bộ nhớ bằng cách loại bỏ tài nguyên kịp thời.
- Hạn chế số lượng biểu đồ hoặc slide nếu không cần thiết để tiết kiệm sức mạnh xử lý.
- Sử dụng cấu trúc dữ liệu hiệu quả để xử lý các tập dữ liệu lớn.

Việc tuân thủ các biện pháp thực hành tốt nhất sẽ đảm bảo ứng dụng của bạn chạy trơn tru, đặc biệt là khi xử lý các bài thuyết trình phức tạp.

## Phần kết luận
Tạo biểu đồ hình vòng tròn động trong PowerPoint bằng Aspose.Slides for Java là một quá trình đơn giản khi bạn hiểu các bước chính. Với hướng dẫn này, giờ đây bạn đã có thể nâng cao bài thuyết trình của mình bằng cách tích hợp các biểu đồ hấp dẫn trực quan giúp truyền đạt hiệu quả thông tin chi tiết về dữ liệu.

Để khám phá sâu hơn các chức năng của Aspose.Slides và tìm hiểu sâu hơn về khả năng của nó, hãy cân nhắc thử nghiệm các loại biểu đồ khác nhau hoặc các tính năng nâng cao như hoạt ảnh và chuyển tiếp.

## Phần Câu hỏi thường gặp
**H: Tôi có thể sử dụng Aspose.Slides cho Java trong các ứng dụng thương mại không?**
A: Có, nhưng bạn sẽ cần phải có giấy phép. Bạn có thể bắt đầu bằng bản dùng thử miễn phí để đánh giá các tính năng của nó.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}