---
title: Định dạng và hoạt ảnh biểu đồ trong Aspose.Slides
linktitle: Định dạng và hoạt ảnh biểu đồ trong Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách định dạng và tạo hoạt ảnh cho biểu đồ trong Aspose.Slides dành cho .NET, nâng cao bản trình bày của bạn bằng hình ảnh quyến rũ.
weight: 10
url: /vi/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Định dạng và hoạt ảnh biểu đồ trong Aspose.Slides


Việc tạo bản trình bày hấp dẫn bằng biểu đồ và hoạt ảnh động có thể nâng cao đáng kể tác động của thông điệp của bạn. Aspose.Slides for .NET cho phép bạn đạt được điều đó. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hoạt ảnh và định dạng biểu đồ bằng Aspose.Slides cho .NET. Chúng tôi sẽ chia các bước thành các phần có thể quản lý được để đảm bảo bạn nắm bắt khái niệm một cách kỹ lưỡng.

## Điều kiện tiên quyết

Trước khi đi sâu vào định dạng và hoạt ảnh biểu đồ bằng Aspose.Slides, bạn sẽ cần những thứ sau:

1.  Aspose.Slides for .NET: Đảm bảo bạn đã cài đặt Aspose.Slides for .NET. Nếu bạn chưa có, bạn có thể[tải về tại đây](https://releases.aspose.com/slides/net/).

2. Bản trình bày hiện có: Có bản trình bày hiện có chứa biểu đồ mà bạn muốn định dạng và tạo hiệu ứng.

3. Kiến thức C# cơ bản: Làm quen với C# sẽ hữu ích trong việc thực hiện các bước.

Bây giờ, hãy bắt đâù.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các không gian tên cần thiết để truy cập các tính năng Aspose.Slides. Trong dự án C# của bạn, hãy thêm dòng sau:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Hoạt hình các thành phần danh mục trong biểu đồ

### Bước 1: Tải bản trình bày và truy cập biểu đồ

Trước tiên, hãy tải bản trình bày hiện có của bạn và truy cập biểu đồ mà bạn muốn tạo hiệu ứng động. Ví dụ này giả định rằng biểu đồ nằm trên slide đầu tiên của bản trình bày của bạn.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Bước 2: Thêm hoạt ảnh vào các thành phần của danh mục

Bây giờ, hãy thêm hoạt ảnh vào các thành phần của danh mục. Trong ví dụ này, chúng tôi đang sử dụng hiệu ứng làm mờ dần.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Bước 3: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày đã sửa đổi vào đĩa.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## Chuỗi hoạt hình trong biểu đồ

### Bước 1: Tải bản trình bày và truy cập biểu đồ

Tương tự như ví dụ trước, bạn sẽ tải bản trình bày và truy cập vào biểu đồ.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Bước 2: Thêm hoạt ảnh vào chuỗi

Bây giờ, hãy thêm hoạt ảnh vào chuỗi biểu đồ. Chúng tôi cũng đang sử dụng hiệu ứng làm mờ ở đây.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Bước 3: Lưu bài thuyết trình

Lưu bản trình bày đã sửa đổi với loạt phim hoạt hình.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Hoạt hình các phần tử chuỗi trong biểu đồ

### Bước 1: Tải bản trình bày và truy cập biểu đồ

Như trước, tải bản trình bày và truy cập biểu đồ.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Bước 2: Thêm hoạt ảnh vào các phần tử của chuỗi

Trong bước này, bạn sẽ thêm hoạt ảnh vào các thành phần của chuỗi, tạo hiệu ứng hình ảnh ấn tượng.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### Bước 3: Lưu bài thuyết trình

Đừng quên lưu bản trình bày có chứa các phần tử loạt phim hoạt hình.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

Chúc mừng! Bây giờ bạn đã học cách định dạng và tạo hiệu ứng cho biểu đồ trong Aspose.Slides cho .NET. Những kỹ thuật này có thể làm cho bài thuyết trình của bạn hấp dẫn và nhiều thông tin hơn.

## Phần kết luận

Aspose.Slides for .NET cung cấp các công cụ mạnh mẽ để định dạng và hoạt ảnh biểu đồ, cho phép bạn tạo các bản trình bày trực quan hấp dẫn thu hút khán giả của mình. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể nắm vững nghệ thuật tạo hoạt ảnh biểu đồ và cải thiện bản trình bày của mình.

## Câu hỏi thường gặp

### 1. Tôi có thể tìm tài liệu về Aspose.Slides cho .NET ở đâu?

 Bạn có thể truy cập tài liệu tại[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. Làm cách nào để tải xuống Aspose.Slides cho .NET?

 Bạn có thể tải xuống Aspose.Slides cho .NET từ[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. Có bản dùng thử miễn phí không?

 Có, bạn có thể dùng thử miễn phí Aspose.Slides cho .NET tại[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. Tôi có thể mua giấy phép tạm thời cho Aspose.Slides cho .NET không?

 Có, bạn có thể mua giấy phép tạm thời tại[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. Tôi có thể nhận hỗ trợ hoặc đặt câu hỏi về Aspose.Slides cho .NET ở đâu?

 Để được hỗ trợ và đặt câu hỏi, hãy truy cập diễn đàn Aspose.Slides tại[https://forum.aspose.com/](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
