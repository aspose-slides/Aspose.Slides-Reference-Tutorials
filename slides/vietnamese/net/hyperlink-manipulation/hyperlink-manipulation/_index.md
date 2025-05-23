---
"description": "Tìm hiểu cách thêm và xóa siêu liên kết trong Aspose.Slides cho .NET. Nâng cao bài thuyết trình của bạn bằng các liên kết tương tác một cách dễ dàng."
"linktitle": "Thao tác siêu liên kết trong Aspose.Slides"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Thao tác siêu liên kết trong Aspose.Slides"
"url": "/vi/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thao tác siêu liên kết trong Aspose.Slides


Siêu liên kết là thành phần thiết yếu trong các bài thuyết trình, vì chúng cung cấp một cách thuận tiện để điều hướng giữa các slide hoặc truy cập các tài nguyên bên ngoài. Aspose.Slides for .NET cung cấp các tính năng mạnh mẽ để thêm và xóa siêu liên kết trong các slide thuyết trình của bạn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn qua quy trình thao tác siêu liên kết bằng Aspose.Slides for .NET. Chúng tôi sẽ đề cập đến việc thêm siêu liên kết vào slide và xóa siêu liên kết khỏi slide. Vậy, hãy cùng tìm hiểu nhé!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Aspose.Slides cho .NET: Bạn phải cài đặt và thiết lập thư viện Aspose.Slides cho .NET. Bạn có thể tìm thấy tài liệu [đây](https://reference.aspose.com/slides/net/) và tải xuống từ [liên kết này](https://releases.aspose.com/slides/net/).

2. Thư mục tài liệu của bạn: Bạn cần một thư mục nơi bạn sẽ lưu trữ các tệp trình bày của mình. Đảm bảo chỉ định đường dẫn đến thư mục này trong mã của bạn.

3. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn có hiểu biết cơ bản về lập trình C#.

Bây giờ bạn đã có đủ các điều kiện tiên quyết, chúng ta hãy chuyển sang hướng dẫn từng bước để thao tác siêu liên kết bằng Aspose.Slides cho .NET.

## Thêm siêu liên kết vào một slide

### Bước 1: Khởi tạo bài thuyết trình

Để bắt đầu, bạn cần khởi tạo một bài thuyết trình bằng Aspose.Slides. Bạn có thể thực hiện việc này bằng mã sau:

```csharp
using (Presentation presentation = new Presentation())
{
    // Mã của bạn ở đây
}
```

### Bước 2: Thêm Khung Văn Bản

Bây giờ, hãy thêm khung văn bản vào slide. Mã này tạo ra một hình chữ nhật có văn bản:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Bước 3: Thêm siêu liên kết

Tiếp theo, bạn sẽ thêm siêu liên kết vào văn bản trong hình dạng bạn đã tạo. Sau đây là cách bạn có thể thực hiện:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Bước 4: Lưu bài thuyết trình

Cuối cùng, hãy lưu bài thuyết trình của bạn bằng siêu liên kết đã thêm:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Xin chúc mừng! Bạn đã thêm thành công siêu liên kết vào slide bằng Aspose.Slides cho .NET.

## Xóa siêu liên kết khỏi trang chiếu

### Bước 1: Khởi tạo bài thuyết trình

Để xóa siêu liên kết khỏi trang chiếu, bạn cần mở bản trình bày hiện có:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Bước 2: Xóa siêu liên kết

Bây giờ, hãy xóa tất cả các siêu liên kết khỏi bản trình bày bằng cách sử dụng mã sau:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Bước 3: Lưu bài thuyết trình

Sau khi xóa các siêu liên kết, hãy lưu bản trình bày:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Và thế là xong! Bạn đã xóa thành công siêu liên kết khỏi slide bằng Aspose.Slides cho .NET.

Tóm lại, Aspose.Slides for .NET cung cấp một cách hiệu quả để thao tác siêu liên kết trong bài thuyết trình của bạn, cho phép bạn tạo các slide tương tác và hấp dẫn. Cho dù bạn muốn thêm siêu liên kết vào tài nguyên bên ngoài hay xóa chúng, Aspose.Slides đều đơn giản hóa quy trình và nâng cao khả năng xây dựng bài thuyết trình của bạn.

Cảm ơn bạn đã tham gia cùng chúng tôi trong hướng dẫn này về thao tác siêu liên kết trong Aspose.Slides cho .NET. Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ thêm, hãy thoải mái khám phá [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/) hoặc liên hệ với cộng đồng Aspose trên [diễn đàn hỗ trợ](https://forum.aspose.com/).

---

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thao tác siêu liên kết trong các bài thuyết trình bằng Aspose.Slides cho .NET. Chúng tôi đã đề cập đến cả việc thêm và xóa siêu liên kết, cho phép bạn tạo các bài thuyết trình động và tương tác. Aspose.Slides đơn giản hóa quy trình, giúp bạn dễ dàng cải thiện các slide của mình bằng siêu liên kết đến các tài nguyên bên ngoài.

Bạn có thắc mắc nào khác về cách sử dụng Aspose.Slides hoặc các khía cạnh khác của thiết kế bài thuyết trình không? Hãy xem Câu hỏi thường gặp bên dưới để biết thêm thông tin chi tiết.

## FAQ (Câu hỏi thường gặp)

### Những lợi thế chính của việc sử dụng Aspose.Slides cho .NET là gì?
Aspose.Slides for .NET cung cấp nhiều tính năng để tạo, chỉnh sửa và chuyển đổi bài thuyết trình. Nó cung cấp một bộ công cụ toàn diện để thêm nội dung, hoạt ảnh và tương tác vào slide của bạn.

### Tôi có thể thêm siêu liên kết vào các đối tượng khác ngoài văn bản trong Aspose.Slides không?
Có, Aspose.Slides cho phép bạn thêm siêu liên kết vào nhiều đối tượng khác nhau, bao gồm hình dạng, hình ảnh và văn bản, giúp bạn linh hoạt hơn khi tạo các bài thuyết trình tương tác.

### Aspose.Slides có tương thích với các định dạng tệp PowerPoint khác nhau không?
Hoàn toàn. Aspose.Slides hỗ trợ nhiều định dạng PowerPoint, bao gồm PPT, PPTX, PPS, v.v. Nó đảm bảo khả năng tương thích với các phiên bản khác nhau của Microsoft PowerPoint.

### Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Slides ở đâu?
Để biết thêm tài liệu chuyên sâu và hỗ trợ cộng đồng, hãy truy cập [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/) và [Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/).

### Làm thế nào tôi có thể xin được giấy phép tạm thời cho Aspose.Slides?
Nếu bạn cần giấy phép tạm thời cho Aspose.Slides, bạn có thể nhận được một giấy phép [đây](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}