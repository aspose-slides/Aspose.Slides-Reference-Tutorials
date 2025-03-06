---
title: Chuyển đổi bản trình bày sang HTML bằng phông chữ nhúng
linktitle: Chuyển đổi bản trình bày sang HTML bằng phông chữ nhúng
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Chuyển đổi bản trình bày PowerPoint sang HTML bằng phông chữ được nhúng bằng Aspose.Slides for .NET. Duy trì tính nguyên bản một cách liền mạch.
weight: 13
url: /vi/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi bản trình bày sang HTML bằng phông chữ nhúng


Trong thời đại kỹ thuật số ngày nay, việc chia sẻ bài thuyết trình và tài liệu trực tuyến đã trở thành một thói quen phổ biến. Tuy nhiên, một thách thức thường nảy sinh là đảm bảo phông chữ của bạn được hiển thị chính xác khi chuyển đổi bản trình bày sang HTML. Hướng dẫn từng bước này sẽ hướng dẫn bạn trong quá trình sử dụng Aspose.Slides for .NET để chuyển đổi bản trình bày sang HTML bằng phông chữ được nhúng, đảm bảo rằng tài liệu của bạn trông giống như bạn dự định.

## Giới thiệu về Aspose.Slides cho .NET

Trước khi đi sâu vào hướng dẫn, hãy giới thiệu ngắn gọn về Aspose.Slides cho .NET. Đây là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các bản trình bày PowerPoint trong các ứng dụng .NET. Với Aspose.Slides, bạn có thể tạo, sửa đổi và chuyển đổi tệp PowerPoint theo chương trình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Slides for .NET: Bạn nên cài đặt thư viện Aspose.Slides trong dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/net/).

## Bước 1: Thiết lập dự án của bạn

1. Tạo một dự án mới hoặc mở một dự án hiện có trong môi trường phát triển .NET ưa thích của bạn.

2. Thêm tham chiếu vào thư viện Aspose.Slides trong dự án của bạn.

3. Nhập các không gian tên cần thiết trong mã của bạn:

   ```csharp
   using Aspose.Slides;
   ```

## Bước 2: Tải bản trình bày của bạn

 Để bắt đầu, bạn cần tải bản trình bày mà bạn muốn chuyển đổi sang HTML. Thay thế`"Your Document Directory"` với thư mục thực nơi chứa tệp trình bày của bạn.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Mã của bạn ở đây
}
```

## Bước 3: Loại trừ phông chữ trình bày mặc định

Trong bước này, bạn có thể chỉ định bất kỳ phông chữ trình bày mặc định nào mà bạn muốn loại trừ khỏi việc nhúng. Điều này có thể giúp tối ưu hóa kích thước của tệp HTML kết quả.

```csharp
string[] fontNameExcludeList = { };
```

## Bước 4: Chọn Bộ điều khiển HTML

Bây giờ, bạn có hai tùy chọn để nhúng phông chữ vào HTML:

### Tùy chọn 1: Nhúng tất cả phông chữ

 Để nhúng tất cả các phông chữ được sử dụng trong bản trình bày, hãy sử dụng`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Tùy chọn 2: Liên kết tất cả các phông chữ

 Để liên kết tới tất cả các phông chữ được sử dụng trong bản trình bày, hãy sử dụng`LinkAllFontsHtmlController`. Bạn nên chỉ định thư mục chứa phông chữ trên hệ thống của bạn.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Bước 5: Xác định tùy chọn HTML

 Tạo ra một`HtmlOptions` đối tượng và đặt trình định dạng HTML thành trình định dạng bạn đã chọn ở bước trước.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Sử dụng embedFontsController để nhúng tất cả các phông chữ
};
```

## Bước 6: Lưu dưới dạng HTML

 Cuối cùng, lưu bản trình bày dưới dạng tệp HTML. Bạn có thể chọn một trong hai`SaveFormat.Html` hoặc`SaveFormat.Html5` tùy thuộc vào yêu cầu của bạn.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Phần kết luận

Chúc mừng! Bạn đã chuyển đổi thành công bản trình bày của mình sang HTML với các phông chữ được nhúng bằng Aspose.Slides for .NET. Điều này đảm bảo rằng phông chữ của bạn sẽ hiển thị chính xác khi chia sẻ bài thuyết trình của bạn trực tuyến.

Giờ đây, bạn có thể dễ dàng tự tin chia sẻ các bản trình bày được định dạng đẹp mắt của mình và biết rằng khán giả sẽ nhìn thấy chúng chính xác như bạn dự định.

 Để biết thêm thông tin và tài liệu tham khảo API chi tiết, hãy xem[Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/).

## Câu hỏi thường gặp

### 1. Tôi có thể chuyển đổi bản trình bày PowerPoint sang HTML bằng Aspose.Slides cho .NET ở chế độ hàng loạt không?

Có, bạn có thể chuyển đổi hàng loạt nhiều bản trình bày sang HTML bằng Aspose.Slides for .NET bằng cách lặp qua các tệp bản trình bày của bạn và áp dụng quy trình chuyển đổi cho từng tệp.

### 2. Có cách nào để tùy chỉnh giao diện của đầu ra HTML không?

Chắc chắn! Aspose.Slides for .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện và định dạng của đầu ra HTML, chẳng hạn như điều chỉnh màu sắc, phông chữ và bố cục.

### 3. Có bất kỳ hạn chế nào đối với việc nhúng phông chữ vào HTML bằng Aspose.Slides cho .NET không?

Mặc dù Aspose.Slides for .NET cung cấp khả năng nhúng phông chữ tuyệt vời nhưng hãy nhớ rằng kích thước tệp HTML của bạn có thể tăng lên khi nhúng phông chữ. Đảm bảo tối ưu hóa các lựa chọn phông chữ của bạn để sử dụng trên web.

### 4. Tôi có thể chuyển đổi bản trình bày PowerPoint sang các định dạng khác bằng Aspose.Slides cho .NET không?

Có, Aspose.Slides for .NET hỗ trợ nhiều định dạng đầu ra, bao gồm PDF, hình ảnh, v.v. Bạn có thể dễ dàng chuyển đổi bài thuyết trình của mình sang định dạng bạn chọn.

### 5. Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Slides cho .NET ở đâu?

 Bạn có thể truy cập vô số tài nguyên, bao gồm cả tài liệu, trên[Aspose.Slides cho tài liệu tham khảo API .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
