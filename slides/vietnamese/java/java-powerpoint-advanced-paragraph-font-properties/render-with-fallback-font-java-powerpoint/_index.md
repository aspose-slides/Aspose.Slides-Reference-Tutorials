---
title: Kết xuất với phông chữ dự phòng trong Java PowerPoint
linktitle: Kết xuất với phông chữ dự phòng trong Java PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách hiển thị văn bản bằng phông chữ dự phòng trong bản trình bày Java PowerPoint bằng Aspose.Slides. Hãy làm theo hướng dẫn từng bước này để triển khai liền mạch.
weight: 13
url: /vi/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kết xuất với phông chữ dự phòng trong Java PowerPoint

## Giới thiệu
Việc tạo và thao tác các bản trình bày PowerPoint bằng Java có thể là một thách thức, nhưng với Aspose.Slides, bạn có thể thực hiện việc này một cách hiệu quả. Một tính năng quan trọng là khả năng hiển thị văn bản với phông chữ dự phòng. Bài viết này cung cấp hướng dẫn chi tiết từng bước về cách triển khai phông chữ dự phòng trong trang chiếu PowerPoint của bạn bằng Aspose.Slides cho Java.
## Điều kiện tiên quyết
Trước khi đi sâu vào triển khai, hãy đảm bảo bạn có mọi thứ mình cần:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Slides cho Java: Bạn có thể tải xuống từ[Trang tải xuống Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Một IDE như IntelliJ IDEA hoặc Eclipse sẽ giúp quá trình phát triển của bạn suôn sẻ hơn.
4. Phần phụ thuộc: Bao gồm Aspose.Slides trong phần phụ thuộc của dự án của bạn.
## Gói nhập khẩu
Đầu tiên, chúng ta cần nhập các gói cần thiết trong chương trình Java của mình.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Hãy chia nhỏ quy trình thành các bước có thể quản lý được.
## Bước 1: Thiết lập dự án của bạn
 Trước khi viết bất kỳ mã nào, hãy đảm bảo dự án của bạn được thiết lập chính xác. Điều này bao gồm việc thêm thư viện Aspose.Slides vào dự án của bạn. Bạn có thể làm điều này bằng cách tải xuống thư viện từ[Aspose.Slides cho Java](https://releases.aspose.com/slides/java/) và thêm nó vào đường dẫn xây dựng của bạn.
## Bước 2: Khởi tạo quy tắc dự phòng phông chữ
 Bạn cần tạo một thể hiện của`IFontFallBackRulesCollection` lớp và thêm quy tắc cho nó. Các quy tắc này xác định dự phòng phông chữ cho các phạm vi Unicode cụ thể.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một phiên bản mới của bộ sưu tập quy tắc
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Tạo một số quy tắc
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Bước 3: Sửa đổi quy tắc dự phòng
Trong bước này, chúng tôi sẽ sửa đổi quy tắc dự phòng bằng cách xóa phông chữ dự phòng hiện có và cập nhật quy tắc cho các phạm vi Unicode cụ thể.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Đang cố gắng xóa phông chữ FallBack "Tahoma" khỏi các quy tắc đã tải
    fallBackRule.remove("Tahoma");
    // Cập nhật quy tắc cho phạm vi được chỉ định
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Xóa mọi quy tắc hiện có khỏi danh sách
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Bước 4: Tải bài thuyết trình
Tải bản trình bày PowerPoint mà bạn muốn sửa đổi.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Bước 5: Gán quy tắc dự phòng cho bản trình bày
Gán các quy tắc dự phòng đã chuẩn bị sẵn cho trình quản lý phông chữ của bản trình bày.
```java
try {
    // Chỉ định danh sách quy tắc đã chuẩn bị để sử dụng
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Hiển thị hình thu nhỏ bằng bộ sưu tập quy tắc đã khởi tạo và lưu nó vào PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Bước 6: Lưu và kiểm tra
Cuối cùng, hãy lưu công việc của bạn và kiểm tra quá trình triển khai để đảm bảo mọi thứ hoạt động như mong đợi. Nếu bạn gặp bất kỳ vấn đề nào, hãy kiểm tra kỹ thiết lập của bạn và đảm bảo tất cả các phần phụ thuộc đều được thêm chính xác.
## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn có thể hiển thị văn bản có phông chữ dự phòng một cách hiệu quả trong bản trình bày PowerPoint của mình bằng Aspose.Slides cho Java. Quá trình này đảm bảo rằng bản trình bày của bạn duy trì định dạng nhất quán, ngay cả khi không có phông chữ chính. Chúc mừng mã hóa!
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides for Java là thư viện cho phép các nhà phát triển tạo, sửa đổi và hiển thị bản trình bày PowerPoint trong các ứng dụng Java.
### Làm cách nào để thêm Aspose.Slides vào dự án của tôi?
 Bạn có thể tải xuống thư viện từ[Trang tải xuống Aspose.Slides](https://releases.aspose.com/slides/java/) và thêm nó vào đường dẫn xây dựng dự án của bạn.
### Phông chữ dự phòng là gì?
Phông chữ dự phòng là phông chữ thay thế được sử dụng khi phông chữ được chỉ định không có sẵn hoặc không hỗ trợ một số ký tự nhất định.
### Tôi có thể sử dụng nhiều quy tắc dự phòng không?
Có, bạn có thể thêm nhiều quy tắc dự phòng để xử lý các phạm vi và phông chữ Unicode khác nhau.
### Tôi có thể nhận hỗ trợ cho Aspose.Slides ở đâu?
 Bạn có thể nhận được sự hỗ trợ từ[Diễn đàn hỗ trợ Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
