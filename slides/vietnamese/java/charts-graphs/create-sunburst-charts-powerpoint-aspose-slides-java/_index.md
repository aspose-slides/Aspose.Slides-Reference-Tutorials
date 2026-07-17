---
date: '2026-07-17'
description: Tìm hiểu cách thêm Sunburst Charts trong PowerPoint bằng Aspose Slides
  for Java. Step‑by‑step guide bao gồm setup, chart creation, customization và real‑world
  use cases.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Cách thêm Sunburst Charts trong PowerPoint bằng Aspose Slides for
  Java. Follow this tutorial để set up thư viện, create a chart, customize data points
  và apply nó vào các dự án thực tế.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Cách Thêm Sunburst Charts trong PowerPoint với Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Cách Thêm Sunburst Charts trong PowerPoint với Aspose (Java)
url: /vi/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Thêm Biểu Đồ Sunburst vào PowerPoint với Aspose (Java)

## Giới thiệu

Thêm một biểu đồ sunburst vào bản trình chiếu PowerPoint có thể ngay lập tức biến một bảng dữ liệu phẳng thành một hình ảnh phân cấp sinh động. Trong hướng dẫn này, bạn sẽ học **cách thêm biểu đồ sunburst** vào PowerPoint bằng Aspose.Slides cho Java, từ việc thiết lập môi trường đến tinh chỉnh màu sắc và nhãn. Dù bạn đang xây dựng bảng điều khiển bán hàng, phân tích công việc dự án, hay bộ slide giáo dục, các bước dưới đây sẽ cung cấp cho bạn một giải pháp sẵn sàng cho sản xuất.

**Bạn sẽ học được**
- Cách cấu hình Aspose.Slides trong dự án Maven hoặc Gradle  
- Cách tạo một bản trình chiếu mới và chèn biểu đồ sunburst  
- Cách tùy chỉnh các điểm dữ liệu, nhãn và màu nền  
- Các kịch bản thực tế mà biểu đồ sunburst tỏa sáng  

Hãy bắt đầu và xem việc biến dữ liệu phân cấp thô thành một hình ảnh PowerPoint chuyên nghiệp dễ dàng như thế nào.

## Câu trả lời nhanh
- **Thư viện chính?** Aspose.Slides cho Java  
- **Loại biểu đồ được hỗ trợ?** Sunburst (phân cấp dạng vòng)  
- **Phiên bản Java tối thiểu?** JDK 16  
- **Thời gian triển khai điển hình?** 10‑15 phút cho một biểu đồ cơ bản  
- **Cần giấy phép cho môi trường sản xuất?** Có, giấy phép Aspose hợp lệ  

## Biểu đồ Sunburst là gì?
Biểu đồ sunburst là một sơ đồ dạng vòng thể hiện dữ liệu phân cấp bằng cách lồng các vòng ra ngoài từ một điểm trung tâm. Nó hoàn hảo để hiển thị các mối quan hệ đa cấp như cấu trúc tổ chức, danh mục sản phẩm, hoặc cây thư mục hệ thống. Mỗi vòng đồng tâm đại diện cho một cấp độ của phân cấp, và kích thước của mỗi đoạn phản ánh giá trị định lượng của nó, cho phép người xem nhanh chóng nắm bắt cả cấu trúc và quy mô.

## Tại sao nên dùng Aspose.Slides cho Java?
Aspose.Slides hỗ trợ **hơn 50 loại biểu đồ** và có thể thao tác các bản trình chiếu với **tới 10.000 slide** mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại hiệu năng cao cho báo cáo quy mô doanh nghiệp. Nó hoạt động đa nền tảng, cung cấp API phong phú, và đi kèm các tùy chọn giấy phép mạnh mẽ loại bỏ giới hạn đánh giá, rất phù hợp cho môi trường sản xuất.

## Yêu cầu trước
- **Bộ công cụ phát triển Java (JDK)** 16 hoặc mới hơn  
- **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo Java nào tương thích  
- Kiến thức cơ bản về cú pháp Java và công cụ xây dựng Maven/Gradle  

## Cài đặt Aspose.Slides cho Java

### Maven Dependency
Thêm artifact Aspose.Slides Maven vào `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Dependency
Nếu bạn thích Gradle, thêm dòng sau vào `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Bạn cũng có thể tải JAR mới nhất trực tiếp từ trang phát hành chính thức: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
Để chạy không bị giới hạn đánh giá, hãy lấy giấy phép:
- **Dùng thử miễn phí** – giấy phép tạm thời để đánh giá nhanh.  
- **Giấy phép tạm thời** – yêu cầu từ [trang web Aspose](https://purchase.aspose.com/temporary-license).  
- **Mua đầy đủ** – mua gói đăng ký để sử dụng không giới hạn trong môi trường sản xuất.

### Basic Initialization
Lớp `Presentation` là điểm khởi đầu để tạo hoặc mở tệp PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Hướng dẫn triển khai

### Cách thêm biểu đồ sunburst vào bản trình chiếu PowerPoint bằng Aspose.Slides cho Java?

Tải một `Presentation` mới, thêm một slide, chèn một `IChart` loại `ChartType.Sunburst`, và gọi `save`. Mẫu ba bước ngắn gọn này tạo ra một biểu đồ sunburst hoàn chỉnh, sẵn sàng cho việc tùy chỉnh tiếp theo.

#### Bước 1: Khởi tạo Presentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Bước 2: Thêm Biểu đồ Sunburst
Giao diện `IChart` định nghĩa một đối tượng biểu đồ có thể đặt trên bất kỳ slide nào. Ở đây chúng ta thêm một biểu đồ sunburst tại tọa độ (100, 100) với kích thước 450 × 400 point.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Bước 3: Lưu Presentation
Luôn ghi lại các thay đổi bằng cách gọi `save`. Bạn có thể chọn PPTX, PDF, hoặc bất kỳ định dạng đầu ra nào trong hơn 50 loại được hỗ trợ.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Sửa đổi các Điểm Dữ liệu trong Biểu đồ

#### Tổng quan
Bạn có thể tùy chỉnh từng lát của sunburst—nhãn, màu sắc và hiển thị—thông qua bộ sưu tập điểm dữ liệu của biểu đồ.

#### Bước 1: Truy cập Bộ sưu tập Điểm Dữ liệu
Series đầu tiên của biểu đồ chứa một bộ sưu tập các đối tượng `IChartDataPoint` đại diện cho mỗi lát.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Bước 2: Hiển thị Giá trị cho Điểm Dữ liệu Cụ thể
Đặt `IsValueShown` thành `true` trên điểm dữ liệu mong muốn để hiển thị giá trị số trực tiếp trên lát.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Bước 3: Sửa Định dạng Nhãn
Điều chỉnh khả năng hiển thị nhãn, màu chữ và nền để cải thiện khả năng đọc.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Bước 4: Đặt Màu Nền cho Điểm Dữ liệu
Tùy chỉnh màu nền của từng lát để phù hợp với bảng màu thương hiệu hoặc để làm nổi bật các phân đoạn quan trọng.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Bước 5: Lưu Presentation Đã Sửa đổi
Ghi lại biểu đồ đã tùy chỉnh bằng cách lưu lại bản trình chiếu một lần nữa.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Ứng dụng thực tiễn

1. **Phân tích Kinh doanh** – Trực quan hoá doanh thu theo khu vực → dòng sản phẩm → SKU trong một góc nhìn vòng duy nhất.  
2. **Quản lý Dự án** – Hiển thị cấu trúc phân tách công việc, từ giai đoạn đến nhiệm vụ và các công việc con.  
3. **Giáo dục** – Lập bản đồ phân cấp chương trình học, chẳng hạn khoa → môn học → mô-đun.  

## Các lưu ý về hiệu năng

- **Tiết kiệm bộ nhớ:** Aspose.Slides truyền dữ liệu dạng stream, vì vậy ngay cả một bộ deck 500 trang có nhiều biểu đồ cũng chỉ chiếm dưới 200 MB RAM.  
- **Thu gom rác:** Giải phóng các đối tượng slide (`slide.dispose()`) khi không còn cần thiết để tránh rò rỉ bộ nhớ.  

## Câu hỏi thường gặp

**H: Biểu đồ sunburst là gì?**  
Đ: Biểu đồ sunburst hiển thị dữ liệu phân cấp trong các vòng đồng tâm, mỗi vòng đại diện cho một cấp độ của phân cấp.

**H: Làm sao cài đặt Aspose.Slides cho Java bằng Maven?**  
Đ: Thêm phụ thuộc Maven được hiển thị trong mục “Maven Dependency” vào `pom.xml` và chạy `mvn clean install`.

**H: Tôi có thể tùy chỉnh các loại biểu đồ khác với Aspose.Slides không?**  
Đ: Có, thư viện hỗ trợ hơn 50 loại biểu đồ, bao gồm column, line, pie và radar.

**H: Bản trình chiếu của tôi không lưu được—cần kiểm tra gì?**  
Đ: Kiểm tra đường dẫn tệp có đúng không, thư mục tồn tại và bạn có quyền ghi. Đồng thời, đảm bảo phương thức `Presentation.save()` đã được gọi.

**H: Tôi có thể tìm thêm trợ giúp hoặc ví dụ ở đâu?**  
Đ: Truy cập [diễn đàn Aspose](https://forum.aspose.com/c/slides/11) hoặc tham khảo [tài liệu tham khảo Aspose.Slides chính thức](https://reference.aspose.com/slides/java/).

## Tài nguyên
- **Tài liệu:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Tham khảo (lowercase):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Diễn đàn cộng đồng:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Tải về:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Cập nhật lần cuối:** 2026-07-17  
**Đã kiểm tra với:** Aspose.Slides cho Java 24.12  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}