---
date: '2026-01-17'
description: Tìm hiểu cách thêm chuỗi vào biểu đồ và tùy chỉnh biểu đồ cột chồng trong
  các bản trình bày .NET bằng cách sử dụng Aspose.Slides cho Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Thêm chuỗi vào biểu đồ với Aspose.Slides cho Java trong .NET
url: /vi/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thành thạo tùy chỉnh biểu đồ trong các bản trình bày .NET bằng Aspose.Slides cho Java

## Giới thiệu
Trong lĩnh vực các bản trình bày dựa trên dữ liệu, biểu đồ là công cụ không thể thiếu giúp biến các con số thô thành những câu chuyện hình ảnh hấp dẫn. Khi bạn cần **add series to chart** một cách lập trình, đặc biệt là trong các tệp trình bày .NET, công việc có thể cảm thấy quá tải. May mắn là **Aspose.Slides for Java** cung cấp một API mạnh mẽ, không phụ thuộc ngôn ngữ, giúp việc tạo và tùy chỉnh biểu đồ trở nên đơn giản—ngay cả khi định dạng mục tiêu là một tệp .NET PPTX.

Trong hướng dẫn này, bạn sẽ khám phá cách **add series to chart**, cách **add chart** loại stacked column, và cách tinh chỉnh các khía cạnh hình ảnh như gap width. Khi kết thúc, bạn sẽ có thể tạo các slide động, giàu dữ liệu, trông chuyên nghiệp và tinh tế.

**Bạn sẽ học được**
- Cách tạo một bản trình bày trống bằng Aspose.Slides  
- Cách **add stacked column chart** vào một slide  
- Cách **add series to chart** và định nghĩa các danh mục  
- Cách điền dữ liệu vào các điểm và điều chỉnh các thiết lập hình ảnh  

Hãy chuẩn bị môi trường phát triển của bạn.

## Trả lời nhanh
- **Lớp chính để bắt đầu một bản trình bày là gì?** `Presentation`  
- **Phương thức nào thêm biểu đồ vào slide?** `slide.getShapes().addChart(...)`  
- **Làm thế nào để thêm một series mới?** `chart.getChartData().getSeries().add(...)`  
- **Có thể thay đổi gap width giữa các thanh không?** Có, sử dụng `setGapWidth()` trên nhóm series  
- **Có cần giấy phép cho môi trường production không?** Có, cần một giấy phép Aspose.Slides for Java hợp lệ  

## “add series to chart” là gì?
Thêm một series vào biểu đồ có nghĩa là chèn một tập hợp dữ liệu mới mà biểu đồ sẽ hiển thị dưới dạng một yếu tố hình ảnh riêng biệt (ví dụ: một thanh, đường, hoặc phần). Mỗi series có thể có các giá trị, màu sắc và định dạng riêng, cho phép bạn so sánh nhiều bộ dữ liệu cạnh nhau.

## Tại sao nên dùng Aspose.Slides for Java để chỉnh sửa bản trình bày .NET?
- **Cross‑platform**: Viết mã Java một lần và tạo các tệp PPTX được sử dụng bởi các ứng dụng .NET.  
- **Không cần COM hay phụ thuộc Office**: Hoạt động trên máy chủ, pipeline CI và container.  
- **API biểu đồ phong phú**: Hỗ trợ hơn 50 loại biểu đồ, bao gồm stacked column charts.  

## Yêu cầu trước
1. Thư viện **Aspose.Slides for Java** (phiên bản 25.4 trở lên).  
2. Công cụ xây dựng Maven hoặc Gradle, hoặc tải JAR thủ công.  
3. Kiến thức cơ bản về Java và cấu trúc PPTX.  

## Cài đặt Aspose.Slides for Java
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
Thêm dòng sau vào file `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Hoặc tải JAR mới nhất từ trang phát hành chính thức: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Mua giấy phép**  
Bắt đầu với bản dùng thử miễn phí bằng cách tải giấy phép tạm thời từ [here](https://purchase.aspose.com/temporary-license/). Đối với môi trường production, mua giấy phép đầy đủ để mở khóa tất cả tính năng.

## Hướng dẫn triển khai từng bước
Dưới mỗi bước bạn sẽ thấy một đoạn mã ngắn gọn (giữ nguyên như trong hướng dẫn gốc) kèm theo giải thích về chức năng của nó.

### Bước 1: Tạo một bản trình bày trống
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

### Bước 2: Thêm một Stacked Column Chart vào Slide
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Phương thức `addChart` tạo một **add stacked column chart** và đặt nó ở góc trên‑trái của slide.*

### Bước 3: Thêm Series vào Biểu đồ (Mục tiêu chính)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Ở đây chúng ta **add series to chart** – mỗi lời gọi tạo một series dữ liệu mới sẽ xuất hiện dưới dạng một nhóm cột riêng biệt.*

### Bước 4: Thêm Danh mục vào Biểu đồ
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Các danh mục đóng vai trò là nhãn trục X, cung cấp ý nghĩa cho mỗi cột.*

### Bước 5: Điền Dữ liệu cho Series
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
*Các điểm dữ liệu cung cấp giá trị số cho mỗi series, và biểu đồ sẽ hiển thị chúng dưới dạng chiều cao của các thanh.*

### Bước 6: Đặt Gap Width cho Nhóm Series của Biểu đồ
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Điều chỉnh gap width giúp cải thiện khả năng đọc, đặc biệt khi có nhiều danh mục.*

## Các trường hợp sử dụng phổ biến
- **Báo cáo tài chính** – so sánh doanh thu quý theo các đơn vị kinh doanh.  
- **Bảng điều khiển dự án** – hiển thị tỷ lệ hoàn thành nhiệm vụ theo từng nhóm.  
- **Phân tích marketing** – trực quan hoá hiệu suất chiến dịch cạnh nhau.  

## Mẹo hiệu năng
- **Tái sử dụng đối tượng `Presentation`** khi tạo nhiều biểu đồ để giảm tải bộ nhớ.  
- **Giới hạn số điểm dữ liệu** chỉ ở mức cần thiết cho câu chuyện hình ảnh.  
- **Giải phóng đối tượng** (`presentation.dispose()`) sau khi lưu để giải phóng tài nguyên.

## Câu hỏi thường gặp
**Q: Tôi có thể thêm các loại biểu đồ khác ngoài stacked column không?**  
A: Có, Aspose.Slides hỗ trợ line, pie, area và nhiều loại biểu đồ khác.

**Q: Tôi có cần giấy phép riêng cho đầu ra .NET không?**  
A: Không, cùng một giấy phép Java hoạt động cho tất cả các định dạng đầu ra, bao gồm cả tệp PPTX .NET.

**Q: Làm sao thay đổi bảng màu của biểu đồ?**  
A: Sử dụng `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` và đặt `Color` mong muốn.

**Q: Có thể thêm nhãn dữ liệu bằng lập trình không?**  
A: Chắc chắn. Gọi `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` để hiển thị giá trị.

**Q: Nếu tôi cần cập nhật một bản trình bày đã tồn tại thì sao?**  
A: Tải tệp bằng `new Presentation("existing.pptx")`, chỉnh sửa biểu đồ và lưu lại.

## Kết luận
Bạn đã có một hướng dẫn toàn diện, từ đầu đến cuối, về cách **add series to chart**, tạo một **stacked column chart**, và tinh chỉnh giao diện của nó trong các bản trình bày .NET bằng Aspose.Slides for Java. Hãy thử nghiệm với các loại biểu đồ, màu sắc và nguồn dữ liệu khác nhau để xây dựng các báo cáo hình ảnh hấp dẫn, gây ấn tượng với các bên liên quan.

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
