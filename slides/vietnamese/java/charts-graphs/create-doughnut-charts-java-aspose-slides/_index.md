---
date: '2026-08-16'
description: Tìm hiểu cách thêm doughnut chart trong Java bằng Aspose.Slides. Hướng
  dẫn từng bước này bao gồm cài đặt phụ thuộc Maven, cấu hình biểu đồ, màu sắc, nhãn
  và lưu file PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Cách thêm doughnut charts trong Java bằng Aspose.Slides. Thực hiện
  theo hướng dẫn này để cài đặt Maven, tùy chỉnh màu sắc, nhãn và tạo file PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Cách thêm doughnut chart trong Java với Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Cách thêm doughnut chart trong Java với Aspose.Slides
url: /vi/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thêm biểu đồ bánh donut trong Java với Aspose.Slides

## Giới thiệu

Việc tạo **biểu đồ bánh donut** một cách lập trình có thể biến các con số thô thành hình ảnh bắt mắt, ngay lập tức kể một câu chuyện. Trong Java, **Aspose.Slides** làm cho quá trình này trở nên đơn giản, cho phép bạn tạo các biểu đồ sẵn sàng cho bản trình bày mà không cần mở PowerPoint. Trong hướng dẫn này, bạn sẽ học **cách thêm biểu đồ bánh donut** vào tệp PPTX từng bước— từ việc thiết lập phụ thuộc Maven Aspose Slides đến tùy chỉnh series, categories, colors và labels, và cuối cùng lưu bản trình bày.

Kết thúc hướng dẫn này, bạn sẽ có thể nhúng các biểu đồ bánh donut động vào bất kỳ tệp PPTX nào, phù hợp cho báo cáo, bảng điều khiển, hoặc các bộ slide tự động.

### Câu trả lời nhanh
- **Thư viện nào được sử dụng?** Aspose.Slides for Java  
- **Nhiệm vụ chính?** Thêm biểu đồ bánh donut vào tệp PPTX  
- **Cách thêm thư viện?** Sử dụng phụ thuộc Maven Aspose Slides (hoặc Gradle)  
- **Phiên bản Java tối thiểu?** JDK 16 hoặc cao hơn  
- **Có thể tùy chỉnh màu sắc và nhãn không?** Có, API cung cấp kiểm soát định dạng đầy đủ  

## Biểu đồ bánh donut là gì và tại sao nên dùng?

Biểu đồ bánh donut là một biến thể của biểu đồ tròn với trung tâm trống, cho phép hiển thị nhiều series dữ liệu dưới dạng các vòng đồng tâm. **Nó trực quan hóa các phần của tổng thể qua nhiều danh mục đồng thời giữ không gian cho thông tin bổ sung ở trung tâm.** Điều này làm cho nó lý tưởng cho việc so sánh doanh số bán hàng theo khu vực trong nhiều quý, phân bổ ngân sách giữa các phòng ban, hoặc bất kỳ kịch bản nào cần hiển thị dữ liệu tỷ lệ phân cấp.

## Tại sao nên sử dụng Aspose.Slides cho Java?

Bạn có thể thêm biểu đồ bánh donut mà không cần cài đặt Microsoft Office, và thư viện xử lý **hơn 50 + định dạng đầu vào và đầu ra** đồng thời làm việc với các bản trình bày có hơn 500 slide. Aspose.Slides cung cấp **tốc độ render nhanh tới 3×** so với tự động hóa Office gốc trên cùng phần cứng, và nó hoạt động trên Windows, Linux và macOS. Những lợi ích định lượng này có nghĩa là bạn có thể tạo các bộ slide lớn trên máy chủ không giao diện đồ họa với hiệu năng dự đoán được.

## Yêu cầu trước

- **Thư viện cần thiết**  
  - Aspose.Slides for Java 25.4 hoặc mới hơn (thư viện cho phép bạn thêm biểu đồ bánh donut).  

- **Môi trường**  
  - JDK 16 hoặc cao hơn được cài đặt trên máy của bạn.  
  - Một IDE như IntelliJ IDEA, Eclipse hoặc NetBeans.  

- **Kiến thức**  
  - Cú pháp Java cơ bản và các khái niệm hướng đối tượng.  
  - Quen thuộc với Maven hoặc Gradle để quản lý phụ thuộc.  

## Phụ thuộc Maven Aspose Slides

Thêm phụ thuộc Maven sau vào tệp `pom.xml` của bạn. Đây là **phụ thuộc maven aspose slides** mà bạn cần để kéo thư viện vào dự án.

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
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Bạn cũng có thể tải JAR trực tiếp từ trang phát hành chính thức:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Nhận giấy phép

Để loại bỏ watermark đánh giá và mở khóa toàn bộ tính năng:

- **Dùng thử miễn phí** – bắt đầu với giấy phép tạm thời.  
- **Giấy phép tạm thời** – yêu cầu một từ [trang web Aspose](https://purchase.aspose.com/temporary-license/).  
- **Giấy phép thương mại** – mua để sử dụng trong môi trường sản xuất.

Áp dụng giấy phép trong mã của bạn:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Hướng dẫn triển khai

### Khởi tạo bản trình bày và thêm biểu đồ bánh donut

Presentation là lớp của Aspose.Slides đại diện cho một bản trình bày PowerPoint.  
Tải một tệp PPTX hiện có hoặc tạo một đối tượng `Presentation` mới, sau đó thêm biểu đồ bánh donut vào slide đầu tiên.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Cấu hình workbook dữ liệu biểu đồ và xóa dữ liệu hiện có

Workbook là một bảng tính nội bộ lưu trữ dữ liệu của biểu đồ.  
Lấy workbook hỗ trợ cho biểu đồ, sau đó xóa bất kỳ series hoặc categories mặc định nào để bạn có thể bắt đầu với một trạng thái sạch.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Thêm series vào biểu đồ

Một series đại diện cho một tập hợp các điểm dữ liệu được vẽ trên biểu đồ.  
Bạn có thể thêm tối đa 15 series. Mỗi series có thể được tùy chỉnh—ở đây chúng tôi đặt explosion, kích thước lỗ bánh donut và góc lát đầu tiên.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Thêm categories và điểm dữ liệu

Categories là các nhãn cho mỗi điểm dữ liệu dọc theo trục của biểu đồ.  
Tạo 15 categories và điền mỗi series với một điểm dữ liệu. Series cuối cùng nhận định dạng nhãn đặc biệt.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Tùy chỉnh màu sắc và nhãn dữ liệu

`FillType.Solid` chỉ định màu nền đặc cho các thành phần của biểu đồ.  
Đặt màu nền đặc cho mỗi series và bật nhãn dữ liệu. Đối với series cuối cùng, chúng tôi cũng thay đổi màu phông chữ của nhãn.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Lưu bản trình bày

`save` ghi bản trình bày vào một tệp ở định dạng đã chọn.  
Ghi bản trình bày đã cập nhật vào đĩa ở định dạng PPTX, hoặc xuất ra PDF nếu cần.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Các vấn đề thường gặp và giải pháp

- **Không tìm thấy giấy phép** – Kiểm tra đường dẫn tới `license.lic` có đúng và tệp có thể đọc được.  
- **Biểu đồ hiển thị trống** – Đảm bảo bạn đã xóa các series/categories hiện có trước khi thêm mới.  
- **Màu không đúng** – Xác nhận rằng `FillType.Solid` được đặt cho cả định dạng fill và line.  
- **Hiệu năng với nhiều series** – Giới hạn số lượng series/categories hoặc tái sử dụng các ô workbook để giữ mức sử dụng bộ nhớ dưới kiểm soát.  

## Câu hỏi thường gặp

**Q: Tôi có thể tạo biểu đồ bánh donut mà không có tệp PPTX có sẵn không?**  
A: Có, khởi tạo `new Presentation()` để bắt đầu từ một bộ slide trống, sau đó thêm biểu đồ như trên.

**Q: Aspose.Slides có hỗ trợ xuất ra PDF không?**  
A: Chắc chắn. Sau khi tạo biểu đồ, gọi `pres.save("output.pdf", SaveFormat.Pdf);` để có phiên bản PDF của slide.

**Q: Làm thế nào để thay đổi kích thước lỗ bánh donut?**  
A: Sử dụng `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` trong đó `value` nằm trong khoảng từ 0 đến 100.

**Q: Có thể thêm nhãn dữ liệu cho tất cả các series, không chỉ series cuối cùng không?**  
A: Có, di chuyển khối định dạng nhãn ra ngoài điều kiện `if (i == ...)` và áp dụng cho mỗi `dataPoint`.

**Q: Các phiên bản Java nào được hỗ trợ?**  
A: Aspose.Slides 25.4 hỗ trợ JDK 16 và mới hơn. Các JDK cũ hơn yêu cầu classifier phù hợp trong phụ thuộc Maven.

---

**Cập nhật lần cuối:** 2026-08-16  
**Đã kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Hướng dẫn liên quan

- [Cách Thêm Biểu Đồ vào PowerPoint bằng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Cách Tùy Chỉnh Màu Sắc Biểu Đồ Tròn trong Java với Aspose.Slides – Hướng Dẫn Toàn Diện](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Hoạt Họa Các Danh Mục Biểu Đồ PowerPoint với Aspose.Slides cho Java | Hướng Dẫn Từng Bước](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}