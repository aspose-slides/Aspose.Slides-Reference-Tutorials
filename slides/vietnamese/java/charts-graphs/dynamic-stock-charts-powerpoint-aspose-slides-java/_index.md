---
date: '2026-09-12'
description: Tìm hiểu cách sử dụng Maven Aspose Slides để thêm và tùy chỉnh dynamic
  stock charts trong PowerPoint bằng Java. Bao gồm setup, adding data series, formatting
  lines và saving.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Bài hướng dẫn Maven Aspose Slides cho thấy cách tạo và tùy chỉnh dynamic
  stock charts trong PowerPoint bằng Java, bao gồm data series, line formatting và
  saving.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Hướng dẫn Maven Aspose Slides: tạo dynamic stock charts trong PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: tạo dynamic stock charts trong PowerPoint bằng Java'
url: /vi/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: tạo biểu đồ chứng khoán động trong PowerPoint bằng Java

## Giới thiệu

**Maven Aspose Slides** cho phép bạn tạo chương trình các bài thuyết trình PowerPoint tinh vi từ Java. Trong hướng dẫn này, bạn sẽ học cách tạo biểu đồ chứng khoán động, thêm và định dạng chuỗi dữ liệu, tùy chỉnh các đường biểu đồ, và cuối cùng lưu tệp. Dù bạn là nhà phân tích tài chính chuẩn bị báo cáo quý hay là nhà phát triển xây dựng các bộ slide tự động, các bước dưới đây sẽ cung cấp cho bạn một giải pháp hoàn chỉnh, sẵn sàng cho môi trường sản xuất.

**Bạn sẽ học**
- Cách thiết lập Maven với Aspose.Slides cho Java  
- Cách thêm biểu đồ chứng khoán và xóa dữ liệu mặc định  
- Cách **add data series chart** và **format chart lines**  
- Cách **customize chart java**‑specific visual elements  
- Cách lưu bản trình bày đã cập nhật

Sẵn sàng biến các con số thô thành hình ảnh chứng khoán bắt mắt? Hãy bắt đầu!

## Câu trả lời nhanh
- **Tôi cần artifact Maven nào?** `aspose-slides` version 25.4 (or newer).  
- **Tôi có thể chạy trên bất kỳ hệ điều hành nào không?** Yes – the library is pure Java and works on Windows, macOS, and Linux.  
- **Tôi có cần giấy phép cho việc phát triển không?** A free temporary license works for testing; a full license is required for production.  
- **Các loại biểu đồ nào được hỗ trợ?** Over 70 built‑in chart types, including Stock, Line, and Bar charts.  
- **Tôi có thể xử lý bản trình bày có kích thước bao nhiêu?** Aspose.Slides can handle files with 500+ slides without loading the whole file into memory.

## Maven Aspose Slides là gì?

`Aspose.Slides for Java` là một API Java cho phép tạo, thao tác và chuyển đổi các tệp PowerPoint mà không cần Microsoft Office. Tích hợp Maven đơn giản hoá việc quản lý phụ thuộc, cho phép bạn tải thư viện trực tiếp từ Maven Central.

## Tại sao nên sử dụng Maven Aspose Slides cho biểu đồ chứng khoán?

Aspose.Slides hỗ trợ **70+ chart types** và có thể render các bản trình bày hàng trăm trang trong chưa đầy một giây trên phần cứng máy chủ tiêu chuẩn. Các tính năng **high‑low line** và **up/down bar** cung cấp cho bạn khả năng kiểm soát chính xác các hình ảnh tài chính, vượt xa những gì giao diện PowerPoint cung cấp.

## Yêu cầu trước

- **Java Development Kit (JDK)** – phiên bản 11 hoặc cao hơn.  
- **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo nào bạn thích.  
- **Aspose.Slides for Java** – phiên bản 25.4 (mới nhất tại thời điểm viết).  

### Cài đặt Aspose.Slides cho Java

#### Maven
Để tích hợp Aspose.Slides vào dự án của bạn bằng Maven, thêm phụ thuộc sau vào `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Đối với người dùng Gradle, thêm đoạn này vào `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Tải trực tiếp
Hoặc tải JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License acquisition** – bắt đầu với bản dùng thử miễn phí hoặc yêu cầu giấy phép tạm thời. Đối với sử dụng thương mại, mua giấy phép đầy đủ.

Để tham khảo chi tiết API, xem [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Cách tạo biểu đồ chứng khoán động từng bước

Tải bản trình bày của bạn, thêm biểu đồ chứng khoán, xóa dữ liệu mặc định, và sau đó chèn các chuỗi và danh mục của riêng bạn. Câu trả lời trực tiếp cho câu hỏi cốt lõi là:

> Tải một PPTX hiện có bằng `new Presentation("template.pptx")`, thêm một `Chart` loại `ChartType.Stock`, xóa các chuỗi và danh mục mặc định, sau đó điền dữ liệu của bạn vào các điểm dữ liệu và tùy chọn định dạng. Cuối cùng, gọi `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Khởi tạo bản trình bày
#### Tổng quan
Bắt đầu bằng cách tải một tệp PowerPoint hiện có để bạn có thể chỉnh sửa trực tiếp.

#### Bước‑bước
1. **Import the library** – lớp `Presentation` là điểm vào cho tất cả các thao tác slide.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Load the presentation file** – cung cấp đường dẫn tới tệp PPTX mẫu của bạn.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Thêm biểu đồ chứng khoán vào slide
#### Tổng quan
Chèn một biểu đồ Stock vào slide đầu tiên của bản trình bày.

Lớp `Chart` đại diện cho một hình dạng biểu đồ có thể được thêm vào slide.

#### Câu trả lời trực tiếp
Bạn thêm một biểu đồ chứng khoán bằng cách gọi `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Điều này tạo ra một đối tượng biểu đồ mà bạn có thể ngay lập tức thao tác.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Xóa chuỗi dữ liệu và danh mục hiện có trong biểu đồ
#### Tổng quan
Xóa bất kỳ chuỗi hoặc danh mục nào đã được điền sẵn để bạn có thể bắt đầu với một bộ dữ liệu sạch.

Đối tượng `ChartData` chứa các chuỗi và danh mục cho một biểu đồ.

#### Câu trả lời trực tiếp
Gọi `chart.getChartData().getSeries().clear()` và `chart.getChartData().getCategories().clear()` để xóa nội dung mặc định trước khi thêm dữ liệu của bạn.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Thêm danh mục vào dữ liệu biểu đồ
#### Tổng quan
Xác định các danh mục trục X (ví dụ: ngày tháng) nhóm các giá trị chứng khoán của bạn.

`ChartCategory` đại diện cho một nhãn trục X cho biểu đồ.

#### Câu trả lời trực tiếp
Tạo một `ChartCategory` mới cho mỗi nhãn bằng cách sử dụng `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, lặp lại cho mỗi tháng hoặc kỳ.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Thêm chuỗi dữ liệu vào biểu đồ
#### Tổng quan
Thêm bốn chuỗi thiết yếu: Open, High, Low và Close.

`ChartSeries` chứa một tập hợp các điểm dữ liệu cho một chuỗi cụ thể trong biểu đồ.

#### Câu trả lời trực tiếp
Đối với mỗi chuỗi, gọi `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Điều này đăng ký chuỗi vào workbook dữ liệu của biểu đồ.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Thêm điểm dữ liệu vào chuỗi
#### Tổng quan
Điền dữ liệu cho mỗi chuỗi bằng các giá trị số đại diện cho giá chứng khoán.

`DataPoint` đại diện cho một giá trị duy nhất trong một chuỗi.

#### Câu trả lời trực tiếp
Lặp qua bộ dữ liệu của bạn và sử dụng `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (hoặc phương thức phù hợp cho loại chuỗi) để chèn từng điểm.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Định dạng các đường high‑low và thanh up/down
#### Tổng quan
Điều chỉnh kiểu hiển thị của các kết nối high‑low và màu nền của thanh up/down.

`Marker` định nghĩa biểu tượng trực quan cho một điểm dữ liệu.

#### Câu trả lời trực tiếp
Đặt `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` và cấu hình `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` để kiểm soát độ dày và màu sắc của đường.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Hiển thị thanh up/down
Sử dụng phương thức `setShowUpDownBars(true)` của biểu đồ để hiển thị các thanh up/down.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Tùy chỉnh nhãn dữ liệu trên các đường high‑low
#### Tổng quan
Hiển thị giá trị số trực tiếp trên các đường high‑low để tham khảo nhanh.

`DataLabel` kiểm soát cách hiển thị của nhãn gắn vào các điểm dữ liệu.

#### Câu trả lời trực tiếp
Kích hoạt nhãn dữ liệu bằng `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` và định dạng chúng theo nhu cầu.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Đặt màu nền cho thanh up/down
#### Tổng quan
Đặt màu nền xanh lá cho thanh lên và màu đỏ cho thanh xuống để truyền tải chuyển động thị trường một cách trực quan.

Đối tượng `UpDownBars` cung cấp quyền truy cập vào định dạng của thanh lên và xuống.

#### Câu trả lời trực tiếp
Áp dụng `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` và đặt màu nền thành `Color.GREEN`; lặp lại cho thanh xuống với `Color.RED`.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Lưu tệp PowerPoint
#### Tổng quan
Lưu các thay đổi của bạn vào một tệp PPTX mới.

Phương thức `save` ghi bản trình bày ra đĩa ở định dạng đã chỉ định.

#### Câu trả lời trực tiếp
Gọi `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – lệnh này ghi bản trình bày đã chỉnh sửa ra đĩa ở định dạng PowerPoint tiêu chuẩn.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Các vấn đề thường gặp và khắc phục
- **Chart not appearing** – đảm bảo tọa độ X/Y và kích thước của biểu đồ nằm trong giới hạn slide.  
- **Data points missing** – xác minh rằng chỉ số ô trong workbook dữ liệu khớp với chuỗi/hàng bạn muốn điền.  
- **License exception** – giấy phép dùng thử tạm thời hết hạn sau 30 ngày; thay thế bằng giấy phép vĩnh viễn cho các bản dựng sản xuất.  
- **Performance slowdown on large files** – sử dụng `Presentation.setCacheSize(0)` để tắt bộ nhớ đệm nếu bạn xử lý hàng ngàn slide trong một lô.

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng mã này trong ứng dụng web không?**  
A: Có. Thư viện thuần Java, vì vậy bạn có thể chạy nó trong bất kỳ container servlet nào hoặc dịch vụ Spring Boot.

**Q: Aspose.Slides có hỗ trợ các loại biểu đồ khác ngoài Stock không?**  
A: Chắc chắn. Nó hỗ trợ hơn 70 loại biểu đồ, bao gồm Line, Bar, Pie và Radar.

**Q: Làm thế nào để thêm tiêu đề biểu đồ bằng chương trình?**  
A: Sử dụng `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` và sau đó định dạng tiêu đề theo nhu cầu.

**Q: Có giới hạn về số điểm dữ liệu mỗi chuỗi không?**  
A: Thực tế, bạn có thể thêm hàng chục nghìn điểm; việc sử dụng bộ nhớ tăng tuyến tính, và thư viện truyền dữ liệu để giữ dung lượng thấp.

**Q: Tôi nên sử dụng coordinates Maven nào cho phiên bản mới nhất?**  
A: Phiên bản mới nhất luôn có sẵn dưới `com.aspose:aspose-slides:25.4` (hoặc mới hơn) trên Maven Central.

---

**Cập nhật lần cuối:** 2026-09-12  
**Kiểm tra với:** Aspose.Slides for Java 25.4  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [aspose slides maven dependency: Thêm và cấu hình biểu đồ trong bản trình bày bằng Aspose.Slides cho Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Tạo biểu đồ PowerPoint Java – Lưu bản trình bày với biểu đồ bằng Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Tạo và định dạng biểu đồ Powerpoint bằng Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}