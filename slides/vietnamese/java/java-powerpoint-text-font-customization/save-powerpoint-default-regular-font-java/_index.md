---
"description": "Tìm hiểu cách thao tác các bài thuyết trình PowerPoint theo chương trình bằng Aspose.Slides for Java. Nắm vững cách xử lý Java PowerPoint với hướng dẫn từng bước."
"linktitle": "Lưu PowerPoint với Phông chữ Thường mặc định bằng Java"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lưu PowerPoint với Phông chữ Thường mặc định bằng Java"
"url": "/vi/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lưu PowerPoint với Phông chữ Thường mặc định bằng Java

## Giới thiệu
Trong lĩnh vực phát triển Java, việc tạo và thao tác các bài thuyết trình PowerPoint theo chương trình có thể cải thiện đáng kể năng suất và các tùy chọn tùy chỉnh. Aspose.Slides for Java là một thư viện mạnh mẽ giúp các nhà phát triển xử lý hiệu quả các tệp PowerPoint, cung cấp một bộ tính năng toàn diện từ các sửa đổi đơn giản đến các bài thuyết trình phức tạp.
## Điều kiện tiên quyết
Trước khi bắt đầu sử dụng Aspose.Slides cho Java, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Aspose.Slides cho Java yêu cầu JDK 1.8 trở lên để hoạt động chính xác.
2. Aspose.Slides cho Java JAR: Tải xuống phiên bản mới nhất của Aspose.Slides cho Java từ [đây](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Sử dụng IntelliJ IDEA, Eclipse hoặc IDE Java khác mà bạn chọn.
4. Hiểu biết cơ bản về Java: Cần phải quen thuộc với những nguyên tắc cơ bản của ngôn ngữ lập trình Java.

## Nhập gói
Để bắt đầu sử dụng Aspose.Slides cho Java, hãy nhập các gói cần thiết:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Điều này đảm bảo rằng bạn có quyền truy cập vào tất cả các lớp và phương thức do Aspose.Slides for Java cung cấp.
## Bước 1: Thiết lập dự án của bạn
Đầu tiên, hãy tạo một dự án Java mới trong IDE của bạn và đưa tệp JAR Aspose.Slides for Java vào đường dẫn xây dựng của dự án.
## Bước 2: Khởi tạo đối tượng trình bày
Khởi tạo một `Presentation` đối tượng bằng cách tải tệp PowerPoint hiện có (.pptx) từ thư mục cục bộ của bạn.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Tải bài trình bày
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Thay thế `"Your Document Directory"` Và `"Your Output Directory"` với đường dẫn tệp thực tế của bạn.
## Bước 3: Lưu bài thuyết trình với phông chữ mặc định thông thường
Chỉ định phông chữ mặc định thông thường cho các định dạng đầu ra (HTML và PDF) bằng cách sử dụng `HtmlOptions` Và `PdfOptions` tương ứng.
```java
try {
    // Tùy chọn lưu HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Tùy chọn lưu PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Đảm bảo thay thế `"Arial Black"` Và `"Lucida Console"` với phông chữ mặc định thông thường mà bạn mong muốn.

## Phần kết luận
Bằng cách làm theo các bước này, bạn đã học cách thao tác các bài thuyết trình PowerPoint bằng Aspose.Slides for Java một cách hiệu quả. Khả năng này cho phép bạn tự động hóa các tác vụ, tùy chỉnh các bài thuyết trình và nâng cao các ứng dụng Java của bạn bằng các chức năng xử lý PowerPoint nâng cao.
## Câu hỏi thường gặp
### Aspose.Slides for Java có thể hoạt động với các phiên bản JDK cũ hơn không?
Aspose.Slides cho Java yêu cầu JDK 1.8 trở lên để tương thích.
### Làm thế nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides cho Java?
Bạn có thể xin giấy phép tạm thời từ [đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm tài liệu chi tiết hơn về Aspose.Slides cho Java ở đâu?
Khám phá tài liệu toàn diện [đây](https://reference.aspose.com/slides/java/).
### Có hỗ trợ cộng đồng nào dành cho Aspose.Slides for Java không?
Có, bạn có thể nhận được sự hỗ trợ của cộng đồng [đây](https://forum.aspose.com/c/slides/11).
### Tôi có thể dùng thử Aspose.Slides cho Java miễn phí không?
Có, hãy tải xuống phiên bản dùng thử miễn phí [đây](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}