---
title: Truy cập các định dạng bố cục trong Java Slides
linktitle: Truy cập các định dạng bố cục trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách truy cập và thao tác các định dạng bố cục trong Java Slides với Aspose.Slides for Java. Tùy chỉnh kiểu hình dạng và đường kẻ dễ dàng trong bản trình bày PowerPoint.
weight: 10
url: /vi/java/presentation-properties/access-layout-formats-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Truy cập các định dạng bố cục trong Java Slides


## Giới thiệu về Định dạng bố cục truy cập trong Trang trình bày Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách truy cập và làm việc với các định dạng bố cục trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Các định dạng bố cục cho phép bạn kiểm soát sự xuất hiện của các hình dạng và đường nét trong các trang trình bày bố cục của bản trình bày. Chúng tôi sẽ đề cập đến cách truy xuất các định dạng điền và định dạng dòng cho các hình dạng trên các trang chiếu bố cục.

## Điều kiện tiên quyết

1. Aspose.Slides cho thư viện Java.
2. Bản trình bày PowerPoint (định dạng PPTX) với các slide bố cục.

## Bước 1: Tải bài thuyết trình

 Đầu tiên chúng ta cần tải bản trình bày PowerPoint chứa các slide bố cục. Thay thế`"Your Document Directory"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Bước 2: Truy cập định dạng bố cục

Bây giờ, hãy duyệt qua các slide bố cục trong bản trình bày và truy cập các định dạng tô màu cũng như định dạng đường kẻ của các hình trên mỗi slide bố cục.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Truy cập các định dạng điền của hình dạng
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Định dạng dòng truy cập của hình dạng
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

Trong đoạn mã trên:

- Chúng tôi lặp lại từng slide bố cục bằng cách sử dụng một`for` vòng.
- Đối với mỗi slide bố cục, chúng ta tạo mảng để lưu trữ các định dạng tô màu và định dạng dòng cho các hình trên slide đó.
-  Chúng tôi sử dụng lồng nhau`for` các vòng lặp để lặp qua các hình dạng trên trang chiếu bố cục và truy xuất các định dạng đường kẻ và màu tô của chúng.

## Bước 3: Làm việc với định dạng bố cục

Bây giờ chúng ta đã truy cập vào các định dạng tô màu và định dạng đường kẻ cho các hình dạng trên các trang chiếu bố cục, bạn có thể thực hiện nhiều thao tác khác nhau trên chúng nếu cần. Ví dụ: bạn có thể thay đổi màu tô, kiểu đường kẻ hoặc các thuộc tính khác của hình dạng.

## Mã nguồn hoàn chỉnh cho các định dạng bố cục truy cập trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách truy cập và thao tác các định dạng bố cục trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Các định dạng bố cục rất cần thiết để kiểm soát sự xuất hiện của các hình dạng và đường nét trong các trang chiếu bố cục trong bản trình bày PowerPoint.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu tô của hình dạng?

 Để thay đổi màu tô của hình, bạn có thể sử dụng`IFillFormat`các phương thức của đối tượng. Đây là một ví dụ:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Đặt loại tô màu thành màu đồng nhất
fillFormat.getSolidFillColor().setColor(Color.RED); // Đặt màu tô thành màu đỏ
```

### Làm cách nào để thay đổi kiểu đường của hình dạng?

 Để thay đổi kiểu đường của một hình, bạn có thể sử dụng`ILineFormat`các phương thức của đối tượng. Đây là một ví dụ:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Đặt kiểu đường thành đơn
lineFormat.setWidth(2.0); // Đặt độ rộng đường thành 2,0 điểm
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Đặt màu đường thành màu xanh
```

### Làm cách nào để áp dụng những thay đổi này cho hình trên trang chiếu bố cục?

Để áp dụng những thay đổi này cho một hình dạng cụ thể trên một trang chiếu bố cục, bạn có thể truy cập hình dạng đó bằng cách sử dụng chỉ mục của nó trong bộ sưu tập hình dạng của trang chiếu bố cục. Ví dụ:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Truy cập hình dạng đầu tiên trên slide bố cục
```

 Sau đó bạn có thể sử dụng`IFillFormat` Và`ILineFormat` như được hiển thị trong các câu trả lời trước để sửa đổi định dạng đường kẻ và màu tô của hình dạng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
