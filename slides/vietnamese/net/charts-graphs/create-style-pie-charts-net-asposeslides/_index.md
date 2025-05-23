---
"date": "2025-04-15"
"description": "Tìm hiểu cách tự động tạo biểu đồ hình tròn trong bài thuyết trình .NET với Aspose.Slides, giúp tăng cường khả năng trực quan hóa dữ liệu một cách dễ dàng."
"title": "Cách tạo và tùy chỉnh biểu đồ hình tròn trong bài thuyết trình .NET bằng Aspose.Slides"
"url": "/vi/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo và tùy chỉnh biểu đồ hình tròn trong bài thuyết trình .NET bằng Aspose.Slides

## Giới thiệu
Tạo các bài thuyết trình hấp dẫn và nhiều thông tin là rất quan trọng để giao tiếp hiệu quả, cho dù bạn đang trình bày dữ liệu tại nơi làm việc hay giới thiệu những phát hiện mới nhất của dự án. Một cách hiệu quả để trực quan hóa dữ liệu là thông qua biểu đồ hình tròn, có thể biểu diễn ngắn gọn các phần của tổng thể. Tuy nhiên, việc tạo thủ công các biểu đồ này trong phần mềm thuyết trình như PowerPoint có thể tốn thời gian và có thể thiếu tính linh hoạt cần thiết cho các bản cập nhật động.

Đó là lúc Aspose.Slides for .NET phát huy tác dụng. Thư viện toàn diện này cho phép bạn tạo, chỉnh sửa và định dạng các bài thuyết trình theo chương trình, khiến nó trở thành công cụ vô giá cho các nhà phát triển muốn tự động hóa quy trình làm việc của họ và đảm bảo tính nhất quán giữa các bài thuyết trình.

Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Aspose.Slides cho .NET để tạo và tùy chỉnh biểu đồ hình tròn trong bài thuyết trình của bạn. Bạn sẽ học cách:
- **Tạo bài thuyết trình và truy cập các slide**
- **Thêm và cấu hình biểu đồ hình tròn**
- **Tùy chỉnh dữ liệu biểu đồ và chuỗi**
- **Kiểu biểu đồ hình tròn**
- **Thêm nhãn tùy chỉnh**
- **Cấu hình thuộc tính hiển thị và lưu bản trình bày**

Bạn đã sẵn sàng để tạo biểu đồ hình tròn tuyệt đẹp một cách dễ dàng chưa? Hãy bắt đầu thôi!

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập xong những điều sau:

### Thư viện bắt buộc
- Aspose.Slides cho .NET (khuyến nghị phiên bản 21.11 trở lên)

### Thiết lập môi trường
- Môi trường phát triển chạy .NET Framework hoặc .NET Core/5+/6+
- Một trình soạn thảo mã như Visual Studio

### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình C#
- Sự quen thuộc với các khái niệm hướng đối tượng

## Thiết lập Aspose.Slides cho .NET
Để bắt đầu, bạn sẽ cần cài đặt thư viện Aspose.Slides. Bạn có thể thực hiện việc này bằng bất kỳ phương pháp nào sau đây:

**.NETCLI**
```bash
dotnet add package Aspose.Slides
```

**Bảng điều khiển quản lý gói**
```powershell
Install-Package Aspose.Slides
```

**Giao diện người dùng của Trình quản lý gói NuGet**
- Mở dự án của bạn trong Visual Studio.
- Vào "Công cụ" > "Trình quản lý gói NuGet" > "Quản lý gói NuGet cho Solution".
- Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.

### Các bước xin cấp giấy phép
Để sử dụng Aspose.Slides, bạn có thể bắt đầu dùng thử miễn phí bằng cách tải xuống giấy phép tạm thời. Truy cập [Trang web của Aspose](https://purchase.aspose.com/temporary-license/) để có được nó. Để sử dụng liên tục, hãy cân nhắc mua giấy phép đầy đủ.

### Khởi tạo và thiết lập cơ bản
Sau khi cài đặt, hãy khởi tạo lớp Presentation, đại diện cho tệp PPTX của bạn:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Hướng dẫn thực hiện
Chúng tôi sẽ chia nhỏ quá trình tạo biểu đồ hình tròn thành các phần dễ quản lý. Mỗi phần được thiết kế để tập trung vào một tính năng cụ thể, cho phép bạn xây dựng kiến thức của mình theo từng bước.

### Tạo bài thuyết trình và truy cập trang trình bày
**Tổng quan:** Bắt đầu bằng cách tạo một bài thuyết trình mới và truy cập vào trang chiếu đầu tiên của bài thuyết trình đó. Việc này sẽ thiết lập bối cảnh để thêm biểu đồ và các thành phần khác.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Khởi tạo lớp Presentation biểu diễn tệp PPTX
    Presentation presentation = new Presentation();
    
    // Truy cập trang chiếu đầu tiên
    ISlide slides = presentation.Slides[0];
}
```

### Thêm và cấu hình biểu đồ hình tròn
**Tổng quan:** Tìm hiểu cách thêm biểu đồ hình tròn vào trang chiếu và đặt tiêu đề cho phù hợp với ngữ cảnh.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Khởi tạo lớp Presentation biểu diễn tệp PPTX
    Presentation presentation = new Presentation();
    
    // Truy cập trang chiếu đầu tiên
    ISlide slides = presentation.Slides[0];
    
    // Thêm biểu đồ với dữ liệu mặc định vào trang chiếu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Thiết lập biểu đồ Tiêu đề
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Tùy chỉnh dữ liệu biểu đồ và chuỗi
**Tổng quan:** Tùy chỉnh danh mục và chuỗi dữ liệu để phù hợp với yêu cầu cụ thể của bạn.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Khởi tạo lớp Presentation biểu diễn tệp PPTX
    Presentation presentation = new Presentation();
    
    // Truy cập trang chiếu đầu tiên
    ISlide slides = presentation.Slides[0];
    
    // Thêm biểu đồ với dữ liệu mặc định vào trang chiếu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Đặt chuỗi đầu tiên thành Hiển thị giá trị
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Thiết lập chỉ mục của bảng dữ liệu biểu đồ
    int defaultWorksheetIndex = 0;
    
    // Nhận bảng tính dữ liệu biểu đồ
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Xóa các chuỗi và danh mục được tạo mặc định
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Thêm danh mục mới
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Thêm series mới
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Đang điền dữ liệu chuỗi
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Tùy chỉnh Kiểu Biểu đồ Hình tròn
**Tổng quan:** Định dạng từng phần riêng biệt của biểu đồ hình tròn để tăng tính hấp dẫn về mặt thị giác và nhấn mạnh các điểm dữ liệu chính.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Khởi tạo lớp Presentation biểu diễn tệp PPTX
    Presentation presentation = new Presentation();
    
    // Truy cập trang chiếu đầu tiên
    ISlide slides = presentation.Slides[0];
    
    // Thêm biểu đồ với dữ liệu mặc định vào trang chiếu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Lấy chuỗi từ biểu đồ
    IChartSeries series = chart.ChartData.Series[0];
    
    // Tùy chỉnh kiểu khu vực cho từng điểm dữ liệu trong chuỗi
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Thiết lập đường viền Sector
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Thiết lập đường viền Sector
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Thiết lập đường viền Sector
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Thêm nhãn tùy chỉnh vào biểu đồ hình tròn
**Tổng quan:** Cải thiện biểu đồ hình tròn của bạn bằng cách thêm nhãn tùy chỉnh để thể hiện dữ liệu rõ ràng hơn.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Điều chỉnh vị trí nhãn khi cần thiết
    }
}
```

### Phần kết luận
Bây giờ bạn đã học cách tạo và tùy chỉnh biểu đồ hình tròn trong các bài thuyết trình .NET bằng Aspose.Slides. Tự động hóa này có thể cải thiện đáng kể các nỗ lực trực quan hóa dữ liệu của bạn, tiết kiệm thời gian và đảm bảo tính nhất quán trong các bài thuyết trình.

Để khám phá sâu hơn các khả năng của Aspose.Slides cho .NET, hãy cân nhắc tìm hiểu thêm các tính năng bổ sung như tạo các loại biểu đồ khác hoặc tích hợp các yếu tố thiết kế phức tạp hơn vào slide của bạn.

Chúc bạn viết mã vui vẻ!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}