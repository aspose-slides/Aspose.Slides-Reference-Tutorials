---
title: Sử dụng tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Aspose.Slides .NET
linktitle: Tùy chọn đánh dấu biểu đồ trên điểm dữ liệu
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách nâng cao biểu đồ PowerPoint của bạn bằng Aspose.Slides for .NET. Tùy chỉnh điểm đánh dấu điểm dữ liệu bằng hình ảnh. Tạo bài thuyết trình hấp dẫn.
weight: 11
url: /vi/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Khi làm việc với các bài thuyết trình và trực quan hóa dữ liệu, Aspose.Slides for .NET cung cấp nhiều tính năng mạnh mẽ để tạo, tùy chỉnh và thao tác với biểu đồ. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng các tùy chọn đánh dấu biểu đồ trên các điểm dữ liệu để cải thiện bản trình bày biểu đồ của bạn. Hướng dẫn từng bước này sẽ hướng dẫn bạn thực hiện quy trình, bắt đầu từ các điều kiện tiên quyết và nhập vùng tên cho đến chia nhỏ từng ví dụ thành nhiều bước.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào sử dụng các tùy chọn đánh dấu biểu đồ trên các điểm dữ liệu, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Slides for .NET: Đảm bảo bạn đã cài đặt Aspose.Slides for .NET. Bạn có thể tải nó xuống từ[trang mạng](https://releases.aspose.com/slides/net/).

- Bản trình bày mẫu: Đối với hướng dẫn này, chúng tôi sẽ sử dụng bản trình bày mẫu có tên "Test.pptx." Bạn nên có bản trình bày này trong thư mục tài liệu của bạn.

Bây giờ, hãy bắt đầu bằng cách nhập các không gian tên cần thiết.

## Nhập không gian tên

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Chúng tôi đã nhập các không gian tên cần thiết và khởi tạo bản trình bày của mình. Bây giờ, hãy tiến hành sử dụng các tùy chọn đánh dấu biểu đồ trên các điểm dữ liệu.

## Bước 1: Tạo biểu đồ mặc định

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Tạo biểu đồ mặc định
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Chúng tôi tạo biểu đồ mặc định thuộc loại "LineWithMarkers" trên trang chiếu tại một vị trí và kích thước được chỉ định.

## Bước 2: Lấy chỉ mục bảng tính dữ liệu biểu đồ mặc định

```csharp
// Lấy chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;
```

Ở đây, chúng tôi lấy chỉ mục của bảng tính dữ liệu biểu đồ mặc định.

## Bước 3: Lấy bảng tính dữ liệu biểu đồ

```csharp
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Chúng tôi tìm nạp sổ làm việc dữ liệu biểu đồ để làm việc với dữ liệu biểu đồ.

## Bước 4: Sửa đổi chuỗi biểu đồ

```csharp
// Xóa loạt bản demo
chart.ChartData.Series.Clear();

// Thêm loạt phim mới
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Ở bước này, chúng tôi xóa mọi chuỗi demo hiện có và thêm chuỗi mới có tên "Sê-ri 1" vào biểu đồ.

## Bước 5: Thiết lập Picture Fill cho Data Points

```csharp
// Đặt hình ảnh cho điểm đánh dấu
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.ChartData.Series[0];

// Thêm điểm dữ liệu mới bằng hình ảnh
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Chúng tôi đặt các điểm đánh dấu hình ảnh cho các điểm dữ liệu, cho phép bạn tùy chỉnh cách mỗi điểm dữ liệu xuất hiện trên biểu đồ.

## Bước 6: Thay đổi kích thước điểm đánh dấu chuỗi biểu đồ

```csharp
// Thay đổi kích thước điểm đánh dấu chuỗi biểu đồ
series.Marker.Size = 15;
```

Ở đây, chúng tôi điều chỉnh kích thước của điểm đánh dấu chuỗi biểu đồ để làm cho nó hấp dẫn về mặt trực quan.

## Bước 7: Lưu bài thuyết trình

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Cuối cùng, chúng ta lưu bài thuyết trình với cài đặt biểu đồ mới.

## Phần kết luận

Aspose.Slides for .NET cho phép bạn tạo các bản trình bày biểu đồ tuyệt đẹp với nhiều tùy chọn tùy chỉnh khác nhau. Trong hướng dẫn này, chúng tôi tập trung vào việc sử dụng các tùy chọn đánh dấu biểu đồ trên các điểm dữ liệu để nâng cao khả năng trình bày trực quan cho dữ liệu của bạn. Với Aspose.Slides cho .NET, bạn có thể đưa bản trình bày của mình lên một tầm cao mới, khiến chúng hấp dẫn và giàu thông tin hơn.

Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ với Aspose.Slides cho .NET, vui lòng truy cập[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/) hoặc tiếp cận với[Cộng đồng đề xuất](https://forum.aspose.com/) để hỗ trợ.

## Câu hỏi thường gặp (FAQ)

### Tôi có thể sử dụng hình ảnh tùy chỉnh làm điểm đánh dấu cho điểm dữ liệu trong Aspose.Slides cho .NET không?
Có, bạn có thể sử dụng hình ảnh tùy chỉnh làm điểm đánh dấu cho điểm dữ liệu trong Aspose.Slides cho .NET, như được minh họa trong hướng dẫn này.

### Làm cách nào để thay đổi loại biểu đồ trong Aspose.Slides cho .NET?
 Bạn có thể thay đổi loại biểu đồ bằng cách chỉ định một loại biểu đồ khác`ChartType` khi tạo biểu đồ, chẳng hạn như "Thanh", "Hình tròn" hoặc "Khu vực".

### Aspose.Slides for .NET có tương thích với các phiên bản PowerPoint mới nhất không?
Aspose.Slides for .NET được thiết kế để hoạt động với nhiều định dạng PowerPoint khác nhau và được cập nhật thường xuyên để duy trì khả năng tương thích với các phiên bản PowerPoint mới nhất.

### Tôi có thể tìm thêm hướng dẫn và tài nguyên về Aspose.Slides cho .NET ở đâu?
 Bạn có thể khám phá các hướng dẫn và tài nguyên bổ sung trong[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/).

### Có phiên bản dùng thử của Aspose.Slides cho .NET không?
 Có, bạn có thể dùng thử Aspose.Slides cho .NET bằng cách tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
