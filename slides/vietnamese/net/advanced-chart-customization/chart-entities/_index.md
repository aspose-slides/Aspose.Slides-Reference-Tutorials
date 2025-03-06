---
title: Tạo biểu đồ đẹp với Aspose.Slides cho .NET
linktitle: Thực thể và định dạng biểu đồ
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo biểu đồ tuyệt đẹp với Aspose.Slides cho .NET. Nâng cao trò chơi trực quan hóa dữ liệu của bạn với hướng dẫn từng bước của chúng tôi.
weight: 13
url: /vi/net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo biểu đồ đẹp với Aspose.Slides cho .NET


Trong thế giới dựa trên dữ liệu ngày nay, trực quan hóa dữ liệu hiệu quả là chìa khóa để truyền tải thông tin đến khán giả của bạn. Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép bạn tạo các bản trình bày và trang trình bày ấn tượng, bao gồm các biểu đồ bắt mắt. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo biểu đồ đẹp mắt bằng Aspose.Slides cho .NET. Chúng tôi sẽ chia từng ví dụ thành nhiều bước để giúp bạn hiểu và triển khai các thực thể và định dạng biểu đồ. Vậy hãy bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào việc tạo các biểu đồ đẹp mắt bằng Aspose.Slides cho .NET, bạn cần đảm bảo rằng mình có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Slides for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Slides for .NET. Bạn có thể tải nó xuống từ[trang mạng](https://releases.aspose.com/slides/net/).

2. Môi trường phát triển: Bạn phải có môi trường phát triển hoạt động với Visual Studio hoặc bất kỳ IDE nào khác hỗ trợ phát triển .NET.

3. Kiến thức C# cơ bản: Làm quen với lập trình C# là điều cần thiết cho hướng dẫn này.

Bây giờ chúng ta đã sắp xếp các điều kiện tiên quyết, hãy tiến hành tạo các biểu đồ đẹp mắt với Aspose.Slides cho .NET.

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết để hoạt động với Aspose.Slides cho .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Bước 1: Tạo bản trình bày

Chúng tôi bắt đầu bằng cách tạo một bản trình bày mới để làm việc. Bản trình bày này sẽ đóng vai trò là khung vẽ cho biểu đồ của chúng tôi.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";

// Tạo thư mục nếu nó chưa có.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Đang khởi tạo bản trình bày
Presentation pres = new Presentation();
```

## Bước 2: Truy cập Slide đầu tiên

Hãy truy cập vào slide đầu tiên trong bản trình bày nơi chúng ta sẽ đặt biểu đồ của mình.

```csharp
// Truy cập slide đầu tiên
ISlide slide = pres.Slides[0];
```

## Bước 3: Thêm biểu đồ mẫu

Bây giờ, chúng ta sẽ thêm biểu đồ mẫu vào slide của mình. Trong ví dụ này, chúng tôi sẽ tạo biểu đồ dạng đường có điểm đánh dấu.

```csharp
// Thêm biểu đồ mẫu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Bước 4: Đặt tiêu đề biểu đồ

Chúng tôi sẽ đặt tiêu đề cho biểu đồ của mình, làm cho biểu đồ có nhiều thông tin hơn và hấp dẫn về mặt trực quan hơn.

```csharp
// Đặt tiêu đề biểu đồ
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Bước 5: Tùy chỉnh đường lưới trục dọc

Trong bước này, chúng ta sẽ tùy chỉnh các đường lưới trục tung để làm cho biểu đồ của chúng ta hấp dẫn hơn về mặt trực quan.

```csharp
// Đặt định dạng đường lưới chính cho trục giá trị
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Đặt định dạng đường lưới nhỏ cho trục giá trị
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Cài đặt định dạng số trục giá trị
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Bước 6: Xác định phạm vi trục dọc

Trong bước này, chúng ta sẽ đặt giá trị tối đa, tối thiểu và đơn vị cho trục tung.

```csharp
// Thiết lập biểu đồ giá trị tối đa, tối thiểu
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Bước 7: Tùy chỉnh văn bản trục dọc

Bây giờ chúng ta sẽ tùy chỉnh sự xuất hiện của văn bản trên trục tung.

```csharp
// Đặt thuộc tính văn bản trục giá trị
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Đặt tiêu đề trục giá trị
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Bước 8: Tùy chỉnh đường lưới trục ngang

Bây giờ, hãy tùy chỉnh các đường lưới cho trục ngang.

```csharp
// Đặt định dạng đường lưới chính cho trục Danh mục
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Đặt định dạng đường lưới nhỏ cho trục Danh mục
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Đặt thuộc tính văn bản trục danh mục
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Bước 9: Tùy chỉnh nhãn trục ngang

Trong bước này, chúng ta sẽ điều chỉnh vị trí và góc xoay của nhãn trục ngang.

```csharp
// Đặt vị trí nhãn trục danh mục
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Cài đặt góc xoay nhãn trục danh mục
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Bước 10: Tùy chỉnh Huyền thoại

Hãy cải thiện các chú giải trong biểu đồ của chúng ta để dễ đọc hơn.

```csharp
// Đặt thuộc tính văn bản chú giải
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Đặt chú thích biểu đồ hiển thị mà không có biểu đồ chồng chéo
chart.Legend.Overlay = true;
```

## Bước 11: Tùy chỉnh nền biểu đồ

Chúng ta sẽ tùy chỉnh màu nền của biểu đồ, tường sau và sàn.

```csharp
// Bảng thiết lập màu tường sau
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Cài đặt màu vùng Lô
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Bước 12: Lưu bài thuyết trình

Cuối cùng, hãy lưu bài thuyết trình của chúng ta với biểu đồ đã được định dạng.

```csharp
// Lưu bản trình bày
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Việc tạo các biểu đồ đẹp mắt và giàu thông tin trong bản trình bày của bạn giờ đây trở nên dễ dàng hơn bao giờ hết với Aspose.Slides cho .NET. Trong hướng dẫn này, chúng tôi đã đề cập đến các bước cần thiết để tùy chỉnh các khía cạnh khác nhau của biểu đồ, làm cho biểu đồ trở nên hấp dẫn về mặt hình ảnh và mang tính thông tin. Với những kỹ thuật này, bạn có thể tạo các biểu đồ tuyệt đẹp để truyền tải dữ liệu của mình đến khán giả một cách hiệu quả.

Bắt đầu thử nghiệm Aspose.Slides cho .NET và đưa trực quan hóa dữ liệu của bạn lên một tầm cao mới!

## Các câu hỏi thường gặp

### 1. Aspose.Slides cho .NET là gì?

Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển .NET tạo, thao tác và chuyển đổi bản trình bày Microsoft PowerPoint. Nó cung cấp nhiều tính năng để làm việc với các trang trình bày, hình dạng, biểu đồ, v.v.

### 2. Tôi có thể tải xuống Aspose.Slides cho .NET ở đâu?

 Bạn có thể tải xuống Aspose.Slides cho .NET từ trang web[đây](https://releases.aspose.com/slides/net/).

### 3. Có bản dùng thử miễn phí Aspose.Slides cho .NET không?

 Có, bạn có thể dùng thử miễn phí Aspose.Slides cho .NET từ[đây](https://releases.aspose.com/).

### 4. Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides cho .NET?

 Nếu bạn cần giấy phép tạm thời, bạn có thể lấy giấy phép từ[liên kết này](https://purchase.aspose.com/temporary-license/).

### 5. Có cộng đồng hoặc diễn đàn hỗ trợ nào cho Aspose.Slides cho .NET không?

 Có, bạn có thể tìm thấy cộng đồng Aspose.Slides và diễn đàn hỗ trợ[đây](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
