---
"description": "Tìm hiểu cách bật thuộc tính Read-Only Recommended trong bản trình bày Java PowerPoint bằng Aspose.Slides for Java. Làm theo hướng dẫn từng bước của chúng tôi với các ví dụ về mã nguồn để tăng cường bảo mật bản trình bày."
"linktitle": "Thuộc tính được đề xuất chỉ đọc trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thuộc tính được đề xuất chỉ đọc trong Java Slides"
"url": "/vi/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thuộc tính được đề xuất chỉ đọc trong Java Slides


## Giới thiệu về việc bật thuộc tính được đề xuất chỉ đọc trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách bật thuộc tính Read-Only Recommended cho các bài thuyết trình PowerPoint bằng Aspose.Slides for Java. Thuộc tính Read-Only Recommended có thể hữu ích khi bạn muốn khuyến khích người dùng xem bài thuyết trình mà không thực hiện bất kỳ thay đổi nào. Các thuộc tính này gợi ý rằng bài thuyết trình nên được mở ở chế độ chỉ đọc. Chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước cùng với mã nguồn Java để thực hiện điều này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập thư viện Aspose.Slides for Java trong dự án của mình. Bạn có thể tải xuống từ [Trang web Aspose.Slides cho Java](https://products.aspose.com/slides/java/).

## Bước 1: Tạo một bài thuyết trình PowerPoint mới

Chúng ta sẽ bắt đầu bằng cách tạo một bài thuyết trình PowerPoint mới bằng Aspose.Slides for Java. Nếu bạn đã có bài thuyết trình, bạn có thể bỏ qua bước này.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Trong đoạn mã trên, chúng tôi đã xác định đường dẫn cho tệp PowerPoint đầu ra và tạo một đối tượng trình bày mới.

## Bước 2: Bật Thuộc tính được đề xuất chỉ đọc

Bây giờ, hãy kích hoạt thuộc tính Read-Only Recommended cho bản trình bày.

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

Trong đoạn mã này, chúng tôi sử dụng `getProtectionManager().setReadOnlyRecommended(true)` phương pháp để thiết lập thuộc tính Chỉ đọc được đề xuất thành `true`. Điều này đảm bảo rằng khi ai đó mở bài thuyết trình, họ sẽ được nhắc mở ở chế độ chỉ đọc.

## Bước 3: Lưu bài thuyết trình

Cuối cùng, chúng ta lưu bản trình bày với thuộc tính Chỉ đọc được đề xuất được bật.

## Mã nguồn đầy đủ cho các thuộc tính được đề xuất chỉ đọc trong Java Slides

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

Trong hướng dẫn này, bạn đã học cách bật thuộc tính Read-Only Recommended cho bản trình bày PowerPoint bằng Aspose.Slides for Java. Tính năng này có thể hữu ích khi bạn muốn hạn chế chỉnh sửa và khuyến khích người xem sử dụng bản trình bày ở chế độ chỉ đọc. Bạn có thể tăng cường bảo mật hơn nữa bằng cách đặt mật khẩu cho bản trình bày.

## Câu hỏi thường gặp

### Làm thế nào để tắt thuộc tính Đề xuất chỉ đọc?

Để vô hiệu hóa thuộc tính Chỉ đọc được đề xuất, chỉ cần sử dụng mã sau:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Tôi có thể đặt mật khẩu cho bài thuyết trình được đề xuất chỉ đọc không?

Có, bạn có thể đặt mật khẩu cho bài thuyết trình Chỉ đọc được khuyến nghị bằng Aspose.Slides cho Java. Bạn có thể sử dụng `setPassword` phương pháp đặt mật khẩu cho bài thuyết trình. Nếu mật khẩu được đặt, người dùng sẽ cần nhập mật khẩu để mở bài thuyết trình, ngay cả ở chế độ chỉ đọc.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Nhớ thay thế `"YourPassword"` bằng mật khẩu bạn muốn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}