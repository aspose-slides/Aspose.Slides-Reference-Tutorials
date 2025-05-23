---
"description": "Tìm hiểu cách thiết lập các kiểu xem được xác định trước trong Java Slides bằng Aspose.Slides cho Java. Hướng dẫn từng bước với các ví dụ về mã và câu hỏi thường gặp."
"linktitle": "Lưu dưới dạng Kiểu xem được xác định trước trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lưu dưới dạng Kiểu xem được xác định trước trong Java Slides"
"url": "/vi/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lưu dưới dạng Kiểu xem được xác định trước trong Java Slides


## Giới thiệu về Lưu dưới dạng Kiểu xem được xác định trước trong Java Slides

Trong hướng dẫn từng bước này, chúng ta sẽ khám phá cách lưu bản trình bày với kiểu xem được xác định trước bằng Aspose.Slides for Java. Chúng tôi sẽ cung cấp cho bạn mã và giải thích cần thiết để hoàn thành nhiệm vụ này thành công.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về lập trình Java.
- Đã cài đặt thư viện Aspose.Slides cho Java.
- Môi trường phát triển tích hợp (IDE) theo lựa chọn của bạn.

## Thiết lập môi trường của bạn

Để bắt đầu, hãy làm theo các bước sau để thiết lập môi trường phát triển của bạn:

1. Tạo một dự án Java mới trong IDE của bạn.
2. Thêm thư viện Aspose.Slides cho Java vào dự án của bạn dưới dạng thư viện phụ thuộc.

Bây giờ môi trường của bạn đã được thiết lập, chúng ta hãy tiếp tục viết mã.

## Bước 1: Tạo bài thuyết trình

Để chứng minh việc lưu bản trình bày với kiểu xem được xác định trước, trước tiên chúng ta sẽ tạo một bản trình bày mới. Sau đây là mã để tạo bản trình bày:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Mở tệp trình bày
Presentation presentation = new Presentation();
```

Trong mã này, chúng ta tạo một `Presentation` đối tượng đại diện cho bài thuyết trình PowerPoint của chúng ta.

## Bước 2: Thiết lập Kiểu xem

Tiếp theo, chúng ta sẽ thiết lập kiểu xem cho bài thuyết trình của mình. Kiểu xem xác định cách bài thuyết trình được hiển thị khi mở. Trong ví dụ này, chúng ta sẽ thiết lập thành "Slide Master View". Đây là mã:

```java
// Thiết lập kiểu xem
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

Trong đoạn mã trên, chúng tôi sử dụng `setLastView` phương pháp của `ViewProperties` lớp để thiết lập kiểu xem thành `SlideMasterView`. Bạn có thể chọn các kiểu xem khác nếu cần.

## Bước 3: Lưu bài thuyết trình

Bây giờ chúng ta đã tạo xong bản trình bày và thiết lập kiểu xem, đã đến lúc lưu bản trình bày. Chúng ta sẽ lưu nó ở định dạng PPTX. Đây là mã:

```java
// Lưu bài thuyết trình
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

Trong mã này, chúng tôi sử dụng `save` phương pháp của `Presentation` lớp để lưu bản trình bày với tên tệp và định dạng đã chỉ định.

## Mã nguồn đầy đủ để lưu dưới dạng kiểu xem được xác định trước trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Mở tệp trình bày
Presentation presentation = new Presentation();
try
{
	// Thiết lập kiểu xem
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Lưu bài thuyết trình
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách lưu bản trình bày với kiểu xem được xác định trước trong Java bằng Aspose.Slides for Java. Bằng cách làm theo mã và các bước được cung cấp, bạn có thể dễ dàng thiết lập kiểu xem cho bản trình bày của mình và lưu chúng theo định dạng mong muốn.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi kiểu xem sang kiểu khác ngoài "Slide Master View"?

Để thay đổi kiểu xem thành kiểu khác ngoài "Slide Master View", chỉ cần thay thế `ViewType.SlideMasterView` với loại chế độ xem mong muốn, chẳng hạn như `ViewType.NhoặcmalView` or `ViewType.SlideSorterView`, trong mã nơi chúng ta thiết lập kiểu xem.

### Tôi có thể thiết lập thuộc tính chế độ xem cho từng slide trong bản trình bày không?

Có, bạn có thể thiết lập thuộc tính chế độ xem cho từng slide bằng Aspose.Slides for Java. Bạn có thể truy cập và thao tác các thuộc tính cho từng slide riêng biệt bằng cách lặp qua các slide trong bản trình bày.

### Tôi có thể lưu bài thuyết trình của mình ở những định dạng nào khác?

Aspose.Slides for Java hỗ trợ nhiều định dạng đầu ra khác nhau, bao gồm PPTX, PDF, TIFF, HTML, v.v. Bạn có thể chỉ định định dạng mong muốn khi lưu bản trình bày của mình bằng cách sử dụng `SaveFormat` giá trị enum.

### Aspose.Slides for Java có phù hợp để xử lý hàng loạt bài thuyết trình không?

Có, Aspose.Slides for Java rất phù hợp cho các tác vụ xử lý hàng loạt. Bạn có thể tự động xử lý nhiều bản trình bày, áp dụng các thay đổi và lưu chúng hàng loạt bằng mã Java.

### Tôi có thể tìm thêm thông tin và tài liệu về Aspose.Slides for Java ở đâu?

Để biết tài liệu và tham khảo toàn diện liên quan đến Aspose.Slides for Java, vui lòng truy cập trang web tài liệu: [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}