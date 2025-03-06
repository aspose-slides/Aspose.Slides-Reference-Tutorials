---
title: Chuỗi biểu đồ sinh động với Aspose.Slides cho .NET
linktitle: Chuỗi hoạt hình trong biểu đồ
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo hiệu ứng cho chuỗi biểu đồ bằng Aspose.Slides cho .NET. Thu hút khán giả của bạn bằng các bài thuyết trình sinh động. Bắt đầu ngay bây giờ!
type: docs
weight: 12
url: /vi/net/chart-formatting-and-animation/animating-series/
---

Bạn đang muốn thêm một số điểm thú vị vào bản trình bày của mình bằng biểu đồ hoạt hình? Aspose.Slides dành cho .NET sẵn sàng giúp biểu đồ của bạn trở nên sống động. Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách tạo hiệu ứng chuỗi trong biểu đồ bằng Aspose.Slides cho .NET. Nhưng trước khi chúng ta đi sâu vào hành động, hãy đề cập đến các điều kiện tiên quyết.

## Điều kiện tiên quyết

Để tạo hiệu ứng thành công cho chuỗi trong biểu đồ bằng Aspose.Slides cho .NET, bạn sẽ cần những thứ sau:

### 1. Aspose.Slides cho Thư viện .NET

 Đảm bảo bạn đã cài đặt thư viện Aspose.Slides for .NET. Nếu chưa có, bạn có thể tải xuống từ[Aspose.Slides cho trang web .NET](https://releases.aspose.com/slides/net/).

### 2. Bản trình bày hiện có với biểu đồ

Chuẩn bị bản trình bày PowerPoint (PPTX) với biểu đồ hiện có mà bạn muốn tạo hiệu ứng động.

Bây giờ chúng ta đã có các điều kiện tiên quyết, hãy chia quy trình thành một loạt các bước để tạo hiệu ứng cho chuỗi biểu đồ.


## Bước 1: Nhập các không gian tên cần thiết

Bạn sẽ cần nhập các không gian tên bắt buộc trong mã C# của mình để hoạt động với Aspose.Slides cho .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Bước 2: Tải bản trình bày hiện có

Trong bước này, hãy tải bản trình bày PowerPoint (PPTX) hiện có chứa biểu đồ mà bạn muốn tạo hiệu ứng.

```csharp
// Đường dẫn tới thư mục tài liệu
string dataDir = "Your Document Directory";

// Khởi tạo lớp Trình bày đại diện cho một tệp trình bày
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Mã của bạn ở đây
}
```

## Bước 3: Lấy tham chiếu của đối tượng biểu đồ

Để làm việc với biểu đồ trong bản trình bày của bạn, bạn cần lấy tham chiếu đến đối tượng biểu đồ:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Bước 4: Tạo hoạt ảnh cho chuỗi

Bây giờ là lúc thêm hiệu ứng hoạt hình vào chuỗi biểu đồ của bạn. Chúng tôi sẽ thêm hiệu ứng làm mờ dần cho toàn bộ biểu đồ và làm cho từng chuỗi xuất hiện lần lượt.

```csharp
// Làm sinh động biểu đồ
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Thêm hoạt ảnh vào từng bộ truyện
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Bước 5: Lưu bản trình bày đã sửa đổi

Khi bạn đã thêm hiệu ứng hoạt hình vào biểu đồ của mình, hãy lưu bản trình bày đã sửa đổi vào đĩa.

```csharp
//Lưu bản trình bày đã sửa đổi
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã tạo thành công loạt ảnh động trong biểu đồ bằng Aspose.Slides cho .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã hướng dẫn bạn quy trình tạo chuỗi hoạt ảnh trong biểu đồ bằng Aspose.Slides cho .NET. Với thư viện mạnh mẽ này, bạn có thể tạo các bài thuyết trình hấp dẫn và năng động, thu hút khán giả của mình.

 Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ thêm, vui lòng liên hệ với cộng đồng Aspose.Slides trên trang web của họ.[diễn đàn hỗ trợ](https://forum.aspose.com/).

## Câu hỏi thường gặp

### Tôi có thể tạo hiệu ứng động cho các thành phần biểu đồ khác ngoài chuỗi bằng Aspose.Slides cho .NET không?
Có, bạn có thể tạo hiệu ứng động cho nhiều thành phần biểu đồ khác nhau, bao gồm điểm dữ liệu, trục và chú giải bằng cách sử dụng Aspose.Slides cho .NET.

### Aspose.Slides for .NET có tương thích với các phiên bản PowerPoint mới nhất không?
Aspose.Slides for .NET hỗ trợ nhiều phiên bản PowerPoint khác nhau, bao gồm PowerPoint 2007 trở lên, đảm bảo khả năng tương thích với hầu hết các phiên bản mới nhất.

### Tôi có thể tùy chỉnh hiệu ứng hoạt ảnh cho từng chuỗi biểu đồ riêng lẻ không?
Có, bạn có thể điều chỉnh các hiệu ứng hoạt ảnh cho từng chuỗi biểu đồ để tạo ra những bài thuyết trình độc đáo và hấp dẫn.

### Có phiên bản dùng thử cho Aspose.Slides cho .NET không?
 Có, bạn có thể dùng thử thư viện với bản dùng thử miễn phí từ[Aspose.Slides cho trang web .NET](https://releases.aspose.com/).

### Tôi có thể mua giấy phép Aspose.Slides cho .NET ở đâu?
 Bạn có thể nhận được giấy phép cho Aspose.Slides cho .NET từ trang mua hàng[đây](https://purchase.aspose.com/buy).