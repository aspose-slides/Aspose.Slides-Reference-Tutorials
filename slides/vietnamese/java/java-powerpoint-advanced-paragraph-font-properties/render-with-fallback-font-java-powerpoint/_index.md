---
"description": "Tìm hiểu cách hiển thị văn bản với phông chữ dự phòng trong bản trình bày Java PowerPoint bằng Aspose.Slides. Làm theo hướng dẫn từng bước này để triển khai liền mạch."
"linktitle": "Kết xuất với Phông chữ Fallback trong Java PowerPoint"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Kết xuất với Phông chữ Fallback trong Java PowerPoint"
"url": "/vi/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Kết xuất với Phông chữ Fallback trong Java PowerPoint

## Giới thiệu
Việc tạo và thao tác các bài thuyết trình PowerPoint bằng Java có thể là một thách thức, nhưng với Aspose.Slides, bạn có thể thực hiện việc này một cách hiệu quả. Một tính năng quan trọng là khả năng hiển thị văn bản với phông chữ dự phòng. Bài viết này cung cấp hướng dẫn chi tiết từng bước về cách triển khai phông chữ dự phòng trong các slide PowerPoint của bạn bằng Aspose.Slides cho Java.
## Điều kiện tiên quyết
Trước khi bắt đầu triển khai, hãy đảm bảo rằng bạn có mọi thứ cần thiết:
1. Bộ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2. Aspose.Slides cho Java: Bạn có thể tải xuống từ [Trang tải xuống Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Một IDE như IntelliJ IDEA hoặc Eclipse sẽ giúp quá trình phát triển của bạn trở nên mượt mà hơn.
4. Phụ thuộc: Bao gồm Aspose.Slides vào phần phụ thuộc của dự án bạn.
## Nhập gói
Đầu tiên, chúng ta cần nhập các gói cần thiết vào chương trình Java của mình.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Hãy chia nhỏ quy trình thành các bước dễ quản lý hơn.
## Bước 1: Thiết lập dự án của bạn
Trước khi viết bất kỳ mã nào, hãy đảm bảo dự án của bạn được thiết lập đúng. Điều này bao gồm việc thêm thư viện Aspose.Slides vào dự án của bạn. Bạn có thể thực hiện việc này bằng cách tải xuống thư viện từ [Aspose.Slides cho Java](https://releases.aspose.com/slides/java/) và thêm nó vào đường dẫn xây dựng của bạn.
## Bước 2: Khởi tạo Quy tắc dự phòng phông chữ
Bạn cần tạo một phiên bản của `IFontFallBackRulesCollection` lớp và thêm các quy tắc vào đó. Các quy tắc này xác định các phông chữ dự phòng cho các phạm vi Unicode cụ thể.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một phiên bản mới của bộ sưu tập quy tắc
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Tạo một số quy tắc
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Bước 3: Sửa đổi Quy tắc dự phòng
Ở bước này, chúng tôi sẽ sửa đổi các quy tắc dự phòng bằng cách xóa các phông chữ dự phòng hiện có và cập nhật các quy tắc cho các phạm vi Unicode cụ thể.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Đang cố gắng xóa phông chữ FallBack "Tahoma" khỏi các quy tắc đã tải
    fallBackRule.remove("Tahoma");
    // Cập nhật các quy tắc cho phạm vi đã chỉ định
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// Xóa bất kỳ quy tắc hiện có nào khỏi danh sách
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Bước 4: Tải bài thuyết trình
Tải bản trình bày PowerPoint mà bạn muốn chỉnh sửa.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Bước 5: Gán Quy tắc dự phòng cho Bài thuyết trình
Gán các quy tắc dự phòng đã chuẩn bị cho trình quản lý phông chữ của bản trình bày.
```java
try {
    // Chỉ định danh sách các quy tắc đã chuẩn bị để sử dụng
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Hiển thị hình thu nhỏ bằng cách sử dụng bộ sưu tập quy tắc đã khởi tạo và lưu nó vào PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Bước 6: Lưu và Kiểm tra
Cuối cùng, hãy lưu công việc của bạn và kiểm tra việc triển khai để đảm bảo mọi thứ hoạt động như mong đợi. Nếu bạn gặp bất kỳ vấn đề nào, hãy kiểm tra lại thiết lập của bạn và đảm bảo tất cả các phụ thuộc được thêm chính xác.
## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn có thể hiển thị văn bản hiệu quả với phông chữ dự phòng trong bài thuyết trình PowerPoint của mình bằng Aspose.Slides for Java. Quy trình này đảm bảo rằng bài thuyết trình của bạn duy trì định dạng nhất quán, ngay cả khi phông chữ chính không khả dụng. Chúc bạn viết mã vui vẻ!
## Câu hỏi thường gặp
### Aspose.Slides for Java là gì?
Aspose.Slides for Java là một thư viện cho phép các nhà phát triển tạo, chỉnh sửa và hiển thị các bài thuyết trình PowerPoint trong các ứng dụng Java.
### Làm thế nào để thêm Aspose.Slides vào dự án của tôi?
Bạn có thể tải xuống thư viện từ [Trang tải xuống Aspose.Slides](https://releases.aspose.com/slides/java/) và thêm nó vào đường dẫn xây dựng dự án của bạn.
### Phông chữ dự phòng là gì?
Phông chữ dự phòng là phông chữ thay thế được sử dụng khi phông chữ được chỉ định không khả dụng hoặc không hỗ trợ một số ký tự nhất định.
### Tôi có thể sử dụng nhiều quy tắc dự phòng không?
Có, bạn có thể thêm nhiều quy tắc dự phòng để xử lý nhiều phông chữ và phạm vi Unicode khác nhau.
### Tôi có thể nhận hỗ trợ cho Aspose.Slides ở đâu?
Bạn có thể nhận được sự hỗ trợ từ [Diễn đàn hỗ trợ Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}