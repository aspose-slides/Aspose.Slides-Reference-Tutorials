---
title: Đặt góc xoay trong Java Slides
linktitle: Đặt góc xoay trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tối ưu hóa các trang trình bày Java của bạn với Aspose.Slides for Java. Tìm hiểu cách thiết lập góc xoay cho các thành phần văn bản. Hướng dẫn từng bước với mã nguồn.
weight: 17
url: /vi/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Thiết lập góc xoay trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt góc xoay cho văn bản trong tiêu đề trục biểu đồ bằng thư viện Aspose.Slides cho Java. Bằng cách điều chỉnh góc xoay, bạn có thể tùy chỉnh giao diện của tiêu đề trục của biểu đồ để phù hợp hơn với nhu cầu trình bày của mình.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ trang web Aspose và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu của họ.

## Bước 1: Tạo bản trình bày

Trước tiên, bạn cần tạo bản trình bày mới hoặc tải bản trình bày hiện có. Trong ví dụ này, chúng ta sẽ tạo một bản trình bày mới:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ vào slide

Tiếp theo, chúng ta sẽ thêm biểu đồ vào slide. Trong ví dụ này, chúng tôi đang thêm biểu đồ cột được nhóm:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Bước 3: Đặt góc quay cho tiêu đề trục

Để đặt góc xoay cho tiêu đề trục, bạn cần truy cập vào tiêu đề trục tung của biểu đồ và điều chỉnh góc xoay của nó. Đây là cách bạn có thể làm điều đó:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

Trong đoạn mã này, chúng tôi đang đặt góc xoay thành 90 độ, góc này sẽ xoay văn bản theo chiều dọc. Bạn có thể điều chỉnh góc theo giá trị mong muốn.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày vào tệp PowerPoint:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Mã nguồn hoàn chỉnh để thiết lập góc xoay trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách đặt góc xoay cho văn bản trong tiêu đề trục biểu đồ bằng Aspose.Slides cho Java. Tính năng này cho phép bạn tùy chỉnh giao diện của biểu đồ để tạo các bản trình bày hấp dẫn trực quan. Thử nghiệm với các góc xoay khác nhau để đạt được giao diện mong muốn cho biểu đồ của bạn.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi góc xoay cho các thành phần văn bản khác trong trang chiếu?

Bạn có thể thay đổi góc xoay cho các thành phần văn bản khác, chẳng hạn như hình dạng hoặc hộp văn bản, bằng cách sử dụng phương pháp tương tự. Truy cập định dạng văn bản của phần tử và đặt góc xoay nếu cần.

### Tôi có thể xoay văn bản trong tiêu đề trục hoành không?

Có, bạn có thể xoay văn bản trong tiêu đề trục hoành bằng cách điều chỉnh góc xoay. Chỉ cần đặt góc xoay thành giá trị mong muốn của bạn, chẳng hạn như 90 độ cho văn bản dọc hoặc 0 độ cho văn bản ngang.

### Những tùy chọn định dạng nào khác có sẵn cho tiêu đề biểu đồ?

Aspose.Slides for Java cung cấp nhiều tùy chọn định dạng khác nhau cho tiêu đề biểu đồ, bao gồm kiểu phông chữ, màu sắc và căn chỉnh. Bạn có thể khám phá tài liệu để biết thêm chi tiết về cách tùy chỉnh tiêu đề biểu đồ.

### Có thể tạo hiệu ứng xoay văn bản trong tiêu đề trục biểu đồ không?

Có, bạn có thể thêm hiệu ứng hoạt hình vào các thành phần văn bản, bao gồm tiêu đề trục biểu đồ bằng Aspose.Slides cho Java. Tham khảo tài liệu để biết thông tin về cách thêm hình động vào bản trình bày của bạn.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
