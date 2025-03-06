---
title: Đặt trục vị trí trong các slide Java
linktitle: Đặt trục vị trí trong các slide Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Cải thiện biểu đồ của bạn với Aspose.Slides cho Java. Tìm hiểu cách đặt trục vị trí trong các trang trình bày Java, tạo bản trình bày ấn tượng và tùy chỉnh bố cục biểu đồ một cách dễ dàng.
weight: 16
url: /vi/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu về Thiết lập trục vị trí trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách đặt trục vị trí trong biểu đồ bằng Aspose.Slides cho Java. Định vị trục có thể hữu ích khi bạn muốn tùy chỉnh hình thức và bố cục của biểu đồ. Chúng ta sẽ tạo biểu đồ cột phân cụm và điều chỉnh vị trí trục hoành giữa các danh mục.

## Điều kiện tiên quyết

 Trước khi chúng ta bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải thư viện từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo bản trình bày

Trước tiên, hãy tạo một bản trình bày mới để làm việc:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Thêm biểu đồ

Tiếp theo, chúng ta sẽ thêm biểu đồ cột nhóm vào slide. Chúng tôi chỉ định loại biểu đồ, vị trí (tọa độ x, y) và kích thước (chiều rộng và chiều cao) của biểu đồ:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Ở đây, chúng tôi đã thêm biểu đồ cột được nhóm ở vị trí (50, 50) với chiều rộng là 450 và chiều cao là 300. Bạn có thể điều chỉnh các giá trị này nếu cần.

## Bước 3: Thiết lập trục vị trí

Để đặt trục vị trí giữa các danh mục, bạn có thể sử dụng mã sau:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Mã này đặt trục hoành để hiển thị giữa các danh mục, điều này có thể hữu ích cho một số bố cục biểu đồ nhất định.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, hãy lưu bài thuyết trình với biểu đồ:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Thay thế`"AsposeClusteredColumnChart.pptx"` với tên tập tin bạn muốn.

Đó là nó! Bạn đã tạo thành công biểu đồ cột được nhóm và đặt trục vị trí giữa các danh mục bằng Aspose.Slides cho Java.

## Mã nguồn hoàn chỉnh
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách đặt trục vị trí trong biểu đồ bằng Aspose.Slides cho Java. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn đã học được cách tạo biểu đồ cột được nhóm và tùy chỉnh giao diện của biểu đồ bằng cách định vị trục hoành giữa các danh mục. Aspose.Slides for Java cung cấp các tính năng mạnh mẽ để làm việc với biểu đồ và bản trình bày, khiến nó trở thành một công cụ có giá trị cho các nhà phát triển Java.

## Câu hỏi thường gặp

### Làm cách nào để tùy chỉnh thêm biểu đồ?

Bạn có thể tùy chỉnh các khía cạnh khác nhau của biểu đồ, bao gồm chuỗi dữ liệu, tiêu đề biểu đồ, chú giải, v.v. Tham khảo đến[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/) để biết hướng dẫn chi tiết và ví dụ.

### Tôi có thể thay đổi loại biểu đồ không?

 Có, bạn có thể thay đổi loại biểu đồ bằng cách sửa đổi`ChartType` tham số khi thêm biểu đồ. Aspose.Slides cho Java hỗ trợ nhiều loại biểu đồ khác nhau như biểu đồ thanh, biểu đồ đường, v.v.

### Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?

 Bạn có thể tìm thấy tài liệu đầy đủ và nhiều ví dụ hơn về[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/) trang.

Hãy nhớ loại bỏ đối tượng trình bày khi bạn hoàn thành nó để giải phóng tài nguyên hệ thống:

```java
if (pres != null) pres.dispose();
```

Đó là tất cả cho hướng dẫn này. Bạn đã học cách đặt trục vị trí trong biểu đồ bằng Aspose.Slides cho Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
