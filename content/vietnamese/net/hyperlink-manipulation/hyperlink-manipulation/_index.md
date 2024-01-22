---
title: Thao tác siêu liên kết trong Aspose.Slides
linktitle: Thao tác siêu liên kết trong Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách thêm và xóa siêu liên kết trong Aspose.Slides cho .NET. Dễ dàng nâng cao bài thuyết trình của bạn bằng các liên kết tương tác.
type: docs
weight: 10
url: /vi/net/hyperlink-manipulation/hyperlink-manipulation/
---

Siêu liên kết là thành phần thiết yếu trong bản trình bày vì chúng cung cấp một cách thuận tiện để điều hướng giữa các trang chiếu hoặc truy cập các tài nguyên bên ngoài. Aspose.Slides for .NET cung cấp các tính năng mạnh mẽ để thêm và xóa siêu liên kết trong các trang trình bày của bạn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thao tác siêu liên kết bằng Aspose.Slides cho .NET. Chúng tôi sẽ đề cập đến việc thêm siêu liên kết vào một trang chiếu và xóa siêu liên kết khỏi một trang chiếu. Vì vậy, hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Slides for .NET: Bạn phải cài đặt và thiết lập thư viện Aspose.Slides for .NET. Bạn có thể tìm thấy tài liệu[đây](https://reference.aspose.com/slides/net/) và tải nó xuống từ[liên kết này](https://releases.aspose.com/slides/net/).

2. Thư mục tài liệu của bạn: Bạn cần một thư mục nơi bạn sẽ lưu trữ các tệp trình bày của mình. Đảm bảo chỉ định đường dẫn đến thư mục này trong mã của bạn.

3. Kiến thức cơ bản về C#: Hướng dẫn này giả sử bạn có hiểu biết cơ bản về lập trình C#.

Bây giờ bạn đã có sẵn các điều kiện tiên quyết, hãy chuyển sang hướng dẫn từng bước về thao tác siêu liên kết bằng Aspose.Slides cho .NET.

## Thêm siêu liên kết vào một slide

### Bước 1: Khởi tạo bản trình bày

Để bắt đầu, bạn cần khởi tạo bản trình bày bằng Aspose.Slides. Bạn có thể làm điều này với đoạn mã sau:

```csharp
using (Presentation presentation = new Presentation())
{
    // Mã của bạn ở đây
}
```

### Bước 2: Thêm khung văn bản

Bây giờ, hãy thêm khung văn bản vào slide. Mã này tạo một hình chữ nhật có văn bản:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Bước 3: Thêm siêu liên kết

Tiếp theo, bạn sẽ thêm siêu liên kết vào văn bản theo hình dạng bạn đã tạo. Đây là cách bạn có thể làm điều đó:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày của bạn với siêu liên kết được thêm vào:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Chúc mừng! Bạn đã thêm thành công siêu liên kết vào trang chiếu bằng Aspose.Slides for .NET.

## Loại bỏ siêu liên kết khỏi một slide

### Bước 1: Khởi tạo bản trình bày

Để xóa siêu liên kết khỏi slide, bạn cần mở bản trình bày hiện có:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Bước 2: Xóa siêu liên kết

Bây giờ, xóa tất cả các siêu liên kết khỏi bản trình bày bằng mã sau:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Bước 3: Lưu bài thuyết trình

Sau khi loại bỏ các siêu liên kết, hãy lưu bản trình bày:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Và thế là xong! Bạn đã loại bỏ thành công các siêu liên kết khỏi một trang trình bày bằng Aspose.Slides for .NET.

Tóm lại, Aspose.Slides for .NET cung cấp một cách hiệu quả để thao tác các siêu liên kết trong bản trình bày của bạn, cho phép bạn tạo các trang trình bày tương tác và hấp dẫn. Cho dù bạn muốn thêm siêu liên kết vào tài nguyên bên ngoài hay xóa chúng, Aspose.Slides sẽ đơn giản hóa quy trình và nâng cao khả năng xây dựng bản trình bày của bạn.

 Cảm ơn bạn đã tham gia cùng chúng tôi trong hướng dẫn này về thao tác siêu liên kết trong Aspose.Slides cho .NET. Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ thêm, vui lòng khám phá[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/) hoặc liên hệ với cộng đồng Aspose trên[diễn đàn hỗ trợ](https://forum.aspose.com/).

---

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thao tác với siêu liên kết trong bản trình bày bằng Aspose.Slides cho .NET. Chúng tôi đã đề cập đến cả việc thêm và loại bỏ các siêu liên kết, cho phép bạn tạo các bản trình bày năng động và tương tác. Aspose.Slides đơn giản hóa quy trình, giúp bạn dễ dàng nâng cao các trang trình bày của mình bằng các siêu liên kết đến các tài nguyên bên ngoài.

Bạn có thêm câu hỏi nào về cách làm việc với Aspose.Slides hoặc các khía cạnh khác của thiết kế bản trình bày không? Hãy xem phần Câu hỏi thường gặp bên dưới để biết thêm thông tin chi tiết.

## Câu hỏi thường gặp (Câu hỏi thường gặp)

### Ưu điểm chính của việc sử dụng Aspose.Slides cho .NET là gì?
Aspose.Slides for .NET cung cấp nhiều tính năng để tạo, thao tác và chuyển đổi bản trình bày. Nó cung cấp một bộ công cụ toàn diện để thêm nội dung, hình động và tương tác vào trang trình bày của bạn.

### Tôi có thể thêm siêu liên kết vào các đối tượng không phải văn bản trong Aspose.Slides không?
Có, Aspose.Slides cho phép bạn thêm siêu liên kết vào nhiều đối tượng khác nhau, bao gồm hình dạng, hình ảnh và văn bản, giúp bạn linh hoạt trong việc tạo bản trình bày tương tác.

### Aspose.Slides có tương thích với các định dạng tệp PowerPoint khác nhau không?
Tuyệt đối. Aspose.Slides hỗ trợ nhiều định dạng PowerPoint khác nhau, bao gồm PPT, PPTX, PPS, v.v. Nó đảm bảo khả năng tương thích với các phiên bản khác nhau của Microsoft PowerPoint.

### Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Slides ở đâu?
Để có tài liệu chuyên sâu và hỗ trợ cộng đồng, hãy truy cập[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/) và[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/).

### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides?
 Nếu bạn cần giấy phép tạm thời cho Aspose.Slides, bạn có thể lấy một giấy phép[đây](https://purchase.aspose.com/temporary-license/).