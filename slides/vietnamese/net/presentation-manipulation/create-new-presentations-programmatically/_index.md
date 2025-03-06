---
title: Tạo bản trình bày mới theo chương trình
linktitle: Tạo bản trình bày mới theo chương trình
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo bản trình bày theo chương trình bằng Aspose.Slides cho .NET. Hướng dẫn từng bước với mã nguồn để tự động hóa hiệu quả.
weight: 10
url: /vi/net/presentation-manipulation/create-new-presentations-programmatically/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo bản trình bày mới theo chương trình


Nếu bạn đang muốn tạo bản trình bày theo chương trình trong .NET thì Aspose.Slides for .NET là một công cụ mạnh mẽ giúp bạn đạt được nhiệm vụ này một cách hiệu quả. Hướng dẫn từng bước này sẽ hướng dẫn bạn qua quá trình tạo bản trình bày mới bằng cách sử dụng mã nguồn được cung cấp.

## Giới thiệu về Aspose.Slides cho .NET

Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các bản trình bày PowerPoint theo chương trình. Cho dù bạn cần tạo báo cáo, tự động hóa bản trình bày hay thao tác với các trang trình bày, Aspose.Slides đều cung cấp nhiều tính năng để giúp công việc của bạn dễ dàng hơn.

## Bước 1: Thiết lập môi trường của bạn

Trước khi chúng ta đi sâu vào mã, bạn sẽ cần thiết lập môi trường phát triển của mình. Đảm bảo bạn có các điều kiện tiên quyết sau:

- Visual Studio hoặc bất kỳ môi trường phát triển .NET nào.
-  Thư viện Aspose.Slides cho .NET (Bạn có thể tải xuống[đây](https://releases.aspose.com/slides/net/)).

## Bước 2: Tạo bản trình bày

Hãy bắt đầu bằng cách tạo một bản trình bày mới bằng mã sau:

```csharp
// Tạo bản trình bày
Presentation pres = new Presentation();
```

Mã này khởi tạo một đối tượng trình bày mới, làm nền tảng cho tệp PowerPoint của bạn.

## Bước 3: Thêm tiêu đề slide

Trong hầu hết các bài thuyết trình, slide đầu tiên là slide tiêu đề. Đây là cách bạn có thể thêm một:

```csharp
// Thêm tiêu đề slide
Slide slide = pres.AddTitleSlide();
```

Mã này thêm một slide tiêu đề vào bản trình bày của bạn.

## Bước 4: Đặt Tiêu đề và Phụ đề

Bây giờ, hãy đặt tiêu đề và phụ đề cho slide tiêu đề của bạn:

```csharp
// Đặt văn bản tiêu đề
((TextHolder)slide.Placeholders[0]).Text = "Slide Title Heading";

// Đặt văn bản phụ đề
((TextHolder)slide.Placeholders[1]).Text = "Slide Title Sub-Heading";
```

Thay thế "Tiêu đề phụ của tiêu đề trang trình bày" và "Tiêu đề phụ của tiêu đề trang trình bày" bằng tiêu đề bạn muốn.

## Bước 5: Lưu bản trình bày của bạn

Cuối cùng, hãy lưu bản trình bày của bạn vào một tệp:

```csharp
// Ghi đầu ra vào đĩa
pres.Write("outAsposeSlides.ppt");
```

Mã này lưu bản trình bày của bạn dưới dạng "outAsposeSlides.ppt" trong thư mục dự án của bạn.

## Phần kết luận

Chúc mừng! Bạn vừa tạo một bản trình bày PowerPoint theo chương trình bằng Aspose.Slides cho .NET. Thư viện mạnh mẽ này mang đến cho bạn sự linh hoạt để tự động hóa và tùy chỉnh bản trình bày của mình một cách dễ dàng.

Bây giờ, bạn có thể bắt đầu kết hợp mã này vào các dự án .NET của mình để tạo các bản trình bày động phù hợp với nhu cầu cụ thể của bạn.

## Câu hỏi thường gặp

1. ### Aspose.Slides cho .NET có được sử dụng miễn phí không?
    Không, Aspose.Slides for .NET là thư viện thương mại. Bạn có thể tìm thấy thông tin về giá cả và giấy phép[đây](https://purchase.aspose.com/buy).

2. ### Tôi có cần bất kỳ quyền đặc biệt nào để sử dụng Aspose.Slides cho .NET trong các dự án của mình không?
    Bạn sẽ cần giấy phép hợp lệ để sử dụng Aspose.Slides cho .NET. Bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/) để đánh giá.

3. ### Tôi có thể tìm hỗ trợ cho Aspose.Slides cho .NET ở đâu?
    Để được hỗ trợ kỹ thuật và thảo luận, bạn có thể truy cập diễn đàn Aspose.Slides[đây](https://forum.aspose.com/).

4. ### Tôi có thể dùng thử Aspose.Slides cho .NET trước khi mua không?
    Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Slides cho .NET[đây](https://releases.aspose.com/). Phiên bản dùng thử có những hạn chế, vì vậy hãy nhớ kiểm tra xem nó có đáp ứng yêu cầu của bạn không.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
