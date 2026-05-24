---
date: '2026-02-24'
description: Tìm hiểu cách tùy chỉnh biểu đồ phân tán bằng Aspose.Slides cho Java.
  Hướng dẫn này sẽ chỉ cho bạn cách tạo, tạo kiểu và lưu các biểu đồ phân tán động
  trong bản trình bày của mình.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Tùy chỉnh biểu đồ phân tán Aspose trong Java
url: /vi/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tùy chỉnh Scatter Chart Aspose trong Java

Trong hướng dẫn này, bạn sẽ học cách **customize scatter chart aspose** với thư viện mạnh mẽ Aspose.Slides for Java. Chúng tôi sẽ hướng dẫn cách thiết lập dự án, tạo biểu đồ scatter, điều chỉnh loại series và marker, và cuối cùng lưu bản trình bày. Khi hoàn thành, bạn sẽ có thể tạo các biểu đồ scatter chuyên nghiệp một cách lập trình và tùy chỉnh mọi chi tiết hình ảnh để phù hợp với thương hiệu hoặc nhu cầu báo cáo của bạn.

## Câu trả lời nhanh
- **Thư viện nào tôi cần?** Aspose.Slides for Java (v25.4+).  
- **Phiên bản Java nào được hỗ trợ?** JDK 8 hoặc cao hơn.  
- **Tôi có thể thay đổi hình dạng marker không?** Có – sử dụng `MarkerStyleType` để chọn sao, vòng tròn, v.v.  
- **Làm thế nào để lưu tệp?** Gọi `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.

## “customize scatter chart aspose” là gì?
Tùy chỉnh một biểu đồ scatter với Aspose có nghĩa là định nghĩa dữ liệu, giao diện và hành vi của biểu đồ một cách lập trình—từ tọa độ điểm tới ký hiệu marker—mà không cần mở PowerPoint thủ công. Cách tiếp cận này lý tưởng cho báo cáo tự động, các bài thuyết trình dựa trên dữ liệu, hoặc bất kỳ tình huống nào bạn cần các hình ảnh lặp lại, chất lượng cao.

## Tại sao nên tùy chỉnh biểu đồ scatter với Aspose.Slides?
- **Kiểm soát toàn diện** – sửa đổi loại series, kiểu marker, màu sắc và hơn thế nữa bằng mã Java.  
- **Tự động hoá** – tạo hàng chục biểu đồ ngay lập tức cho bảng điều khiển hoặc báo cáo hàng loạt.  
- **Đa nền tảng** – hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java, không cần cài đặt Office.  
- **Hiệu năng** – API nhẹ giúp xử lý tập dữ liệu lớn một cách hiệu quả.

## Yêu cầu trước
Để làm theo, hãy chắc chắn rằng bạn có:

- **Aspose.Slides for Java** (v25.4 hoặc sau).  
- **Java Development Kit (JDK)** 8 + đã cài đặt.  
- Maven hoặc Gradle để quản lý phụ thuộc (hoặc bạn có thể tải JAR thủ công).  
- Kiến thức cơ bản về Java và quen thuộc với công cụ xây dựng bạn chọn.

## Cài đặt Aspose.Slides cho Java
Tích hợp thư viện vào dự án của bạn bằng một trong các phương pháp dưới đây.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Hoặc tải bản phát hành mới nhất từ [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Nhận giấy phép
- **Dùng thử miễn phí** – đánh giá 30 ngày.  
- **Giấy phép tạm thời** – thời gian thử nghiệm kéo dài.  
- **Giấy phép đầy đủ** – sử dụng trong môi trường sản xuất với hỗ trợ cao cấp.

## Hướng dẫn từng bước để tùy chỉnh Scatter Chart Aspose

### 1️⃣ Chuẩn bị thư mục cho các tệp trình chiếu của bạn
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Tại sao điều này quan trọng:* Đảm bảo thư mục đầu ra tồn tại ngăn ngừa `FileNotFoundException` khi bạn lưu PPTX sau này.

### 2️⃣ Tạo một bản trình chiếu mới và lấy slide đầu tiên
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Một `Presentation` mới cung cấp một canvas sạch sẽ; slide đầu tiên là nơi chúng ta sẽ đặt biểu đồ.

### 3️⃣ Thêm biểu đồ scatter với đường mượt
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` tạo một biểu đồ scatter đường mượt, lý tưởng cho việc trực quan hoá xu hướng.

### 4️⃣ Xóa mọi series mặc định và thêm series của bạn
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Việc loại bỏ series mặc định cho phép bạn kiểm soát hoàn toàn dữ liệu hiển thị.

### 5️⃣ Điền dữ liệu cho series đầu tiên bằng các điểm dữ liệu
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` nhận một ô giá trị X và một ô giá trị Y, xây dựng biểu đồ scatter điểm theo điểm.

### 6️⃣ Tùy chỉnh loại series và giao diện marker
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Ở đây chúng tôi **customize the scatter chart aspose** bằng cách chuyển sang đường thẳng, phóng to marker và chọn các ký hiệu riêng biệt (sao so với vòng tròn) để tăng độ rõ ràng trực quan.

### 7️⃣ Lưu bản trình chiếu
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Lưu dưới dạng `Pptx` giữ lại mọi tùy chỉnh biểu đồ và làm cho tệp sẵn sàng chia sẻ hoặc chỉnh sửa thêm.

## Các trường hợp sử dụng phổ biến cho biểu đồ scatter đã tùy chỉnh
- **Bảng điều khiển tài chính** – vẽ giá cổ phiếu so với khối lượng.  
- **Nghiên cứu khoa học** – hiển thị các phép đo thực nghiệm với marker lỗi.  
- **Quản lý dự án** – so sánh nỗ lực dự kiến và thực tế qua các nhiệm vụ.  

## Mẹo về hiệu năng
- Giải phóng đối tượng `Presentation` (`pres.dispose()`) sau khi lưu để giải phóng tài nguyên gốc.  
- Đối với tập dữ liệu lớn, hãy điền workbook trước rồi sau đó gắn series để tránh làm mới UI liên tục.  
- Tái sử dụng một thể hiện `IChartDataWorkbook` duy nhất khi thêm nhiều series.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi màu của marker?
Sử dụng `series.getMarker().getFillFormat().setFillColor(Color)` trong đó `Color` là một thể hiện của `java.awt.Color` (ví dụ, `Color.RED`).

### Tôi có thể thêm hơn hai series vào biểu đồ scatter không?
Chắc chắn. Lặp lại lời gọi `chart.getChartData().getSeries().add(...)` cho mỗi series bổ sung và điền các điểm dữ liệu tương ứng.

### Có thể đặt chú giải tùy chỉnh cho mỗi series không?
Có. Sau khi tạo một series, gọi `series.getLegend().setText("Your Legend Text")` để ghi đè tên mặc định.

### Làm sao để xuất biểu đồ dưới dạng hình ảnh thay vì PPTX?
Gọi `chart.getImage().save("chart.png", ImageFormat.Png)` sau khi cấu hình biểu đồ. Điều này sẽ cho bạn một tệp PNG độc lập.

### Nếu tôi cần tạo hoạt ảnh cho các điểm scatter thì sao?
Aspose.Slides hỗ trợ hiệu ứng hoạt ảnh. Sử dụng `chart.getTimeline().getMainSequence().addEffect(...)` để thêm hoạt ảnh xuất hiện hoặc nhấn mạnh vào biểu đồ hoặc từng series.

---

**Cập nhật lần cuối:** 2026-02-24  
**Đã kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}