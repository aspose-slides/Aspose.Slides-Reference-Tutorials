---
"description": "Tìm hiểu cách thêm bình luận và trả lời tương tác vào bài thuyết trình PowerPoint của bạn bằng Aspose.Slides cho .NET. Tăng cường sự tương tác và cộng tác."
"linktitle": "Thêm bình luận của phụ huynh vào Slide"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Thêm bình luận của phụ huynh vào Slide bằng Aspose.Slides"
"url": "/vi/net/slide-comments-manipulation/add-parent-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm bình luận của phụ huynh vào Slide bằng Aspose.Slides


Bạn có muốn cải thiện bài thuyết trình PowerPoint của mình bằng các tính năng tương tác không? Aspose.Slides for .NET cho phép bạn kết hợp các bình luận và trả lời, tạo ra trải nghiệm năng động và hấp dẫn cho khán giả của bạn. Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách thêm bình luận gốc vào slide bằng Aspose.Slides for .NET. Hãy cùng khám phá tính năng thú vị này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Aspose.Slides cho .NET: Đảm bảo rằng bạn đã cài đặt Aspose.Slides cho .NET. Bạn có thể tải xuống [đây](https://releases.aspose.com/slides/net/).

2. Visual Studio: Bạn sẽ cần Visual Studio để tạo và chạy ứng dụng .NET của mình.

3. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn có hiểu biết cơ bản về lập trình C#.

Bây giờ chúng ta đã đáp ứng được các điều kiện tiên quyết, hãy tiến hành nhập các không gian tên cần thiết.

## Nhập không gian tên

Đầu tiên, bạn cần nhập các không gian tên có liên quan vào dự án của mình. Các không gian tên này cung cấp các lớp và phương thức cần thiết để làm việc với Aspose.Slides cho .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Với các điều kiện tiên quyết và không gian tên đã được thiết lập, chúng ta hãy chia nhỏ quy trình thành nhiều bước để thêm chú thích gốc vào trang chiếu.

## Bước 1: Tạo bài thuyết trình

Để bắt đầu, bạn cần tạo một bài thuyết trình mới bằng Aspose.Slides for .NET. Bài thuyết trình này sẽ là khung để bạn thêm bình luận.

```csharp
// Đường dẫn đến thư mục đầu ra.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Mã để thêm bình luận của bạn sẽ nằm ở đây.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

Trong đoạn mã trên, hãy thay thế `"Output Path"` với đường dẫn mong muốn cho bản trình bày đầu ra của bạn.

## Bước 2: Thêm tác giả bình luận

Trước khi thêm bình luận, bạn cần xác định tác giả của các bình luận này. Trong ví dụ này, chúng ta có hai tác giả, "Author_1" và "Author_2", mỗi tác giả được biểu diễn bằng một trường hợp của `ICommentAuthor`.

```csharp
// Thêm bình luận
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Thêm trả lời cho bình luận1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Ở bước này, chúng ta tạo hai tác giả bình luận và thêm bình luận ban đầu cùng với phản hồi cho bình luận đó.

## Bước 3: Thêm nhiều câu trả lời hơn

Để tạo cấu trúc phân cấp của các bình luận, bạn có thể thêm nhiều phản hồi hơn vào các bình luận hiện có. Ở đây, chúng tôi thêm phản hồi thứ hai vào "comment1".

```csharp
// Thêm trả lời cho bình luận1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Điều này thiết lập luồng hội thoại trong bài thuyết trình của bạn.

## Bước 4: Thêm các câu trả lời lồng nhau

Bình luận cũng có thể có các phản hồi lồng nhau. Để chứng minh điều này, chúng tôi thêm phản hồi vào "phản hồi 2 cho bình luận 1", tạo thành phản hồi phụ.

```csharp
// Thêm trả lời vào trả lời
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Bước này làm nổi bật tính linh hoạt của Aspose.Slides cho .NET trong việc quản lý phân cấp chú thích.

## Bước 5: Thêm bình luận và trả lời

Bạn có thể tiếp tục thêm nhiều bình luận và trả lời hơn nữa nếu cần. Trong ví dụ này, chúng tôi thêm hai bình luận nữa và trả lời một trong số chúng.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Bước này hướng dẫn cách bạn có thể tạo nội dung hấp dẫn và tương tác cho bài thuyết trình của mình.

## Bước 6: Hiển thị hệ thống phân cấp

Để trực quan hóa phân cấp bình luận, bạn có thể hiển thị nó trên bảng điều khiển. Bước này là tùy chọn nhưng có thể hữu ích cho việc gỡ lỗi và hiểu cấu trúc.

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

Trong một số trường hợp, bạn có thể cần xóa bình luận và phản hồi của họ. Đoạn mã dưới đây minh họa cách xóa "comment1" và tất cả phản hồi của nó.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Bước này hữu ích cho việc quản lý và cập nhật nội dung bài thuyết trình của bạn.

Với các bước này, bạn có thể tạo bài thuyết trình với các bình luận và trả lời tương tác bằng Aspose.Slides for .NET. Cho dù bạn muốn thu hút khán giả hay cộng tác với các thành viên trong nhóm, tính năng này cung cấp nhiều khả năng.

## Phần kết luận

Aspose.Slides for .NET cung cấp một bộ công cụ mạnh mẽ để nâng cao bài thuyết trình PowerPoint của bạn. Với khả năng thêm bình luận và trả lời, bạn có thể tạo nội dung động và tương tác thu hút khán giả. Hướng dẫn từng bước này đã chỉ cho bạn cách thêm bình luận phụ vào slide, thiết lập phân cấp và thậm chí xóa bình luận khi cần thiết. Bằng cách làm theo các bước này và khám phá tài liệu Aspose.Slides [đây](https://reference.aspose.com/slides/net/), bạn có thể nâng cao bài thuyết trình của mình.

## Câu hỏi thường gặp

### Tôi có thể thêm bình luận vào các slide cụ thể trong bài thuyết trình của mình không?
Có, bạn có thể thêm bình luận vào bất kỳ slide nào trong bài thuyết trình bằng cách chỉ định slide mục tiêu khi tạo bình luận.

### Có thể tùy chỉnh giao diện của bình luận trong bài thuyết trình không?
Aspose.Slides for .NET cho phép bạn tùy chỉnh giao diện của bình luận, bao gồm văn bản, thông tin tác giả và vị trí trên trang chiếu.

### Tôi có thể xuất bình luận và trả lời sang một tệp riêng không?
Có, bạn có thể xuất bình luận và phản hồi sang một tệp trình bày riêng biệt, như minh họa ở bước 7.

### Aspose.Slides for .NET có tương thích với phiên bản PowerPoint mới nhất không?
Aspose.Slides for .NET được thiết kế để hoạt động với nhiều phiên bản PowerPoint khác nhau, đảm bảo khả năng tương thích với các bản phát hành mới nhất.

### Có tùy chọn cấp phép nào dành cho Aspose.Slides dành cho .NET không?
Có, bạn có thể khám phá các tùy chọn cấp phép, bao gồm cả giấy phép tạm thời, trên trang web Aspose [đây](https://purchase.aspose.com/buy) hoặc dùng thử miễn phí [đây](https://releases.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}