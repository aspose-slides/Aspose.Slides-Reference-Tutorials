---
title: Đặt phông chữ dự phòng trong Java PowerPoint
linktitle: Đặt phông chữ dự phòng trong Java PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt dự phòng phông chữ trong Java PowerPoint bằng Aspose.Slides cho Java để đảm bảo hiển thị văn bản nhất quán.
type: docs
weight: 16
url: /vi/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào sự phức tạp của việc thiết lập phông chữ dự phòng trong bản trình bày Java PowerPoint bằng Aspose.Slides cho Java. Dự phòng phông chữ rất quan trọng để đảm bảo rằng văn bản trong bản trình bày của bạn hiển thị chính xác trên các thiết bị và hệ điều hành khác nhau, ngay cả khi không có sẵn phông chữ được yêu cầu.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).
- Hiểu biết cơ bản về ngôn ngữ lập trình Java.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.

## Gói nhập khẩu
Trước tiên, hãy đưa các gói Aspose.Slides for Java cần thiết vào lớp Java của bạn:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Bước 1: Khởi tạo quy tắc dự phòng phông chữ
Để đặt phông chữ dự phòng, bạn cần xác định các quy tắc chỉ định phạm vi Unicode và phông chữ dự phòng tương ứng. Đây là cách bạn có thể khởi tạo các quy tắc này:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Bước 2: Áp dụng quy tắc dự phòng phông chữ
Tiếp theo, bạn áp dụng các quy tắc này cho bản trình bày hoặc trang chiếu nơi cần đặt phông chữ dự phòng. Dưới đây là ví dụ về việc áp dụng các quy tắc này cho một slide trong bản trình bày PowerPoint:
```java
// Giả sử slide là đối tượng Slide của bạn
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Phần kết luận
Đặt phông chữ dự phòng trong bản trình bày Java PowerPoint bằng Aspose.Slides cho Java là điều cần thiết để đảm bảo hiển thị văn bản nhất quán trên các môi trường khác nhau. Bằng cách xác định các quy tắc dự phòng như được minh họa trong hướng dẫn này, bạn có thể xử lý các tình huống không có phông chữ cụ thể, duy trì tính toàn vẹn của bản trình bày của bạn.

## Câu hỏi thường gặp
### Phông chữ dự phòng trong bản trình bày PowerPoint là gì?
Dự phòng phông chữ đảm bảo rằng văn bản hiển thị chính xác bằng cách thay thế các phông chữ có sẵn cho những phông chữ chưa được cài đặt.
### Làm cách nào tôi có thể tải xuống Aspose.Slides cho Java?
 Bạn có thể tải xuống Aspose.Slides cho Java từ[đây](https://releases.aspose.com/slides/java/).
### Aspose.Slides cho Java có tương thích với tất cả các IDE Java không?
Có, Aspose.Slides cho Java tương thích với các IDE Java phổ biến như IntelliJ IDEA và Eclipse.
### Tôi có thể nhận giấy phép tạm thời cho các sản phẩm Aspose không?
Có, bạn có thể lấy giấy phép tạm thời cho các sản phẩm Aspose từ[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Để được hỗ trợ liên quan đến Aspose.Slides cho Java, hãy truy cập[diễn đàn giả định](https://forum.aspose.com/c/slides/11).