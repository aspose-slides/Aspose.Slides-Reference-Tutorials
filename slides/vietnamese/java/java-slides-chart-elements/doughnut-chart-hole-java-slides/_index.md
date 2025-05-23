---
"description": "Tạo biểu đồ hình bánh rán với kích thước lỗ tùy chỉnh trong Java Slides bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn để tùy chỉnh biểu đồ."
"linktitle": "Lỗ biểu đồ hình tròn trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lỗ biểu đồ hình tròn trong Java Slides"
"url": "/vi/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lỗ biểu đồ hình tròn trong Java Slides


## Giới thiệu về Biểu đồ hình tròn có lỗ trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách tạo biểu đồ hình bánh rán có lỗ bằng Aspose.Slides for Java. Hướng dẫn từng bước này sẽ hướng dẫn bạn thực hiện quy trình với các ví dụ về mã nguồn.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống từ [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).

## Bước 1: Nhập các thư viện cần thiết

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

// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
```

## Bước 3: Tạo biểu đồ hình bánh rán

```java
try {
    // Tạo biểu đồ hình tròn trên trang chiếu đầu tiên
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Đặt kích thước của lỗ trong biểu đồ hình tròn (theo phần trăm)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Lưu bài thuyết trình vào đĩa
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Loại bỏ đối tượng trình bày
    if (presentation != null) presentation.dispose();
}
```

## Bước 4: Chạy mã

Chạy mã Java trong IDE hoặc trình soạn thảo văn bản của bạn để tạo biểu đồ hình bánh rán có kích thước lỗ được chỉ định. Đảm bảo thay thế `"Your Document Directory"` với đường dẫn thực tế mà bạn muốn lưu bản trình bày.

## Mã nguồn đầy đủ cho biểu đồ hình tròn Donut trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Ghi bản trình bày vào đĩa
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo biểu đồ hình bánh rán có lỗ bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh kích thước của lỗ bằng cách điều chỉnh `setDoughnutHoleSize` tham số phương pháp.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi màu sắc của các phân đoạn biểu đồ?

Để thay đổi màu sắc của các phân đoạn biểu đồ, bạn có thể sử dụng `setDataPointsInLegend` phương pháp trên `IChart` đối tượng và thiết lập màu mong muốn cho mỗi điểm dữ liệu.

### Tôi có thể thêm nhãn vào các phân đoạn biểu đồ hình tròn không?

Có, bạn có thể thêm nhãn vào các phân đoạn biểu đồ hình tròn bằng cách sử dụng `setDataPointsLabelValue` phương pháp trên `IChart` sự vật.

### Có thể thêm tiêu đề vào biểu đồ không?

Chắc chắn rồi! Bạn có thể thêm tiêu đề vào biểu đồ bằng cách sử dụng `setTitle` phương pháp trên `IChart` đối tượng và cung cấp văn bản tiêu đề mong muốn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}