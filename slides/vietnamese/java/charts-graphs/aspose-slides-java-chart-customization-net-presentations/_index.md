---
date: '2026-06-08'
description: Tìm hiểu cách thêm chuỗi vào biểu đồ và tùy chỉnh biểu đồ cột chồng trong
  các bản trình chiếu .NET bằng cách sử dụng Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Thêm chuỗi vào biểu đồ với Aspose.Slides for Java trong .NET
url: /vi/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thành thạo Tùy chỉnh Biểu đồ trong Bài thuyết trình .NET bằng Aspose.Slides cho Java

## Giới thiệu
Trong lĩnh vực các bài thuyết trình dựa trên dữ liệu, biểu đồ là công cụ không thể thiếu giúp biến những con số thô thành những câu chuyện hình ảnh hấp dẫn. Khi bạn cần **thêm series vào biểu đồ** một cách lập trình, đặc biệt là trong các tệp .NET presentation, công việc có thể cảm thấy quá tải. May mắn là **Aspose.Slides cho Java** cung cấp một API mạnh mẽ, không phụ thuộc ngôn ngữ, giúp việc tạo và tùy chỉnh biểu đồ trở nên đơn giản—ngay cả khi định dạng đích là một tệp .NET PPTX. Hướng dẫn này sẽ chỉ cho bạn cách thêm series, xây dựng biểu đồ cột chồng, và tinh chỉnh các khía cạnh hình ảnh như độ rộng khoảng trống, để bạn có thể tạo ra các slide động, giàu dữ liệu, trông chuyên nghiệp và tinh tế.

## Câu trả lời nhanh
Lớp `Presentation` đại diện cho một tệp PPTX, và `slide.getShapes().addChart(...)` chèn một hình dạng biểu đồ. Dùng `chart.getChartData().getSeries().add(...)` để thêm một series, và `setGapWidth()` để điều chỉnh khoảng cách.

- **Lớp chính để bắt đầu một bài thuyết trình là gì?** `Presentation` – đại diện cho một tệp PPTX trong bộ nhớ.  
- **Phương thức nào thêm biểu đồ vào slide?** `slide.getShapes().addChart(...)` tạo đối tượng biểu đồ trên slide.  
- **Làm thế nào để thêm một series mới?** `chart.getChartData().getSeries().add(...)` chèn một series dữ liệu mới.  
- **Có thể thay đổi độ rộng khoảng trống giữa các cột không?** Có—gọi `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (giá trị là phần trăm).  
- **Có cần giấy phép cho môi trường sản xuất không?** Chắc chắn—giấy phép hợp lệ của Aspose.Slides cho Java sẽ mở khóa tất cả tính năng và loại bỏ watermark đánh giá.

## “add series to chart” là gì?
Thêm một series vào biểu đồ có nghĩa là chèn một tập hợp các điểm dữ liệu mới mà biểu đồ sẽ hiển thị như một yếu tố hình ảnh riêng biệt (ví dụ: một nhóm cột riêng). Mỗi series có thể có các giá trị, màu sắc và định dạng riêng, cho phép so sánh cạnh nhau của nhiều bộ dữ liệu.

## Tại sao nên dùng Aspose.Slides cho Java để chỉnh sửa bài thuyết trình .NET?
Aspose.Slides cho Java cho phép bạn tạo hoặc chỉnh sửa các tệp PPTX hoàn toàn tương thích với trình xem PowerPoint .NET, mà không cần cài đặt Microsoft Office. Sử dụng Aspose.Slides cho Java khi bạn cần một giải pháp phía máy chủ, đa nền tảng, tạo hoặc cập nhật các tệp .NET PPTX, hỗ trợ hơn 50 loại biểu đồ, và xử lý các tệp lên tới 500 MB mà không cần tải toàn bộ tài liệu vào bộ nhớ. API của nó hoạt động trong Java, Kotlin, Scala hoặc bất kỳ ngôn ngữ JVM nào, mang lại cùng một đầu ra mà các nhà phát triển .NET mong đợi.

## Yêu cầu trước
- Thư viện **Aspose.Slides cho Java** (phiên bản 25.4 trở lên).  
- Maven, Gradle, hoặc tải JAR thủ công.  
- Kiến thức cơ bản về Java và quen thuộc với cấu trúc tệp PPTX.  

## Cài đặt Aspose.Slides cho Java
### Cài đặt Maven
Thêm phụ thuộc sau vào file `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Cài đặt Gradle
Thêm dòng này vào file `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Hoặc tải JAR mới nhất từ trang phát hành chính thức: [Phiên bản Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).

**Mua giấy phép**  
Bắt đầu với bản dùng thử miễn phí bằng cách tải giấy phép tạm thời từ [đây](https://purchase.aspose.com/temporary-license/). Đối với môi trường sản xuất, mua giấy phép đầy đủ để mở khóa tất cả tính năng và loại bỏ watermark đánh giá.

## Hướng dẫn thực hiện từng bước
Dưới mỗi bước bạn sẽ thấy một đoạn mã ngắn gọn (giữ nguyên như trong tutorial gốc) kèm theo giải thích về chức năng của nó.

### Bước 1: Tạo một Presentation trống
`Presentation` là lớp đầu vào đại diện cho một tệp PowerPoint trong bộ nhớ.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Chúng ta bắt đầu với một tệp PPTX sạch, cung cấp một canvas để thêm biểu đồ.*

### Bước 2: Thêm biểu đồ Cột Chồng vào Slide
`Chart` đại diện cho một hình dạng biểu đồ trong slide. `ChartType.StackedColumn` chỉ định biểu đồ cột chồng.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Phương thức `addChart` tạo một **biểu đồ cột chồng** và đặt nó ở góc trên‑trái của slide.*

### Bước 3: Thêm Series vào Biểu đồ (Mục tiêu chính)
`Series` bao bọc một series dữ liệu duy nhất trong biểu đồ.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Ở đây chúng ta **thêm series vào biểu đồ** – mỗi lần gọi tạo một series dữ liệu mới sẽ xuất hiện như một nhóm cột riêng.*

### Bước 4: Thêm Danh mục (Categories) vào Biểu đồ
`Category` định nghĩa nhãn trục X cho dữ liệu biểu đồ.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Các danh mục hoạt động như nhãn trục X, cung cấp ý nghĩa cho mỗi cột.*

### Bước 5: Điền Dữ liệu cho Series
`DataPoint` chứa một giá trị số cho một series tại một danh mục cụ thể.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Các điểm dữ liệu cung cấp giá trị số cho mỗi series, biểu đồ sẽ hiển thị chúng dưới dạng chiều cao cột.*

### Bước 6: Đặt Độ rộng Khoảng trống cho Nhóm Series của Biểu đồ
`SeriesGroup` kiểm soát các thuộc tính bố cục cho một nhóm series, chẳng hạn như độ rộng khoảng trống.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Điều chỉnh độ rộng khoảng trống giúp cải thiện khả năng đọc, đặc biệt khi có nhiều danh mục.*

## Các trường hợp sử dụng phổ biến
- **Báo cáo tài chính** – so sánh doanh thu quý theo các đơn vị kinh doanh.  
- **Bảng điều khiển dự án** – hiển thị tỷ lệ hoàn thành nhiệm vụ theo từng nhóm.  
- **Phân tích marketing** – trực quan hoá hiệu suất chiến dịch cạnh nhau.  
Những kịch bản này hưởng lợi từ **ví dụ biểu đồ cột chồng** vì chúng làm nổi bật đóng góp của từng danh mục vào tổng thể.

## Mẹo hiệu năng
- **Tái sử dụng đối tượng `Presentation`** khi tạo nhiều biểu đồ để giảm tải bộ nhớ.  
- **Giới hạn số điểm dữ liệu** chỉ ở mức cần thiết cho câu chuyện hình ảnh; Aspose.Slides có thể xử lý 10.000 điểm, nhưng tốc độ render giảm đáng kể sau ~5.000 điểm.  
- **Giải phóng đối tượng** (`presentation.dispose()`) sau khi lưu để giải phóng tài nguyên và tránh rò rỉ bộ nhớ.  

## Câu hỏi thường gặp
**H: Tôi có thể thêm các loại biểu đồ khác ngoài cột chồng không?**  
Đ: Có, Aspose.Slides hỗ trợ line, pie, area, radar, bubble và hơn 50 loại biểu đồ khác, tất cả đều có thể tạo qua cùng một phương thức `addChart`.

**H: Tôi có cần giấy phép riêng cho đầu ra .NET không?**  
Đ: Không, cùng một giấy phép Java hoạt động cho mọi định dạng đầu ra, bao gồm cả tệp PPTX .NET.

**H: Làm sao thay đổi bảng màu của biểu đồ?**  
Đ: Dùng `series.getFormat().getFill().setFillType(FillType.Solid)` rồi thiết lập đối tượng `Color` mong muốn cho mỗi series.

**H: Có thể thêm nhãn dữ liệu (data labels) bằng lập trình không?**  
Đ: Chắc chắn. Gọi `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` để hiển thị giá trị số trên mỗi cột.

**H: Nếu cần cập nhật một bài thuyết trình đã tồn tại thì sao?**  
Đ: Tải tệp bằng `new Presentation("existing.pptx")`, chỉnh sửa biểu đồ bằng các API tương tự, và lưu lại.

## Kết luận
Bạn đã có một hướng dẫn toàn diện, từ đầu tới cuối, về cách **thêm series vào biểu đồ**, tạo **biểu đồ cột chồng**, và tinh chỉnh giao diện của chúng trong các bài thuyết trình .NET bằng Aspose.Slides cho Java. Hãy thử nghiệm với các loại biểu đồ, màu sắc và nguồn dữ liệu khác nhau để xây dựng các báo cáo hình ảnh ấn tượng, gây ấn tượng với các bên liên quan và thúc đẩy quyết định dựa trên dữ liệu.

---

**Cập nhật lần cuối:** 2026-06-08  
**Đã kiểm tra với:** Aspose.Slides cho Java 25.4 (JDK 16)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Cách Tạo Biểu đồ Cột Chồng Dựa trên Phần Trăm trong .NET bằng Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Tạo và Điều chỉnh Series Biểu đồ trong Aspose.Slides .NET để Trực quan hoá Dữ liệu Hiệu quả](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Xóa Các Điểm Dữ liệu Cụ thể trong Series Biểu đồ với Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}