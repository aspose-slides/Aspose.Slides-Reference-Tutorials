---
date: '2026-07-27'
description: Cách tùy chỉnh biểu đồ bằng Aspose.Slides for Java. Học cách tạo biểu
  đồ PowerPoint, định dạng scatter series, và lưu presentations một cách hiệu quả.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Cách tùy chỉnh biểu đồ với Aspose.Slides for Java. Hướng dẫn này cho
  thấy cách tạo biểu đồ PowerPoint, định dạng scatter points, và xuất presentations.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Cách Tùy Chỉnh Biểu Đồ: Scatter Chart Aspose trong Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Cách Tùy Chỉnh Biểu Đồ: Scatter Chart Aspose trong Java'
url: /vi/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tùy chỉnh biểu đồ Scatter Aspose trong Java

Trong hướng dẫn này, bạn sẽ khám phá **cách tùy chỉnh biểu đồ** — cụ thể là biểu đồ scatter — bằng cách sử dụng thư viện mạnh mẽ Aspose.Slides for Java. Chúng tôi sẽ hướng dẫn qua việc thiết lập dự án, tạo biểu đồ scatter, điều chỉnh loại series và marker, và cuối cùng lưu bản trình chiếu. Khi hoàn thành, bạn sẽ có thể tạo các biểu đồ scatter chuyên nghiệp một cách lập trình và tùy chỉnh mọi chi tiết hình ảnh để phù hợp với thương hiệu hoặc nhu cầu báo cáo của bạn.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Slides for Java (v25.4+).  
- **Phiên bản Java nào được hỗ trợ?** JDK 8 hoặc cao hơn.  
- **Tôi có thể thay đổi hình dạng marker không?** Yes – use `MarkerStyleType` to pick stars, circles, etc.  
- **Làm thế nào để lưu tệp?** Call `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Cần giấy phép không?** A free trial works for development; a commercial license is needed for production.

## Cách tùy chỉnh biểu đồ trong Java với Aspose.Slides?
`Presentation` là lớp Aspose.Slides đại diện cho toàn bộ tệp PowerPoint trong bộ nhớ. Tải một `Presentation` mới, thêm một biểu đồ scatter vào slide đầu tiên, cấu hình series và kiểu marker, sau đó gọi `save`. Quy trình duy nhất này tạo ra một biểu đồ được định dạng đầy đủ chỉ trong vài dòng mã Java, sẵn sàng để chèn vào bất kỳ bản PowerPoint nào.

## “Tùy chỉnh biểu đồ scatter Aspose” là gì?
Việc tùy chỉnh một biểu đồ scatter với Aspose có nghĩa là định nghĩa chương trình dữ liệu, giao diện và hành vi của biểu đồ — mọi thứ từ tọa độ điểm đến ký hiệu marker — mà không cần mở PowerPoint thủ công. Cách tiếp cận này lý tưởng cho báo cáo tự động, các bài thuyết trình dựa trên dữ liệu, hoặc bất kỳ tình huống nào bạn cần các hình ảnh trực quan lặp lại, chất lượng cao.

## Tại sao nên tùy chỉnh biểu đồ scatter với Aspose.Slides?
Aspose.Slides cung cấp cho các nhà phát triển quyền kiểm soát hoàn toàn qua lập trình đối với giao diện biểu đồ, cho phép tạo ra các hình ảnh trực quan chất lượng cao một cách tự động, tích hợp liền mạch vào quy trình báo cáo, và khả năng tùy chỉnh mọi yếu tố hình ảnh mà không cần mở PowerPoint thủ công, giúp tiết kiệm thời gian và đảm bảo tính nhất quán trong các bài thuyết trình.

- **Kiểm soát đầy đủ** – modify series types, marker styles, colors, and more via Java code.  
- **Tự động hóa** – generate dozens of charts on the fly for dashboards or batch reports.  
- **Đa nền tảng** – works on any OS that supports Java, no Office installation required.  
- **Hiệu năng** – lightweight API that processes **150+ chart types** and handles multi‑hundred‑page presentations without loading the whole file into memory.

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

Hoặc tải phiên bản mới nhất từ [Aspose Releases](https://releases.aspose.com/slides/java/).

#### License Acquisition
- **Free Trial** – đánh giá 30 ngày.  
- **Temporary License** – thời gian thử nghiệm kéo dài.  
- **Full License** – production use with premium support.

## Hướng dẫn từng bước để tùy chỉnh biểu đồ Scatter Aspose

### 1️⃣ Prepare a folder for your presentation files
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*​Tại sao điều này quan trọng:* Đảm bảo thư mục đầu ra tồn tại ngăn ngừa `FileNotFoundException` khi bạn lưu PPTX sau này.

### 2️⃣ Create a new presentation and grab the first slide
`Presentation` đại diện cho một tài liệu PowerPoint và cung cấp quyền truy cập vào các slide và shape. Lớp `Presentation` đại diện cho toàn bộ tệp PowerPoint trong bộ nhớ.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Add a scatter chart with smooth lines
`ChartType.ScatterWithSmoothLines` tạo một biểu đồ scatter trong đó các điểm được nối bằng các đường mượt.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Clear any default series and add your own
`IChartSeries` đại diện cho một series dữ liệu trong biểu đồ.  
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

### 5️⃣ Populate the first series with data points
`addDataPointForScatterSeries` thêm một điểm X‑Y duy nhất vào một series scatter.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Customize series type and marker appearance
`Marker` kiểm soát ký hiệu hình ảnh được sử dụng cho mỗi điểm dữ liệu trong một series biểu đồ.  
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

### 7️⃣ Save the presentation
`save` ghi bản trình chiếu vào một tệp với định dạng được chỉ định.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Các trường hợp sử dụng phổ biến cho biểu đồ Scatter được tùy chỉnh
- **Financial dashboards** – plot stock price vs. volume.  
- **Scientific research** – display experimental measurements with error markers.  
- **Project management** – compare planned vs. actual effort across tasks.  

## Mẹo hiệu năng
- Gọi `pres.dispose()` sau khi lưu để giải phóng bộ nhớ gốc.  
- Đối với bộ dữ liệu lớn, hãy điền workbook trước và sau đó liên kết series để tránh làm mới UI lặp lại.  
- Tái sử dụng một thể hiện `IChartDataWorkbook` duy nhất khi thêm nhiều series để giữ mức sử dụng bộ nhớ thấp.

## Câu hỏi thường gặp

**Q: Làm thế nào để thay đổi màu của marker?**  
A: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color` is a `java.awt.Color` instance such as `Color.RED`.

**Q: Tôi có thể thêm hơn hai series vào biểu đồ scatter không?**  
A: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional series and populate its points accordingly.

**Q: Có thể đặt chú giải tùy chỉnh cho mỗi series không?**  
A: Absolutely. After creating a series, invoke `series.getLegend().setText("Your Legend Text")` to override the default name.

**Q: Làm sao tôi có thể xuất biểu đồ dưới dạng hình ảnh thay vì PPTX?**  
A: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring the chart. This produces a standalone PNG file.

**Q: Nếu tôi cần tạo hoạt ảnh cho các điểm scatter thì sao?**  
A: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)` to add entrance or emphasis animations to the chart or individual series.

---

**Cập nhật lần cuối:** 2026-07-27  
**Kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Tạo và tùy chỉnh biểu đồ PowerPoint trong Java bằng Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Cách tạo biểu đồ Bubble trong PowerPoint bằng Aspose.Slides cho Java (Hướng dẫn)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Tạo và tùy chỉnh biểu đồ với đường xu hướng trong Aspose.Slides cho Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}