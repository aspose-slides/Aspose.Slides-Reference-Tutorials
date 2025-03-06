---
title: Thư mục gốc ClsId trong Java Slides
linktitle: Thư mục gốc ClsId trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt ClsId thư mục gốc trong Aspose.Slides cho bản trình bày Java. Tùy chỉnh hành vi siêu liên kết với CLSID.
weight: 10
url: /vi/java/media-controls/root-directory-clsid-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Thiết lập thư mục gốc ClsId trong Aspose.Slides cho Java

Trong Aspose.Slides cho Java, bạn có thể đặt ClsId Thư mục gốc, là CLSID (Mã định danh lớp) được sử dụng để chỉ định ứng dụng sẽ được sử dụng làm thư mục gốc khi siêu liên kết trong bản trình bày của bạn được kích hoạt. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thực hiện việc này từng bước.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Thư viện Aspose.Slides dành cho Java đã được thêm vào dự án của bạn. Bạn có thể tải nó xuống từ[Aspose.Slides cho Tài liệu Java](https://reference.aspose.com/slides/java/).
- Trình chỉnh sửa mã hoặc Môi trường phát triển tích hợp (IDE) được thiết lập để phát triển Java.

## Bước 1: Tạo bản trình bày mới

Trước tiên, hãy tạo một bản trình bày mới bằng Aspose.Slides cho Java. Trong ví dụ này, chúng ta sẽ tạo một bản trình bày trống.

```java
// Tên tệp xuất ra
String resultPath = "your_output_path/pres.ppt"; // Thay thế "your_output_path" bằng thư mục đầu ra mong muốn của bạn.
Presentation pres = new Presentation();
```

Trong đoạn mã trên, chúng ta xác định đường dẫn cho tệp trình bày đầu ra và tạo một tệp mới`Presentation` sự vật.

## Bước 2: Đặt thư mục gốc ClsId

 Để đặt ClsId thư mục gốc, bạn cần tạo một phiên bản của`PptOptions` và đặt CLSID mong muốn. CLSID đại diện cho ứng dụng sẽ được sử dụng làm thư mục gốc khi siêu liên kết được kích hoạt.

```java
PptOptions pptOptions = new PptOptions();
// Đặt CLSID thành 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 Trong đoạn mã trên, chúng ta tạo một`PptOptions` đối tượng và đặt CLSID thành 'Microsoft Powerpoint.Show.8'. Bạn có thể thay thế nó bằng CLSID của ứng dụng bạn muốn sử dụng làm thư mục gốc.

## Bước 3: Lưu bài thuyết trình

Bây giờ, hãy lưu bài thuyết trình với bộ Root Directory ClsId.

```java
// Lưu bản trình bày
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 Ở bước này, chúng ta lưu bản trình bày vào vị trí đã chỉ định`resultPath` với`PptOptions` chúng tôi đã tạo trước đó.

## Bước 4: Dọn dẹp

 Đừng quên vứt bỏ`Presentation` phản đối việc giải phóng mọi tài nguyên được phân bổ.

```java
if (pres != null) {
    pres.dispose();
}
```

## Mã nguồn hoàn chỉnh cho thư mục gốc ClsId trong Java Slides

```java
// Tên tệp xuất ra
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//đặt CLSID thành 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Lưu bản trình bày
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Bạn đã đặt thành công ClsId thư mục gốc trong Aspose.Slides cho Java. Điều này cho phép bạn chỉ định ứng dụng sẽ được sử dụng làm thư mục gốc khi siêu liên kết được kích hoạt trong bản trình bày của bạn. Bạn có thể tùy chỉnh CLSID theo yêu cầu cụ thể của mình.

## Câu hỏi thường gặp

### Làm cách nào để tìm CLSID cho một ứng dụng cụ thể?

Để tìm CLSID cho một ứng dụng cụ thể, bạn có thể tham khảo tài liệu hoặc tài nguyên do nhà phát triển ứng dụng cung cấp. CLSID là số nhận dạng duy nhất được gán cho các đối tượng COM và thường dành riêng cho từng ứng dụng.

### Tôi có thể đặt CLSID tùy chỉnh cho thư mục gốc không?

 Có, bạn có thể đặt CLSID tùy chỉnh cho thư mục gốc bằng cách chỉ định giá trị CLSID mong muốn bằng cách sử dụng`setRootDirectoryClsid` phương thức, như được hiển thị trong ví dụ mã. Điều này cho phép bạn sử dụng một ứng dụng cụ thể làm thư mục gốc khi siêu liên kết được kích hoạt trong bản trình bày của bạn.

### Điều gì xảy ra nếu tôi không đặt ClsId Thư mục gốc?

Nếu bạn không đặt ClsId thư mục gốc thì hành vi mặc định sẽ phụ thuộc vào trình xem hoặc ứng dụng được sử dụng để mở bản trình bày. Nó có thể sử dụng ứng dụng mặc định của chính nó làm thư mục gốc khi siêu liên kết được kích hoạt.

### Tôi có thể thay đổi ClsId thư mục gốc cho các siêu liên kết riêng lẻ không?

Không, ClsId thư mục gốc thường được đặt ở cấp bản trình bày và áp dụng cho tất cả các siêu liên kết trong bản trình bày. Nếu bạn cần chỉ định các ứng dụng khác nhau cho các siêu kết nối riêng lẻ, bạn có thể cần phải xử lý các siêu kết nối đó một cách riêng biệt trong mã của mình.

### Có bất kỳ hạn chế nào đối với CLSID mà tôi có thể sử dụng không?

CLSID bạn có thể sử dụng thường được xác định bởi các ứng dụng được cài đặt trên hệ thống. Bạn nên sử dụng CLSID tương ứng với các ứng dụng hợp lệ có khả năng xử lý siêu liên kết. Xin lưu ý rằng việc sử dụng CLSID không hợp lệ có thể dẫn đến hành vi không mong muốn.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
