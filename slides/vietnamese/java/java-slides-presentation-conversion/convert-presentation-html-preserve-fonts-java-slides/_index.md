---
"description": "Chuyển đổi bản trình bày PowerPoint sang HTML trong khi vẫn giữ nguyên phông chữ gốc bằng Aspose.Slides cho Java."
"linktitle": "Chuyển đổi bài thuyết trình sang HTML bằng cách giữ nguyên phông chữ gốc trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Chuyển đổi bài thuyết trình sang HTML bằng cách giữ nguyên phông chữ gốc trong Java Slides"
"url": "/vi/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi bài thuyết trình sang HTML bằng cách giữ nguyên phông chữ gốc trong Java Slides


## Giới thiệu về Chuyển đổi Bài thuyết trình sang HTML với việc Giữ nguyên Phông chữ Gốc trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách chuyển đổi bản trình bày PowerPoint (PPTX) sang HTML trong khi vẫn giữ nguyên phông chữ gốc bằng Aspose.Slides for Java. Điều này sẽ đảm bảo rằng HTML kết quả giống với giao diện của bản trình bày gốc.

## Bước 1: Thiết lập dự án
Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn đã thiết lập xong các bước cần thiết:

1. Tải xuống Aspose.Slides cho Java: Nếu bạn chưa tải xuống, hãy tải xuống và đưa thư viện Aspose.Slides cho Java vào dự án của bạn.

2. Tạo một dự án Java: Thiết lập một dự án Java trong IDE yêu thích của bạn và đảm bảo rằng bạn có thư mục "lib" nơi bạn có thể đặt tệp JAR Aspose.Slides.

3. Nhập các lớp bắt buộc: Nhập các lớp cần thiết vào đầu tệp Java của bạn:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Bước 2: Chuyển đổi bài thuyết trình sang HTML với phông chữ gốc

Bây giờ, chúng ta hãy chuyển đổi bản trình bày PowerPoint sang HTML trong khi vẫn giữ nguyên phông chữ gốc:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Tải bài thuyết trình
Presentation pres = new Presentation("input.pptx");

try {
    // Loại trừ các phông chữ trình bày mặc định như Calibri và Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Tạo tùy chọn HTML và thiết lập định dạng HTML tùy chỉnh
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Lưu bản trình bày dưới dạng HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Loại bỏ đối tượng trình bày
    if (pres != null) pres.dispose();
}
```

Trong đoạn mã này:

- Chúng tôi tải bản trình bày PowerPoint đầu vào bằng cách sử dụng `Presentation`.

- Chúng tôi xác định một danh sách các phông chữ (`fontNameExcludeList`) mà chúng ta muốn loại trừ khỏi việc nhúng trong HTML. Điều này hữu ích để loại trừ các phông chữ phổ biến như Calibri và Arial để giảm kích thước tệp.

- Chúng tôi tạo ra một trường hợp của `EmbedAllFontsHtmlController` và truyền danh sách loại trừ phông chữ cho nó.

- Chúng tôi tạo ra `HtmlOptions` và thiết lập một trình định dạng HTML tùy chỉnh bằng cách sử dụng `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Cuối cùng, chúng ta lưu bản trình bày dưới dạng HTML với các tùy chọn đã chỉ định.

## Mã nguồn đầy đủ để chuyển đổi bài thuyết trình sang HTML với việc giữ nguyên phông chữ gốc trong Java Slides

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

Trong hướng dẫn này, bạn đã học cách chuyển đổi bản trình bày PowerPoint sang HTML trong khi vẫn giữ nguyên phông chữ gốc bằng Aspose.Slides for Java. Điều này hữu ích khi bạn muốn duy trì độ trung thực về mặt hình ảnh của bản trình bày khi chia sẻ chúng trên web.

## Câu hỏi thường gặp

### Làm thế nào để tải xuống Aspose.Slides cho Java?

Bạn có thể tải xuống Aspose.Slides cho Java từ trang web Aspose. Truy cập [đây](https://downloads.aspose.com/slides/java/) để có phiên bản mới nhất.

### Tôi có thể tùy chỉnh danh sách phông chữ bị loại trừ không?

Có, bạn có thể tùy chỉnh `fontNameExcludeList` mảng để bao gồm hoặc loại trừ các phông chữ cụ thể theo yêu cầu của bạn.

### Phương pháp này có hiệu quả với các định dạng PowerPoint cũ hơn như PPT không?

Ví dụ mã này được thiết kế cho các tệp PPTX. Nếu bạn cần chuyển đổi các tệp PPT cũ hơn, bạn có thể cần điều chỉnh mã.

### Tôi có thể tùy chỉnh thêm đầu ra HTML như thế nào?

Bạn có thể khám phá `HtmlOptions` lớp để tùy chỉnh nhiều khía cạnh khác nhau của đầu ra HTML, chẳng hạn như kích thước slide, chất lượng hình ảnh, v.v.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}