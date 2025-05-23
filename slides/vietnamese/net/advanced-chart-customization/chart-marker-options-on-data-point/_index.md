---
"description": "Tìm hiểu cách cải thiện biểu đồ PowerPoint của bạn bằng Aspose.Slides cho .NET. Tùy chỉnh các điểm đánh dấu dữ liệu bằng hình ảnh. Tạo các bài thuyết trình hấp dẫn."
"linktitle": "Tùy chọn đánh dấu biểu đồ trên điểm dữ liệu"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Sử dụng tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Aspose.Slides .NET"
"url": "/vi/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sử dụng tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Aspose.Slides .NET


Khi làm việc với các bài thuyết trình và trực quan hóa dữ liệu, Aspose.Slides for .NET cung cấp nhiều tính năng mạnh mẽ để tạo, tùy chỉnh và thao tác biểu đồ. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng các tùy chọn đánh dấu biểu đồ trên các điểm dữ liệu để nâng cao bài thuyết trình biểu đồ của bạn. Hướng dẫn từng bước này sẽ hướng dẫn bạn thực hiện quy trình, bắt đầu từ các điều kiện tiên quyết và nhập không gian tên, cho đến việc chia nhỏ từng ví dụ thành nhiều bước.

## Điều kiện tiên quyết

Trước khi tìm hiểu cách sử dụng các tùy chọn đánh dấu biểu đồ trên các điểm dữ liệu, hãy đảm bảo rằng bạn đã đáp ứng các điều kiện tiên quyết sau:

- Aspose.Slides cho .NET: Đảm bảo bạn đã cài đặt Aspose.Slides cho .NET. Bạn có thể tải xuống từ [trang web](https://releases.aspose.com/slides/net/).

- Bài thuyết trình mẫu: Đối với hướng dẫn này, chúng tôi sẽ sử dụng một bài thuyết trình mẫu có tên "Test.pptx". Bạn nên có bài thuyết trình này trong thư mục tài liệu của mình.

Bây giờ, chúng ta hãy bắt đầu bằng cách nhập các không gian tên cần thiết.

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

// Tạo biểu đồ mặc định
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Chúng tôi tạo biểu đồ mặc định loại "LineWithMarkers" trên trang chiếu ở vị trí và kích thước đã chỉ định.

## Bước 2: Lấy chỉ mục bảng dữ liệu biểu đồ mặc định

```csharp
// Nhận chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;
```

Ở đây, chúng ta lấy được chỉ mục của bảng tính dữ liệu biểu đồ mặc định.

## Bước 3: Lấy bảng dữ liệu biểu đồ

```csharp
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Chúng tôi lấy bảng tính dữ liệu biểu đồ để làm việc với dữ liệu biểu đồ.

## Bước 4: Sửa đổi Chuỗi Biểu đồ

```csharp
// Xóa loạt bản demo
chart.ChartData.Series.Clear();

// Thêm series mới
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Ở bước này, chúng tôi xóa mọi chuỗi demo hiện có và thêm một chuỗi mới có tên "Dòng 1" vào biểu đồ.

## Bước 5: Thiết lập Picture Fill cho các điểm dữ liệu

```csharp
// Đặt hình ảnh cho các điểm đánh dấu
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Lấy chuỗi biểu đồ đầu tiên
IChartSeries series = chart.ChartData.Series[0];

// Thêm điểm dữ liệu mới với hình ảnh điền
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

Chúng tôi thiết lập các điểm đánh dấu hình ảnh cho các điểm dữ liệu, cho phép bạn tùy chỉnh cách mỗi điểm dữ liệu xuất hiện trên biểu đồ.

## Bước 6: Thay đổi Kích thước Đánh dấu Chuỗi Biểu đồ

```csharp
// Thay đổi kích thước đánh dấu chuỗi biểu đồ
series.Marker.Size = 15;
```

Tại đây, chúng ta điều chỉnh kích thước của điểm đánh dấu biểu đồ để làm cho nó hấp dẫn về mặt thị giác.

## Bước 7: Lưu bài thuyết trình

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Cuối cùng, chúng ta lưu bản trình bày với thiết lập biểu đồ mới.

## Phần kết luận

Aspose.Slides for .NET cho phép bạn tạo các bài thuyết trình biểu đồ tuyệt đẹp với nhiều tùy chọn tùy chỉnh khác nhau. Trong hướng dẫn này, chúng tôi tập trung vào việc sử dụng các tùy chọn đánh dấu biểu đồ trên các điểm dữ liệu để nâng cao khả năng biểu diễn trực quan của dữ liệu. Với Aspose.Slides for .NET, bạn có thể đưa bài thuyết trình của mình lên một tầm cao mới, khiến chúng hấp dẫn và nhiều thông tin hơn.

Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ với Aspose.Slides cho .NET, vui lòng truy cập [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/) hoặc liên hệ với [Cộng đồng Aspose](https://forum.aspose.com/) để được hỗ trợ.

## Những câu hỏi thường gặp (FAQ)

### Tôi có thể sử dụng hình ảnh tùy chỉnh làm điểm đánh dấu cho các điểm dữ liệu trong Aspose.Slides cho .NET không?
Có, bạn có thể sử dụng hình ảnh tùy chỉnh làm điểm đánh dấu cho các điểm dữ liệu trong Aspose.Slides cho .NET, như được trình bày trong hướng dẫn này.

### Làm thế nào để tôi có thể thay đổi loại biểu đồ trong Aspose.Slides cho .NET?
Bạn có thể thay đổi loại biểu đồ bằng cách chỉ định một loại khác `ChartType` khi tạo biểu đồ, chẳng hạn như "Thanh", "Hình tròn" hoặc "Diện tích".

### Aspose.Slides for .NET có tương thích với phiên bản PowerPoint mới nhất không?
Aspose.Slides for .NET được thiết kế để hoạt động với nhiều định dạng PowerPoint khác nhau và được cập nhật thường xuyên để duy trì khả năng tương thích với các phiên bản PowerPoint mới nhất.

### Tôi có thể tìm thêm hướng dẫn và tài nguyên về Aspose.Slides cho .NET ở đâu?
Bạn có thể khám phá thêm các hướng dẫn và tài nguyên trong [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/).

### Có phiên bản dùng thử của Aspose.Slides cho .NET không?
Có, bạn có thể dùng thử Aspose.Slides cho .NET bằng cách tải xuống phiên bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}