---
date: '2026-06-13'
description: Tìm hiểu cách thêm Excel vào PowerPoint và tạo PowerPoint từ Excel bằng
  cách tạo biểu đồ tròn động với Aspose.Slides for Java.
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'Thêm Excel vào PowerPoint: Bản trình bày động với biểu đồ tròn sử dụng Aspose.Slides
  for Java'
url: /vi/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thêm Excel vào PowerPoint: Bản trình bày động với biểu đồ tròn sử dụng Aspose.Slides cho Java

Trong môi trường dựa trên dữ liệu ngày nay, **thêm Excel vào PowerPoint** nhanh chóng và đáng tin cậy để khán giả của bạn có thể nhìn thấy các con số dưới dạng hình ảnh. Hướng dẫn này sẽ chỉ cho bạn cách tạo một PowerPoint từ Excel, tạo biểu đồ tròn bằng Java, và cấu hình phạm vi dữ liệu của biểu đồ — tất cả đều sử dụng Aspose.Slides cho Java. Khi hoàn thành, bạn sẽ có một bản trình bày sẵn sàng sử dụng, lấy dữ liệu trực tiếp từ một workbook Excel.

## Trả lời nhanh
- **Thư viện nào tạo biểu đồ trong Java?** Aspose.Slides for Java.  
- **Tôi có thể lấy dữ liệu Excel trực tiếp vào biểu đồ PowerPoint không?** Có – sử dụng Aspose.Cells để đọc workbook và đưa dữ liệu vào biểu đồ.  
- **Loại biểu đồ nào được minh họa?** Biểu đồ tròn.  
- **Làm thế nào để đặt phạm vi dữ liệu cho biểu đồ?** Bằng cách gọi `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.  
- **Lợi ích chính của cách tiếp cận này là gì?** Tự động hoá quy trình “thêm Excel vào PowerPoint”, loại bỏ việc sao chép‑dán thủ công.

## **add Excel to PowerPoint** là gì?
Thêm Excel vào PowerPoint có nghĩa là nhập dữ liệu bảng tính một cách lập trình và hiển thị nó trong bộ slide. Điều này cho phép bạn giữ dữ liệu nguồn ở định dạng Excel gốc trong khi trình bày nó dưới dạng biểu đồ chuyên nghiệp, đảm bảo bất kỳ cập nhật nào của workbook đều được phản ánh ngay lập tức trong bản trình bày.

## Tại sao tạo PowerPoint từ Excel bằng Aspose.Slides cho Java?
Tạo PowerPoint từ Excel bằng Aspose.Slides cho Java cho phép bạn xây dựng bộ slide trong vài giây, lấy dữ liệu trực tiếp từ workbook mà không cần sao chép‑dán thủ công. Thư viện hỗ trợ hơn 50 định dạng nhập và xuất, xử lý các workbook hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, và cung cấp kiểm soát lập trình đầy đủ đối với kiểu dáng biểu đồ, màu sắc và phạm vi dữ liệu.

## Cách tạo PowerPoint từ Excel bằng Aspose.Slides cho Java?
Tải workbook Excel bằng Aspose.Cells, tạo một `Presentation` mới, thêm một hình dạng biểu đồ tròn vào slide, sau đó liên kết biểu đồ với phạm vi dữ liệu của workbook. Chỉ với vài dòng mã Java, bạn có thể tạo ra một tệp `.pptx` hoàn chỉnh phản ánh các giá trị mới nhất của bảng tính.

## Cách nhập Excel vào PowerPoint với Aspose.Slides?
Nhập Excel vào PowerPoint được thực hiện bằng cách đọc tệp Excel vào một đối tượng `Workbook`, chuyển đổi workbook thành mảng byte, và truyền mảng byte đó vào nguồn dữ liệu của biểu đồ. Biểu đồ tự động đọc phạm vi đã chỉ định, vì vậy hình ảnh luôn đồng bộ với bảng tính.

## Cách đặt phạm vi dữ liệu cho biểu đồ trong Aspose.Slides cho Java?
Sử dụng phương thức `chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` để chỉ định biểu đồ tới các ô chính xác chứa danh mục và giá trị của bạn. Lệnh duy nhất này định nghĩa cả nguồn dữ liệu và bố cục, loại bỏ nhu cầu xây dựng series thủ công.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- **Java Development Kit (JDK) 1.8+** đã được cài đặt.
- **Aspose.Slides for Java** và **Aspose.Cells for Java** (Maven, Gradle, hoặc tải JAR trực tiếp).
- Một workbook Excel (`book1.xlsx`) chứa dữ liệu bạn muốn trực quan hoá.
- Một giấy phép Aspose hợp lệ (bản dùng thử miễn phí hoạt động cho mục đích đánh giá).

### Thư viện yêu cầu
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

Hoặc tải JAR trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Nhận giấy phép
- **Free Trial:** Có sẵn trên [trang tải xuống Aspose](https://releases.aspose.com/slides/java/).  
- **Temporary License:** Để thử nghiệm mà không có giới hạn đánh giá, đăng ký tại [trang giấy phép tạm thời của Aspose](https://purchase.aspose.com/temporary-license/).  
- **Purchase License:** Để sử dụng sản phẩm Aspose trong môi trường sản xuất, mua giấy phép đầy đủ.

## Cài đặt Aspose.Slides cho Java

Thêm phụ thuộc Aspose.Slides vào dự án của bạn (xem các đoạn mã Maven/Gradle ở trên) và đặt các tệp JAR vào classpath nếu bạn không sử dụng công cụ xây dựng.

### Khởi tạo và cấu hình cơ bản
Nhập lớp cốt lõi đại diện cho tệp PowerPoint:  
```java
import com.aspose.slides.Presentation;
```  

## Hướng dẫn triển khai

Dưới đây là hướng dẫn từng bước bao gồm **create pie chart java**, **set chart data range**, và **add Excel to PowerPoint** trong một quy trình duy nhất.

### Tạo và Thêm Biểu Đồ vào Bản Trình Bày

**Tổng quan:** Khởi tạo một bản trình bày mới, lấy slide đầu tiên, và chèn một biểu đồ tròn.

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
Đối tượng `IChart` đại diện cho một hình dạng biểu đồ trên slide.  
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
Lớp `Workbook` từ Aspose.Cells tải tệp Excel vào bộ nhớ.  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **Mục đích:** Đọc tệp Excel vào bộ nhớ.

### Lưu Workbook vào ByteArrayOutputStream

**Tổng quan:** Chuyển đổi workbook thành mảng byte để Aspose.Slides có thể sử dụng.

#### Bước 1: Tạo ByteArrayOutputStream  
`ByteArrayOutputStream` cung cấp một bộ đệm trong bộ nhớ cho dữ liệu nhị phân.  
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

### Ghi Dữ liệu Workbook vào Biểu Đồ

**Tổng quan:** Đưa mảng byte Excel vào biểu đồ như nguồn dữ liệu.

#### Bước 1: Đưa Dữ liệu vào Biểu Đồ  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **Mục đích:** Liên kết biểu đồ với dữ liệu Excel.

### Đặt Phạm vi Dữ liệu Biểu Đồ và Cấu hình Series

**Tổng quan:** Xác định các ô mà biểu đồ sẽ đọc và cải thiện kiểu dáng hình ảnh.

#### Bước 1: Xác định Phạm vi Dữ liệu  
Phương thức `setRange` xác định các ô Excel được sử dụng làm nguồn dữ liệu cho biểu đồ.  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **Giải thích:** Chỉ định biểu đồ tới phạm vi chính xác trên *Sheet2*.

#### Bước 2: Cấu hình Thuộc tính Series  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **Mục đích:** Cho phép màu sắc khác nhau cho mỗi phần của biểu đồ tròn.

### Lưu Bản Trình Bày vào Tệp

**Tổng quan:** Lưu bản trình bày đã hoàn thành vào đĩa.

#### Bước 1: Xác định Đường dẫn Đầu ra  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- Chọn một thư mục nơi bạn muốn lưu tệp PowerPoint cuối cùng.

#### Bước 2: Lưu Bản Trình Bày  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **Giải thích:** Ghi bản trình bày dưới dạng tệp `.pptx`.

## Ứng dụng Thực tế

1. **Business Reporting:** Chuyển các bảng tính bán hàng hàng tháng thành bộ slide chuyên nghiệp chỉ bằng một lệnh.  
2. **Educational Tools:** Hiển thị phân tích thống kê cho các bài thuyết trình lớp học mà không cần tạo biểu đồ thủ công.  
3. **Dashboard Integration:** Tự động tạo các bảng điều khiển dựa trên slide, lấy dữ liệu trực tiếp từ workbook Excel.

## Các cân nhắc về hiệu năng

- **Quản lý bộ nhớ:** Bao gói các stream trong try‑with‑resources hoặc đóng chúng trong khối `finally` để tránh rò rỉ.  
- **Bộ dữ liệu lớn:** Xử lý dữ liệu theo khối hoặc sử dụng `Workbook.getWorksheets().clear()` sau khi trích xuất các giá trị cần thiết.  
- **Tải lười:** Chỉ tải workbook khi bạn cần điền dữ liệu vào biểu đồ, không phải khi khởi động ứng dụng.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Biểu đồ không hiển thị dữ liệu** | Xác minh chuỗi phạm vi khớp chính xác với tên sheet và địa chỉ ô (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | Sử dụng `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` để đảm bảo luồng được giải phóng kịp thời. |
| **Giấy phép không được áp dụng** | Tải giấy phép trước khi bất kỳ lớp Aspose nào được khởi tạo: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Slides mà không có giấy phép không?**  
A: Có, nhưng chế độ đánh giá sẽ thêm watermark và giới hạn một số tính năng. Đối với môi trường sản xuất, hãy lấy giấy phép tạm thời hoặc đầy đủ.

**Q: Làm thế nào để xử lý các bản trình bày lớn trong Aspose.Slides?**  
A: Sử dụng quản lý tài nguyên hiệu quả, chia bản trình bày thành các phần nhỏ hơn, và giải phóng các đối tượng không dùng ngay lập tức.

**Q: Aspose.Slides có thể xuất ra những định dạng tệp nào?**  
A: PPTX, PDF, XPS, ODP, HTML, và các định dạng ảnh như PNG, JPEG và BMP.

**Q: Có thể cập nhật tệp PowerPoint hiện có thay vì tạo mới không?**  
A: Chắc chắn. Tải tệp hiện có bằng `new Presentation("existing.pptx")`, chỉnh sửa slide/biểu đồ, sau đó lưu.

**Q: Thư viện có hỗ trợ đặt màu tùy chỉnh cho từng phần của biểu đồ tròn không?**  
A: Có – sau khi lấy series, bạn có thể đặt `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` và gán một `Color`.

## Tài nguyên
- **Documentation:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)
- **Purchase License:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Free Trial:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Temporary License:** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Cập nhật lần cuối:** 2026-06-13  
**Được kiểm tra với:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách Cập nhật Phạm vi Dữ liệu Biểu đồ PowerPoint bằng Aspose.Slides cho Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [Cách thêm biểu đồ tròn vào PowerPoint với Aspose.Slides cho Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Cách Thêm Biểu đồ vào PowerPoint bằng Aspose.Slides cho Java: Hướng dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}