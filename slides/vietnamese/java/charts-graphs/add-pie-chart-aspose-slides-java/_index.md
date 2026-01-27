---
date: '2026-01-09'
description: Khám phá cách sử dụng Aspose.Slides Maven để thêm biểu đồ vào slide và
  tùy chỉnh biểu đồ tròn trong các bài thuyết trình Java. Hướng dẫn cài đặt từng bước,
  mã nguồn và các ví dụ thực tế.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - Thêm biểu đồ tròn vào bản trình chiếu'
url: /vi/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Thêm Biểu Đồ Tròn Vào Bản Trình Chiếu Sử Dụng Aspose.Slides Java

## Giới thiệu
Việc tạo các bản trình chiếu hấp dẫn về mặt hình ảnh là rất quan trọng để truyền đạt thông tin một cách hiệu quả, đặc biệt khi việc trực quan hoá dữ liệu đóng vai trò then chốt. Nếu bạn muốn tự động hoá quy trình này bằng **aspose slides maven**, bạn đã đến đúng nơi. Trong hướng dẫn này, bạn sẽ học cách **add chart to slide** — cụ thể là biểu đồ tròn — sử dụng Aspose.Slides cho Java, và xem cách tùy chỉnh nó cho các kịch bản thực tế!

### Những Điều Bạn Sẽ Học
- Cách khởi tạo một đối tượng presentation trong Java.  
- Các bước **add a pie chart java** trên slide đầu tiên của bản trình chiếu.  
- Truy cập workbook dữ liệu biểu đồ và liệt kê các worksheet bên trong.  

Hãy cùng khám phá cách bạn có thể tận dụng Aspose.Slides Java để nâng cao bản trình chiếu của mình với các biểu đồ động!

## Câu Trả Lời Nhanh
- **What library adds charts via Maven?** aspose slides maven  
- **Which chart type is demonstrated?** Pie chart (add chart to slide)  
- **Minimum Java version required?** JDK 16 or later  
- **Do I need a license for testing?** Bạn có cần giấy phép để thử nghiệm không? Một bản dùng thử miễn phí hoạt động; sản xuất cần giấy phép  
- **Where can I find the Maven dependency?** Trong phần thiết lập bên dưới  

## Aspose Slides Maven là gì?
Aspose.Slides for Java là một API mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và render các tệp PowerPoint một cách lập trình. Gói Maven (`aspose-slides`) đơn giản hoá việc quản lý phụ thuộc, cho phép bạn tập trung vào việc xây dựng và tùy chỉnh slide—như thêm biểu đồ tròn—mà không phải lo lắng về việc xử lý tệp ở mức thấp.

## Tại sao nên sử dụng Aspose.Slides Maven để thêm biểu đồ vào slide?
- **Tự động hoá:** Tự động tạo báo cáo và bảng điều khiển.  
- **Độ chính xác:** Kiểm soát đầy đủ các loại biểu đồ, dữ liệu và kiểu dáng.  
- **Đa nền tảng:** Hoạt động trên bất kỳ môi trường Java nào.  

## Yêu cầu trước
- **Aspose.Slides for Java** version 25.4 hoặc mới hơn (Maven/Gradle).  
- JDK 16+ đã được cài đặt.  
- Một IDE (IntelliJ IDEA, Eclipse, v.v.).  
- Kiến thức cơ bản về Java và quen thuộc với Maven hoặc Gradle.  

## Cài đặt Aspose.Slides cho Java
Đầu tiên, bao gồm Aspose.Slides vào dự án của bạn qua Maven hoặc Gradle.

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

Ngoài ra, bạn có thể [download the latest release](https://releases.aspose.com/slides/java/) trực tiếp từ trang web của Aspose.

### Cấp phép
Aspose.Slides for Java cung cấp bản dùng thử miễn phí với giấy phép tạm thời để thử nghiệm. Đối với việc sử dụng sản xuất không giới hạn, hãy mua giấy phép qua [purchase page](https://purchase.aspose.com/buy).

## Hướng Dẫn Triển Khai
Dưới đây chúng tôi chia giải pháp thành hai tính năng: thêm biểu đồ tròn và truy cập workbook dữ liệu của biểu đồ.

### Tính năng 1: Tạo Presentation và Thêm Biểu Đồ
#### Tổng quan
Phần này cho thấy cách tạo một presentation mới và **add a pie chart** vào slide đầu tiên.

#### Các bước thực hiện

**Step 1: Initialize a New Presentation Object**  
```java
Presentation pres = new Presentation();
```
*Creates the `Presentation` instance that will hold all slides.*  
*Tạo instance `Presentation` sẽ chứa tất cả các slide.*

**Step 2: Add a Pie Chart**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Places a pie chart at coordinates (50, 50) with a width of 400 and height of 500. The `ChartType.Pie` enum tells Aspose to render a pie chart.*  
*Đặt một biểu đồ tròn tại tọa độ (50, 50) với chiều rộng 400 và chiều cao 500. Enum `ChartType.Pie` cho Aspose biết phải render một biểu đồ tròn.*

**Step 3: Dispose of Resources**  
```java
if (pres != null) pres.dispose();
```
*Releases native resources; always call `dispose()` when you’re done.*  
*Giải phóng tài nguyên gốc; luôn gọi `dispose()` khi hoàn thành.*

### Tính năng 2: Truy cập Workbook Dữ liệu Biểu Đồ và Các Worksheet
#### Tổng quan
Học cách tiếp cận workbook nền tảng lưu trữ dữ liệu biểu đồ và lặp qua các worksheet của nó.

#### Các bước thực hiện

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Same as Feature 1, Step 1.*  
*Giống như Tính năng 1, Bước 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*Same as Feature 1, Step 2.*  
*Giống như Tính năng 1, Bước 2.*

**Step 3: Get the Chart Data Workbook**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Retrieves the `IChartDataWorkbook` linked to the chart.*  
*Lấy `IChartDataWorkbook` liên kết với biểu đồ.*

**Step 4: Iterate Through Worksheets**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Prints each worksheet’s name, letting you verify the data structure.*  
*In ra tên của mỗi worksheet, giúp bạn xác nhận cấu trúc dữ liệu.*

**Step 5: Dispose of Resources**  
*Same as Feature 1, Step 3.*  
*Giống như Tính năng 1, Bước 3.*

## Ứng dụng thực tiễn
- **Báo cáo dữ liệu:** Tự động tạo bộ slide với các chỉ số cập nhật cho trí tuệ kinh doanh.  
- **Bài thuyết trình học thuật:** Trực quan hoá kết quả nghiên cứu mà không cần tạo biểu đồ thủ công.  
- **Tài liệu marketing:** Trình bày hiệu suất sản phẩm hoặc kết quả khảo sát ngay lập tức.  

## Các lưu ý về hiệu năng
- Giữ số lượng slide và biểu đồ ở mức hợp lý; mỗi cái tiêu tốn bộ nhớ.  
- Luôn gọi `dispose()` để giải phóng tài nguyên gốc.  
- Tối ưu hoá việc xử lý dữ liệu workbook—tránh tải các tập dữ liệu khổng lồ vào một biểu đồ duy nhất.  

## Kết luận
Chúng tôi đã trình bày cách **aspose slides maven** cho phép bạn **add chart to slide** một cách lập trình và cách làm việc với workbook dữ liệu của biểu đồ. Với những khối xây dựng này, bạn có thể tự động hoá bất kỳ quy trình báo cáo nào cần đầu ra PowerPoint chuyên nghiệp.

### Các bước tiếp theo
- Khám phá các tùy chọn định dạng biểu đồ (màu sắc, chú giải, nhãn dữ liệu).  
- Kết nối tới nguồn dữ liệu bên ngoài (CSV, cơ sở dữ liệu) để điền dữ liệu biểu đồ một cách động.  
- Kết hợp nhiều loại biểu đồ trong một bản trình chiếu để kể chuyện phong phú hơn.  

## Câu hỏi thường gặp

**Q: How do I install Aspose.Slides for Java?**  
A: Use the Maven or Gradle dependency shown above, or download the library from the releases page.  
**Q: What are the system requirements for Aspose.Slides?**  
A: JDK 16 or later; the library is platform‑independent.  
**Q: Can I add other chart types besides pie charts?**  
A: Yes, Aspose.Slides supports bar, line, scatter, and many more chart types.  
**Q: How should I handle large presentations efficiently?**  
A: Dispose of objects promptly, limit the number of high‑resolution images, and reuse chart templates when possible.  
**Q: Where can I find more details about Aspose.Slides features?**  
A: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/) for a complete API reference.  
**Q: Is a license required for commercial use?**  
A: A valid license is required for production; a free trial is available for evaluation.  
**Q: Does the Maven package include all chart capabilities?**  
A: Yes, the `aspose-slides` Maven artifact contains the full charting engine.  

## Tài nguyên
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-01-09  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
