---
"description": "Tìm hiểu cách tạo biểu đồ tuyệt đẹp với Aspose.Slides cho .NET. Nâng cao khả năng trực quan hóa dữ liệu của bạn với hướng dẫn từng bước của chúng tôi."
"linktitle": "Các thực thể biểu đồ và định dạng"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Tạo biểu đồ đẹp với Aspose.Slides cho .NET"
"url": "/vi/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tạo biểu đồ đẹp với Aspose.Slides cho .NET


Trong thế giới dữ liệu ngày nay, trực quan hóa dữ liệu hiệu quả là chìa khóa để truyền tải thông tin đến đối tượng của bạn. Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép bạn tạo các bài thuyết trình và slide ấn tượng, bao gồm các biểu đồ bắt mắt. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo biểu đồ đẹp mắt bằng Aspose.Slides for .NET. Chúng tôi sẽ chia nhỏ từng ví dụ thành nhiều bước để giúp bạn hiểu và triển khai các thực thể và định dạng biểu đồ. Vậy, hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi bắt đầu tạo biểu đồ đẹp mắt bằng Aspose.Slides cho .NET, bạn cần đảm bảo rằng mình đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Aspose.Slides cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tải xuống từ [trang web](https://releases.aspose.com/slides/net/).

2. Môi trường phát triển: Bạn nên có môi trường phát triển hoạt động với Visual Studio hoặc bất kỳ IDE nào khác hỗ trợ phát triển .NET.

3. Kiến thức cơ bản về C#: Sự quen thuộc với lập trình C# là điều cần thiết cho hướng dẫn này.

Bây giờ chúng ta đã sắp xếp xong các điều kiện tiên quyết, hãy tiến hành tạo các biểu đồ đẹp mắt bằng Aspose.Slides cho .NET.

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết để làm việc với Aspose.Slides cho .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Bước 1: Tạo bài thuyết trình

Chúng ta bắt đầu bằng cách tạo một bài thuyết trình mới để làm việc. Bài thuyết trình này sẽ đóng vai trò là khung vẽ cho biểu đồ của chúng ta.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";

// Tạo thư mục nếu thư mục đó chưa có.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Khởi tạo bài thuyết trình
Presentation pres = new Presentation();
```

## Bước 2: Truy cập vào Slide đầu tiên

Chúng ta hãy truy cập vào trang chiếu đầu tiên trong bài thuyết trình nơi chúng ta sẽ đặt biểu đồ.

```csharp
// Truy cập vào slide đầu tiên
ISlide slide = pres.Slides[0];
```

## Bước 3: Thêm biểu đồ mẫu

Bây giờ, chúng ta sẽ thêm một biểu đồ mẫu vào slide của mình. Trong ví dụ này, chúng ta sẽ tạo một biểu đồ đường có đánh dấu.

```csharp
// Thêm biểu đồ mẫu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Bước 4: Đặt tiêu đề biểu đồ

Chúng ta sẽ đặt tiêu đề cho biểu đồ để biểu đồ có nhiều thông tin hơn và hấp dẫn hơn về mặt thị giác.

```csharp
// Thiết lập tiêu đề biểu đồ
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

## Bước 5: Tùy chỉnh Đường lưới trục dọc

Ở bước này, chúng ta sẽ tùy chỉnh các đường lưới trục dọc để làm cho biểu đồ hấp dẫn hơn về mặt thị giác.

```csharp
// Thiết lập định dạng đường lưới chính cho trục giá trị
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Thiết lập định dạng đường lưới phụ cho trục giá trị
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Thiết lập định dạng số trục giá trị
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Bước 6: Xác định phạm vi trục dọc

Ở bước này, chúng ta sẽ thiết lập giá trị tối đa, tối thiểu và đơn vị cho trục dọc.

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

## Bước 7: Tùy chỉnh Văn bản Trục Dọc

Bây giờ chúng ta sẽ tùy chỉnh giao diện của văn bản trên trục dọc.

```csharp
// Thiết lập Thuộc tính Văn bản Trục Giá trị
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Thiết lập giá trị tiêu đề trục
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

## Bước 8: Tùy chỉnh Đường lưới trục ngang

Bây giờ, chúng ta hãy tùy chỉnh các đường lưới cho trục ngang.

```csharp
// Thiết lập định dạng đường lưới chính cho trục Danh mục
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Thiết lập định dạng đường lưới phụ cho trục Danh mục
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Thiết lập Thuộc tính Văn bản Trục Thể loại
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

Ở bước này, chúng ta sẽ điều chỉnh vị trí và góc quay của nhãn trục ngang.

```csharp
// Thiết lập vị trí nhãn trục danh mục
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Thiết lập góc quay nhãn trục danh mục
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Bước 10: Tùy chỉnh chú giải

Hãy cải thiện chú thích trong biểu đồ để dễ đọc hơn.

```csharp
// Thiết lập Thuộc tính Văn bản Huyền thoại
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Đặt hiển thị chú giải biểu đồ mà không chồng chéo biểu đồ
chart.Legend.Overlay = true;
```

## Bước 11: Tùy chỉnh nền biểu đồ

Chúng tôi sẽ tùy chỉnh màu nền của biểu đồ, tường sau và sàn nhà.

```csharp
// Thiết lập biểu đồ màu tường phía sau
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Thiết lập màu vùng vẽ
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Bước 12: Lưu bài thuyết trình

Cuối cùng, hãy lưu bài thuyết trình với biểu đồ đã định dạng.

```csharp
// Lưu bài thuyết trình
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Việc tạo biểu đồ đẹp và nhiều thông tin trong bài thuyết trình của bạn giờ đây dễ dàng hơn bao giờ hết với Aspose.Slides for .NET. Trong hướng dẫn này, chúng tôi đã đề cập đến các bước thiết yếu để tùy chỉnh nhiều khía cạnh khác nhau của biểu đồ, giúp biểu đồ trở nên hấp dẫn và nhiều thông tin. Với các kỹ thuật này, bạn có thể tạo ra các biểu đồ tuyệt đẹp truyền tải dữ liệu của mình đến khán giả một cách hiệu quả.

Hãy bắt đầu thử nghiệm với Aspose.Slides cho .NET và đưa khả năng trực quan hóa dữ liệu của bạn lên một tầm cao mới!

## Những câu hỏi thường gặp

### 1. Aspose.Slides dành cho .NET là gì?

Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển .NET tạo, thao tác và chuyển đổi các bài thuyết trình Microsoft PowerPoint. Nó cung cấp nhiều tính năng để làm việc với các slide, hình dạng, biểu đồ, v.v.

### 2. Tôi có thể tải Aspose.Slides cho .NET ở đâu?

Bạn có thể tải xuống Aspose.Slides cho .NET từ trang web [đây](https://releases.aspose.com/slides/net/).

### 3. Có bản dùng thử miễn phí Aspose.Slides cho .NET không?

Có, bạn có thể dùng thử miễn phí Aspose.Slides cho .NET từ [đây](https://releases.aspose.com/).

### 4. Làm thế nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides cho .NET?

Nếu bạn cần giấy phép tạm thời, bạn có thể xin giấy phép từ [liên kết này](https://purchase.aspose.com/temporary-license/).

### 5. Có cộng đồng hoặc diễn đàn hỗ trợ nào cho Aspose.Slides dành cho .NET không?

Có, bạn có thể tìm thấy cộng đồng Aspose.Slides và diễn đàn hỗ trợ [đây](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}