---
"description": "Tìm hiểu cách thiết lập sổ làm việc bên ngoài và cập nhật dữ liệu biểu đồ trong Java Slides bằng Aspose.Slides for Java. Nâng cao kỹ năng tự động hóa PowerPoint của bạn."
"linktitle": "Thiết lập sổ làm việc bên ngoài với dữ liệu biểu đồ cập nhật trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thiết lập sổ làm việc bên ngoài với dữ liệu biểu đồ cập nhật trong Java Slides"
"url": "/vi/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thiết lập sổ làm việc bên ngoài với dữ liệu biểu đồ cập nhật trong Java Slides


## Giới thiệu về Set External Workbook With Update Chart Data trong Java Slides

Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập sổ làm việc bên ngoài với dữ liệu biểu đồ được cập nhật trong Java Slides bằng cách sử dụng Aspose.Slides for Java API. Thư viện mạnh mẽ này cho phép bạn thao tác các bài thuyết trình PowerPoint theo chương trình, giúp bạn dễ dàng tự động hóa các tác vụ như cập nhật dữ liệu biểu đồ từ nguồn bên ngoài. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ cách thực hiện tác vụ này với hướng dẫn từng bước và mã Java đi kèm.

## Điều kiện tiên quyết

Trước khi bắt đầu triển khai, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Aspose.Slides for Java: Bạn nên cài đặt thư viện Aspose.Slides for Java. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

2. Môi trường phát triển Java: Đảm bảo bạn đã thiết lập môi trường phát triển Java trên hệ thống của mình.

## Bước 1: Tạo một bài thuyết trình mới

Để bắt đầu, hãy tạo một bài thuyết trình PowerPoint mới bằng Aspose.Slides for Java. Sau đây là mã Java để thực hiện điều đó:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Bây giờ, chúng ta hãy thêm một biểu đồ vào bài thuyết trình của mình. Chúng ta sẽ tạo một biểu đồ hình tròn trong ví dụ này:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Bước 3: Thiết lập Workbook bên ngoài

Đây là nơi chúng ta đặt sổ làm việc bên ngoài làm nguồn dữ liệu cho biểu đồ của mình. Bạn cần cung cấp URL đến sổ làm việc bên ngoài, ngay cả khi nó không tồn tại vào lúc này:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://đường dẫn/không/tồn tại", sai);
```

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày với dữ liệu biểu đồ đã cập nhật:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho Set External Workbook với dữ liệu biểu đồ cập nhật trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://đường dẫn/không/tồn tại", sai);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách thiết lập sổ làm việc bên ngoài với dữ liệu biểu đồ được cập nhật trong Java Slides bằng Aspose.Slides for Java. Điều này có thể cực kỳ hữu ích để cập nhật biểu đồ động trong bản trình bày PowerPoint của bạn từ các nguồn dữ liệu bên ngoài.

## Câu hỏi thường gặp

### Làm thế nào để cập nhật dữ liệu bảng tính ngoài cho biểu đồ?

Để cập nhật dữ liệu sổ làm việc bên ngoài cho biểu đồ, bạn chỉ cần sửa đổi dữ liệu trong sổ làm việc bên ngoài tại URL đã chỉ định. Lần sau khi bạn mở bản trình bày, Aspose.Slides for Java sẽ lấy dữ liệu đã cập nhật từ sổ làm việc bên ngoài và cập nhật biểu đồ cho phù hợp.

### Tôi có thể sử dụng tệp cục bộ làm sổ làm việc bên ngoài không?

Có, bạn có thể sử dụng tệp cục bộ làm sổ làm việc bên ngoài bằng cách cung cấp đường dẫn tệp thay vì URL. Chỉ cần đảm bảo đường dẫn tệp là chính xác và có thể truy cập được từ ứng dụng Java của bạn.

### Có bất kỳ hạn chế nào khi sử dụng sổ làm việc ngoài với Aspose.Slides cho Java không?

Mặc dù sử dụng sổ làm việc bên ngoài là một tính năng mạnh mẽ, hãy lưu ý rằng tính khả dụng của dữ liệu trong sổ làm việc bên ngoài phụ thuộc vào khả năng truy cập của nó tại URL hoặc đường dẫn tệp được cung cấp. Đảm bảo rằng nguồn dữ liệu bên ngoài khả dụng khi bạn mở bản trình bày để tránh các sự cố truy xuất dữ liệu.

### Tôi có thể tùy chỉnh giao diện biểu đồ sau khi cài đặt bảng tính bên ngoài không?

Có, bạn có thể tùy chỉnh giao diện của biểu đồ, bao gồm tiêu đề, nhãn, màu sắc, v.v., ngay cả sau khi thiết lập sổ làm việc bên ngoài. Aspose.Slides for Java cung cấp nhiều tùy chọn định dạng biểu đồ để đáp ứng nhu cầu của bạn.

### Tôi có thể tìm thêm tài liệu và tài nguyên về Aspose.Slides for Java ở đâu?

Để biết tài liệu chi tiết và các tài nguyên bổ sung, hãy truy cập tài liệu Aspose.Slides cho Java tại [đây](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}