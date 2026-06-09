---
date: '2026-03-02'
description: Tìm hiểu cách thêm Excel vào PowerPoint và tạo PowerPoint từ Excel bằng
  cách tạo biểu đồ tròn động với Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 'Thêm Excel vào PowerPoint: Bản trình bày động với biểu đồ tròn sử dụng Aspose.Slides
  cho Java'
url: /vi/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thêm Excel vào PowerPoint: Bản trình chiếu động với biểu đồ tròn sử dụng Aspose.Slides cho Java

Trong môi trường dựa trên dữ liệu ngày nay, **add Excel to PowerPoint** nhanh chóng và đáng tin cậy để khán giả của bạn có thể nhìn thấy các con số dưới dạng hình ảnh. Hướng dẫn này sẽ chỉ cho bạn cách tạo một PowerPoint từ Excel, tạo biểu đồ tròn bằng Java, và cấu hình phạm vi dữ liệu cho biểu đồ — tất cả đều sử dụng Aspose.Slides cho Java. Khi kết thúc, bạn sẽ có một bản trình chiếu sẵn sàng sử dụng, lấy dữ liệu trực tiếp từ một workbook Excel.

## Câu trả lời nhanh
- **What library creates charts in Java?** Aspose.Slides for Java.
- **Can I pull Excel data directly into a PowerPoint chart?** Yes – use Aspose.Cells to read the workbook and feed it to the chart.
- **Which chart type is demonstrated?** A pie chart.
- **How do I set the data range for the chart?** By calling `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.
- **What is the primary benefit of this approach?** Automates the “add Excel to PowerPoint” workflow, eliminating manual copy‑paste.

## **add Excel to PowerPoint** là gì?
Thêm Excel vào PowerPoint có nghĩa là nhập dữ liệu bảng tính một cách lập trình và hiển thị nó trong bộ slide. Với Aspose.Slides và Aspose.Cells, bạn có thể đọc bất kỳ tệp Excel nào, ánh xạ các ô vào series của biểu đồ, và tạo ra một bản trình chiếu chuyên nghiệp mà không cần mở PowerPoint thủ công.

## Tại sao tạo PowerPoint từ Excel bằng Aspose.Slides cho Java?
- **Speed:** Build reports in seconds, not minutes.  
- **Accuracy:** Data is read directly from the source workbook, removing transcription errors.  
- **Flexibility:** Customize chart colors, styles, and data ranges on the fly.  
- **Scalability:** Integrate into batch jobs, web services, or scheduled reporting pipelines.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- **Java Development Kit (JDK) 1.8+** đã được cài đặt.  
- Thư viện **Aspose.Slides for Java** và **Aspose.Cells for Java** (Maven, Gradle, hoặc tải JAR trực tiếp).  
- Một workbook Excel (`book1.xlsx`) chứa dữ liệu bạn muốn trực quan hoá.  
- Một giấy phép Aspose hợp lệ (bản dùng thử miễn phí hoạt động cho mục đích đánh giá).

### Thư viện cần thiết
Bạn sẽ cần Aspose.Slides và Aspose.Cells. Sử dụng một trong các công cụ quản lý phụ thuộc sau:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Hoặc, tải các JAR trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Cách lấy giấy phép
- **Free Trial:** Available on the [Aspose download page](https://releases.aspose.com/slides/java/).  
- **Temporary License:** For testing without evaluation limitations, apply for one at [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).  
- **Purchase License:** To use Aspose products in production, purchase the full license.

## Cài đặt Aspose.Slides cho Java

Thêm phụ thuộc Aspose.Slides vào dự án của bạn (xem các đoạn mã Maven/Gradle ở trên) và đặt các tệp JAR vào classpath nếu bạn không sử dụng công cụ xây dựng.

### Khởi tạo và Cấu hình Cơ bản
Nhập lớp cốt lõi đại diện cho tệp PowerPoint:

```java
import com.aspose.slides.Presentation;
```

## Hướng dẫn thực hiện

Dưới đây là hướng dẫn từng bước bao gồm **create pie chart java**, **set chart data range**, và **add Excel to PowerPoint** trong một quy trình duy nhất.

### Tạo và Thêm Biểu đồ vào Bản trình chiếu

**Tổng quan:** Khởi tạo một bản trình chiếu mới, lấy slide đầu tiên, và chèn một biểu đồ tròn.

#### Bước 1: Khởi tạo Presentation
```java
Presentation pres = new Presentation();
```
- **Mục đích:** Tạo một tệp PowerPoint trống trong bộ nhớ.

#### Bước 2: Truy cập Slide đầu tiên
```java
ISlide slide = pres.getSlides().get_Item(0);
```
- **Giải thích:** Lấy slide đầu tiên được tạo tự động.

#### Bước 3: Thêm biểu đồ tròn vào Slide
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **Tham số:** Vị trí (`x`, `y`) và kích thước (`width`, `height`).  
- **Mục đích:** Đặt một hình dạng biểu đồ tròn trên slide.

### Tải Workbook từ Tệp

**Tổng quan:** Tải workbook Excel chứa dữ liệu cho biểu đồ.

#### Bước 1: Xác định Thư mục Tài liệu
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- Đặt giá trị này thành thư mục chứa `book1.xlsx`.

#### Bước 2: Mở Workbook
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **Mục đích:** Đọc tệp Excel vào bộ nhớ.

### Lưu Workbook vào ByteArrayOutputStream

**Tổng quan:** Chuyển workbook thành mảng byte để Aspose.Slides có thể sử dụng.

#### Bước 1: Tạo ByteArrayOutputStream
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```
- **Mục đích:** Cung cấp một luồng trong bộ nhớ để lưu trữ tạm thời.

#### Bước 2: Lưu Workbook vào Stream
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```
- **Giải thích:** Ghi workbook dưới dạng luồng byte XLSX.

### Ghi Dữ liệu Workbook vào Biểu đồ

**Tổng quan:** Cung cấp mảng byte Excel cho biểu đồ làm nguồn dữ liệu.

#### Bước 1: Đưa Dữ liệu vào Biểu đồ
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **Mục đích:** Liên kết biểu đồ với dữ liệu Excel.

### Đặt Phạm vi Dữ liệu cho Biểu đồ và Cấu hình Series

**Tổng quan:** Xác định các ô mà biểu đồ sẽ đọc và cải thiện kiểu dáng trực quan.

#### Bước 1: Xác định Phạm vi Dữ liệu
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```
- **Giải thích:** Chỉ định biểu đồ tới phạm vi chính xác trên *Sheet2*.

#### Bước 2: Cấu hình Thuộc tính Series
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```
- **Mục đích:** Cho phép màu sắc khác nhau cho mỗi miếng của biểu đồ tròn.

### Lưu Bản trình chiếu vào Tệp

**Tổng quan:** Lưu bản trình chiếu đã hoàn thành vào đĩa.

#### Bước 1: Xác định Đường dẫn Đầu ra
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```
- Chọn một thư mục nơi bạn muốn lưu tệp PowerPoint cuối cùng.

#### Bước 2: Lưu Presentation
```java
pres.save(outPath, SaveFormat.Pptx);
```
- **Giải thích:** Ghi bản trình chiếu dưới dạng tệp `.pptx`.

## Ứng dụng Thực tiễn

1. **Business Reporting:** Turn monthly sales spreadsheets into polished slide decks with a single command.  
2. **Educational Tools:** Show statistical breakdowns for classroom presentations without manual chart creation.  
3. **Dashboard Integration:** Automate the generation of slide‑based dashboards that pull live data from Excel workbooks.

## Các yếu tố về Hiệu suất

- **Memory Management:** Wrap streams in try‑with‑resources or close them in a `finally` block to avoid leaks.  
- **Large Datasets:** Process data in chunks or use `Workbook.getWorksheets().clear()` after extracting needed values.  
- **Lazy Loading:** Load the workbook only when you need to populate the chart, not at application startup.

## Các vấn đề thường gặp và Giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Biểu đồ không hiển thị dữ liệu** | Xác minh chuỗi phạm vi khớp chính xác với tên sheet và địa chỉ ô (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | Sử dụng `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` để đảm bảo luồng được giải phóng kịp thời. |
| **Giấy phép không được áp dụng** | Tải giấy phép trước khi bất kỳ lớp Aspose nào được khởi tạo: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Slides mà không có giấy phép không?**  
A: Có, nhưng chế độ đánh giá sẽ thêm watermark và giới hạn một số tính năng. Đối với môi trường sản xuất, hãy lấy giấy phép tạm thời hoặc đầy đủ.

**Q: Làm thế nào để xử lý các bản trình chiếu lớn trong Aspose.Slides?**  
A: Sử dụng quản lý tài nguyên hiệu quả, chia bản trình chiếu thành các phần nhỏ hơn, và giải phóng các đối tượng không dùng ngay lập tức.

**Q: Aspose.Slides có thể xuất ra những định dạng tệp nào?**  
A: PPTX, PDF, XPS, ODP, HTML, và các định dạng hình ảnh như PNG, JPEG, và BMP.

**Q: Có thể cập nhật tệp PowerPoint hiện có thay vì tạo mới không?**  
A: Chắc chắn. Tải tệp hiện có bằng `new Presentation("existing.pptx")`, chỉnh sửa slide/biểu đồ, sau đó lưu.

**Q: Thư viện có hỗ trợ đặt màu tùy chỉnh cho từng miếng của biểu đồ tròn không?**  
A: Có – sau khi lấy series, bạn có thể đặt `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` và gán một `Color`.

## Tài nguyên
- **Documentation:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)
- **Purchase License:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Free Trial:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Temporary License:** [Get a Temporary License](https://purchase.aspose.com/temporary-license)

---

**Cập nhật lần cuối:** 2026-03-02  
**Kiểm tra với:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}