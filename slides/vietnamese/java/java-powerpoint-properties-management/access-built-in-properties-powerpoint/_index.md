---
"description": "Tìm hiểu cách truy cập các thuộc tính tích hợp trong PowerPoint bằng Aspose.Slides for Java. Hướng dẫn này hướng dẫn bạn cách lấy tác giả, ngày tạo và nhiều thông tin khác."
"linktitle": "Truy cập các thuộc tính tích hợp trong PowerPoint"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Truy cập các thuộc tính tích hợp trong PowerPoint"
"url": "/vi/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Truy cập các thuộc tính tích hợp trong PowerPoint

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách truy cập các thuộc tính tích hợp trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Aspose.Slides là một thư viện mạnh mẽ cho phép các nhà phát triển Java làm việc với các bản trình bày PowerPoint theo chương trình, cho phép các tác vụ như đọc và sửa đổi các thuộc tính một cách liền mạch.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng đủ các điều kiện tiên quyết sau:
1. Java Development Kit (JDK): Đảm bảo rằng bạn đã cài đặt JDK trên hệ thống của mình. Bạn có thể tải xuống từ [đây](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides cho Java: Tải xuống và cài đặt Aspose.Slides cho Java từ [liên kết này](https://releases.aspose.com/slides/java/).

## Nhập gói
Trước tiên, bạn cần nhập các gói cần thiết vào dự án Java của mình. Thêm câu lệnh import sau vào đầu tệp Java của bạn:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Bước 1: Thiết lập đối tượng trình bày
Bắt đầu bằng cách thiết lập đối tượng Presentation để đại diện cho bản trình bày PowerPoint mà bạn muốn làm việc. Sau đây là cách bạn có thể thực hiện:
```java
// Đường dẫn đến thư mục chứa tệp trình bày
String dataDir = "path_to_your_presentation_directory/";
// Khởi tạo lớp Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Bước 2: Truy cập Thuộc tính Tài liệu
Sau khi thiết lập đối tượng Presentation, bạn có thể truy cập các thuộc tính tích hợp của bản trình bày bằng giao diện IDocumentProperties. Sau đây là cách bạn có thể truy xuất các thuộc tính khác nhau:
### Loại
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Tình trạng hiện tại
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Ngày tạo
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Tác giả
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Sự miêu tả
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Từ khóa
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Lần sửa đổi cuối cùng bởi
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Người giám sát
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Ngày sửa đổi
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Định dạng trình bày
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Ngày in cuối cùng
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Chia sẻ giữa các nhà sản xuất
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Chủ thể
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Tiêu đề
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách truy cập các thuộc tính tích hợp trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bằng cách làm theo các bước được nêu ở trên, bạn có thể dễ dàng truy xuất nhiều thuộc tính khác nhau như tác giả, ngày tạo và tiêu đề theo chương trình.
## Câu hỏi thường gặp
### Tôi có thể sửa đổi các thuộc tính tích hợp này bằng Aspose.Slides cho Java không?
Có, bạn có thể sửa đổi các thuộc tính này bằng Aspose.Slides. Chỉ cần sử dụng các phương thức thiết lập thích hợp được cung cấp bởi giao diện IDocumentProperties.
### Aspose.Slides có tương thích với các phiên bản PowerPoint khác nhau không?
Aspose.Slides hỗ trợ nhiều phiên bản PowerPoint, đảm bảo khả năng tương thích trên nhiều nền tảng khác nhau.
### Tôi có thể lấy các thuộc tính tùy chỉnh không?
Có, bên cạnh các thuộc tính tích hợp, bạn cũng có thể truy xuất và sửa đổi các thuộc tính tùy chỉnh bằng Aspose.Slides cho Java.
### Aspose.Slides có cung cấp tài liệu và hỗ trợ không?
Có, bạn có thể tìm thấy tài liệu toàn diện và truy cập diễn đàn hỗ trợ trên [Trang web Aspose](https://reference.aspose.com/slides/java/).
### Có phiên bản dùng thử nào cho Aspose.Slides dành cho Java không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}