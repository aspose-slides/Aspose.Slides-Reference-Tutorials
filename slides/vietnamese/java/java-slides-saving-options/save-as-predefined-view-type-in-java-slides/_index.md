---
title: Lưu dưới dạng Kiểu xem được xác định trước trong Trang trình bày Java
linktitle: Lưu dưới dạng Kiểu xem được xác định trước trong Trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt các loại chế độ xem được xác định trước trong Java Slides bằng Aspose.Slides for Java. Hướng dẫn từng bước với các ví dụ về mã và Câu hỏi thường gặp.
weight: 10
url: /vi/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Lưu dưới dạng Kiểu xem được xác định trước trong Trang trình bày Java

Trong hướng dẫn từng bước này, chúng ta sẽ khám phá cách lưu bản trình bày với loại chế độ xem được xác định trước bằng Aspose.Slides cho Java. Chúng tôi sẽ cung cấp cho bạn mã và giải thích cần thiết để hoàn thành nhiệm vụ này thành công.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về lập trình Java.
- Đã cài đặt thư viện Aspose.Slides cho Java.
- Môi trường phát triển tích hợp (IDE) do bạn lựa chọn.

## Thiết lập môi trường của bạn

Để bắt đầu, hãy làm theo các bước sau để thiết lập môi trường phát triển của bạn:

1. Tạo một dự án Java mới trong IDE của bạn.
2. Thêm thư viện Aspose.Slides for Java vào dự án của bạn dưới dạng phụ thuộc.

Bây giờ môi trường của bạn đã được thiết lập, hãy tiếp tục với mã.

## Bước 1: Tạo bản trình bày

Để minh họa việc lưu bản trình bày với kiểu xem được xác định trước, trước tiên chúng ta sẽ tạo một bản trình bày mới. Đây là mã để tạo bản trình bày:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Mở tập tin trình bày
Presentation presentation = new Presentation();
```

 Trong mã này, chúng tôi tạo một mới`Presentation` đối tượng, đại diện cho bản trình bày PowerPoint của chúng tôi.

## Bước 2: Đặt kiểu xem

Tiếp theo, chúng tôi sẽ đặt loại chế độ xem cho bản trình bày của mình. Các loại dạng xem xác định cách hiển thị bản trình bày khi mở. Trong ví dụ này, chúng tôi sẽ đặt nó thành "Chế độ xem trang trình bày chính". Đây là mã:

```java
// Cài đặt kiểu xem
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Trong đoạn mã trên, chúng tôi sử dụng`setLastView` phương pháp của`ViewProperties` lớp để đặt kiểu xem thành`SlideMasterView`. Bạn có thể chọn các kiểu xem khác nếu cần.

## Bước 3: Lưu bài thuyết trình

Bây giờ chúng ta đã tạo xong bản trình bày và thiết lập kiểu xem, đã đến lúc lưu bản trình bày. Chúng tôi sẽ lưu nó ở định dạng PPTX. Đây là mã:

```java
// Đang lưu bản trình bày
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 Trong mã này, chúng tôi sử dụng`save` phương pháp của`Presentation` class để lưu bản trình bày với tên tệp và định dạng được chỉ định.

## Mã nguồn hoàn chỉnh để lưu dưới dạng loại chế độ xem được xác định trước trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Mở tập tin trình bày
Presentation presentation = new Presentation();
try
{
	// Cài đặt kiểu xem
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Đang lưu bản trình bày
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách lưu bản trình bày với kiểu xem được xác định trước trong Java bằng Aspose.Slides cho Java. Bằng cách làm theo mã và các bước được cung cấp, bạn có thể dễ dàng đặt loại chế độ xem cho bản trình bày của mình và lưu chúng ở định dạng mong muốn.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi loại chế độ xem thành loại khác ngoài "Chế độ xem trang trình bày chính"?

 Để thay đổi loại chế độ xem thành một loại khác ngoài "Chế độ xem trang trình bày chính", chỉ cần thay thế`ViewType.SlideMasterView` với kiểu xem mong muốn, chẳng hạn như`ViewType.NormalView` hoặc`ViewType.SlideSorterView`, trong mã nơi chúng tôi đặt loại chế độ xem.

### Tôi có thể đặt thuộc tính chế độ xem cho từng trang chiếu trong bản trình bày không?

Có, bạn có thể đặt thuộc tính chế độ xem cho từng trang chiếu bằng Aspose.Slides cho Java. Bạn có thể truy cập và thao tác các thuộc tính cho từng slide riêng biệt bằng cách lặp qua các slide trong bản trình bày.

### Tôi có thể lưu bản trình bày của mình ở những định dạng nào khác?

Aspose.Slides cho Java hỗ trợ nhiều định dạng đầu ra khác nhau, bao gồm PPTX, PDF, TIFF, HTML, v.v. Bạn có thể chỉ định định dạng mong muốn khi lưu bản trình bày của mình bằng cách sử dụng`SaveFormat` giá trị enum.

### Aspose.Slides cho Java có phù hợp để xử lý hàng loạt bản trình bày không?

Có, Aspose.Slides cho Java rất phù hợp cho các tác vụ xử lý hàng loạt. Bạn có thể tự động hóa việc xử lý nhiều bản trình bày, áp dụng các thay đổi và lưu chúng hàng loạt bằng mã Java.

### Tôi có thể tìm thêm thông tin và tài liệu về Aspose.Slides cho Java ở đâu?

 Để có tài liệu và tài liệu tham khảo toàn diện liên quan đến Aspose.Slides cho Java, vui lòng truy cập trang web tài liệu:[Aspose.Slides cho Tài liệu Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
