---
"description": "Tìm hiểu cách tùy chỉnh biểu đồ nâng cao trong Aspose.Slides cho .NET. Tạo biểu đồ hấp dẫn trực quan với hướng dẫn từng bước."
"linktitle": "Tùy chỉnh biểu đồ nâng cao trong Aspose.Slides"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Tùy chỉnh biểu đồ nâng cao trong Aspose.Slides"
"url": "/vi/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tùy chỉnh biểu đồ nâng cao trong Aspose.Slides


Tạo biểu đồ hấp dẫn và nhiều thông tin là một phần thiết yếu của việc trình bày dữ liệu trong nhiều ứng dụng. Aspose.Slides for .NET cung cấp các công cụ mạnh mẽ để tùy chỉnh biểu đồ, cho phép bạn tinh chỉnh mọi khía cạnh của biểu đồ. Trong hướng dẫn này, chúng ta sẽ khám phá các kỹ thuật tùy chỉnh biểu đồ nâng cao bằng Aspose.Slides for .NET.

## Điều kiện tiên quyết

Trước khi tìm hiểu sâu hơn về tùy chỉnh biểu đồ nâng cao với Aspose.Slides cho .NET, hãy đảm bảo rằng bạn đã đáp ứng các điều kiện tiên quyết sau:

1. Aspose.Slides cho Thư viện .NET: Bạn cần cài đặt và cấu hình đúng thư viện Aspose.Slides trong dự án .NET của mình. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/net/).

2. Môi trường phát triển .NET: Bạn nên thiết lập môi trường phát triển .NET, bao gồm Visual Studio hoặc bất kỳ IDE nào khác mà bạn chọn.

3. Kiến thức cơ bản về C#: Sự quen thuộc với ngôn ngữ lập trình C# sẽ hữu ích vì chúng ta sẽ viết mã C# để làm việc với Aspose.Slides.

Bây giờ, chúng ta hãy chia nhỏ quá trình tùy chỉnh biểu đồ nâng cao thành nhiều bước để hướng dẫn bạn thực hiện.

## Bước 1: Tạo bài thuyết trình

Đầu tiên, hãy tạo một bài thuyết trình mới bằng Aspose.Slides.

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

Ở bước này, chúng ta sẽ khởi tạo một bản trình bày mới để chứa biểu đồ của mình.

## Bước 2: Truy cập vào Slide đầu tiên

Tiếp theo, hãy truy cập vào trang chiếu đầu tiên trong bản trình bày mà bạn muốn thêm biểu đồ.

```csharp
// Truy cập vào slide đầu tiên
ISlide slide = pres.Slides[0];
```

Đoạn mã này cho phép bạn làm việc với slide đầu tiên trong bản trình bày.

## Bước 3: Thêm biểu đồ mẫu

Bây giờ, hãy thêm một biểu đồ mẫu vào slide. Trong ví dụ này, chúng ta sẽ tạo một biểu đồ đường có đánh dấu.

```csharp
// Thêm biểu đồ mẫu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Tại đây, chúng ta chỉ định loại biểu đồ (LineWithMarkers) cũng như vị trí và kích thước của biểu đồ đó trên trang chiếu.

## Bước 4: Đặt tiêu đề biểu đồ

Hãy đặt tiêu đề cho biểu đồ để cung cấp bối cảnh.

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

Mã này đặt tiêu đề cho biểu đồ, chỉ định văn bản, giao diện và kiểu phông chữ.

## Bước 5: Tùy chỉnh các đường lưới chính

Bây giờ, chúng ta hãy tùy chỉnh các đường lưới chính cho trục giá trị.

```csharp
// Thiết lập định dạng đường lưới chính cho trục giá trị
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Bước này cấu hình giao diện của các đường lưới chính trên trục giá trị.

## Bước 6: Tùy chỉnh các đường lưới nhỏ

Tương tự như vậy, chúng ta có thể tùy chỉnh các đường lưới nhỏ cho trục giá trị.

```csharp
// Thiết lập định dạng đường lưới phụ cho trục giá trị
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Mã này điều chỉnh giao diện của các đường lưới nhỏ trên trục giá trị.

## Bước 7: Xác định Định dạng Số Trục Giá trị

Tùy chỉnh định dạng số cho trục giá trị.

```csharp
// Thiết lập định dạng số trục giá trị
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Bước này cho phép bạn định dạng các số hiển thị trên trục giá trị.

## Bước 8: Đặt giá trị tối đa và tối thiểu của biểu đồ

Xác định giá trị tối đa và tối thiểu cho biểu đồ.

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

Tại đây, bạn chỉ định phạm vi giá trị mà trục biểu đồ sẽ hiển thị.

## Bước 9: Tùy chỉnh Thuộc tính Văn bản Trục Giá trị

Bạn cũng có thể tùy chỉnh thuộc tính văn bản của trục giá trị.

```csharp
// Thiết lập Thuộc tính Văn bản Trục Giá trị
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Mã này cho phép bạn điều chỉnh kiểu phông chữ và giao diện của nhãn trục giá trị.

## Bước 10: Thêm Tiêu đề Trục Giá trị

Nếu biểu đồ của bạn yêu cầu tiêu đề cho trục giá trị, bạn có thể thêm tiêu đề bằng bước này.

```csharp
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

Ở bước này, bạn có thể đặt tiêu đề cho trục giá trị.

## Bước 11: Tùy chỉnh các Đường lưới chính cho Trục danh mục

Bây giờ, chúng ta hãy tập trung vào các đường lưới chính cho trục danh mục.

```csharp
// Thiết lập định dạng đường lưới chính cho trục Danh mục
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Mã này cấu hình giao diện của các đường lưới chính trên trục danh mục.

## Bước 12: Tùy chỉnh các đường lưới phụ cho trục danh mục

Tương tự như trục giá trị, bạn có thể tùy chỉnh các đường lưới nhỏ cho trục danh mục.

```csharp
// Thiết lập định dạng đường lưới phụ cho trục Danh mục
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Tại đây, bạn điều chỉnh giao diện của các đường lưới nhỏ trên trục danh mục.

## Bước 13: Tùy chỉnh Thuộc tính Văn bản Trục Danh mục

Tùy chỉnh thuộc tính văn bản cho nhãn trục danh mục.

```csharp
// Thiết lập Thuộc tính Văn bản Trục Thể loại
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Mã này cho phép bạn điều chỉnh kiểu phông chữ và giao diện của nhãn trục danh mục.

## Bước 14: Thêm Tiêu đề Trục Danh mục

Bạn cũng có thể thêm tiêu đề vào trục danh mục nếu cần.

```csharp
// Thiết lập Tiêu đề Thể loại
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

Ở bước này, bạn có thể đặt tiêu đề cho trục danh mục.

## Bước 15: Tùy chỉnh bổ sung

Bạn có thể khám phá thêm các tùy chỉnh, chẳng hạn như chú giải, tường sau biểu đồ, sàn và màu vùng vẽ. Các tùy chỉnh này cho phép bạn tăng cường sức hấp dẫn trực quan của biểu đồ.

```csharp
// Tùy chỉnh bổ sung (Tùy chọn)

// Thiết lập Thuộc tính Văn bản Huyền thoại
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Đặt hiển thị chú giải biểu đồ mà không chồng chéo biểu đồ
chart.Legend.Overlay = true;

// Vẽ chuỗi đầu tiên trên trục giá trị thứ cấp (nếu cần)
// Chart.ChartData.Series[0].PlotOnSecondAxis = đúng;

// Thiết lập biểu đồ màu tường phía sau
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Thiết lập biểu đồ màu sàn
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Thiết lập màu vùng vẽ
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Lưu bài thuyết trình
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Những tùy chỉnh bổ sung này là tùy chọn và có thể được áp dụng dựa trên yêu cầu thiết kế biểu đồ cụ thể của bạn.

## Phần kết luận

Trong hướng dẫn từng bước này, chúng tôi đã khám phá cách tùy chỉnh biểu đồ nâng cao bằng Aspose.Slides cho .NET. Bạn đã học cách tạo bản trình bày, thêm biểu đồ và tinh chỉnh giao diện của nó, bao gồm các đường lưới, nhãn trục và các thành phần trực quan khác. Với các tùy chọn tùy chỉnh mạnh mẽ do Aspose.Slides cung cấp, bạn có thể tạo biểu đồ truyền tải dữ liệu hiệu quả và thu hút đối tượng mục tiêu.

Nếu bạn có bất kỳ câu hỏi hoặc gặp bất kỳ thách thức nào khi làm việc với Aspose.Slides cho .NET, hãy thoải mái khám phá tài liệu [đây](https://reference.aspose.com/slides/net/) hoặc tìm kiếm sự trợ giúp trong Aspose.Slides [diễn đàn](https://forum.aspose.com/).

## Câu hỏi thường gặp

### Aspose.Slides hỗ trợ những phiên bản .NET nào cho .NET?
Aspose.Slides for .NET hỗ trợ nhiều phiên bản .NET khác nhau, bao gồm .NET Framework và .NET Core. Bạn có thể tham khảo tài liệu để biết danh sách đầy đủ các phiên bản được hỗ trợ.

### Tôi có thể tạo biểu đồ từ các nguồn dữ liệu như tệp Excel bằng Aspose.Slides cho .NET không?
Có, Aspose.Slides for .NET cho phép bạn tạo biểu đồ từ các nguồn dữ liệu bên ngoài như bảng tính Excel. Bạn có thể khám phá tài liệu để biết các ví dụ chi tiết.

### Làm thế nào để tôi có thể thêm nhãn dữ liệu tùy chỉnh vào chuỗi biểu đồ của mình?
Để thêm nhãn dữ liệu tùy chỉnh vào chuỗi biểu đồ của bạn, bạn có thể truy cập `DataLabels` thuộc tính của series và tùy chỉnh nhãn khi cần. Tham khảo tài liệu để biết các mẫu mã và ví dụ.

### Có thể xuất biểu đồ sang các định dạng tệp khác nhau như PDF hoặc định dạng hình ảnh không?
Có, Aspose.Slides for .NET cung cấp các tùy chọn để xuất bản trình bày của bạn với biểu đồ sang nhiều định dạng khác nhau, bao gồm định dạng PDF và hình ảnh. Bạn có thể sử dụng thư viện để lưu tác phẩm của mình ở định dạng đầu ra mong muốn.

### Tôi có thể tìm thêm hướng dẫn và ví dụ về Aspose.Slides cho .NET ở đâu?
Bạn có thể tìm thấy rất nhiều hướng dẫn, ví dụ về mã và tài liệu trên Aspose.Slides [trang web](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}