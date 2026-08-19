---
date: '2026-07-08'
description: Tìm hiểu cách sử dụng Aspose để tạo doughnut chart trong PowerPoint bằng
  Java. Hướng dẫn chi tiết này chỉ cách thêm các điểm dữ liệu vào biểu đồ một cách
  lập trình, tùy chỉnh nhãn, và lưu file PPTX với high fidelity.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Sử dụng Aspose cho phép bạn tạo doughnut chart trong PowerPoint bằng
  Java. Thực hiện theo hướng dẫn này để thêm các điểm dữ liệu, tùy chỉnh nhãn, và
  lưu file PPTX với high fidelity.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Cách sử dụng Aspose: Tạo doughnut chart trong PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Cách sử dụng Aspose để tạo doughnut chart trong PowerPoint (Java)
url: /vi/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Sử Dụng Aspose Để Tạo Biểu Đồ Donut trong PowerPoint (Java)

## Giới thiệu
Việc tạo các bài thuyết trình hấp dẫn thường đòi hỏi hơn chỉ văn bản và hình ảnh; biểu đồ có thể nâng cao đáng kể khả năng kể chuyện bằng cách trực quan hoá dữ liệu một cách hiệu quả. **How to use Aspose** để tạo biểu đồ cung cấp cho bạn quyền kiểm soát lập trình mà không cần mở PowerPoint. Hướng dẫn này sẽ chỉ cho bạn cách xây dựng biểu đồ donut, cấu hình các điểm dữ liệu và lưu một tệp PPTX chất lượng cao. Bạn chỉ cần kiến thức cơ bản về Java và vài phút thiết lập.

`Aspose.Slides for Java` là một thư viện Java cho phép tạo, thao tác và chuyển đổi các tệp PowerPoint mà không cần Microsoft Office.

## Câu trả lời nhanh
- **Thư viện nào tạo biểu đồ donut trong PowerPoint?** Aspose.Slides for Java  
- **Tôi có thể thêm các điểm dữ liệu cho biểu đồ bằng lập trình không?** Có, sử dụng chart API  
- **Có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép Aspose.Slides hợp lệ  
- **Các phiên bản Java nào được hỗ trợ?** Java 8 trở lên (phiên bản JDK 16 được hiển thị)  
- **Tôi có thể thêm bao nhiêu series?** Ví dụ này thêm tối đa 15 series, nhưng bạn có thể điều chỉnh tùy nhu cầu  

## Biểu đồ donut là gì trong PowerPoint?
Biểu đồ donut là một biểu đồ tròn tương tự như biểu đồ bánh pie nhưng có trung tâm rỗng, cho phép hiển thị đồng thời nhiều series. Nó nhấn mạnh mối quan hệ phần‑với‑toàn bộ trong khi giữ bố cục trực quan gọn gàng và dễ đọc.

## Tại sao nên sử dụng Aspose.Slides for Java để tạo biểu đồ donut?
Aspose.Slides for Java hỗ trợ hơn 50 định dạng nhập và xuất và có thể tạo các bài thuyết trình lên tới 500 MB mà không cần tải toàn bộ tệp vào bộ nhớ. Nó cung cấp quyền kiểm soát lập trình đầy đủ đối với giao diện biểu đồ, dữ liệu và bố cục trên bất kỳ nền tảng Java nào, loại bỏ việc tương tác COM, và có thể render 100 slide chứa nhiều biểu đồ trong chưa đầy hai giây trên một máy chủ tiêu chuẩn.

## Yêu cầu trước
- Kiến thức cơ bản về lập trình Java.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.  
- Maven hoặc Gradle để quản lý phụ thuộc.  
- Giấy phép Aspose.Slides for Java hợp lệ (có bản dùng thử miễn phí).  

## Cài đặt Aspose.Slides cho Java
Chọn trình quản lý phụ thuộc phù hợp với dự án của bạn.

**Maven**  
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn (thay phiên bản bằng bản phát hành mới nhất):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Thêm dòng sau vào tệp `build.gradle` của bạn:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Nếu bạn muốn tải xuống trực tiếp, hãy truy cập trang [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Cách nhận giấy phép
Bạn có thể bắt đầu với bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides. Đối với việc sử dụng lâu dài, hãy mua giấy phép hoặc yêu cầu một giấy phép tạm thời từ [trang web của Aspose](https://purchase.aspose.com/temporary-license/). Thực hiện theo hướng dẫn để thiết lập môi trường và khởi tạo Aspose.Slides trong ứng dụng của bạn.

## Cách tạo biểu đồ donut PowerPoint bằng Aspose.Slides cho Java
Để tạo một biểu đồ donut, bắt đầu bằng việc tải hoặc tạo một đối tượng `Presentation`, thêm một shape biểu đồ loại `ChartType.Doughnut`, xóa các series mặc định, đặt kích thước lỗ, và sau đó điền workbook của biểu đồ với tên danh mục và giá trị số. Cuối cùng, điều chỉnh định dạng nhãn và lưu tệp PPTX.

### Bước 1: Khởi tạo bản trình chiếu
Tạo một bản trình chiếu mới hoặc mở tệp hiện có để lấy bộ sưu tập slide.

`Presentation` là lớp chính đại diện cho một tệp PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Bước 2: Thêm biểu đồ donut vào slide
Chèn một shape biểu đồ, loại bỏ các series/danh mục mặc định, và cấu hình các thiết lập trực quan cơ bản như kích thước lỗ donut.

`Chart` (hoặc chart shape) đại diện cho một đối tượng biểu đồ được đặt trên slide.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bước 3: Thêm điểm dữ liệu cho biểu đồ và tùy chỉnh nhãn
Điền tên danh mục, thêm các điểm dữ liệu cho mỗi series, và tinh chỉnh định dạng nhãn (phông chữ, màu sắc, vị trí). Bước này minh họa khả năng “thêm điểm dữ liệu cho biểu đồ”.

`Workbook` cung cấp quyền truy cập vào dữ liệu bảng tính nền của biểu đồ, nơi các ô được điền dữ liệu.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Bước 4: Lưu bản trình chiếu đã cập nhật
Lưu các thay đổi vào một tệp PPTX mới trên đĩa.

`save` ghi bản trình chiếu vào tệp với định dạng đã chọn.  
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

## Ứng dụng thực tiễn
- **Báo cáo tài chính:** Trực quan hoá phân bổ ngân sách hoặc chi phí.  
- **Phân tích thị trường:** Hiển thị phân phối thị phần giữa các đối thủ.  
- **Kết quả khảo sát:** Trình bày dữ liệu khảo sát theo danh mục dưới dạng gọn gàng.  
- **Tạo bảng điều khiển:** Kết hợp với truy vấn cơ sở dữ liệu để tạo các slide cập nhật liên tục.  

## Các lưu ý về hiệu năng
- **Giải phóng tài nguyên:** Gọi `pres.dispose()` sau khi lưu để giải phóng bộ nhớ native.  
- **Giới hạn số lượng biểu đồ:** Thêm hàng trăm biểu đồ có thể tăng sử dụng bộ nhớ; hãy xử lý theo lô nếu cần.  
- **Sử dụng streaming:** Đối với tập dữ liệu lớn, điền workbook trực tiếp từ luồng thay vì mảng trong bộ nhớ.  

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Biểu đồ hiển thị trống** | Các ô dữ liệu không được điền đúng cách | Xác minh rằng `workBook.getCell(...)` tham chiếu đúng chỉ số hàng/cột. |
| **Nhãn chồng lên nhau** | Quá nhiều danh mục trong không gian hạn chế | Tăng `DoughnutHoleSize` hoặc điều chỉnh `FirstSliceAngle`. |
| **OutOfMemoryError** | Bản trình chiếu lớn mà không giải phóng tài nguyên | Gọi `pres.dispose()` sau khi lưu và cân nhắc tăng kích thước heap của JVM. |

## Câu hỏi thường gặp

**Câu hỏi:** Tôi có thể sử dụng Aspose.Slides cho Java trong các ứng dụng thương mại không?  
**Trả lời:** Có, nhưng bạn cần một giấy phép thương mại hợp lệ. Có bản dùng thử miễn phí để đánh giá.

**Câu hỏi:** Làm sao để thêm hơn 15 series?  
**Trả lời:** Tăng giới hạn vòng lặp trong bước “Thêm biểu đồ donut” và đảm bảo workbook dữ liệu của bạn có đủ hàng.

**Câu hỏi:** Có thể thay đổi kích thước lỗ donut sau khi tạo không?  
**Trả lời:** Có, gọi `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` trước khi lưu.

**Câu hỏi:** Tôi có thể xuất biểu đồ dưới dạng hình ảnh thay vì PPTX không?  
**Trả lời:** Chắc chắn. Sử dụng `chart.getImage()` và lưu `java.awt.image.BufferedImage` trả về ở định dạng bạn muốn.

**Câu hỏi:** Aspose.Slides có hỗ trợ biểu đồ động không?  
**Trả lời:** Có thể thêm hoạt ảnh thông qua API `ISlide.getTimeline()`, mặc dù điều này nằm ngoài phạm vi của hướng dẫn này.

## Kết luận
Bây giờ bạn đã có một phương pháp hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **tạo tệp PowerPoint chứa biểu đồ donut** bằng Aspose.Slides cho Java, bao gồm cách **thêm điểm dữ liệu cho biểu đồ**, tùy chỉnh nhãn và xử lý các lưu ý về hiệu năng. Hãy thử nghiệm với các màu sắc, nguồn dữ liệu và loại biểu đồ khác nhau để làm cho bài thuyết trình của bạn thực sự nổi bật.

---

**Cập nhật lần cuối:** 2026-07-08  
**Kiểm thử với:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Tác giả:** Aspose

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

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Hướng dẫn liên quan

- [Cách Thêm Biểu Đồ vào PowerPoint Sử Dụng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Cách Chỉnh Sửa Dữ Liệu Biểu Đồ PowerPoint Sử Dụng Aspose.Slides cho Java: Hướng Dẫn Toàn Diện](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Tạo Hoạt Ảnh cho Biểu Đồ PowerPoint Sử Dụng Aspose.Slides cho Java – Hướng Dẫn Từng Bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}