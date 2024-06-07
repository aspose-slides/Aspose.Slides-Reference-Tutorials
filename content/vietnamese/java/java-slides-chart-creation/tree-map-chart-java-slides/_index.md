---
title: Biểu đồ bản đồ cây trong Java Slides
linktitle: Biểu đồ bản đồ cây trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tạo biểu đồ bản đồ cây trong các trang trình bày Java bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn để trực quan hóa dữ liệu phân cấp.
type: docs
weight: 13
url: /vi/java/chart-creation/tree-map-chart-java-slides/
---

## Giới thiệu về Biểu đồ bản đồ cây trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách tạo biểu đồ Bản đồ dạng cây trong bản trình bày PowerPoint bằng thư viện Aspose.Slides cho Java. Biểu đồ Bản đồ cây là một cách hiệu quả để trực quan hóa dữ liệu phân cấp.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập thư viện Aspose.Slides cho Java trong dự án Java của mình.

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

    // Lưu bài thuyết trình với biểu đồ Tree Map
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Mã nguồn hoàn chỉnh cho biểu đồ bản đồ cây trong các trang trình bày Java
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
	//chi nhánh 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//chi nhánh 2
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

Trong hướng dẫn này, bạn đã học cách tạo biểu đồ Bản đồ cây trong bản trình bày PowerPoint bằng thư viện Aspose.Slides cho Java. Biểu đồ Bản đồ cây là một công cụ có giá trị để trực quan hóa dữ liệu phân cấp, làm cho bản trình bày của bạn có nhiều thông tin và hấp dẫn hơn.

## Câu hỏi thường gặp

### Làm cách nào để thêm dữ liệu vào biểu đồ Bản đồ cây?

 Để thêm dữ liệu vào biểu đồ Bản đồ cây, hãy sử dụng`series.getDataPoints().addDataPointForTreemapSeries()` phương thức, truyền các giá trị dữ liệu dưới dạng tham số.

### Làm cách nào tôi có thể tùy chỉnh giao diện của biểu đồ Bản đồ cây?

 Bạn có thể tùy chỉnh giao diện của biểu đồ Bản đồ cây bằng cách sửa đổi các thuộc tính khác nhau của`chart` Và`series` các đối tượng, chẳng hạn như màu sắc, nhãn và bố cục.

### Tôi có thể tạo nhiều biểu đồ Bản đồ cây trong một bản trình bày không?

Có, bạn có thể tạo nhiều biểu đồ Bản đồ cây trong một bản trình bày bằng cách làm theo các bước tương tự và chỉ định các vị trí trang chiếu khác nhau.

### Làm cách nào để lưu bản trình bày bằng biểu đồ Bản đồ cây?

 Sử dụng`pres.save()` phương pháp lưu bản trình bày với biểu đồ Bản đồ cây ở định dạng mong muốn (ví dụ: PPTX).