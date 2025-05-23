---
"date": "2025-04-17"
"description": "Tìm hiểu cách tạo, tùy chỉnh và lưu biểu đồ có nhãn phần trăm trong bài thuyết trình Java bằng Aspose.Slides. Nâng cao kỹ năng thuyết trình của bạn ngay hôm nay!"
"title": "Tạo và tùy chỉnh biểu đồ trong bài thuyết trình Java bằng Aspose.Slides"
"url": "/vi/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo và tùy chỉnh biểu đồ trong bài thuyết trình Java bằng Aspose.Slides

## Giới thiệu
Việc tạo ra các bài thuyết trình hấp dẫn thường liên quan đến nhiều thứ hơn là chỉ văn bản; nó đòi hỏi các biểu đồ động truyền tải thông tin hiệu quả. Nếu bạn đang muốn nâng cao các bài thuyết trình dựa trên Java của mình bằng các tính năng biểu đồ tinh vi bằng Aspose.Slides, hướng dẫn này dành cho bạn. Chúng tôi sẽ hướng dẫn bạn cách tạo bài thuyết trình, thêm và định cấu hình biểu đồ, tính tổng, hiển thị nhãn phần trăm và lưu công việc của bạn—tất cả chỉ trong một vài bước đơn giản.

**Những gì bạn sẽ học được:**
- Cách tạo và tùy chỉnh bài thuyết trình bằng biểu đồ bằng Aspose.Slides cho Java
- Tính tổng số danh mục trong biểu đồ
- Hiển thị dữ liệu dưới dạng nhãn phần trăm trên biểu đồ
- Lưu bài thuyết trình với các tính năng biểu đồ nâng cao

Hãy cùng tìm hiểu những điều kiện tiên quyết bạn cần có trước khi bắt đầu.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, hãy đảm bảo bạn có những điều sau:

- **Bộ phát triển Java (JDK)**: Phiên bản 8 trở lên.
- **Ý TƯỞNG**:Chẳng hạn như IntelliJ IDEA, Eclipse hoặc bất kỳ IDE nào hỗ trợ Java.
- **Aspose.Slides cho Thư viện Java**:Điều này rất quan trọng để xử lý các tính năng trình bày.

### Thư viện và phiên bản bắt buộc
Bạn sẽ cần Aspose.Slides for Java. Sau đây là cách đưa nó vào dự án của bạn:

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

Ngoài ra, bạn có thể tải trực tiếp phiên bản mới nhất từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

### Thiết lập môi trường
Đảm bảo môi trường phát triển của bạn được cấu hình để sử dụng JDK 8 trở lên và IDE của bạn được thiết lập để quản lý các phụ thuộc bằng Maven hoặc Gradle.

**Mua giấy phép:**
- **Dùng thử miễn phí**: Truy cập các tính năng cơ bản cho mục đích thử nghiệm.
- **Giấy phép tạm thời**: Kiểm tra các tính năng nâng cao mà không có giới hạn đánh giá.
- **Mua**:Để sử dụng thương mại lâu dài, hãy cân nhắc việc mua giấy phép.

## Thiết lập Aspose.Slides cho Java
Bắt đầu bằng cách thiết lập thư viện Aspose.Slides trong dự án Java của bạn. Sau đây là cách khởi tạo và cấu hình nó:

1. Thêm sự phụ thuộc thông qua Maven hoặc Gradle như được hiển thị ở trên.
2. Nhập các gói Aspose.Slides cần thiết:
   ```java
   import com.aspose.slides.*;
   ```

3. Khởi tạo một cái mới `Presentation` ví dụ:
   ```java
   Presentation presentation = new Presentation();
   ```

Thiết lập này sẽ cho phép bạn bắt đầu xây dựng bài thuyết trình theo chương trình.

## Hướng dẫn thực hiện

### Tạo và tùy chỉnh biểu đồ trong bài thuyết trình của bạn

#### Tổng quan
Việc tạo biểu đồ bao gồm khởi tạo bản trình bày, truy cập các trang chiếu và thêm biểu đồ với các thuộc tính cụ thể như loại, vị trí và kích thước.

**Các bước thực hiện:**
1. **Tạo phiên bản trình bày**: Bắt đầu bằng cách tạo một phiên bản của `Presentation` lớp học.
2. **Truy cập Slide**: Lấy lại slide đầu tiên bằng cách sử dụng `get_Item(0)`.
3. **Thêm biểu đồ**: Sử dụng `addChart()` để thêm biểu đồ cột xếp chồng ở tọa độ đã chỉ định với kích thước xác định.

```java
// Tính năng: Tạo bài thuyết trình với biểu đồ
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Tính tổng số cho các danh mục

#### Tổng quan
Tính tổng số danh mục bao gồm việc lặp lại từng chuỗi trong biểu đồ để tính tổng giá trị cho từng danh mục.

**Các bước thực hiện:**
1. **Khởi tạo mảng**: Tạo một mảng để lưu trữ tổng giá trị.
2. **Lặp lại qua các danh mục và chuỗi**: Sử dụng các vòng lặp lồng nhau để tích lũy tổng số cho mỗi danh mục từ tất cả các chuỗi.

```java
// Tính năng: Tính tổng số cho các danh mục trong biểu đồ
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Hiển thị dữ liệu dưới dạng nhãn phần trăm trên biểu đồ

#### Tổng quan
Tính năng này tập trung vào việc cấu hình nhãn dữ liệu để hiển thị giá trị dưới dạng phần trăm, mang lại sự rõ ràng trong hình ảnh trực quan.

**Các bước thực hiện:**
1. **Cấu hình nhãn sê-ri**: Thiết lập các thuộc tính nhãn như kích thước phông chữ và khả năng hiển thị của các phím chú giải.
2. **Tính phần trăm**: Tính phần trăm cho mỗi điểm dữ liệu dựa trên tổng giá trị danh mục.
3. **Đặt nhãn văn bản**: Định dạng nhãn để hiển thị phần trăm với hai chữ số thập phân.

```java
// Tính năng: Hiển thị dữ liệu dưới dạng nhãn phần trăm trên biểu đồ
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Lưu bài thuyết trình với biểu đồ

#### Tổng quan
Cuối cùng, lưu bài thuyết trình của bạn vào đường dẫn chỉ định ở định dạng PPTX.

**Các bước thực hiện:**
1. **Phương pháp lưu**: Sử dụng `save()` phương pháp trên `Presentation` ví dụ.
2. **Xử lý tài nguyên**: Đảm bảo giải phóng tài nguyên sau khi lưu.

```java
// Tính năng: Lưu bài thuyết trình với biểu đồ
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Ứng dụng thực tế

1. **Báo cáo tài chính**: Sử dụng biểu đồ để hiển thị phần trăm tăng trưởng doanh thu giữa các phòng ban.
2. **Phân tích dữ liệu bán hàng**: Trực quan hóa dữ liệu bán hàng theo khu vực với nhãn phần trăm để có thông tin chi tiết rõ ràng hơn.
3. **Bài thuyết trình giáo dục**: Nâng cao hiệu quả thuyết trình học thuật bằng số liệu thống kê trực quan.
4. **Chiến dịch tiếp thị**: Hiển thị số liệu hiệu suất chiến dịch dưới dạng hình ảnh hấp dẫn.
5. **Cuộc họp chiến lược kinh doanh**:Sử dụng biểu đồ để truyền tải dữ liệu phức tạp trong các cuộc thảo luận về kế hoạch chiến lược.

## Cân nhắc về hiệu suất
- **Quản lý bộ nhớ**: Xử lý `Presentation` các đối tượng kịp thời để giải phóng tài nguyên.
- **Tối ưu hóa việc tải biểu đồ**: Chỉ tải các thành phần biểu đồ cần thiết vào bộ nhớ nếu có thể.
- **Xử lý hàng loạt**:Khi xử lý nhiều bản trình bày, hãy cân nhắc xử lý chúng theo từng đợt để quản lý hiệu quả mức tiêu thụ tài nguyên.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}