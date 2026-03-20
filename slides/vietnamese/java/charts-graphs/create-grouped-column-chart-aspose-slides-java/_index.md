---
date: '2026-03-20'
description: Tìm hiểu cách thêm biểu đồ cột nhóm vào bản trình bày PowerPoint, tùy
  chỉnh biểu đồ PowerPoint và chèn biểu đồ chuỗi dữ liệu bằng Aspose.Slides cho Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Cách thêm biểu đồ cột nhóm trong PowerPoint bằng Aspose.Slides cho Java
url: /vi/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thêm biểu đồ cột nhóm trong PowerPoint bằng Aspose.Slides cho Java

## Introduction

Khi bạn cần **thêm biểu đồ cột nhóm** vào một bộ PowerPoint, một hình ảnh rõ ràng có thể biến các con số thô thành một câu chuyện dễ hiểu ngay lập tức. Thực hiện việc này thủ công trong PowerPoint có thể tốn thời gian, đặc biệt khi bạn phải tạo nhiều slide một cách lập trình. **Aspose.Slides for Java** loại bỏ rào cản – nó cho phép bạn tạo, tùy chỉnh biểu đồ PowerPoint và chèn biểu đồ chuỗi dữ liệu chỉ với vài dòng mã.

Trong tutorial này bạn sẽ học cách:
- Khởi tạo một bản trình bày PowerPoint mới bằng Aspose.Slides cho Java.
- **Thêm biểu đồ vào slide** và cấu hình nó dưới dạng biểu đồ cột nhóm.
- **Tạo biểu đồ cột nhóm** bằng cách định nghĩa các mức nhóm cho các danh mục.
- **Chèn biểu đồ chuỗi dữ liệu** để dữ liệu của bạn được hiển thị đúng.
- Lưu bản trình bày đã hoàn thiện dưới dạng tệp PPTX.

Hãy chắc chắn rằng bạn có mọi thứ cần thiết trước khi chúng ta bắt đầu với mã.

## Quick Answers
- **What is the primary class?** `Presentation` from `com.aspose.slides`.
- **Which chart type is used?** `ChartType.ClusteredColumn`.
- **Do I need a license for testing?** A free trial works, but a license removes evaluation limits.
- **What Java version is supported?** JDK 16 or newer (the example uses JDK 16).
- **How to run the sample?** Add the Maven/Gradle dependency, compile, and run the `main` method.

## What is “add clustered column chart”?

Một *biểu đồ cột nhóm* (còn gọi là biểu đồ cột nhóm) hiển thị nhiều chuỗi dữ liệu cạnh nhau cho mỗi danh mục, giúp dễ dàng so sánh các giá trị giữa các nhóm. Trong PowerPoint, loại biểu đồ này lý tưởng cho doanh thu quý, kết quả khảo sát, hoặc bất kỳ trường hợp nào bạn cần đối chiếu nhiều bộ dữ liệu trong cùng một danh mục.

## Why use Aspose.Slides to add clustered column chart?

- **Full automation** – tạo hàng chục slide mà không cần nỗ lực thủ công.
- **Fine‑grained customization** – kiểm soát màu sắc, nhãn, mức nhóm và hơn thế nữa.
- **Cross‑platform** – hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.
- **No Office installation required** – tạo tệp PPTX trên máy chủ hoặc trong các pipeline CI.

## Prerequisites

- Thư viện **Aspose.Slides for Java** (phiên bản mới nhất được khuyến nghị).  
- JDK 16 hoặc mới hơn.  
- Công cụ xây dựng Maven hoặc Gradle (hoặc bạn có thể thêm JAR thủ công).  
- Một IDE hoặc trình soạn thảo văn bản để chạy mã Java.

## Setting Up Aspose.Slides for Java

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

### License Acquisition

Trước khi triển khai vào môi trường production, hãy mua giấy phép:
- **Free trial** – khám phá tất cả tính năng mà không cần mua.
- **Temporary license** – đánh giá các khả năng mở rộng trong thời gian ngắn.
- **Full license** – mở khóa sử dụng không giới hạn. Nhận giấy phép tại [Aspose's purchase page](https://purchase.aspose.com/buy).

## Implementation Guide

Chúng tôi sẽ hướng dẫn từng bước, giải thích **cách thêm biểu đồ** và **tùy chỉnh biểu đồ PowerPoint** trong quá trình thực hiện.

### Initialize Presentation

Đầu tiên, tạo một đối tượng `Presentation` mới và lấy slide mặc định.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Add Chart to Slide

Bây giờ chúng ta **thêm biểu đồ vào slide** bằng loại `ClusteredColumn` và xóa mọi dữ liệu mặc định.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Prepare Chart Data Workbook

Biểu đồ lưu trữ dữ liệu trong một workbook nội bộ. Chúng ta xóa nó để bắt đầu từ đầu.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Add Categories with Grouping Levels

Việc nhóm các danh mục tạo ra hiệu ứng **biểu đồ cột nhóm**. Mỗi danh mục có thể thuộc về một nhóm logic.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Add Data Series to Chart

Ở đây chúng ta **chèn biểu đồ chuỗi dữ liệu** mà sẽ được hiển thị dưới dạng các cột riêng biệt.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Save Presentation with Chart

Cuối cùng, ghi tệp PPTX ra đĩa.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications

- **Business Reports** – so sánh doanh thu quý theo khu vực.  
- **Academic Research** – hiển thị kết quả thí nghiệm được nhóm theo điều kiện thử nghiệm.  
- **Project Management** – trực quan hoá tỷ lệ hoàn thành nhiệm vụ của nhiều đội trên một slide duy nhất.

## Performance Considerations

- **Memory management** – giải phóng các workbook lớn sau khi sử dụng.  
- **Batch operations** – tránh cập nhật biểu đồ trong các vòng lặp chặt; thu thập dữ liệu trước, sau đó áp dụng.  
- **Built‑in optimizations** – Aspose.Slides cung cấp các phương thức như `Presentation.optimize()` cho các tệp lớn.

## Common Pitfalls & Tips

- **Pitfall:** Quên xóa các series/danh mục hiện có có thể dẫn đến dữ liệu trùng lặp.  
  **Tip:** Luôn gọi `clear()` trước khi điền dữ liệu mới.  
- **Pitfall:** Sử dụng địa chỉ ô sai (ví dụ, `"c2"` thay vì `"C2"`).  
  **Tip:** Tham chiếu ô không phân biệt chữ hoa/thường, nhưng nên giữ nhất quán để dễ đọc.  
- **Tip:** Sử dụng `setGroupingItem` để tạo nhãn nhóm có ý nghĩa; chúng sẽ tự động xuất hiện trong chú giải biểu đồ.

## Frequently Asked Questions

**Q1: How can I add multiple series to my chart?**  
A1: Call `ch.getChartData().getSeries().add()` repeatedly, providing a unique name and data points for each series.

**Q2: What are some common issues with Aspose.Slides charts?**  
A2: Issues often stem from mismatched data ranges or missing workbook cells. Verify that every category and data point has a corresponding cell.

**Q3: Can I use Aspose.Slides with other programming languages?**  
A3: Yes, Aspose provides equivalent libraries for .NET, C++, Python, and more.

**Q4: How do I update an existing chart in a presentation?**  
A4: Load the presentation, locate the chart via `slide.getShapes().get_Item(index)`, then modify its series or formatting as needed.

**Q5: Are there limitations on chart types with Aspose.Slides?**  
A5: The library supports a wide range of chart types, but always check the latest documentation for any newly added or deprecated types.

## Resources

- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Free Trial**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Temporary License**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support Forum**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose