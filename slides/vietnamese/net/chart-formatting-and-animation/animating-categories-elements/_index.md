---
title: Hoạt ảnh biểu đồ mạnh mẽ với Aspose.Slides cho .NET
linktitle: Hoạt hình các thành phần danh mục trong biểu đồ
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo hiệu ứng động cho các thành phần biểu đồ trong PowerPoint bằng Aspose.Slides for .NET. Hướng dẫn từng bước để có bài thuyết trình ấn tượng.
weight: 11
url: /vi/net/chart-formatting-and-animation/animating-categories-elements/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Trong thế giới thuyết trình, hình ảnh động có thể làm cho nội dung của bạn trở nên sống động, đặc biệt khi xử lý biểu đồ. Aspose.Slides for .NET cung cấp một loạt các tính năng mạnh mẽ cho phép bạn tạo hoạt ảnh tuyệt đẹp cho biểu đồ của mình. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hiệu ứng cho các thành phần danh mục trong biểu đồ bằng Aspose.Slides cho .NET.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, bạn phải có sẵn các điều kiện tiên quyết sau:

-  Aspose.Slides for .NET: Đảm bảo rằng bạn đã cài đặt Aspose.Slides for .NET trong môi trường phát triển của mình. Nếu chưa có, bạn có thể tải xuống từ[đây](https://releases.aspose.com/slides/net/).

- Bản trình bày hiện có: Bạn phải có bản trình bày PowerPoint với biểu đồ mà bạn muốn tạo hiệu ứng động. Nếu bạn không có, hãy tạo một bản trình bày mẫu có biểu đồ cho mục đích thử nghiệm.

Bây giờ bạn đã có mọi thứ, hãy bắt đầu tạo hoạt ảnh cho các thành phần biểu đồ đó!

## Nhập không gian tên

Bước đầu tiên là nhập các không gian tên cần thiết để truy cập chức năng của Aspose.Slides. Thêm các không gian tên sau vào dự án của bạn:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Bước 1: Tải bài thuyết trình

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Nhận tham chiếu của đối tượng biểu đồ
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

Trong bước này, chúng tôi tải bản trình bày PowerPoint hiện có chứa biểu đồ mà bạn muốn tạo hiệu ứng động. Sau đó chúng ta truy cập vào đối tượng biểu đồ trong slide đầu tiên.

## Bước 2: Tạo hiệu ứng cho các phần tử của danh mục

```csharp
// Các phần tử của danh mục sinh động
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Bước này thêm hiệu ứng hoạt hình "Làm mờ" vào toàn bộ biểu đồ, làm cho nó xuất hiện sau hoạt ảnh trước đó.

Tiếp theo, chúng tôi sẽ thêm hoạt ảnh vào từng thành phần riêng lẻ trong từng danh mục của biểu đồ. Đây là nơi phép thuật thực sự xảy ra.

## Bước 3: Tạo hiệu ứng cho các phần tử riêng lẻ

Chúng tôi sẽ chia hoạt ảnh của từng phần tử trong mỗi danh mục thành các bước sau:

### Bước 3.1: Các phần tử hoạt hình trong Danh mục 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Ở đây, chúng tôi đang tạo hoạt ảnh cho các phần tử riêng lẻ trong danh mục 0 của biểu đồ, làm cho chúng xuất hiện lần lượt. Hiệu ứng "Xuất hiện" được sử dụng cho hoạt ảnh này.

### Bước 3.2: Các phần tử hoạt hình trong Danh mục 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Quá trình này được lặp lại cho danh mục 1, tạo hoạt ảnh cho các phần tử riêng lẻ của nó bằng hiệu ứng "Xuất hiện".

### Bước 3.3: Các phần tử hoạt hình trong Danh mục 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Quá trình tương tự tiếp tục xảy ra với loại 2, tạo hoạt ảnh cho từng phần tử của nó.

## Bước 4: Lưu bài thuyết trình

```csharp
// Ghi tập tin trình bày vào đĩa
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

Ở bước cuối cùng, chúng ta lưu bản trình bày với các hoạt ảnh mới được thêm vào. Bây giờ, các thành phần biểu đồ của bạn sẽ hoạt hình đẹp mắt khi bạn chạy bản trình bày.

## Phần kết luận

Hoạt hình các thành phần danh mục trong biểu đồ có thể nâng cao sức hấp dẫn trực quan cho bản trình bày của bạn. Với Aspose.Slides cho .NET, quá trình này trở nên đơn giản và hiệu quả. Bạn đã học cách nhập không gian tên, tải bản trình bày và thêm hoạt ảnh vào toàn bộ biểu đồ cũng như các thành phần riêng lẻ của biểu đồ. Hãy sáng tạo và làm cho bài thuyết trình của bạn hấp dẫn hơn với Aspose.Slides for .NET.

## Câu hỏi thường gặp

### 1. Làm cách nào tôi có thể tải xuống Aspose.Slides cho .NET?
 Bạn có thể tải xuống Aspose.Slides cho .NET từ[liên kết này](https://releases.aspose.com/slides/net/).

### 2. Tôi có cần kinh nghiệm viết mã để sử dụng Aspose.Slides cho .NET không?
Mặc dù trải nghiệm viết mã rất hữu ích nhưng Aspose.Slides for .NET vẫn cung cấp tài liệu và ví dụ mở rộng để hỗ trợ người dùng ở mọi cấp độ kỹ năng.

### 3. Tôi có thể sử dụng Aspose.Slides for .NET với bất kỳ phiên bản PowerPoint nào không?
Aspose.Slides for .NET được thiết kế để hoạt động với nhiều phiên bản PowerPoint khác nhau, đảm bảo khả năng tương thích.

### 4. Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides cho .NET?
 Bạn có thể lấy giấy phép tạm thời cho Aspose.Slides cho .NET[đây](https://purchase.aspose.com/temporary-license/).

### 5. Có diễn đàn cộng đồng nào hỗ trợ Aspose.Slides cho .NET không?
 Có, bạn có thể tìm thấy diễn đàn cộng đồng hỗ trợ cho Aspose.Slides for .NET[đây](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
