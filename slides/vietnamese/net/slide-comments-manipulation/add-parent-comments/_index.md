---
title: Thêm nhận xét của phụ huynh vào slide bằng Aspose.Slides
linktitle: Thêm nhận xét của phụ huynh vào slide
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách thêm nhận xét và câu trả lời tương tác vào bản trình bày PowerPoint của bạn bằng Aspose.Slides cho .NET. Tăng cường sự tham gia và hợp tác.
weight: 12
url: /vi/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Bạn đang tìm cách cải thiện bản trình bày PowerPoint của mình bằng các tính năng tương tác? Aspose.Slides for .NET cho phép bạn kết hợp các nhận xét và câu trả lời, tạo ra trải nghiệm năng động và hấp dẫn cho khán giả của bạn. Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách thêm nhận xét gốc vào trang trình bày bằng Aspose.Slides cho .NET. Hãy cùng tìm hiểu và khám phá tính năng thú vị này.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Slides for .NET: Đảm bảo rằng bạn đã cài đặt Aspose.Slides for .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/slides/net/).

2. Visual Studio: Bạn sẽ cần Visual Studio để tạo và chạy ứng dụng .NET của mình.

3. Kiến thức cơ bản về C#: Hướng dẫn này giả sử bạn có hiểu biết cơ bản về lập trình C#.

Bây giờ chúng ta đã có các điều kiện tiên quyết, hãy tiến hành nhập các không gian tên cần thiết.

## Nhập không gian tên

Trước tiên, bạn sẽ cần nhập các không gian tên có liên quan vào dự án của mình. Các không gian tên này cung cấp các lớp và phương thức cần thiết để làm việc với Aspose.Slides cho .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Với các điều kiện tiên quyết và không gian tên đã sẵn sàng, hãy chia quy trình thành nhiều bước để thêm nhận xét gốc vào trang chiếu.

## Bước 1: Tạo bản trình bày

Để bắt đầu, bạn cần tạo bản trình bày mới bằng Aspose.Slides cho .NET. Bản trình bày này sẽ là khung vẽ để bạn thêm nhận xét của mình.

```csharp
// Đường dẫn đến thư mục đầu ra.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Mã của bạn để thêm nhận xét sẽ xuất hiện ở đây.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 Trong đoạn mã trên, thay thế`"Output Path"` với đường dẫn mong muốn cho bản trình bày đầu ra của bạn.

## Bước 2: Thêm tác giả bình luận

Trước khi thêm bình luận, bạn cần xác định tác giả của những bình luận này. Trong ví dụ này, chúng tôi có hai tác giả, "Tác giả_1" và "Tác giả_2", mỗi tác giả được biểu thị bằng một phiên bản của`ICommentAuthor`.

```csharp
// Thêm bình luận
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Thêm câu trả lời cho bình luận1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Trong bước này, chúng tôi tạo hai tác giả nhận xét và thêm nhận xét ban đầu cũng như phản hồi cho nhận xét.

## Bước 3: Thêm câu trả lời khác

Để tạo cấu trúc phân cấp cho các nhận xét, bạn có thể thêm nhiều câu trả lời hơn cho các nhận xét hiện có. Ở đây, chúng tôi thêm câu trả lời thứ hai vào "comment1."

```csharp
// Thêm câu trả lời cho bình luận1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Điều này thiết lập một luồng hội thoại trong bài thuyết trình của bạn.

## Bước 4: Thêm câu trả lời lồng nhau

Các bình luận cũng có thể có các câu trả lời lồng nhau. Để chứng minh điều này, chúng tôi thêm câu trả lời vào "trả lời 2 cho nhận xét 1", tạo câu trả lời phụ.

```csharp
// Thêm câu trả lời để trả lời
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Bước này nêu bật tính linh hoạt của Aspose.Slides dành cho .NET trong việc quản lý hệ thống phân cấp nhận xét.

## Bước 5: Thêm nhận xét và trả lời

Bạn có thể tiếp tục thêm nhiều nhận xét và trả lời nếu cần. Trong ví dụ này, chúng tôi thêm hai nhận xét nữa và trả lời một trong số chúng.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Bước này trình bày cách bạn có thể tạo nội dung hấp dẫn và tương tác cho bài thuyết trình của mình.

## Bước 6: Hiển thị thứ bậc

Để trực quan hóa hệ thống phân cấp nhận xét, bạn có thể hiển thị nó trên bảng điều khiển. Bước này là tùy chọn nhưng có thể hữu ích cho việc gỡ lỗi và hiểu cấu trúc.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## Bước 7: Xóa bình luận

Trong một số trường hợp, bạn có thể cần xóa nhận xét và câu trả lời của họ. Đoạn mã bên dưới minh họa cách xóa "comment1" và tất cả các câu trả lời của nó.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Bước này rất hữu ích cho việc quản lý và cập nhật nội dung bài thuyết trình của bạn.

Với các bước này, bạn có thể tạo bản trình bày có nhận xét và phản hồi tương tác bằng Aspose.Slides cho .NET. Cho dù bạn đang muốn thu hút khán giả hay cộng tác với các thành viên trong nhóm thì tính năng này đều mang lại nhiều khả năng.

## Phần kết luận

Aspose.Slides for .NET cung cấp một bộ công cụ mạnh mẽ để cải thiện bản trình bày PowerPoint của bạn. Với khả năng thêm nhận xét và phản hồi, bạn có thể tạo nội dung động và tương tác thu hút khán giả của mình. Hướng dẫn từng bước này đã chỉ cho bạn cách thêm nhận xét dành cho phụ huynh vào trang trình bày, thiết lập hệ thống phân cấp và thậm chí xóa nhận xét khi cần thiết. Bằng cách làm theo các bước sau và khám phá tài liệu Aspose.Slides[đây](https://reference.aspose.com/slides/net/), bạn có thể đưa bản trình bày của mình lên một tầm cao mới.

## Câu hỏi thường gặp

### Tôi có thể thêm nhận xét vào các trang trình bày cụ thể trong bản trình bày của mình không?
Có, bạn có thể thêm nhận xét vào bất kỳ trang chiếu nào trong bản trình bày của mình bằng cách chỉ định trang chiếu đích khi tạo nhận xét.

### Có thể tùy chỉnh sự xuất hiện của các bình luận trong bản trình bày?
Aspose.Slides for .NET cho phép bạn tùy chỉnh giao diện của nhận xét, bao gồm văn bản, thông tin tác giả và vị trí của chúng trên trang chiếu.

### Tôi có thể xuất nhận xét và câu trả lời sang một tệp riêng không?
Có, bạn có thể xuất nhận xét và câu trả lời sang một tệp trình bày riêng biệt, như được minh họa ở bước 7.

### Aspose.Slides for .NET có tương thích với các phiên bản PowerPoint mới nhất không?
Aspose.Slides for .NET được thiết kế để hoạt động với nhiều phiên bản PowerPoint, đảm bảo khả năng tương thích với các bản phát hành mới nhất.

### Có bất kỳ tùy chọn cấp phép nào có sẵn cho Aspose.Slides cho .NET không?
 Có, bạn có thể khám phá các tùy chọn cấp phép, bao gồm cả giấy phép tạm thời, trên trang web Aspose[đây](https://purchase.aspose.com/buy) hoặc dùng thử miễn phí[đây](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
