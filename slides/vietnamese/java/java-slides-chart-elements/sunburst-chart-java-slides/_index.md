---
"description": "Tạo biểu đồ Sunburst tuyệt đẹp trong Java Slides với Aspose.Slides. Tìm hiểu cách tạo biểu đồ và xử lý dữ liệu từng bước."
"linktitle": "Biểu đồ Sunburst trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ Sunburst trong Java Slides"
"url": "/vi/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ Sunburst trong Java Slides


## Giới thiệu về Biểu đồ Sunburst trong Java Slides với Aspose.Slides

Trong hướng dẫn này, bạn sẽ học cách tạo biểu đồ Sunburst trong bản trình bày PowerPoint bằng cách sử dụng Aspose.Slides for Java API. Biểu đồ Sunburst là biểu đồ hình tròn được sử dụng để biểu diễn dữ liệu phân cấp. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và cấu hình thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Nhập thư viện cần thiết

Đầu tiên, hãy nhập các thư viện cần thiết để làm việc với Aspose.Slides và tạo biểu đồ Sunburst trong ứng dụng Java của bạn.

```java
import com.aspose.slides.*;
```

## Bước 2: Khởi tạo bài thuyết trình

Khởi tạo bản trình bày PowerPoint và chỉ định thư mục nơi tệp bản trình bày của bạn sẽ được lưu.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Bước 3: Tạo biểu đồ Sunburst

Tạo biểu đồ Sunburst trên slide. Chúng tôi chỉ định vị trí (X, Y) và kích thước (chiều rộng, chiều cao) của biểu đồ.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Bước 4: Chuẩn bị dữ liệu biểu đồ

Xóa mọi danh mục và dữ liệu chuỗi hiện có khỏi biểu đồ và tạo sổ làm việc dữ liệu cho biểu đồ.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Bước 5: Xác định phân cấp biểu đồ

Xác định cấu trúc phân cấp của biểu đồ Sunburst. Bạn có thể thêm các nhánh, thân và lá làm danh mục.

```java
// Chi nhánh 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Chi nhánh 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Bước 6: Thêm dữ liệu vào biểu đồ

Thêm điểm dữ liệu vào chuỗi biểu đồ Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Bước 7: Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình bằng biểu đồ Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho biểu đồ Sunburst trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//nhánh 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//nhánh 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo biểu đồ Sunburst trong bản trình bày PowerPoint bằng cách sử dụng Aspose.Slides for Java API. Bạn đã thấy cách khởi tạo bản trình bày, tạo biểu đồ, xác định phân cấp biểu đồ, thêm điểm dữ liệu và lưu bản trình bày. Bây giờ bạn có thể sử dụng kiến thức này để tạo biểu đồ Sunburst tương tác và nhiều thông tin trong các ứng dụng Java của mình.

## Câu hỏi thường gặp

### Làm thế nào để tùy chỉnh giao diện của biểu đồ Sunburst?

Bạn có thể tùy chỉnh giao diện của biểu đồ Sunburst bằng cách sửa đổi các thuộc tính như màu sắc, nhãn và kiểu. Tham khảo tài liệu Aspose.Slides để biết các tùy chọn tùy chỉnh chi tiết.

### Tôi có thể thêm nhiều điểm dữ liệu vào biểu đồ không?

Có, bạn có thể thêm nhiều điểm dữ liệu hơn vào biểu đồ bằng cách sử dụng `series.getDataPoints().addDataPointForSunburstSeries()` phương pháp cho mỗi điểm dữ liệu bạn muốn đưa vào.

### Làm thế nào tôi có thể thêm chú giải công cụ vào biểu đồ Sunburst?

Để thêm chú giải công cụ vào biểu đồ Sunburst, bạn có thể đặt định dạng nhãn dữ liệu để hiển thị thông tin bổ sung, chẳng hạn như giá trị hoặc mô tả, khi di chuột qua các phân đoạn biểu đồ.

### Có thể tạo biểu đồ Sunburst tương tác bằng siêu liên kết không?

Có, bạn có thể tạo biểu đồ Sunburst tương tác với siêu liên kết bằng cách thêm siêu liên kết vào các thành phần hoặc phân đoạn biểu đồ cụ thể. Tham khảo tài liệu Aspose.Slides để biết chi tiết về cách thêm siêu liên kết.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}