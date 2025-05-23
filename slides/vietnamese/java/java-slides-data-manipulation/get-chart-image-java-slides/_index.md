---
"description": "Tìm hiểu cách lấy hình ảnh biểu đồ trong Java Slides bằng Aspose.Slides for Java. Hướng dẫn từng bước này cung cấp mã nguồn và mẹo để tích hợp liền mạch."
"linktitle": "Lấy hình ảnh biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lấy hình ảnh biểu đồ trong Java Slides"
"url": "/vi/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lấy hình ảnh biểu đồ trong Java Slides


## Giới thiệu về Get Chart Image trong Java Slides

Aspose.Slides for Java là một thư viện mạnh mẽ cho phép bạn làm việc với các bài thuyết trình PowerPoint theo chương trình. Với thư viện này, bạn có thể tạo, thao tác và trích xuất nhiều thành phần khác nhau từ các bài thuyết trình, bao gồm cả biểu đồ. Một yêu cầu chung là lấy hình ảnh biểu đồ từ các slide và chúng tôi sẽ trình bày cách thực hiện điều đó trong hướng dẫn này.

## Điều kiện tiên quyết

Trước khi tìm hiểu sâu hơn về mã, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides for Java đã được tải xuống và cấu hình trong dự án của bạn. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Thiết lập dự án của bạn

Bắt đầu bằng cách tạo một dự án Java trong Môi trường phát triển tích hợp (IDE) ưa thích của bạn. Đảm bảo rằng bạn đã thêm thư viện Aspose.Slides for Java vào các phụ thuộc của dự án.

## Bước 2: Khởi tạo bài thuyết trình

Để bắt đầu, bạn cần khởi tạo một bản trình bày PowerPoint. Trong ví dụ này, chúng tôi giả sử bạn có một tệp PowerPoint có tên "test.pptx" trong thư mục tài liệu của bạn.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Bước 3: Thêm biểu đồ và lấy hình ảnh

Tiếp theo, bạn có thể thêm biểu đồ vào slide và lấy hình ảnh của nó. Trong ví dụ này, chúng ta sẽ thêm biểu đồ cột nhóm.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

Trong đoạn mã này, chúng tôi tạo một biểu đồ cột nhóm trên trang trình bày đầu tiên của bản trình bày và sau đó lấy hình ảnh thu nhỏ của nó. Hình ảnh được lưu dưới dạng "image.png" trong thư mục đã chỉ định.

## Mã nguồn đầy đủ để lấy hình ảnh biểu đồ trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Việc lấy hình ảnh biểu đồ từ Java Slides bằng Aspose.Slides for Java là một quá trình đơn giản. Với mã được cung cấp, bạn có thể dễ dàng tích hợp chức năng này vào các ứng dụng Java của mình, cho phép bạn làm việc hiệu quả với các bài thuyết trình PowerPoint.

## Câu hỏi thường gặp

### Làm thế nào để cài đặt Aspose.Slides cho Java?

Cài đặt Aspose.Slides cho Java rất đơn giản. Bạn có thể tải xuống thư viện từ [đây](https://releases.aspose.com/slides/java/) và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu.

### Tôi có thể tùy chỉnh biểu đồ trước khi lấy hình ảnh không?

Có, bạn có thể tùy chỉnh giao diện, dữ liệu và các thuộc tính khác của biểu đồ trước khi lấy hình ảnh của biểu đồ. Aspose.Slides for Java cung cấp nhiều tùy chọn để tùy chỉnh biểu đồ.

### Aspose.Slides for Java còn cung cấp những tính năng nào khác?

Aspose.Slides for Java cung cấp nhiều tính năng để làm việc với các bài thuyết trình PowerPoint, bao gồm tạo slide, chỉnh sửa văn bản, chỉnh sửa hình dạng và nhiều tính năng khác. Bạn có thể khám phá tài liệu để biết thông tin chi tiết.

### Aspose.Slides for Java có phù hợp để sử dụng cho mục đích thương mại không?

Có, Aspose.Slides for Java có thể được sử dụng cho mục đích thương mại. Nó cung cấp các tùy chọn cấp phép phục vụ cho cả nhà phát triển cá nhân và doanh nghiệp.

### Tôi có thể lưu hình ảnh biểu đồ ở định dạng khác không?

Chắc chắn rồi! Bạn có thể lưu hình ảnh biểu đồ ở nhiều định dạng khác nhau, chẳng hạn như JPEG hoặc GIF, bằng cách chỉ định phần mở rộng tệp thích hợp trong `ImageIO.write` phương pháp.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}