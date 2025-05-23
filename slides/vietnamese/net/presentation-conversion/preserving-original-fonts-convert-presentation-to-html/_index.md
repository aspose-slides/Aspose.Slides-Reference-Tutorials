---
"description": "Tìm hiểu cách giữ nguyên phông chữ gốc trong khi chuyển đổi bản trình bày sang HTML bằng Aspose.Slides cho .NET. Đảm bảo tính nhất quán của phông chữ và tác động trực quan một cách dễ dàng."
"linktitle": "Bảo tồn phông chữ gốc - Chuyển đổi bản trình bày sang HTML"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Bảo tồn phông chữ gốc - Chuyển đổi bản trình bày sang HTML"
"url": "/vi/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bảo tồn phông chữ gốc - Chuyển đổi bản trình bày sang HTML


Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình bảo toàn phông chữ gốc khi chuyển đổi bản trình bày sang HTML bằng Aspose.Slides for .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn C# cần thiết và giải thích chi tiết từng bước. Đến cuối hướng dẫn này, bạn sẽ có thể đảm bảo rằng phông chữ trong tài liệu HTML đã chuyển đổi của mình vẫn giữ nguyên bản trình bày gốc.

## 1. Giới thiệu

Khi chuyển đổi bản trình bày PowerPoint sang HTML, điều quan trọng là phải duy trì phông chữ gốc để đảm bảo tính nhất quán về mặt hình ảnh của nội dung. Aspose.Slides for .NET cung cấp giải pháp mạnh mẽ để đạt được điều này. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước cần thiết để duy trì phông chữ gốc trong quá trình chuyển đổi.

## 2. Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

- Visual Studio được cài đặt trên máy của bạn.
- Thư viện Aspose.Slides cho .NET đã được thêm vào dự án của bạn.

## 3. Thiết lập dự án của bạn

Để bắt đầu, hãy tạo một dự án mới trong Visual Studio và thêm thư viện Aspose.Slides cho .NET làm tài liệu tham khảo.

## 4. Tải bài thuyết trình

Sử dụng mã sau để tải bản trình bày PowerPoint của bạn:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Mã của bạn ở đây
}
```

Thay thế `"Your Document Directory"` với đường dẫn đến tệp trình bày của bạn.

## 5. Loại trừ phông chữ mặc định

Để loại trừ các phông chữ mặc định như Calibri và Arial, hãy sử dụng mã sau:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Bạn có thể tùy chỉnh danh sách này khi cần.

## 6. Nhúng tất cả phông chữ

Tiếp theo, chúng ta sẽ nhúng tất cả các phông chữ vào tài liệu HTML. Điều này đảm bảo rằng các phông chữ gốc được bảo toàn. Sử dụng mã sau:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Lưu dưới dạng HTML

Bây giờ, hãy lưu bản trình bày dưới dạng tài liệu HTML có nhúng phông chữ:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Thay thế `"output.html"` với tên tập tin đầu ra bạn mong muốn.

## 8. Kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách giữ nguyên phông chữ gốc khi chuyển đổi bản trình bày PowerPoint sang HTML bằng Aspose.Slides for .NET. Bằng cách làm theo các bước này, bạn có thể đảm bảo rằng tài liệu HTML đã chuyển đổi của mình vẫn giữ được tính toàn vẹn về mặt hình ảnh của bản trình bày gốc.

## 9. Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tùy chỉnh danh sách phông chữ bị loại trừ không?

Có, bạn có thể. Sửa đổi `fontNameExcludeList` mảng để bao gồm hoặc loại trừ các phông chữ cụ thể theo yêu cầu của bạn.

### Câu hỏi 2: Nếu tôi không muốn nhúng tất cả phông chữ thì sao?

Nếu bạn chỉ muốn nhúng các phông chữ cụ thể, bạn có thể sửa đổi mã cho phù hợp. Tham khảo tài liệu Aspose.Slides for .NET để biết thêm chi tiết.

### Câu hỏi 3: Có yêu cầu cấp phép nào khi sử dụng Aspose.Slides cho .NET không?

Có, bạn có thể cần giấy phép hợp lệ để sử dụng Aspose.Slides cho .NET trong các dự án của mình. Tham khảo trang web Aspose để biết thông tin cấp phép.

### Câu hỏi 4: Tôi có thể chuyển đổi các định dạng tệp khác sang HTML bằng Aspose.Slides cho .NET không?

Aspose.Slides for .NET chủ yếu tập trung vào các bài thuyết trình PowerPoint. Để chuyển đổi các định dạng tệp khác sang HTML, bạn có thể cần khám phá các sản phẩm Aspose khác được thiết kế riêng cho các định dạng đó.

### Câu hỏi 5: Tôi có thể truy cập các nguồn lực và hỗ trợ bổ sung ở đâu?

Bạn có thể tìm thêm tài liệu, hướng dẫn và hỗ trợ trên trang web Aspose. Truy cập [Aspose.Slides cho Tài liệu .NET](https://reference.aspose.com/slides/net/) để biết thông tin chi tiết.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}