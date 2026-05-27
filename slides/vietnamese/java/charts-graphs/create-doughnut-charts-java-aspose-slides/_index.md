---
date: '2026-03-07'
description: Tìm hiểu cách tạo biểu đồ bánh donut trong Java bằng Aspose.Slides. Hướng
  dẫn từng bước này bao gồm việc thiết lập phụ thuộc Aspose Slides cho Maven, cấu
  hình biểu đồ và lưu bản trình bày.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Hướng dẫn tạo biểu đồ vòng bánh Java với Aspose.Slides
url: /vi/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo Biểu Đồ Donut Java với Hướng Dẫn Aspose.Slides

## Giới thiệu

Việc tạo **doughnut chart** một cách lập trình có thể biến các con số thô thành hình ảnh bắt mắt, ngay lập tức truyền tải câu chuyện. Trong Java, **Aspose.Slides** làm cho quá trình này trở nên đơn giản, cho phép bạn tạo các biểu đồ sẵn sàng cho bản trình chiếu mà không cần mở PowerPoint. Trong hướng dẫn này, bạn sẽ học cách **create doughnut chart java** từng bước— từ việc thiết lập phụ thuộc Maven Aspose Slides đến tùy chỉnh series, categories, và cuối cùng lưu bản trình chiếu.

Khi kết thúc hướng dẫn này, bạn sẽ có thể nhúng các doughnut chart động vào bất kỳ tệp PPTX nào, phù hợp cho báo cáo, bảng điều khiển, hoặc bộ slide tự động.

### Câu trả lời nhanh
- **Thư viện nào được sử dụng?** Aspose.Slides for Java  
- **Nhiệm vụ chính?** Tạo doughnut chart java trong tệp PPTX  
- **Cách thêm thư viện?** Sử dụng phụ thuộc Maven Aspose Slides (hoặc Gradle)  
- **Phiên bản Java tối thiểu?** JDK 16 hoặc cao hơn  
- **Có thể tùy chỉnh màu sắc và nhãn không?** Có, API cung cấp kiểm soát định dạng đầy đủ  

## Biểu Đồ Doughnut là gì và Tại sao nên dùng?

Biểu đồ doughnut là một biến thể của biểu đồ tròn với trung tâm trống, cho phép bạn hiển thị nhiều series dữ liệu trong các vòng đồng tâm. Điều này làm cho nó trở nên lý tưởng để so sánh các phần của tổng thể qua nhiều danh mục—ví dụ doanh số bán hàng theo khu vực trong nhiều quý hoặc phân bổ ngân sách theo phòng ban.

## Tại sao nên dùng Aspose.Slides cho Java?

- **Không cần cài đặt Office** – tạo tệp PPTX trên bất kỳ máy chủ nào.  
- **API phong phú** – kiểm soát đầy đủ các loại biểu đồ, điểm dữ liệu và kiểu dáng.  
- **Hiệu năng cao** – tối ưu cho các bản trình chiếu lớn.  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS.

## Yêu cầu trước

- **Thư viện yêu cầu:**  
  - Aspose.Slides for Java phiên bản 25.4 hoặc mới hơn.  

- **Cài đặt môi trường:**  
  - JDK 16 hoặc cao hơn.  
  - IDE yêu thích của bạn (IntelliJ IDEA, Eclipse, NetBeans, v.v.).  

- **Kiến thức yêu cầu:**  
  - Lập trình Java cơ bản.  
  - Quen thuộc với Maven hoặc Gradle để quản lý phụ thuộc.

## Phụ thuộc Maven Aspose Slides

Thêm phụ thuộc Maven sau vào file `pom.xml` của bạn. Đây là **maven aspose slides dependency** cần thiết để kéo thư viện vào dự án.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Nếu bạn thích Gradle, hãy sử dụng đoạn mã tương đương bên dưới.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Bạn cũng có thể tải JAR trực tiếp từ trang phát hành chính thức:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Nhận giấy phép

Để loại bỏ watermark đánh giá và mở khóa toàn bộ tính năng:

- **Dùng thử miễn phí** – bắt đầu với giấy phép tạm thời.  
- **Giấy phép tạm thời** – yêu cầu từ [trang web Aspose](https://purchase.aspose.com/temporary-license/).  
- **Giấy phép thương mại** – mua để sử dụng trong môi trường sản xuất.

Áp dụng giấy phép trong mã của bạn:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Hướng dẫn thực hiện

### Khởi tạo Presentation và Thêm Doughnut Chart

Đầu tiên, tạo hoặc tải một presentation và thêm doughnut chart vào slide đầu tiên.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Cấu hình Workbook dữ liệu biểu đồ và Xóa dữ liệu hiện có

Tiếp theo, lấy workbook hỗ trợ cho biểu đồ và xóa bất kỳ series hoặc categories mặc định nào.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Thêm Series vào Biểu đồ

Bây giờ chúng ta sẽ thêm tối đa 15 series. Mỗi series có thể được tùy chỉnh—ở đây chúng ta đặt explosion, kích thước lỗ doughnut và góc lát đầu tiên.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Thêm Categories và Data Points

Chúng ta sẽ tạo 15 categories và điền mỗi series với một data point. Series cuối cùng sẽ nhận định dạng nhãn đặc biệt.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Lưu Presentation

Cuối cùng, ghi presentation đã cập nhật ra đĩa.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Các vấn đề thường gặp và giải pháp

- **Không tìm thấy giấy phép** – Kiểm tra đường dẫn tới `license.lic` có đúng và tệp có thể đọc được.  
- **Biểu đồ hiện ra trống** – Đảm bảo bạn đã xóa series/categories hiện có trước khi thêm mới.  
- **Màu không đúng** – Kiểm tra rằng `FillType.Solid` được đặt cho cả định dạng fill và line.  
- **Hiệu năng với nhiều series** – Giới hạn số lượng series/categories hoặc tái sử dụng các ô workbook.

## Câu hỏi thường gặp

**Q: Tôi có thể tạo doughnut chart mà không có tệp PPTX có sẵn không?**  
A: Có, khởi tạo `new Presentation()` để bắt đầu từ một bộ slide trống.

**Q: Aspose.Slides có hỗ trợ xuất ra PDF không?**  
A: Chắc chắn. Sau khi tạo biểu đồ, gọi `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: Làm thế nào để thay đổi kích thước lỗ doughnut?**  
A: Sử dụng `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` trong đó value là 0‑100.

**Q: Có thể thêm nhãn dữ liệu cho tất cả series, không chỉ series cuối cùng không?**  
A: Có, di chuyển khối định dạng nhãn ra ngoài điều kiện `if (i == ...)` và áp dụng cho mỗi `dataPoint`.

**Q: Các phiên bản Java nào được hỗ trợ?**  
A: Aspose.Slides 25.4 hỗ trợ JDK 16 và mới hơn. Các JDK cũ hơn yêu cầu classifier phù hợp.

**Cập nhật lần cuối:** 2026-03-07  
**Đã kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}