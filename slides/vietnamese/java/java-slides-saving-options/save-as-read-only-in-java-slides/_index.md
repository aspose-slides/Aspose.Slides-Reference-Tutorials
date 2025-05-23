---
"description": "Tìm hiểu cách lưu bản trình bày PowerPoint dưới dạng chỉ đọc trong Java bằng Aspose.Slides. Bảo vệ nội dung của bạn bằng hướng dẫn từng bước và ví dụ về mã."
"linktitle": "Lưu dưới dạng Chỉ đọc trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lưu dưới dạng Chỉ đọc trong Java Slides"
"url": "/vi/java/saving-options/save-as-read-only-in-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lưu dưới dạng Chỉ đọc trong Java Slides


## Giới thiệu về Lưu dưới dạng Chỉ đọc trong Java Slides Sử dụng Aspose.Slides cho Java

Trong thời đại kỹ thuật số ngày nay, việc đảm bảo tính bảo mật và toàn vẹn của tài liệu là tối quan trọng. Nếu bạn đang làm việc với các bài thuyết trình PowerPoint bằng Java, bạn có thể gặp phải nhu cầu lưu chúng dưới dạng chỉ đọc để ngăn chặn các sửa đổi trái phép. Trong hướng dẫn toàn diện này, chúng ta sẽ khám phá cách thực hiện điều này bằng cách sử dụng API Aspose.Slides for Java mạnh mẽ. Chúng tôi sẽ cung cấp cho bạn các hướng dẫn từng bước và ví dụ về mã nguồn để giúp bạn bảo vệ các bài thuyết trình của mình một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết triển khai, hãy đảm bảo bạn đã đáp ứng các điều kiện tiên quyết sau:

1. Aspose.Slides for Java: Bạn nên cài đặt Aspose.Slides for Java. Nếu bạn chưa cài đặt, bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

2. Môi trường phát triển Java: Đảm bảo bạn đã thiết lập môi trường phát triển Java trên hệ thống của mình.

3. Kiến thức cơ bản về Java: Có kiến thức về lập trình Java sẽ rất có lợi.

## Bước 1: Thiết lập dự án của bạn

Để bắt đầu, hãy tạo một dự án Java mới trong Môi trường phát triển tích hợp (IDE) ưa thích của bạn. Đảm bảo đưa thư viện Aspose.Slides for Java vào dự án của bạn.

## Bước 2: Tạo bài thuyết trình

Trong bước này, chúng ta sẽ tạo một bài thuyết trình PowerPoint mới bằng Aspose.Slides for Java. Sau đây là mã Java để thực hiện điều này:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu thư mục đó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Khởi tạo một đối tượng Presentation biểu diễn một tệp PPT
Presentation presentation = new Presentation();
```

Hãy chắc chắn thay thế `"Your Document Directory"` với đường dẫn đến thư mục bạn muốn lưu bản trình bày.

## Bước 3: Thêm nội dung (Tùy chọn)

Bạn có thể thêm nội dung vào bài thuyết trình của mình khi cần. Bước này là tùy chọn và phụ thuộc vào nội dung cụ thể mà bạn muốn đưa vào.

## Bước 4: Thiết lập bảo vệ ghi

Để làm cho bài thuyết trình chỉ đọc, chúng tôi sẽ thiết lập bảo vệ ghi bằng cách cung cấp mật khẩu. Sau đây là cách bạn có thể thực hiện:

```java
// Thiết lập bảo vệ ghi mật khẩu
presentation.getProtectionManager().setWriteProtection("your_password");
```

Thay thế `"your_password"` bằng mật khẩu bạn muốn đặt để bảo vệ ghi.

## Bước 5: Lưu bài thuyết trình

Cuối cùng, chúng ta sẽ lưu bản trình bày vào một tệp có chế độ bảo vệ chỉ đọc:

```java
// Lưu bài thuyết trình của bạn vào một tập tin
presentation.save(dataDir + "ReadonlyPresentation.pptx", SaveFormat.Pptx);
```

Đảm bảo bạn thay thế `"ReadonlyPresentation.pptx"` với tên tập tin bạn muốn.

## Mã nguồn đầy đủ để lưu dưới dạng chỉ đọc trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu thư mục đó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Khởi tạo một đối tượng Presentation biểu diễn một tệp PPT
Presentation presentation = new Presentation();
try
{
	//....làm một số việc ở đây.....
	// Thiết lập bảo vệ ghi mật khẩu
	presentation.getProtectionManager().setWriteProtection("test");
	// Lưu bài thuyết trình của bạn vào một tập tin
	presentation.save(dataDir + "WriteProtected_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách lưu bản trình bày PowerPoint dưới dạng chỉ đọc trong Java bằng thư viện Aspose.Slides for Java. Tính năng bảo mật này sẽ giúp bạn bảo vệ nội dung có giá trị của mình khỏi những sửa đổi trái phép.

## Câu hỏi thường gặp

### Làm thế nào để xóa chế độ bảo vệ ghi khỏi bài thuyết trình?

Để xóa chế độ bảo vệ ghi khỏi bản trình bày, bạn có thể sử dụng `removeWriteProtection()` phương pháp được cung cấp bởi Aspose.Slides cho Java. Đây là một ví dụ:

```java
// Xóa bỏ bảo vệ ghi
presentation.getProtectionManager().removeWriteProtection();
```

### Tôi có thể đặt mật khẩu khác nhau cho chế độ chỉ đọc và bảo vệ ghi không?

Có, bạn có thể thiết lập các mật khẩu khác nhau để bảo vệ chỉ đọc và bảo vệ ghi. Chỉ cần sử dụng các phương pháp thích hợp để thiết lập các mật khẩu mong muốn:

- `setReadProtection(String password)` để bảo vệ chỉ đọc.
- `setWriteProtection(String password)` để bảo vệ việc ghi.

### Có thể bảo vệ các slide cụ thể trong bài thuyết trình không?

Có, bạn có thể bảo vệ các slide cụ thể trong bài thuyết trình bằng cách thiết lập chế độ bảo vệ ghi trên từng slide. Sử dụng `Slide` đối tượng của `getProtectionManager()` phương pháp quản lý bảo vệ cho các slide cụ thể.

### Điều gì xảy ra nếu tôi quên mật khẩu bảo vệ ghi?

Nếu bạn quên mật khẩu bảo vệ ghi, không có cách tích hợp nào để khôi phục mật khẩu. Hãy đảm bảo lưu giữ bản ghi mật khẩu của bạn ở một nơi an toàn để tránh bất kỳ sự bất tiện nào.

### Tôi có thể thay đổi mật khẩu chỉ đọc sau khi đã cài đặt không?

Có, bạn có thể thay đổi mật khẩu chỉ đọc sau khi thiết lập. Sử dụng `setReadProtection(String newPassword)` phương pháp sử dụng mật khẩu mới để cập nhật mật khẩu bảo vệ chỉ đọc.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}