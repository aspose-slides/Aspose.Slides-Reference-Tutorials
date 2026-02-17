---
date: '2026-02-17'
description: Tìm hiểu cách tạo biểu đồ bánh vòng trong PowerPoint bằng Aspose.Slides
  cho Java và thêm các điểm dữ liệu cho biểu đồ một cách lập trình. Thực hiện các
  bước đơn giản và xem các ví dụ mã.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Tạo biểu đồ bánh vòng PowerPoint bằng Aspose.Slides cho Java
url: /vi/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ bánh donut PowerPoint với Aspose.Slides cho Java

## Giới thiệu
Việc tạo các bản thuyết trình hấp dẫn thường đòi hỏi nhiều hơn chỉ văn bản và hình ảnh; biểu đồ có thể nâng cao đáng kể khả năng kể chuyện bằng cách trực quan hoá dữ liệu một cách hiệu quả. Tuy nhiên, nhiều nhà phát triển gặp khó khăn khi tích hợp các tính năng biểu đồ động vào tệp PowerPoint một cách lập trình. Hướng dẫn này trình bày cách **tạo biểu đồ bánh donut PowerPoint** bằng Aspose.Slides cho Java — một công cụ mạnh mẽ kết hợp tính linh hoạt và dễ sử dụng.

**Bạn sẽ học được:**
- Cách khởi tạo một bản trình bày bằng Aspose.Slides cho Java
- Hướng dẫn từng bước để thêm biểu đồ bánh donut vào các slide
- Cấu hình các điểm dữ liệu và tùy chỉnh thuộc tính nhãn
- Lưu bản trình bày đã chỉnh sửa với độ chính xác cao

Hãy khám phá cách bạn có thể tận dụng các tính năng này để nâng cao bản thuyết trình của mình. Trước khi bắt đầu, hãy chắc chắn bạn đã quen thuộc với các khái niệm cơ bản của lập trình Java.

## Câu trả lời nhanh
- **Thư viện nào tạo biểu đồ bánh donut PowerPoint?** Aspose.Slides cho Java
- **Tôi có thể thêm điểm dữ liệu biểu đồ bằng lập trình không?** Có, sử dụng API biểu đồ
- **Có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép Aspose.Slides hợp lệ
- **Các phiên bản Java nào được hỗ trợ?** Java 8 trở lên (phiên bản JDK 16 được hiển thị)
- **Tôi có thể thêm bao nhiêu series?** Ví dụ này thêm tới 15 series, nhưng bạn có thể điều chỉnh tùy nhu cầu

## Biểu đồ bánh donut trong PowerPoint là gì?
Biểu đồ bánh donut là một biến thể của biểu đồ tròn với trung tâm rỗng, cho phép bạn hiển thị nhiều series dữ liệu trong một không gian gọn gàng, hấp dẫn về mặt hình ảnh. Nó lý tưởng để thể hiện mối quan hệ phần‑với‑toàn bộ đồng thời giữ thiết kế sạch sẽ.

## Tại sao nên dùng Aspose.Slides cho Java để tạo biểu đồ bánh donut?
- **Kiểm soát toàn diện** về giao diện, dữ liệu và bố cục biểu đồ mà không cần mở PowerPoint
- **Không cần COM interop** – hoạt động trên bất kỳ nền tảng nào hỗ trợ Java
- **Hiệu năng cao** khi tạo các bộ slide lớn hoặc tích hợp với dịch vụ web
- **Tùy chỉnh phong phú** như phá nổ (explosion), kích thước lỗ, góc lát, và định dạng nhãn

## Yêu cầu trước
- Kiến thức cơ bản về lập trình Java.
- Một IDE như IntelliJ IDEA hoặc Eclipse.
- Maven hoặc Gradle để quản lý phụ thuộc.
- Giấy phép Aspose.Slides cho Java hợp lệ (có bản dùng thử miễn phí).

## Cài đặt Aspose.Slides cho Java
Chọn trình quản lý phụ thuộc phù hợp với dự án của bạn.

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

Nếu bạn muốn tải trực tiếp, hãy truy cập trang [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Cấp giấy phép
Bạn có thể bắt đầu với bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides. Đối với việc sử dụng lâu dài, hãy mua giấy phép hoặc yêu cầu giấy phép tạm thời từ [trang web của Aspose](https://purchase.aspose.com/temporary-license/). Thực hiện các hướng dẫn được cung cấp để thiết lập môi trường và khởi tạo Aspose.Slides trong ứng dụng của bạn.

## Cách tạo biểu đồ bánh donut PowerPoint bằng Aspose.Slides cho Java
Dưới đây là hướng dẫn đầy đủ, từng bước. Mỗi khối mã sẽ được giải thích ngay trước nó, giúp bạn nắm rõ mọi thao tác.

### Bước 1: Khởi tạo bản trình bày
Đầu tiên, tải một tệp PPTX hiện có hoặc tạo một tệp mới. Điều này chuẩn bị bộ sưu tập slide để thực hiện các sửa đổi tiếp theo.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Bước 2: Thêm biểu đồ bánh donut vào slide
Chúng ta thêm hình dạng biểu đồ, xóa mọi series/danh mục mặc định, và thiết lập các thuộc tính hiển thị cơ bản.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Bước 3: Thêm điểm dữ liệu biểu đồ và tùy chỉnh nhãn
Ở bước này, chúng ta điền các danh mục, thêm điểm dữ liệu cho mỗi series, và tinh chỉnh giao diện nhãn. Đây là nơi từ khóa **add chart data points** được áp dụng.

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
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
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

### Bước 4: Lưu bản trình bày đã cập nhật
Cuối cùng, ghi lại các thay đổi vào một tệp PPTX mới.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Ứng dụng thực tiễn
Biểu đồ bánh donut có thể được sử dụng trong nhiều kịch bản thực tế:
- **Báo cáo tài chính:** Trực quan hoá phân bổ ngân sách hoặc chi phí.
- **Phân tích thị trường:** Hiển thị tỷ lệ thị phần giữa các đối thủ.
- **Kết quả khảo sát:** Trình bày dữ liệu khảo sát phân loại trong một dạng gọn gàng.
- **Tạo bảng điều khiển:** Kết hợp với truy vấn cơ sở dữ liệu để tạo các slide cập nhật tự động.

## Các lưu ý về hiệu năng
- **Giải phóng tài nguyên:** Gọi `pres.dispose()` khi hoàn thành để giải phóng bộ nhớ native.
- **Giới hạn số lượng biểu đồ:** Thêm hàng trăm biểu đồ có thể làm tăng mức tiêu thụ bộ nhớ; hãy xử lý theo lô nếu cần.
- **Sử dụng streaming:** Đối với tập dữ liệu lớn, hãy nạp workbook trực tiếp từ luồng thay vì các mảng trong bộ nhớ.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Biểu đồ hiển thị trống** | Các ô dữ liệu không được điền đúng | Kiểm tra lại các tham chiếu `workBook.getCell(...)` để đảm bảo chỉ số hàng/cột chính xác. |
| **Nhãn chồng lên nhau** | Quá nhiều danh mục trong không gian hạn chế | Tăng giá trị `DoughnutHoleSize` hoặc điều chỉnh `FirstSliceAngle`. |
| **OutOfMemoryError** | Bản trình bày lớn mà không giải phóng | Gọi `pres.dispose()` sau khi lưu và cân nhắc tăng kích thước heap JVM. |

## Câu hỏi thường gặp

**H: Tôi có thể sử dụng Aspose.Slides cho Java trong các ứng dụng thương mại không?**  
Đ: Có, nhưng bạn cần một giấy phép thương mại hợp lệ. Bản dùng thử miễn phí có sẵn để đánh giá.

**H: Làm sao để thêm hơn 15 series?**  
Đ: Tăng giới hạn vòng lặp trong bước “Add Doughnut Chart” và đảm bảo workbook dữ liệu của bạn có đủ hàng.

**H: Có thể thay đổi kích thước lỗ bánh donut sau khi tạo không?**  
Đ: Có, gọi `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` bất kỳ lúc nào trước khi lưu.

**H: Tôi có thể xuất biểu đồ dưới dạng hình ảnh thay vì PPTX không?**  
Đ: Hoàn toàn có thể. Sử dụng `chart.getImage()` và lưu `java.awt.image.BufferedImage` trả về ở định dạng bạn muốn.

**H: Aspose.Slides có hỗ trợ biểu đồ động không?**  
Đ: Hoạt ảnh có thể được thêm qua API `ISlide.getTimeline()`, tuy nhiên điều này nằm ngoài phạm vi của hướng dẫn này.

## Kết luận
Bây giờ bạn đã có một phương pháp hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **tạo biểu đồ bánh donut PowerPoint** bằng Aspose.Slides cho Java, bao gồm cách **thêm điểm dữ liệu biểu đồ**, tùy chỉnh nhãn, và xử lý các cân nhắc về hiệu năng. Hãy thử nghiệm với các màu sắc, nguồn dữ liệu và loại biểu đồ khác nhau để làm cho bản thuyết trình của bạn thực sự nổi bật.

---

**Cập nhật lần cuối:** 2026-02-17  
**Được kiểm tra với:** Aspose.Slides cho Java 25.4 (phiên bản JDK 16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}