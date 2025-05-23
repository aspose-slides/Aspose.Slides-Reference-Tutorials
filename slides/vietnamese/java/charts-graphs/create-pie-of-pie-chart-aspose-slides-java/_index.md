---
"date": "2025-04-17"
"description": "Tìm hiểu cách tạo và tùy chỉnh biểu đồ Pie of Pie bằng Aspose.Slides for Java. Hướng dẫn này bao gồm thiết lập, triển khai và ứng dụng thực tế."
"title": "Tạo biểu đồ hình tròn trong Java với Aspose.Slides&#58; Hướng dẫn toàn diện"
"url": "/vi/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ hình tròn trong Java với Aspose.Slides: Hướng dẫn toàn diện

## Biểu đồ & Đồ thị

### Giới thiệu

Trong trực quan hóa dữ liệu, biểu đồ hình tròn là một cách trực quan để biểu diễn tỷ lệ trong một tập dữ liệu. Tuy nhiên, khi xử lý các tập dữ liệu phức tạp, trong đó một số phân đoạn nhỏ hơn đáng kể so với các phân đoạn khác, biểu đồ hình tròn truyền thống có thể trở nên lộn xộn và khó diễn giải. Biểu đồ hình tròn của hình tròn giải quyết vấn đề này bằng cách chia các lát cắt nhỏ thành một biểu đồ thứ cấp, tăng cường khả năng đọc.

Trong hướng dẫn này, bạn sẽ học cách tạo và thao tác Biểu đồ hình tròn bằng Aspose.Slides for Java. Bạn sẽ học cách thiết lập môi trường, tạo biểu đồ, tùy chỉnh các thuộc tính như nhãn dữ liệu và vị trí chia tách, và lưu bản trình bày của bạn ở định dạng PPTX. Đến cuối, bạn sẽ thành thạo các tính năng này với các ứng dụng thực tế và mẹo về hiệu suất.

**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho Java
- Tạo biểu đồ hình tròn
- Tùy chỉnh các thuộc tính biểu đồ như nhãn dữ liệu và cấu hình chia tách
- Lưu bài thuyết trình của bạn vào đĩa

Bạn đã sẵn sàng bắt đầu chưa? Trước tiên hãy cùng xem qua các điều kiện tiên quyết nhé!

## Điều kiện tiên quyết

Trước khi tạo Biểu đồ hình tròn, hãy đảm bảo bạn có:

### Thư viện, phiên bản và phụ thuộc cần thiết:
- **Aspose.Slides cho Java**: Thiết yếu để quản lý các bài thuyết trình PowerPoint theo chương trình.

### Yêu cầu thiết lập môi trường:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn. Chúng tôi khuyên bạn nên sử dụng JDK 16 trở lên.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA, Eclipse hoặc NetBeans.

### Điều kiện tiên quyết về kiến thức:
- Hiểu biết cơ bản về lập trình Java
- Quen thuộc với Maven hoặc Gradle để quản lý sự phụ thuộc

## Thiết lập Aspose.Slides cho Java

### Thông tin cài đặt:

**Chuyên gia:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Cấp độ:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải xuống trực tiếp**: Bạn có thể tải xuống phiên bản mới nhất từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

### Các bước xin cấp giấy phép:
- **Dùng thử miễn phí**:Bắt đầu bằng bản dùng thử 30 ngày để khám phá tất cả các tính năng.
- **Giấy phép tạm thời**Yêu cầu cấp giấy phép tạm thời để đánh giá mở rộng.
- **Mua**: Hãy cân nhắc mua giấy phép nếu Aspose.Slides đáp ứng được nhu cầu của bạn.

### Khởi tạo và thiết lập cơ bản

Sau khi bạn đã thiết lập thư viện trong dự án của mình, hãy khởi tạo nó bằng cách tạo một phiên bản của `Presentation` lớp học:

```java
Presentation presentation = new Presentation();
```

Điều này thiết lập bối cảnh để thêm nhiều biểu đồ khác nhau vào slide của bạn. Tiếp theo, chúng ta hãy chuyển sang triển khai Biểu đồ Pie of Pie của chúng ta.

## Hướng dẫn thực hiện

### Tạo biểu đồ 'Pie of Pie'

#### Tổng quan
Chúng ta sẽ bắt đầu bằng cách tạo một thể hiện của một `Presentation` và thêm biểu đồ Pie of Pie vào trang chiếu đầu tiên. Biểu đồ này sẽ trực quan hóa dữ liệu hiệu quả bằng cách tách các phân đoạn nhỏ hơn thành một hình tròn thứ cấp, tăng khả năng đọc.

#### Bước 1: Tạo một phiên bản của lớp Presentation
```java
// Tạo một bài thuyết trình mới
ePresentation presentation = new Presentation();
```
Mã này khởi tạo bài thuyết trình nơi chúng ta sẽ thêm biểu đồ.

#### Bước 2: Thêm biểu đồ 'Pie of Pie' vào trang chiếu đầu tiên
```java
// Thêm biểu đồ Pie vào trang chiếu đầu tiên tại vị trí (50, 50) với kích thước (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Ở đây chúng tôi chỉ định loại biểu đồ (`PieOfPie`) và vị trí cũng như kích thước của nó trên slide.

#### Bước 3: Đặt Nhãn Dữ liệu để Hiển thị Giá trị cho Chuỗi
```java
// Cấu hình nhãn dữ liệu để hiển thị giá trị
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Bước này đảm bảo rằng mỗi phân đoạn trong biểu đồ hình tròn của chúng ta hiển thị giá trị tương ứng, hỗ trợ giải thích dữ liệu nhanh chóng.

#### Bước 4: Cấu hình Kích thước hình tròn thứ hai và Chia theo Phần trăm
```java
// Đặt kích thước của hình tròn thứ cấp
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Chia bánh theo phần trăm
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Đặt vị trí chia tách
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Các cấu hình này cho phép bạn tùy chỉnh cách biểu đồ chia và hiển thị các phân đoạn nhỏ hơn, giúp người xem dễ hiểu hơn.

#### Bước 5: Lưu bài thuyết trình vào đĩa theo định dạng PPTX
```java
// Xác định thư mục đầu ra
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Lưu bản trình bày\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}