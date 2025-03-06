---
title: Lưu dưới dạng Chỉ đọc trong Trang trình bày Java
linktitle: Lưu dưới dạng Chỉ đọc trong Trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách lưu bản trình bày PowerPoint ở dạng chỉ đọc trong Java bằng Aspose.Slides. Bảo vệ nội dung của bạn bằng hướng dẫn từng bước và ví dụ về mã.
weight: 11
url: /vi/java/saving-options/save-as-read-only-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu về Lưu dưới dạng chỉ đọc trong các slide Java bằng Aspose.Slides cho Java

Trong thời đại kỹ thuật số ngày nay, việc đảm bảo tính bảo mật và toàn vẹn cho tài liệu của bạn là điều tối quan trọng. Nếu đang làm việc với bản trình bày PowerPoint bằng Java, bạn có thể cần phải lưu chúng dưới dạng chỉ đọc để ngăn chặn những sửa đổi trái phép. Trong hướng dẫn toàn diện này, chúng ta sẽ khám phá cách đạt được điều này bằng cách sử dụng API Aspose.Slides for Java mạnh mẽ. Chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước và ví dụ về mã nguồn để giúp bạn bảo vệ bản trình bày của mình một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào chi tiết triển khai, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Slides cho Java: Bạn nên cài đặt Aspose.Slides cho Java. Nếu chưa có, bạn có thể tải xuống từ[đây](https://releases.aspose.com/slides/java/).

2. Môi trường phát triển Java: Đảm bảo bạn đã thiết lập môi trường phát triển Java trên hệ thống của mình.

3. Kiến thức Java cơ bản: Làm quen với lập trình Java sẽ có lợi.

## Bước 1: Thiết lập dự án của bạn

Để bắt đầu, hãy tạo một dự án Java mới trong Môi trường phát triển tích hợp (IDE) ưa thích của bạn. Đảm bảo bao gồm thư viện Aspose.Slides for Java trong dự án của bạn.

## Bước 2: Tạo bản trình bày

Trong bước này, chúng ta sẽ tạo bản trình bày PowerPoint mới bằng Aspose.Slides cho Java. Đây là mã Java để đạt được điều này:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Khởi tạo đối tượng Trình bày đại diện cho tệp PPT
Presentation presentation = new Presentation();
```

 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn đến thư mục mong muốn nơi bạn muốn lưu bản trình bày.

## Bước 3: Thêm nội dung (Tùy chọn)

Bạn có thể thêm nội dung vào bản trình bày của mình nếu cần. Bước này là tùy chọn và tùy thuộc vào nội dung cụ thể mà bạn muốn đưa vào.

## Bước 4: Cài đặt bảo vệ ghi

Để làm cho bản trình bày ở chế độ chỉ đọc, chúng tôi sẽ đặt tính năng chống ghi bằng cách cung cấp mật khẩu. Đây là cách bạn có thể làm điều đó:

```java
// Cài đặt mật khẩu bảo vệ ghi
presentation.getProtectionManager().setWriteProtection("your_password");
```

 Thay thế`"your_password"` với mật khẩu bạn muốn đặt để bảo vệ ghi.

## Bước 5: Lưu bài thuyết trình

Cuối cùng, chúng ta sẽ lưu bản trình bày vào một tệp có bảo vệ chỉ đọc:

```java
// Lưu bản trình bày của bạn vào một tập tin
presentation.save(dataDir + "ReadonlyPresentation.pptx", SaveFormat.Pptx);
```

 Đảm bảo bạn thay thế`"ReadonlyPresentation.pptx"` với tên tập tin bạn muốn.

## Mã nguồn hoàn chỉnh để lưu dưới dạng chỉ đọc trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Khởi tạo đối tượng Trình bày đại diện cho tệp PPT
Presentation presentation = new Presentation();
try
{
	//....làm một số việc ở đây.....
	// Cài đặt mật khẩu bảo vệ ghi
	presentation.getProtectionManager().setWriteProtection("test");
	// Lưu bản trình bày của bạn vào một tập tin
	presentation.save(dataDir + "WriteProtected_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách lưu bản trình bày PowerPoint ở dạng chỉ đọc trong Java bằng thư viện Aspose.Slides cho Java. Tính năng bảo mật này sẽ giúp bạn bảo vệ nội dung có giá trị của mình khỏi những sửa đổi trái phép.

## Câu hỏi thường gặp

### Làm cách nào để loại bỏ tính năng bảo vệ chống ghi khỏi bản trình bày?

 Để loại bỏ tính năng chống ghi khỏi bản trình bày, bạn có thể sử dụng`removeWriteProtection()` phương thức được cung cấp bởi Aspose.Slides cho Java. Đây là một ví dụ:

```java
// Xóa bảo vệ ghi
presentation.getProtectionManager().removeWriteProtection();
```

### Tôi có thể đặt các mật khẩu khác nhau để bảo vệ chỉ đọc và bảo vệ ghi không?

Có, bạn có thể đặt các mật khẩu khác nhau để bảo vệ chỉ đọc và bảo vệ ghi. Chỉ cần sử dụng các phương pháp thích hợp để đặt mật khẩu mong muốn:

- `setReadProtection(String password)` để bảo vệ chỉ đọc.
- `setWriteProtection(String password)` để bảo vệ ghi.

### Có thể bảo vệ các slide cụ thể trong bản trình bày không?

 Có, bạn có thể bảo vệ các trang chiếu cụ thể trong bản trình bày bằng cách đặt tính năng chống ghi trên từng trang chiếu. Sử dụng`Slide` các đối tượng`getProtectionManager()`phương pháp quản lý bảo vệ cho các slide cụ thể.

### Điều gì xảy ra nếu tôi quên mật khẩu bảo vệ ghi?

Nếu bạn quên mật khẩu bảo vệ ghi, không có cách nào tích hợp sẵn để khôi phục mật khẩu đó. Đảm bảo lưu giữ hồ sơ mật khẩu của bạn ở một nơi an toàn để tránh mọi bất tiện.

### Tôi có thể thay đổi mật khẩu chỉ đọc sau khi cài đặt không?

 Có, bạn có thể thay đổi mật khẩu chỉ đọc sau khi cài đặt. Sử dụng`setReadProtection(String newPassword)` bằng mật khẩu mới để cập nhật mật khẩu bảo vệ chỉ đọc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
