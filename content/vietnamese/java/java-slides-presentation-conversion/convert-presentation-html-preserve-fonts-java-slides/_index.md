---
title: Chuyển đổi bản trình bày sang HTML với việc giữ nguyên phông chữ gốc trong trang trình bày Java
linktitle: Chuyển đổi bản trình bày sang HTML với việc giữ nguyên phông chữ gốc trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Chuyển đổi bản trình bày PowerPoint sang HTML trong khi vẫn giữ nguyên phông chữ gốc bằng Aspose.Slides cho Java.
type: docs
weight: 14
url: /vi/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Giới thiệu về Chuyển đổi bản trình bày sang HTML với việc giữ nguyên phông chữ gốc trong trang trình bày Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách chuyển đổi bản trình bày PowerPoint (PPTX) sang HTML trong khi vẫn giữ nguyên phông chữ gốc bằng Aspose.Slides cho Java. Điều này sẽ đảm bảo rằng HTML kết quả gần giống với hình thức của bản trình bày gốc.

## Bước 1: Thiết lập dự án
Trước khi đi sâu vào mã, hãy đảm bảo rằng bạn đã có sẵn thiết lập cần thiết:

1. Tải xuống Aspose.Slides cho Java: Nếu bạn chưa có, hãy tải xuống và đưa thư viện Aspose.Slides cho Java vào dự án của bạn.

2. Tạo một dự án Java: Thiết lập một dự án Java trong IDE yêu thích của bạn và đảm bảo bạn có thư mục "lib" nơi bạn có thể đặt tệp JAR Aspose.Slides.

3. Nhập các lớp bắt buộc: Nhập các lớp cần thiết ở đầu tệp Java của bạn:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Bước 2: Chuyển đổi bản trình bày sang HTML với phông chữ gốc

Bây giờ, hãy chuyển đổi bản trình bày PowerPoint sang HTML trong khi vẫn giữ nguyên phông chữ gốc:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Tải bản trình bày
Presentation pres = new Presentation("input.pptx");

try {
    // Loại trừ các phông chữ trình bày mặc định như Calibri và Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Tạo các tùy chọn HTML và đặt trình định dạng HTML tùy chỉnh
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Lưu bản trình bày dưới dạng HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Vứt bỏ đối tượng trình bày
    if (pres != null) pres.dispose();
}
```

Trong đoạn mã này:

-  Chúng tôi tải bản trình bày PowerPoint đầu vào bằng cách sử dụng`Presentation`.

- Chúng tôi xác định một danh sách các phông chữ (`fontNameExcludeList`mà chúng tôi muốn loại trừ khỏi việc nhúng vào HTML. Điều này hữu ích trong việc loại trừ các phông chữ phổ biến như Calibri và Arial để giảm kích thước tệp.

-  Chúng tôi tạo một thể hiện của`EmbedAllFontsHtmlController` và chuyển danh sách loại trừ phông chữ cho nó.

-  Chúng tôi tạo ra`HtmlOptions` và đặt trình định dạng HTML tùy chỉnh bằng cách sử dụng`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Cuối cùng, chúng tôi lưu bản trình bày dưới dạng HTML với các tùy chọn được chỉ định.

## Mã nguồn hoàn chỉnh để chuyển đổi bản trình bày sang HTML mà vẫn giữ nguyên phông chữ gốc trong trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// loại trừ phông chữ trình bày mặc định
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách chuyển đổi bản trình bày PowerPoint sang HTML trong khi vẫn giữ nguyên phông chữ gốc bằng Aspose.Slides cho Java. Điều này hữu ích khi bạn muốn duy trì độ trung thực trực quan của bản trình bày khi chia sẻ chúng trên web.

## Câu hỏi thường gặp

### Làm cách nào để tải xuống Aspose.Slides cho Java?

 Bạn có thể tải xuống Aspose.Slides cho Java từ trang web Aspose. Thăm nom[đây](https://downloads.aspose.com/slides/java/) để có được phiên bản mới nhất.

### Tôi có thể tùy chỉnh danh sách các phông chữ bị loại trừ không?

 Có, bạn có thể tùy chỉnh`fontNameExcludeList` array để bao gồm hoặc loại trừ các phông chữ cụ thể theo yêu cầu của bạn.

### Phương pháp này có hoạt động với các định dạng PowerPoint cũ hơn như PPT không?

Ví dụ mã này được thiết kế cho các tệp PPTX. Nếu bạn cần chuyển đổi các tệp PPT cũ hơn, bạn có thể cần phải điều chỉnh mã.

### Làm cách nào tôi có thể tùy chỉnh thêm đầu ra HTML?

 Bạn có thể khám phá`HtmlOptions` class để tùy chỉnh các khía cạnh khác nhau của đầu ra HTML, chẳng hạn như kích thước trang chiếu, chất lượng hình ảnh, v.v.