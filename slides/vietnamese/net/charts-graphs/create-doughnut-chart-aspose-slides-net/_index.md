---
"date": "2025-04-15"
"description": "Tìm hiểu cách tạo biểu đồ hình tròn động bằng Aspose.Slides cho .NET. Làm theo hướng dẫn này để biết hướng dẫn từng bước, bao gồm thiết lập và các tính năng nâng cao."
"title": "Hướng dẫn từng bước&#58; Tạo biểu đồ hình tròn với Aspose.Slides .NET | Biểu đồ & Đồ thị"
"url": "/vi/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hướng dẫn từng bước: Tạo biểu đồ hình tròn với Aspose.Slides .NET

## Giới thiệu

Hãy tưởng tượng bạn được giao nhiệm vụ trình bày kết quả phân tích dữ liệu cho nhóm hoặc khách hàng của mình và bạn cần một cách hấp dẫn để trực quan hóa thông tin. Hãy nhập biểu đồ hình tròn—một công cụ đa năng có thể chuyển đổi các số liệu thô thành những hiểu biết dễ hiểu. Với Aspose.Slides dành cho .NET, việc tạo biểu đồ hình tròn tùy chỉnh trong các slide thuyết trình của bạn thật đơn giản và hiệu quả. Hướng dẫn này sẽ hướng dẫn bạn cách sử dụng Aspose.Slides để tạo biểu đồ hình tròn hấp dẫn về mặt hình ảnh, hoàn chỉnh với các cấu hình chuỗi được tùy chỉnh.

**Những gì bạn sẽ học được:**
- Thiết lập môi trường phát triển của bạn với Aspose.Slides cho .NET
- Tạo và tùy chỉnh biểu đồ hình tròn trong bài thuyết trình
- Triển khai các tính năng nâng cao như tên danh mục và dòng dẫn đầu
- Tối ưu hóa hiệu suất cho các tập dữ liệu lớn

Hãy cùng tìm hiểu những điều kiện tiên quyết bạn cần có để bắt đầu.

## Điều kiện tiên quyết

Trước khi triển khai tính năng này, hãy đảm bảo rằng môi trường phát triển của bạn được thiết lập đúng cách. Hướng dẫn này giả định bạn có kiến thức cơ bản về lập trình .NET và quen thuộc với Visual Studio hoặc IDE tương tự.

### Thư viện và phiên bản bắt buộc
- **Aspose.Slides cho .NET**: Đảm bảo khả năng tương thích với phiên bản mới nhất bằng cách kiểm tra [tài liệu chính thức](https://reference.aspose.com/slides/net/).

### Yêu cầu thiết lập môi trường
- Môi trường .NET đang hoạt động.
- Truy cập vào trình soạn thảo mã, chẳng hạn như Visual Studio.

### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về C# và .NET framework.
- Quen thuộc với các khái niệm về phần mềm trình bày (tùy chọn nhưng hữu ích).

## Thiết lập Aspose.Slides cho .NET

Để bắt đầu sử dụng Aspose.Slides trong dự án của bạn, bạn cần cài đặt nó thông qua NuGet. Sau đây là các phương pháp có sẵn:

**Sử dụng .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Sử dụng Trình quản lý gói:**
```powershell
Install-Package Aspose.Slides
```

**Giao diện người dùng của Trình quản lý gói NuGet:**
Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.

### Các bước xin cấp giấy phép

1. **Dùng thử miễn phí**: Bắt đầu bằng một [dùng thử miễn phí](https://releases.aspose.com/slides/net/) để khám phá các chức năng cơ bản.
2. **Giấy phép tạm thời**: Nhận giấy phép tạm thời nếu bạn cần truy cập vào đầy đủ các tính năng cho mục đích đánh giá bằng cách truy cập [đây](https://purchase.aspose.com/temporary-license/).
3. **Mua**: Đối với mục đích thương mại, hãy mua giấy phép từ [Trang web Aspose](https://purchase.aspose.com/buy).

Sau khi cài đặt và cấp phép, hãy khởi tạo Aspose.Slides trong dự án của bạn:
```csharp
using Aspose.Slides;

// Khởi tạo Aspose.Slides cho .NET
var presentation = new Presentation();
```

## Hướng dẫn thực hiện

### Tạo bài thuyết trình mới và thêm biểu đồ hình tròn

#### Tổng quan
Chúng ta sẽ bắt đầu bằng cách tạo một bài thuyết trình mới và thêm biểu đồ hình bánh rán vào trang chiếu đầu tiên. Phần này bao gồm việc tải bài thuyết trình hiện có, truy cập trang chiếu và chèn biểu đồ.

**Bước 1: Tải hoặc Tạo Bài thuyết trình**
Đầu tiên, hãy chỉ định thư mục tài liệu của bạn và tải bản trình bày hiện có:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Nếu bạn không có tệp hiện có, hãy tạo tệp mới bằng `new Presentation()`.

**Bước 2: Truy cập vào Slide đầu tiên**
Truy cập vào trang chiếu đầu tiên nơi chúng ta sẽ thêm biểu đồ:
```csharp
ISlide slide = pres.Slides[0];
```

**Bước 3: Thêm biểu đồ hình tròn**
Thêm biểu đồ hình tròn ở tọa độ và kích thước đã chỉ định:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Cấu hình sổ làm việc dữ liệu

#### Tổng quan
Phần này giải thích cách cấu hình sổ làm việc dữ liệu liên quan đến biểu đồ hình tròn của bạn.

**Bước 4: Truy cập và xóa dữ liệu hiện có**
Truy cập vào sổ làm việc dữ liệu của biểu đồ. Sau đó xóa bất kỳ chuỗi hoặc danh mục hiện có nào:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Bước 5: Tắt chú giải và thêm chuỗi**
Tắt chú giải để giữ cho biểu đồ gọn gàng, sau đó thêm tối đa 15 chuỗi với cấu hình tùy chỉnh:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Thêm danh mục và điểm dữ liệu

#### Tổng quan
Bây giờ, chúng ta hãy điền các danh mục và điểm dữ liệu vào biểu đồ cho từng chuỗi.

**Bước 6: Thêm danh mục**
Lặp lại để thêm 15 danh mục:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Bước 7: Điền điểm dữ liệu**
Thêm điểm dữ liệu cho mỗi chuỗi trong danh mục hiện tại:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Tùy chỉnh giao diện
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Cấu hình định dạng nhãn cho loạt cuối cùng
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Cấu hình hiển thị nhãn
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Lưu bài thuyết trình

**Bước 8: Lưu tệp**
Cuối cùng, lưu bài thuyết trình của bạn vào một thư mục được chỉ định:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}