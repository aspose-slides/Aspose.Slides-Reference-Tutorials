---
title: Giữ nguyên phông chữ gốc - Chuyển đổi bản trình bày sang HTML
linktitle: Giữ nguyên phông chữ gốc - Chuyển đổi bản trình bày sang HTML
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách giữ nguyên phông chữ gốc trong khi chuyển đổi bản trình bày sang HTML bằng Aspose.Slides for .NET. Đảm bảo tính nhất quán của phông chữ và tác động trực quan một cách dễ dàng.
type: docs
weight: 14
url: /vi/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình giữ nguyên phông chữ gốc khi chuyển đổi bản trình bày sang HTML bằng Aspose.Slides cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn C# cần thiết và giải thích chi tiết từng bước. Đến cuối hướng dẫn này, bạn sẽ có thể đảm bảo rằng các phông chữ trong tài liệu HTML đã chuyển đổi của bạn vẫn trung thực với bản trình bày gốc.

## 1. Giới thiệu

Khi chuyển đổi bản trình bày PowerPoint sang HTML, điều quan trọng là phải duy trì phông chữ gốc để đảm bảo tính nhất quán về mặt hình ảnh cho nội dung của bạn. Aspose.Slides for .NET cung cấp một giải pháp mạnh mẽ để đạt được điều này. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước cần thiết để giữ nguyên phông chữ gốc trong quá trình chuyển đổi.

## 2. Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Visual Studio được cài đặt trên máy của bạn.
- Thư viện Aspose.Slides cho .NET đã được thêm vào dự án của bạn.

## 3. Thiết lập dự án của bạn

Để bắt đầu, hãy tạo một dự án mới trong Visual Studio và thêm thư viện Aspose.Slides cho .NET làm tài liệu tham khảo.

## 4. Tải bài thuyết trình

Sử dụng đoạn mã sau để tải bản trình bày PowerPoint của bạn:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Mã của bạn ở đây
}
```

 Thay thế`"Your Document Directory"` với đường dẫn đến tập tin trình bày của bạn.

## 5. Loại trừ phông chữ mặc định

Để loại trừ các phông chữ mặc định như Calibri và Arial, hãy sử dụng mã sau:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Bạn có thể tùy chỉnh danh sách này nếu cần.

## 6. Nhúng tất cả các phông chữ

Tiếp theo, chúng tôi sẽ nhúng tất cả các phông chữ vào tài liệu HTML. Điều này đảm bảo rằng các phông chữ gốc được giữ nguyên. Sử dụng mã sau đây:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Lưu dưới dạng HTML

Bây giờ, hãy lưu bản trình bày dưới dạng tài liệu HTML có phông chữ được nhúng:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Thay thế`"output.html"` với tên tệp đầu ra mong muốn của bạn.

## 8. Kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách giữ nguyên phông chữ gốc khi chuyển đổi bản trình bày PowerPoint sang HTML bằng Aspose.Slides cho .NET. Bằng cách làm theo các bước này, bạn có thể đảm bảo rằng tài liệu HTML đã chuyển đổi của mình duy trì tính toàn vẹn trực quan của bản trình bày gốc.

## 9. Câu hỏi thường gặp

### Q1: Tôi có thể tùy chỉnh danh sách các phông chữ bị loại trừ không?

 Vâng, bạn có thể. Sửa đổi`fontNameExcludeList` array để bao gồm hoặc loại trừ các phông chữ cụ thể theo yêu cầu của bạn.

### Câu hỏi 2: Nếu tôi không muốn nhúng tất cả phông chữ thì sao?

Nếu bạn chỉ muốn nhúng các phông chữ cụ thể, bạn có thể sửa đổi mã cho phù hợp. Tham khảo tài liệu Aspose.Slides for .NET để biết thêm chi tiết.

### Câu hỏi 3: Có bất kỳ yêu cầu cấp phép nào để sử dụng Aspose.Slides cho .NET không?

Có, bạn có thể cần giấy phép hợp lệ để sử dụng Aspose.Slides for .NET trong các dự án của mình. Tham khảo trang web Aspose để biết thông tin cấp phép.

### Câu hỏi 4: Tôi có thể chuyển đổi các định dạng tệp khác sang HTML bằng Aspose.Slides cho .NET không?

Aspose.Slides for .NET chủ yếu tập trung vào các bài thuyết trình PowerPoint. Để chuyển đổi các định dạng tệp khác sang HTML, bạn có thể cần khám phá các sản phẩm Aspose khác được thiết kế riêng cho các định dạng đó.

### Câu hỏi 5: Tôi có thể tiếp cận các tài nguyên và hỗ trợ bổ sung ở đâu?

 Bạn có thể tìm thêm tài liệu, hướng dẫn và hỗ trợ trên trang web Aspose. Thăm nom[Aspose.Slides cho Tài liệu .NET](https://reference.aspose.com/slides/net/) để biết thông tin chi tiết.
