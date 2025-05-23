---
"description": "Tạo biểu đồ đa danh mục trong Java Slides bằng Aspose.Slides for Java. Hướng dẫn từng bước với mã nguồn để trực quan hóa dữ liệu ấn tượng trong các bài thuyết trình."
"linktitle": "Biểu đồ đa danh mục trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ đa danh mục trong Java Slides"
"url": "/vi/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ đa danh mục trong Java Slides


## Giới thiệu về Biểu đồ đa danh mục trong Java Slides với Aspose.Slides

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách tạo biểu đồ nhiều danh mục trong Java slides bằng cách sử dụng Aspose.Slides for Java API. Hướng dẫn này sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn để giúp bạn tạo biểu đồ cột cụm với nhiều danh mục và chuỗi.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong môi trường phát triển Java của mình.

## Bước 1: Thiết lập môi trường
Đầu tiên, hãy nhập các lớp cần thiết và tạo một đối tượng Presentation mới để làm việc với các slide.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm Slide và Biểu đồ
Tiếp theo, tạo một slide và thêm biểu đồ cột nhóm vào đó.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Bước 3: Xóa dữ liệu hiện có
Xóa mọi dữ liệu hiện có khỏi biểu đồ.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Bước 4: Thiết lập danh mục dữ liệu
Bây giờ, hãy thiết lập các danh mục dữ liệu cho biểu đồ. Chúng ta sẽ tạo nhiều danh mục và nhóm chúng lại.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Thêm danh mục và nhóm chúng lại
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Bước 5: Thêm Chuỗi
Bây giờ, chúng ta hãy thêm một chuỗi vào biểu đồ cùng với các điểm dữ liệu.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Bước 6: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày có biểu đồ.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã tạo thành công biểu đồ đa danh mục trong slide Java bằng Aspose.Slides. Bạn có thể tùy chỉnh biểu đồ này thêm nữa để phù hợp với yêu cầu cụ thể của mình.

## Mã nguồn đầy đủ cho biểu đồ đa danh mục trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//            Thêm Series
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Lưu bài thuyết trình có biểu đồ
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo biểu đồ nhiều danh mục trong Java slides bằng cách sử dụng Aspose.Slides for Java API. Chúng ta đã thực hiện hướng dẫn từng bước với mã nguồn để tạo biểu đồ cột cụm với nhiều danh mục và chuỗi.

## Câu hỏi thường gặp

### Làm thế nào để tùy chỉnh giao diện biểu đồ?

Bạn có thể tùy chỉnh giao diện biểu đồ bằng cách sửa đổi các thuộc tính như màu sắc, phông chữ và kiểu. Tham khảo tài liệu Aspose.Slides để biết các tùy chọn tùy chỉnh chi tiết.

### Tôi có thể thêm nhiều chuỗi vào biểu đồ không?

Có, bạn có thể thêm chuỗi bổ sung vào biểu đồ bằng cách làm theo quy trình tương tự như được hiển thị ở Bước 5.

### Làm thế nào để thay đổi loại biểu đồ?

Để thay đổi loại biểu đồ, hãy thay thế `ChartType.ClusteredColumn` với loại biểu đồ mong muốn khi thêm biểu đồ ở Bước 2.

### Làm thế nào để thêm tiêu đề vào biểu đồ?

Bạn có thể thêm tiêu đề vào biểu đồ bằng cách sử dụng `ch.getChartTitle().getTextFrame().setText("Chart Title");` phương pháp.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}