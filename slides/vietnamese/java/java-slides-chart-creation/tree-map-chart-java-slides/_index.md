---
"description": "Tạo biểu đồ bản đồ cây trong Java Slides bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn để trực quan hóa dữ liệu phân cấp."
"linktitle": "Biểu đồ bản đồ cây trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ bản đồ cây trong Java Slides"
"url": "/vi/java/chart-creation/tree-map-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ bản đồ cây trong Java Slides


## Giới thiệu về Tree Map Chart trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách tạo biểu đồ Tree Map trong bản trình bày PowerPoint bằng thư viện Aspose.Slides for Java. Biểu đồ Tree Map là một cách hiệu quả để trực quan hóa dữ liệu phân cấp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình.

## Bước 1: Nhập thư viện cần thiết

```java
import com.aspose.slides.*;
```

## Bước 2: Tải bài thuyết trình

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Bước 3: Tạo biểu đồ bản đồ cây

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // Tạo nhánh 1
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // Tạo nhánh 2
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // Thêm điểm dữ liệu
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // Lưu bản trình bày với biểu đồ Tree Map
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Mã nguồn đầy đủ cho biểu đồ bản đồ cây trong Java Slides
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
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
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo biểu đồ Tree Map trong bài thuyết trình PowerPoint bằng thư viện Aspose.Slides for Java. Biểu đồ Tree Map là công cụ hữu ích để trực quan hóa dữ liệu phân cấp, giúp bài thuyết trình của bạn nhiều thông tin và hấp dẫn hơn.

## Câu hỏi thường gặp

### Làm thế nào để thêm dữ liệu vào biểu đồ Tree Map?

Để thêm dữ liệu vào biểu đồ Tree Map, hãy sử dụng `series.getDataPoints().addDataPointForTreemapSeries()` phương pháp truyền các giá trị dữ liệu dưới dạng tham số.

### Làm thế nào để tùy chỉnh giao diện của biểu đồ Tree Map?

Bạn có thể tùy chỉnh giao diện của biểu đồ Tree Map bằng cách sửa đổi các thuộc tính khác nhau của `chart` Và `series` các đối tượng như màu sắc, nhãn và bố cục.

### Tôi có thể tạo nhiều biểu đồ Tree Map trong một bài thuyết trình không?

Có, bạn có thể tạo nhiều biểu đồ Tree Map trong một bài thuyết trình bằng cách làm theo các bước tương tự và chỉ định các vị trí trang chiếu khác nhau.

### Làm thế nào để lưu bài thuyết trình có biểu đồ Tree Map?

Sử dụng `pres.save()` phương pháp lưu bản trình bày với biểu đồ Tree Map theo định dạng mong muốn (ví dụ: PPTX).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}