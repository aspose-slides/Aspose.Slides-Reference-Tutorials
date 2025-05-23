---
"date": "2025-04-17"
"description": "Tìm hiểu cách tạo biểu đồ hình bánh rán tuyệt đẹp trong Java với Aspose.Slides. Hướng dẫn toàn diện này bao gồm khởi tạo, cấu hình dữ liệu và lưu bản trình bày."
"title": "Tạo biểu đồ hình tròn trong Java bằng Aspose.Slides&#58; Hướng dẫn toàn diện"
"url": "/vi/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ hình tròn trong Java bằng Aspose.Slides: Hướng dẫn từng bước

## Giới thiệu

Trong môi trường dữ liệu ngày nay, việc trực quan hóa thông tin hiệu quả là chìa khóa để nâng cao sự hiểu biết và tương tác. Mặc dù việc tạo biểu đồ chuyên nghiệp theo chương trình có vẻ khó khăn, đặc biệt là với Java, hướng dẫn này sẽ hướng dẫn bạn sử dụng Aspose.Slides for Java để tạo biểu đồ Doughnut một cách dễ dàng.

Bằng cách làm theo các bước này, các nhà phát triển sẽ có được kinh nghiệm thực tế trong việc thao tác các slide thuyết trình và tích hợp trực quan hóa dữ liệu một cách liền mạch.

**Những điểm chính cần ghi nhớ:**
- Khởi tạo đối tượng Presentation bằng Aspose.Slides Java.
- Cấu hình dữ liệu biểu đồ và quản lý các chuỗi hoặc danh mục hiện có.
- Thêm và tùy chỉnh chuỗi và danh mục cho biểu đồ của bạn.
- Định dạng và hiển thị điểm dữ liệu một cách hiệu quả.
- Lưu bài thuyết trình của bạn ở nhiều định dạng khác nhau một cách dễ dàng.

Trước khi bắt đầu triển khai, hãy đảm bảo bạn có mọi thứ cần thiết để bắt đầu.

## Điều kiện tiên quyết

Để làm theo hướng dẫn này, hãy đảm bảo bạn có:

- **Thư viện bắt buộc:**
  - Aspose.Slides cho Java phiên bản 25.4 trở lên.
  
- **Thiết lập môi trường:**
  - Hệ thống của bạn phải cài đặt JDK 16 trở lên.
  - Một IDE như IntelliJ IDEA, Eclipse hoặc NetBeans.

- **Điều kiện tiên quyết về kiến thức:**
  - Hiểu biết cơ bản về các khái niệm lập trình Java.
  - Quen thuộc với việc quản lý các phụ thuộc trong các dự án Maven hoặc Gradle.

## Thiết lập Aspose.Slides cho Java

Để tích hợp Aspose.Slides vào dự án của bạn, hãy làm theo các bước sau dựa trên công cụ xây dựng của bạn:

**Thiết lập Maven:**
Thêm phụ thuộc sau vào `pom.xml` tài liệu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Thiết lập Gradle:**
Bao gồm những điều sau đây trong `build.gradle` tài liệu:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải xuống trực tiếp:**
Ngoài ra, hãy tải xuống phiên bản mới nhất trực tiếp từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

### Xin giấy phép

Để sử dụng Aspose.Slides mà không có giới hạn đánh giá:
- **Dùng thử miễn phí:** Bắt đầu với giấy phép tạm thời để khám phá đầy đủ tính năng.
- **Giấy phép tạm thời:** Nhận một thông qua [Trang web Aspose](https://purchase.aspose.com/temporary-license/).
- **Mua:** Hãy cân nhắc mua để sử dụng lâu dài.

Áp dụng giấy phép của bạn vào ứng dụng Java bằng cách sử dụng:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Hướng dẫn thực hiện

### Khởi tạo Trình bày và Biểu đồ

#### Tổng quan
Bắt đầu bằng cách khởi tạo một đối tượng trình bày và thêm biểu đồ Doughnut vào trang chiếu đầu tiên.

**Bước 1: Khởi tạo bài thuyết trình**
Tải tệp PPTX hiện có hoặc tạo tệp mới:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Bước 2: Thêm biểu đồ hình tròn**
Tạo biểu đồ trên trang chiếu đầu tiên theo tọa độ đã chỉ định:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Cấu hình Sổ làm việc dữ liệu biểu đồ và xóa các chuỗi/thể loại hiện có

#### Tổng quan
Cấu hình sổ làm việc dữ liệu biểu đồ và xóa bất kỳ chuỗi hoặc danh mục nào có sẵn.

**Bước 1: Truy cập Sổ làm việc dữ liệu biểu đồ**
Truy xuất bảng tính được liên kết với biểu đồ của bạn:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Bước 2: Xóa các Series và Categories hiện có**
Đảm bảo không có điểm dữ liệu còn sót lại:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Thêm Chuỗi vào Biểu đồ

#### Tổng quan
Điền nhiều chuỗi vào biểu đồ của bạn, mỗi chuỗi được tùy chỉnh về giao diện và hành vi.

**Bước 1: Thêm Chuỗi theo Lần Lặp**
Lặp qua các chỉ mục để thêm chuỗi:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Tùy chỉnh loạt bài
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Thêm danh mục và điểm dữ liệu vào biểu đồ

#### Tổng quan
Cấu hình danh mục và thêm điểm dữ liệu với định dạng cụ thể cho nhãn.

**Bước 1: Thêm danh mục**
Lặp qua các chỉ mục cho từng danh mục:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Bước 2: Thêm Điểm Dữ Liệu vào Mỗi Chuỗi**
Lặp lại từng chuỗi cho danh mục hiện tại:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Cài đặt định dạng điểm dữ liệu
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Định dạng nhãn cho loạt cuối cùng
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

        // Điều chỉnh tùy chọn hiển thị
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Điều chỉnh vị trí nhãn
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Lưu bài thuyết trình

#### Tổng quan
Sau khi cấu hình xong biểu đồ, hãy lưu bản trình bày vào thư mục đã chỉ định.

**Bước 1: Lưu bài thuyết trình**
Sử dụng `save` phương pháp viết thay đổi:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Bây giờ bạn đã học cách tạo và tùy chỉnh biểu đồ Doughnut trong Java bằng Aspose.Slides. Các bước này cung cấp nền tảng để tích hợp hình ảnh dữ liệu phức tạp vào bài thuyết trình của bạn.

**Các bước tiếp theo:**
- Thử nghiệm với các loại biểu đồ khác nhau có sẵn trong Aspose.Slides.
- Khám phá các tùy chọn tùy chỉnh bổ sung như màu sắc, phông chữ và kiểu dáng để phù hợp với nhu cầu xây dựng thương hiệu của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}