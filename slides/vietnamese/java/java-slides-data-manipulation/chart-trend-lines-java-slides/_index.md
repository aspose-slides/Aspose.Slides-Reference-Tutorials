---
"description": "Tìm hiểu cách thêm nhiều đường xu hướng khác nhau vào Java Slides bằng Aspose.Slides for Java. Hướng dẫn từng bước với các ví dụ mã để trực quan hóa dữ liệu hiệu quả."
"linktitle": "Biểu đồ đường xu hướng trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ đường xu hướng trong Java Slides"
"url": "/vi/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ đường xu hướng trong Java Slides


## Giới thiệu về Biểu đồ Đường xu hướng trong Java Slides: Hướng dẫn từng bước

Trong hướng dẫn toàn diện này, chúng ta sẽ khám phá cách tạo đường xu hướng biểu đồ trong Java Slides bằng Aspose.Slides for Java. Đường xu hướng biểu đồ có thể là một bổ sung có giá trị cho bài thuyết trình của bạn, giúp trực quan hóa và phân tích xu hướng dữ liệu một cách hiệu quả. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình với các giải thích rõ ràng và ví dụ về mã.

## Điều kiện tiên quyết

Trước khi bắt đầu tạo đường xu hướng biểu đồ, hãy đảm bảo bạn đã đáp ứng các điều kiện tiên quyết sau:

- Môi trường phát triển Java
- Aspose.Slides cho Thư viện Java
- Trình biên tập mã theo lựa chọn của bạn

## Bước 1: Bắt đầu

Chúng ta hãy bắt đầu bằng cách thiết lập môi trường cần thiết và tạo một bản trình bày mới:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu thư mục đó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Tạo bài thuyết trình trống
Presentation pres = new Presentation();
```

Chúng tôi đã khởi tạo bản trình bày và bây giờ chúng tôi đã sẵn sàng để thêm biểu đồ cột cụm:

```java
// Tạo biểu đồ cột cụm
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Bước 2: Thêm Đường xu hướng hàm mũ

Hãy bắt đầu bằng cách thêm đường xu hướng hàm mũ vào biểu đồ của chúng ta:

```java
// Thêm đường xu hướng hàm mũ cho chuỗi biểu đồ 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Bước 3: Thêm Đường xu hướng tuyến tính

Tiếp theo, chúng ta sẽ thêm đường xu hướng tuyến tính vào chuỗi biểu đồ của mình:

```java
// Thêm đường xu hướng tuyến tính cho chuỗi biểu đồ 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Bước 4: Thêm Đường xu hướng Logarit

Bây giờ, chúng ta hãy thêm đường xu hướng logarit vào một loạt biểu đồ khác:

```java
// Thêm đường xu hướng logarit cho biểu đồ chuỗi 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Bước 5: Thêm Đường xu hướng trung bình động

Chúng ta cũng có thể thêm đường xu hướng trung bình động:

```java
// Thêm đường xu hướng trung bình động cho biểu đồ chuỗi 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Bước 6: Thêm Đường xu hướng đa thức

Thêm đường xu hướng đa thức:

```java
// Thêm đường xu hướng đa thức cho chuỗi biểu đồ 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Bước 7: Thêm Đường xu hướng công suất

Cuối cùng, chúng ta hãy thêm đường xu hướng sức mạnh:

```java
// Thêm đường xu hướng điện cho biểu đồ chuỗi 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Bước 8: Lưu bài thuyết trình

Bây giờ chúng ta đã thêm nhiều đường xu hướng khác nhau vào biểu đồ, hãy lưu bản trình bày:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Xin chúc mừng! Bạn đã tạo thành công bản trình bày với nhiều loại đường xu hướng khác nhau trong Java Slides bằng Aspose.Slides for Java.

## Mã nguồn đầy đủ cho biểu đồ đường xu hướng trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu thư mục đó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Tạo bài thuyết trình trống
Presentation pres = new Presentation();
// Tạo biểu đồ cột cụm
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Thêm đường xu hướng ponential cho chuỗi biểu đồ 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Thêm đường xu hướng tuyến tính cho chuỗi biểu đồ 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Thêm đường xu hướng Logarit cho chuỗi biểu đồ 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Thêm đường xu hướng MovingAverage cho chuỗi biểu đồ 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Thêm đường xu hướng đa thức cho chuỗi biểu đồ 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Thêm đường xu hướng Power cho biểu đồ chuỗi 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Lưu bài thuyết trình
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thêm các loại đường xu hướng khác nhau vào biểu đồ trong Java Slides bằng thư viện Aspose.Slides for Java. Cho dù bạn đang làm việc về phân tích dữ liệu hay tạo các bài thuyết trình thông tin, khả năng trực quan hóa xu hướng có thể là một công cụ mạnh mẽ.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi màu của đường xu hướng trong Aspose.Slides cho Java?

Để thay đổi màu của đường xu hướng, bạn có thể sử dụng `getSolidFillColor().setColor(Color)` phương pháp như thể hiện trong ví dụ về cách thêm đường xu hướng tuyến tính.

### Tôi có thể thêm nhiều đường xu hướng vào một chuỗi biểu đồ không?

Có, bạn có thể thêm nhiều đường xu hướng vào một loạt biểu đồ duy nhất. Chỉ cần gọi `getTrendLines().add()` phương pháp cho mỗi đường xu hướng bạn muốn thêm.

### Làm cách nào để xóa đường xu hướng khỏi biểu đồ trong Aspose.Slides cho Java?

Để xóa đường xu hướng khỏi biểu đồ, bạn có thể sử dụng `removeAt(int index)` phương pháp này chỉ rõ chỉ số của đường xu hướng mà bạn muốn xóa.

### Có thể tùy chỉnh cách hiển thị phương trình đường xu hướng không?

Có, bạn có thể tùy chỉnh màn hình hiển thị phương trình đường xu hướng bằng cách sử dụng `setDisplayEquation(boolean)` phương pháp như đã trình bày trong ví dụ.

### Làm thế nào tôi có thể truy cập thêm nhiều tài nguyên và ví dụ về Aspose.Slides cho Java?

Bạn có thể truy cập các tài nguyên, tài liệu và ví dụ bổ sung cho Aspose.Slides cho Java trên [Trang web Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}