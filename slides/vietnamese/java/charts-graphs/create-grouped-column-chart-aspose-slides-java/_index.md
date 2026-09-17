---
date: '2026-09-17'
description: Tìm hiểu cách thêm clustered column chart vào bản trình chiếu PowerPoint,
  tùy chỉnh biểu đồ PowerPoint và chèn data series chart bằng Aspose.Slides for Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Tìm hiểu cách thêm clustered column chart vào bản trình chiếu PowerPoint
  bằng Aspose.Slides for Java, bao gồm các bước chèn data series, tùy chỉnh grouping
  và lưu tệp dưới dạng PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Thêm clustered column chart vào PowerPoint bằng Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: Cách thêm clustered column chart trong PowerPoint bằng Aspose.Slides for Java
url: /vi/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm biểu đồ cột nhóm trong PowerPoint bằng Aspose.Slides cho Java

## Giới thiệu

Khi bạn cần **thêm biểu đồ cột nhóm** vào một bộ slide PowerPoint, một hình ảnh rõ ràng có thể biến số liệu thô thành một câu chuyện dễ hiểu ngay lập tức. Thực hiện việc này thủ công trong PowerPoint có thể tốn thời gian, đặc biệt khi bạn phải tạo nhiều slide một cách lập trình. **Aspose.Slides for Java** loại bỏ rào cản – nó cho phép bạn tạo, tùy chỉnh biểu đồ PowerPoint và chèn biểu đồ chuỗi dữ liệu chỉ với vài dòng mã.

Trong tutorial này bạn sẽ học cách:
- Khởi tạo một bản trình bày PowerPoint mới bằng Aspose.Slides for Java.  
- **Thêm biểu đồ vào slide** và cấu hình nó thành biểu đồ cột nhóm.  
- **Tạo biểu đồ cột nhóm** bằng cách định nghĩa các mức nhóm cho các danh mục.  
- **Chèn biểu đồ chuỗi dữ liệu** để dữ liệu của bạn hiển thị đúng.  
- Lưu bản trình bày đã hoàn thiện dưới dạng tệp PPTX.

## Câu trả lời nhanh
- **Lớp chính là gì?** `Presentation` từ `com.aspose.slides`.  
- **Loại biểu đồ nào được sử dụng?** `ChartType.ClusteredColumn`.  
- **Tôi có cần giấy phép để thử nghiệm không?** Bản dùng thử miễn phí hoạt động, nhưng giấy phép sẽ loại bỏ các giới hạn đánh giá.  
- **Phiên bản Java nào được hỗ trợ?** JDK 16 hoặc mới hơn (ví dụ sử dụng JDK 16).  
- **Cách chạy mẫu?** Thêm phụ thuộc Maven/Gradle, biên dịch và chạy phương thức `main`.

## Biểu đồ cột nhóm là gì?

Biểu đồ cột nhóm hiển thị nhiều chuỗi dữ liệu cạnh nhau cho mỗi danh mục, cho phép bạn so sánh các giá trị giữa các nhóm trong một hình ảnh duy nhất. Nó lý tưởng cho doanh thu quý, kết quả khảo sát, hoặc bất kỳ trường hợp nào bạn cần so sánh nhiều bộ dữ liệu trong cùng một danh mục.

## Tại sao nên dùng Aspose.Slides để thêm biểu đồ cột nhóm?

Bạn có thể tự động tạo hàng chục slide, tùy chỉnh mọi yếu tố hình ảnh, và chạy mã trên bất kỳ hệ điều hành nào hỗ trợ Java—không cần cài đặt Microsoft Office. Aspose.Slides hỗ trợ **hơn 50 loại biểu đồ** và có thể xử lý các bản trình bày với **tối đa 500 slide** mà không cần tải toàn bộ tệp vào bộ nhớ, phù hợp cho các quy trình báo cáo quy mô lớn.

## Yêu cầu trước
- Thư viện **Aspose.Slides for Java** (phiên bản mới nhất được khuyến nghị).  
- JDK 16 hoặc mới hơn.  
- Công cụ xây dựng Maven hoặc Gradle (hoặc bạn có thể thêm JAR thủ công).  
- Một IDE hoặc trình soạn thảo văn bản để chạy mã Java.

## Cài đặt Aspose.Slides cho Java

Thêm thư viện vào dự án của bạn bằng một trong các script xây dựng sau.

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

Ngoài ra, bạn có thể tải trực tiếp bản phát hành mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Nhận giấy phép

Trước khi triển khai vào môi trường sản xuất, hãy lấy giấy phép:
- **Bản dùng thử** – khám phá tất cả tính năng mà không cần mua.  
- **Giấy phép tạm thời** – đánh giá các khả năng mở rộng trong thời gian ngắn.  
- **Giấy phép đầy đủ** – mở khóa sử dụng không giới hạn. Lấy nó từ [Aspose's purchase page](https://purchase.aspose.com/buy).

## Cách thêm biểu đồ cột nhóm trong PowerPoint bằng Aspose.Slides cho Java?

Tải một `Presentation` mới, thêm một slide, chèn một `Chart` loại `ChartType.ClusteredColumn`, điền dữ liệu vào workbook nội bộ của nó với các danh mục và chuỗi, sau đó lưu tệp dưới dạng PPTX. Quy trình này tạo ra một biểu đồ cột nhóm hoàn chỉnh chỉ với một vài lời gọi API.

### Khởi tạo bản trình bày

`Presentation` là lớp đại diện cho tệp PowerPoint trong bộ nhớ, cho phép bạn thêm slide, hình dạng và biểu đồ một cách lập trình.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Thêm biểu đồ vào slide

`ChartType.ClusteredColumn` cho Aspose.Slides biết để hiển thị một biểu đồ cột nhóm.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Chuẩn bị workbook dữ liệu biểu đồ

Biểu đồ lưu trữ dữ liệu trong một workbook nội bộ. Xóa nó sẽ cho bạn một khởi đầu sạch sẽ cho dữ liệu tùy chỉnh.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Thêm danh mục với mức nhóm

Nhóm các danh mục tạo ra hiệu ứng biểu đồ cột nhóm. Mỗi danh mục có thể thuộc một nhóm logic xuất hiện trong nhãn trục.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Thêm chuỗi dữ liệu vào biểu đồ

Các đối tượng `Series` đại diện cho các cột riêng lẻ trong biểu đồ. Thêm nhiều chuỗi sẽ tạo ra các cột cạnh nhau cho mỗi danh mục.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Lưu bản trình bày kèm biểu đồ

Lưu `Presentation` sẽ ghi ra một tệp PPTX tiêu chuẩn có thể mở bằng bất kỳ trình xem PowerPoint nào.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Ứng dụng thực tiễn

- **Báo cáo kinh doanh** – so sánh doanh thu quý theo khu vực.  
- **Nghiên cứu học thuật** – hiển thị kết quả thí nghiệm được nhóm theo điều kiện thử nghiệm.  
- **Quản lý dự án** – trực quan hoá tỷ lệ hoàn thành nhiệm vụ cho nhiều đội trên một slide duy nhất.

## Các cân nhắc về hiệu năng

- **Quản lý bộ nhớ** – giải phóng các workbook lớn sau khi sử dụng.  
- **Hoạt động batch** – tránh cập nhật biểu đồ trong vòng lặp chặt; thu thập dữ liệu trước, sau đó áp dụng.  
- **Tối ưu hoá tích hợp** – Aspose.Slides cung cấp các phương thức như `Presentation.optimize()` cho tệp lớn, giảm lượng bộ nhớ tiêu thụ tới **30 %**.

## Những lỗi thường gặp & mẹo

- **Cạm bẫy:** Quên xóa các series/danh mục hiện có có thể dẫn đến dữ liệu trùng lặp.  
  **Mẹo:** Luôn gọi `clear()` trước khi điền dữ liệu mới.  
- **Cạm bẫy:** Sử dụng địa chỉ ô sai (ví dụ, `"c2"` thay vì `"C2"`).  
  **Mẹo:** Tham chiếu ô không phân biệt chữ hoa/thường, nhưng hãy giữ chúng nhất quán để dễ đọc.  
- **Mẹo:** Sử dụng `setGroupingItem` để tạo nhãn nhóm có ý nghĩa; chúng sẽ xuất hiện trong chú giải biểu đồ tự động.

## Câu hỏi thường gặp

**Q1: Làm thế nào tôi có thể thêm nhiều series vào biểu đồ?**  
A1: Gọi `ch.getChartData().getSeries().add()` liên tục, cung cấp một tên duy nhất và các điểm dữ liệu cho mỗi series.

**Q2: Một số vấn đề thường gặp với biểu đồ Aspose.Slides là gì?**  
A2: Các vấn đề thường xuất phát từ phạm vi dữ liệu không khớp hoặc thiếu ô trong workbook. Kiểm tra rằng mỗi danh mục và điểm dữ liệu đều có ô tương ứng.

**Q3: Tôi có thể dùng Aspose.Slides với các ngôn ngữ lập trình khác không?**  
A3: Có, Aspose cung cấp các thư viện tương đương cho .NET, C++, Python và hơn nữa.

**Q4: Làm sao để cập nhật một biểu đồ hiện có trong bản trình bày?**  
A4: Tải bản trình bày, tìm biểu đồ qua `slide.getShapes().get_Item(index)`, sau đó chỉnh sửa series hoặc định dạng theo nhu cầu.

**Q5: Có giới hạn nào về loại biểu đồ với Aspose.Slides không?**  
A5: Thư viện hỗ trợ hơn **50 loại biểu đồ** và liên tục bổ sung các loại mới; luôn kiểm tra tài liệu mới nhất để có danh sách cập nhật nhất.

## Tài nguyên

- **Tài liệu:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Tải xuống:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Mua:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Dùng thử miễn phí:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Giấy phép tạm thời:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Diễn đàn hỗ trợ:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-09-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose

## Hướng dẫn liên quan

- [Hướng dẫn tạo biểu đồ trong Java với Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Cách thêm biểu đồ vào PowerPoint bằng Aspose.Slides cho Java: Hướng dẫn từng bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Thêm hoạt ảnh vào biểu đồ PowerPoint bằng Aspose.Slides cho Java – Hướng dẫn từng bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}