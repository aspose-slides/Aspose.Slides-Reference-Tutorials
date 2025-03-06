---
title: Đặt giá trị chiều cao phông chữ cục bộ trong PowerPoint bằng Java
linktitle: Đặt giá trị chiều cao phông chữ cục bộ trong PowerPoint bằng Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách điều chỉnh độ cao phông chữ trong bản trình bày PowerPoint bằng Java với Aspose.Slides. Dễ dàng nâng cao định dạng văn bản trong trang trình bày của bạn.
weight: 17
url: /vi/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt giá trị chiều cao phông chữ cục bộ trong PowerPoint bằng Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ tìm hiểu cách điều chỉnh độ cao phông chữ ở nhiều cấp độ khác nhau trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Kiểm soát kích thước phông chữ là rất quan trọng để tạo ra các bài thuyết trình có cấu trúc và hấp dẫn trực quan. Chúng ta sẽ xem qua các ví dụ từng bước để minh họa cách đặt chiều cao phông chữ cho các thành phần văn bản khác nhau.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/slides/java/).
- Hiểu biết cơ bản về lập trình Java và thuyết trình PowerPoint
## Gói nhập khẩu
Đảm bảo bao gồm các gói Aspose.Slides cần thiết trong tệp Java của bạn:
```java
import com.aspose.slides.*;
```
## Bước 1: Khởi tạo đối tượng trình bày
Đầu tiên, tạo một đối tượng trình bày PowerPoint mới:
```java
Presentation pres = new Presentation();
```
## Bước 2: Thêm hình dạng và khung văn bản
Thêm hình tự động có khung văn bản vào slide đầu tiên:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Bước 3: Tạo các phần văn bản
Xác định các phần văn bản có độ cao phông chữ khác nhau:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Bước 4: Đặt chiều cao phông chữ
Đặt chiều cao phông chữ ở các cấp độ khác nhau:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Bước 5: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi vào một tệp:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Hướng dẫn này đã trình bày cách điều chỉnh độ cao phông chữ trong các trang chiếu PowerPoint theo chương trình bằng cách sử dụng Aspose.Slides cho Java. Bằng cách điều chỉnh kích thước phông chữ ở các cấp độ khác nhau (toàn bộ bản trình bày, đoạn văn và phần), bạn có thể kiểm soát chính xác định dạng văn bản trong bản trình bày của mình.
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API mạnh mẽ để thao tác các bản trình bày PowerPoint theo chương trình.
### Tôi có thể tìm tài liệu về Aspose.Slides cho Java ở đâu?
 Bạn có thể tìm thấy tài liệu[đây](https://reference.aspose.com/slides/java/).
### Tôi có thể dùng thử Aspose.Slides cho Java trước khi mua không?
 Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Slides cho Java?
 Để được hỗ trợ, hãy truy cập[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Tôi có thể mua giấy phép Aspose.Slides cho Java ở đâu?
 Bạn có thể mua giấy phép[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
