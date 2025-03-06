---
title: Đặt sổ làm việc bên ngoài với dữ liệu biểu đồ cập nhật trong các trang trình bày Java
linktitle: Đặt sổ làm việc bên ngoài với dữ liệu biểu đồ cập nhật trong các trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt sổ làm việc bên ngoài và cập nhật dữ liệu biểu đồ trong Java Slides bằng Aspose.Slides for Java. Nâng cao kỹ năng tự động hóa PowerPoint của bạn.
weight: 20
url: /vi/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Đặt sổ làm việc bên ngoài với dữ liệu biểu đồ cập nhật trong Java Slides

Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập sổ làm việc bên ngoài với dữ liệu biểu đồ được cập nhật trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Thư viện mạnh mẽ này cho phép bạn thao tác các bản trình bày PowerPoint theo chương trình, giúp dễ dàng tự động hóa các tác vụ như cập nhật dữ liệu biểu đồ từ nguồn bên ngoài. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ cách thực hiện nhiệm vụ này với hướng dẫn từng bước và mã Java đi kèm.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào triển khai, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Slides cho Java: Bạn nên cài đặt thư viện Aspose.Slides cho Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

2. Môi trường phát triển Java: Đảm bảo bạn đã thiết lập môi trường phát triển Java trên hệ thống của mình.

## Bước 1: Tạo bản trình bày mới

Để bắt đầu, hãy tạo một bản trình bày PowerPoint mới bằng Aspose.Slides cho Java. Đây là mã Java để làm điều đó:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Bây giờ, hãy thêm biểu đồ vào bản trình bày của chúng ta. Chúng tôi sẽ tạo biểu đồ Hình tròn trong ví dụ này:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Bước 3: Đặt sổ làm việc bên ngoài

Đây là nơi chúng tôi đặt sổ làm việc bên ngoài làm nguồn dữ liệu cho biểu đồ của mình. Bạn cần cung cấp URL tới sổ làm việc bên ngoài, ngay cả khi nó hiện không tồn tại:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://đường dẫn/không/tồn tại", sai);
```

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày với dữ liệu biểu đồ được cập nhật:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh để đặt sổ làm việc bên ngoài với dữ liệu biểu đồ cập nhật trong các trang trình bày Java

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

Chúc mừng! Bạn đã học cách thiết lập một sổ làm việc bên ngoài với dữ liệu biểu đồ được cập nhật trong Java Slides bằng Aspose.Slides for Java. Điều này có thể cực kỳ hữu ích để cập nhật động các biểu đồ trong bản trình bày PowerPoint của bạn từ các nguồn dữ liệu bên ngoài.

## Câu hỏi thường gặp

### Làm cách nào để cập nhật dữ liệu sổ làm việc bên ngoài cho biểu đồ?

Để cập nhật dữ liệu sổ làm việc bên ngoài cho biểu đồ, bạn chỉ cần sửa đổi dữ liệu trong sổ làm việc bên ngoài tại URL đã chỉ định. Lần tiếp theo bạn mở bản trình bày, Aspose.Slides for Java sẽ tìm nạp dữ liệu cập nhật từ sổ làm việc bên ngoài và cập nhật biểu đồ tương ứng.

### Tôi có thể sử dụng tệp cục bộ làm sổ làm việc bên ngoài không?

Có, bạn có thể sử dụng tệp cục bộ làm sổ làm việc bên ngoài bằng cách cung cấp đường dẫn tệp thay vì URL. Chỉ cần đảm bảo đường dẫn tệp chính xác và có thể truy cập được từ ứng dụng Java của bạn.

### Có bất kỳ hạn chế nào khi sử dụng sổ làm việc bên ngoài với Aspose.Slides cho Java không?

Mặc dù việc sử dụng sổ làm việc bên ngoài là một tính năng mạnh mẽ nhưng hãy nhớ rằng tính khả dụng của dữ liệu sổ làm việc bên ngoài phụ thuộc vào khả năng truy cập của nó tại URL hoặc đường dẫn tệp được cung cấp. Đảm bảo rằng nguồn dữ liệu ngoài có sẵn khi bạn mở bản trình bày để tránh các vấn đề về truy xuất dữ liệu.

### Tôi có thể tùy chỉnh giao diện biểu đồ sau khi cài đặt sổ làm việc bên ngoài không?

Có, bạn có thể tùy chỉnh hình thức của biểu đồ, bao gồm tiêu đề, nhãn, màu sắc, v.v., ngay cả sau khi cài đặt sổ làm việc bên ngoài. Aspose.Slides for Java cung cấp các tùy chọn định dạng biểu đồ mở rộng để đáp ứng nhu cầu của bạn.

### Tôi có thể tìm thêm tài liệu và tài nguyên cho Aspose.Slides cho Java ở đâu?

 Để biết tài liệu chi tiết và các tài nguyên bổ sung, hãy truy cập tài liệu Aspose.Slides for Java tại[đây](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
