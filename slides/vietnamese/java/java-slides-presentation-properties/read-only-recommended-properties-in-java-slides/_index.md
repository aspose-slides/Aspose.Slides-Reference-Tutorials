---
title: Thuộc tính được đề xuất chỉ đọc trong Java Slides
linktitle: Thuộc tính được đề xuất chỉ đọc trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách bật thuộc tính Đề xuất chỉ đọc trong bản trình bày Java PowerPoint bằng Aspose.Slides cho Java. Hãy làm theo hướng dẫn từng bước của chúng tôi với các ví dụ về mã nguồn để tăng cường bảo mật cho bản trình bày.
weight: 17
url: /vi/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Kích hoạt các thuộc tính được đề xuất chỉ đọc trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách bật các thuộc tính Đề xuất chỉ đọc cho bản trình bày PowerPoint bằng Aspose.Slides cho Java. Thuộc tính Chỉ đọc được đề xuất có thể hữu ích khi bạn muốn khuyến khích người dùng xem bản trình bày mà không thực hiện bất kỳ thay đổi nào. Các thuộc tính này gợi ý rằng bản trình bày nên được mở ở chế độ chỉ đọc. Chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước cùng với mã nguồn Java để đạt được điều này.

## Điều kiện tiên quyết

 Trước khi chúng ta bắt đầu, hãy đảm bảo bạn đã thiết lập thư viện Aspose.Slides cho Java trong dự án của mình. Bạn có thể tải nó xuống từ[Aspose.Slides cho trang web Java](https://products.aspose.com/slides/java/).

## Bước 1: Tạo bản trình bày PowerPoint mới

Chúng ta sẽ bắt đầu bằng cách tạo một bản trình bày PowerPoint mới bằng Aspose.Slides cho Java. Nếu bạn đã có bản trình bày, bạn có thể bỏ qua bước này.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Trong đoạn mã trên, chúng tôi đã xác định đường dẫn cho tệp PowerPoint đầu ra và tạo một đối tượng bản trình bày mới.

## Bước 2: Kích hoạt thuộc tính được đề xuất chỉ đọc

Bây giờ, hãy bật thuộc tính Đề xuất chỉ đọc cho bản trình bày.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 Trong đoạn mã này, chúng tôi sử dụng`getProtectionManager().setReadOnlyRecommended(true)` phương pháp để đặt thuộc tính Đề xuất chỉ đọc thành`true`. Điều này đảm bảo rằng khi ai đó mở bài thuyết trình, họ sẽ được nhắc mở bài thuyết trình ở chế độ chỉ đọc.

## Bước 3: Lưu bài thuyết trình

Cuối cùng, chúng tôi lưu bản trình bày với thuộc tính Đề xuất chỉ đọc được bật.

## Mã nguồn hoàn chỉnh cho các thuộc tính được đề xuất chỉ đọc trong các trang trình bày Java

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã tìm hiểu cách bật thuộc tính Đề xuất chỉ đọc cho bản trình bày PowerPoint bằng Aspose.Slides cho Java. Tính năng này có thể hữu ích khi bạn muốn hạn chế chỉnh sửa và khuyến khích người xem sử dụng bài thuyết trình ở chế độ chỉ đọc. Bạn có thể tăng cường bảo mật hơn nữa bằng cách đặt mật khẩu cho bài thuyết trình.

## Câu hỏi thường gặp

### Làm cách nào để tắt thuộc tính Đề xuất chỉ đọc?

Để tắt thuộc tính Đề xuất chỉ đọc, chỉ cần sử dụng mã sau:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Tôi có thể đặt mật khẩu cho bài thuyết trình được đề xuất chỉ đọc không?

Có, bạn có thể đặt mật khẩu cho bản trình bày Đề xuất chỉ đọc bằng Aspose.Slides cho Java. Bạn có thể dùng`setPassword` cách đặt mật khẩu cho bài thuyết trình. Nếu đặt mật khẩu, người dùng sẽ cần nhập mật khẩu đó để mở bài thuyết trình, ngay cả ở chế độ chỉ đọc.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Nhớ thay thế`"YourPassword"` với mật khẩu bạn mong muốn.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
