---
title: Thêm siêu liên kết vào trang trình bày trong .NET bằng Aspose.Slides
linktitle: Thêm siêu liên kết vào slide
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách thêm siêu liên kết vào trang chiếu PowerPoint bằng Aspose.Slides cho .NET. Nâng cao bài thuyết trình của bạn với các yếu tố tương tác.
type: docs
weight: 12
url: /vi/net/hyperlink-manipulation/add-hyperlink/
---

Trong thế giới thuyết trình kỹ thuật số, tính tương tác là chìa khóa. Việc thêm siêu liên kết vào trang chiếu của bạn có thể làm cho bản trình bày của bạn hấp dẫn và nhiều thông tin hơn. Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép bạn tạo, sửa đổi và thao tác với các bản trình bày PowerPoint theo chương trình. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách thêm siêu liên kết vào các trang trình bày của bạn bằng Aspose.Slides cho .NET. 

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào việc thêm siêu liên kết vào trang chiếu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Visual Studio: Bạn nên cài đặt Visual Studio trên máy tính của mình để viết và thực thi mã .NET.

2. Aspose.Slides cho .NET: Bạn cần cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/net/).

3. Kiến thức C# cơ bản: Làm quen với lập trình C# sẽ có lợi.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Trong trường hợp này, bạn sẽ cần có các không gian tên sau từ thư viện Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Bây giờ, hãy chia nhỏ quá trình thêm siêu liên kết vào slide thành nhiều bước.

## Bước 1: Khởi tạo bản trình bày

Đầu tiên, tạo một bản trình bày mới bằng Aspose.Slides. Đây là cách bạn có thể làm điều đó:

```csharp
using (Presentation presentation = new Presentation())
{
    // Mã của bạn ở đây
}
```

Mã này khởi tạo một bản trình bày PowerPoint mới.

## Bước 2: Thêm khung văn bản

Bây giờ, hãy thêm khung văn bản vào slide của bạn. Khung văn bản này sẽ đóng vai trò là thành phần có thể nhấp vào trong slide của bạn. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Đoạn mã trên tạo hình tự động hình chữ nhật và thêm khung văn bản có dòng chữ "Aspose: File Format APIs".

## Bước 3: Thêm siêu liên kết

Tiếp theo, hãy thêm siêu liên kết vào khung văn bản bạn đã tạo. Điều này sẽ làm cho văn bản có thể nhấp được.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

Trong bước này, chúng tôi đặt URL siêu liên kết thành "https://www.aspose.com/" và cung cấp chú giải công cụ để biết thêm thông tin. Bạn cũng có thể định dạng hình thức của siêu kết nối như minh họa ở trên.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày của bạn với siêu liên kết được thêm vào.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Mã này lưu bản trình bày dưới dạng "trình bày-out.pptx."

Bây giờ, bạn đã thêm thành công siêu liên kết vào slide bằng Aspose.Slides for .NET.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách thêm siêu liên kết vào các trang chiếu trong bản trình bày PowerPoint bằng Aspose.Slides cho .NET. Bằng cách làm theo các bước này, bạn có thể làm cho bản trình bày của mình trở nên tương tác và hấp dẫn hơn, cung cấp các liên kết có giá trị đến các tài nguyên hoặc thông tin bổ sung.

 Để biết thêm thông tin chi tiết và tài liệu, hãy truy cập[Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/).

## Câu hỏi thường gặp

### 1. Tôi có thể thêm siêu liên kết vào các hình dạng khác ngoài khung văn bản không?

Có, bạn có thể thêm siêu liên kết vào nhiều hình dạng khác nhau như hình chữ nhật, hình ảnh, v.v. bằng cách sử dụng Aspose.Slides for .NET.

### 2. Làm cách nào để xóa siêu liên kết khỏi hình trong slide PowerPoint?

 Bạn có thể xóa siêu kết nối khỏi hình bằng cách đặt`HyperlinkClick` tài sản để`null`.

### 3. Tôi có thể thay đổi động URL siêu liên kết trong mã của mình không?

 Tuyệt đối! Bạn có thể cập nhật URL của siêu liên kết tại bất kỳ điểm nào trong mã của mình bằng cách sửa đổi thuộc tính`Hyperlink` tài sản.

### 4. Tôi có thể thêm những yếu tố tương tác nào khác vào trang chiếu PowerPoint bằng Aspose.Slides?

Aspose.Slides cung cấp nhiều tính năng tương tác, bao gồm các nút hành động, thành phần đa phương tiện và hình động.

### 5. Aspose.Slides có sẵn cho các ngôn ngữ lập trình khác không?

Có, Aspose.Slides có sẵn cho nhiều ngôn ngữ lập trình khác nhau, bao gồm Java và Python.