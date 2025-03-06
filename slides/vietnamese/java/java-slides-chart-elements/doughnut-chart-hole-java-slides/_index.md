---
title: Lỗ biểu đồ bánh rán trong trang trình bày Java
linktitle: Lỗ biểu đồ bánh rán trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tạo biểu đồ bánh rán với kích thước lỗ tùy chỉnh trong trang trình bày Java bằng cách sử dụng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn để tùy chỉnh biểu đồ.
weight: 11
url: /vi/java/chart-elements/doughnut-chart-hole-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Biểu đồ bánh rán có lỗ trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn tạo biểu đồ bánh rán có lỗ bằng Aspose.Slides cho Java. Hướng dẫn từng bước này sẽ hướng dẫn bạn thực hiện quy trình bằng các ví dụ về mã nguồn.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải nó xuống từ[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/).

## Bước 1: Nhập thư viện cần thiết

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Bước 2: Khởi tạo bài thuyết trình

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
```

## Bước 3: Tạo biểu đồ bánh rán

```java
try {
    // Tạo biểu đồ bánh rán trên trang trình bày đầu tiên
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Đặt kích thước của lỗ trong biểu đồ bánh rán (theo tỷ lệ phần trăm)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Lưu bản trình bày vào đĩa
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Vứt bỏ đối tượng trình bày
    if (presentation != null) presentation.dispose();
}
```

## Bước 4: Chạy mã

 Chạy mã Java trong IDE hoặc trình soạn thảo văn bản của bạn để tạo biểu đồ bánh rán với kích thước lỗ được chỉ định. Đảm bảo thay thế`"Your Document Directory"` với đường dẫn thực tế mà bạn muốn lưu bản trình bày.

## Mã nguồn hoàn chỉnh cho lỗ biểu đồ bánh rán trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Ghi bài thuyết trình vào đĩa
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

 Trong hướng dẫn này, bạn đã học cách tạo biểu đồ bánh rán có lỗ bằng Aspose.Slides cho Java. Bạn có thể tùy chỉnh kích thước của lỗ bằng cách điều chỉnh`setDoughnutHoleSize` tham số phương thức.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu của các phân đoạn biểu đồ?

 Để thay đổi màu của các đoạn biểu đồ, bạn có thể sử dụng`setDataPointsInLegend` phương pháp trên`IChart` đối tượng và đặt màu mong muốn cho từng điểm dữ liệu.

### Tôi có thể thêm nhãn vào các phân đoạn biểu đồ vành khuyên không?

 Có, bạn có thể thêm nhãn vào các phân đoạn biểu đồ vành khuyên bằng cách sử dụng`setDataPointsLabelValue` phương pháp trên`IChart` sự vật.

### Có thể thêm tiêu đề vào biểu đồ không?

 Chắc chắn! Bạn có thể thêm tiêu đề vào biểu đồ bằng cách sử dụng`setTitle` phương pháp trên`IChart` đối tượng và cung cấp văn bản tiêu đề mong muốn.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
