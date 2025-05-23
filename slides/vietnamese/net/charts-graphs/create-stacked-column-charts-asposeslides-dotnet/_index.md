---
"date": "2025-04-15"
"description": "Tìm hiểu cách tạo biểu đồ cột xếp chồng theo phần trăm hấp dẫn trực quan bằng Aspose.Slides cho .NET. Thực hiện theo hướng dẫn từng bước này để trực quan hóa dữ liệu rõ ràng."
"title": "Cách tạo biểu đồ cột xếp chồng theo phần trăm trong .NET bằng Aspose.Slides"
"url": "/vi/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ cột xếp chồng theo phần trăm bằng Aspose.Slides cho .NET

## Giới thiệu

Trong lĩnh vực trực quan hóa dữ liệu, việc trình bày thông tin rõ ràng và hiệu quả là rất quan trọng để đưa ra quyết định có tác động. Để hiển thị các tập dữ liệu phức tạp một cách trực quan, biểu đồ cột xếp chồng theo phần trăm là lý tưởng. Hướng dẫn này sẽ hướng dẫn bạn cách tạo các biểu đồ này bằng Aspose.Slides for .NET, một thư viện mạnh mẽ được thiết kế để thao tác các tệp trình bày.

Bằng cách làm theo hướng dẫn này, bạn sẽ học được:
- Thiết lập dữ liệu biểu đồ và cấu hình định dạng số.
- Thêm chuỗi và tùy chỉnh giao diện của chúng.
- Định dạng nhãn để tăng khả năng đọc.

Bạn đã sẵn sàng chưa? Hãy bắt đầu với những điều kiện tiên quyết bạn cần!

## Điều kiện tiên quyết

Trước khi tạo biểu đồ cột xếp chồng theo phần trăm, hãy đảm bảo môi trường của bạn được thiết lập đúng. Bạn sẽ cần:

### Thư viện, Phiên bản và Phụ thuộc bắt buộc
- **Aspose.Slides cho .NET**: Đảm bảo thư viện này đã được cài đặt.

### Yêu cầu thiết lập môi trường
- Môi trường phát triển có cài đặt .NET SDK.
- Visual Studio hoặc bất kỳ IDE tương thích nào để chạy mã C#.

### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình C#.
- Quen thuộc với việc thiết lập dự án .NET và quản lý gói.

## Thiết lập Aspose.Slides cho .NET

Để bắt đầu tạo biểu đồ bằng Aspose.Slides, trước tiên hãy cài đặt thư viện bằng một trong các phương pháp sau:

**.NETCLI**
```bash
dotnet add package Aspose.Slides
```

**Trình quản lý gói**
```powershell
Install-Package Aspose.Slides
```

**Giao diện người dùng của Trình quản lý gói NuGet**
- Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.

### Các bước xin cấp giấy phép

Bắt đầu với bản dùng thử miễn phí bằng cách tải xuống giấy phép tạm thời từ [Trang web của Aspose](https://purchase.aspose.com/temporary-license/). Để tiếp tục sử dụng, hãy cân nhắc mua giấy phép đầy đủ. 

Sau khi thiết lập, hãy khởi chạy Aspose.Slides trong dự án của bạn:
```csharp
using Aspose.Slides;
```

## Hướng dẫn thực hiện

Khi môi trường đã sẵn sàng, chúng ta hãy chia nhỏ quá trình tạo biểu đồ cột xếp chồng theo phần trăm thành các bước.

### Tạo và cấu hình biểu đồ

#### Tổng quan
Tạo một phiên bản của `Presentation` lớp, điều này rất cần thiết khi làm việc với các slide. Sau đó, thêm và định cấu hình biểu đồ cột xếp chồng trên slide của bạn.

#### Thêm biểu đồ cột xếp chồng
```csharp
// Tạo một thể hiện của lớp Presentation
document = new Presentation();

// Tham khảo trang trình bày đầu tiên
slide = document.Slides[0];

// Thêm biểu đồ PercentsStackedColumn ở vị trí (20, 20) với kích thước (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Cấu hình định dạng số
Đảm bảo dữ liệu của bạn được hiển thị dưới dạng phần trăm:
```csharp
// Cấu hình định dạng số cho trục dọc
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Đặt định dạng số thành phần trăm
```

#### Thêm Chuỗi Dữ Liệu và Điểm
Xóa dữ liệu chuỗi hiện có và thêm dữ liệu mới:
```csharp
// Xóa bất kỳ dữ liệu chuỗi hiện có nào
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Sổ làm việc dữ liệu biểu đồ Access
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Thêm một loạt dữ liệu mới "Reds"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Đặt màu tô cho chuỗi thành Đỏ
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Cấu hình thuộc tính định dạng nhãn cho chuỗi "Reds"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Đặt định dạng phần trăm
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Thêm một loạt phim "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Đặt màu tô cho chuỗi thành Xanh lam
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Đặt định dạng phần trăm
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Lưu bài thuyết trình
Lưu bài thuyết trình của bạn vào một tập tin:
```csharp
// Lưu bản trình bày ở định dạng PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Mẹo khắc phục sự cố
- Đảm bảo tất cả không gian tên được nhập chính xác.
- Kiểm tra lỗi đánh máy trong tên thuộc tính và lệnh gọi phương thức.
- Xác minh đường dẫn lưu tệp của bạn có tồn tại và có quyền phù hợp không.

## Ứng dụng thực tế

Sau đây là một số trường hợp mà biểu đồ cột xếp chồng theo phần trăm có thể hữu ích:
1. **Phân tích bán hàng**: Hình dung hiệu suất sản phẩm ở các khu vực khác nhau theo tỷ lệ so với tổng doanh số.
2. **Phân bổ ngân sách**: Hiển thị cách các phòng ban phân bổ ngân sách của mình liên quan đến chi tiêu chung của công ty.
3. **Nghiên cứu thị trường**: So sánh sở thích của người tiêu dùng đối với nhiều loại sản phẩm khác nhau theo thời gian.
4. **Dữ liệu giáo dục**: Hiển thị sự phân bố điểm của học sinh ở các môn học khác nhau.
5. **Thống kê chăm sóc sức khỏe**: Thể hiện thông tin nhân khẩu học của bệnh nhân trong nhiều tình trạng sức khỏe khác nhau.

## Cân nhắc về hiệu suất

Để có hiệu suất tối ưu, hãy cân nhắc:
- Giới hạn số lượng điểm dữ liệu ở mức cần thiết.
- Tải trước dữ liệu để giảm thiểu thời gian xử lý khi chạy.
- Sử dụng các biện pháp quản lý bộ nhớ hiệu quả với Aspose.Slides cho .NET.

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách tạo biểu đồ cột xếp chồng theo phần trăm bằng Aspose.Slides cho .NET. Công cụ này cải thiện bài thuyết trình bằng cách làm cho dữ liệu phức tạp dễ hiểu hơn và hấp dẫn hơn về mặt trực quan.

Bước tiếp theo? Khám phá các loại biểu đồ khác có trong Aspose.Slides hoặc tích hợp chức năng này vào các ứng dụng lớn hơn. Chúc bạn viết mã vui vẻ!

## Phần Câu hỏi thường gặp

**Câu hỏi 1: Tôi có thể sử dụng Aspose.Slides miễn phí không?**
A1: Có, bạn có thể bắt đầu bằng bản dùng thử miễn phí để kiểm tra các tính năng của Aspose.Slides.

**Câu hỏi 2: Aspose.Slides hỗ trợ những loại biểu đồ nào cho .NET?**
A2: Hỗ trợ nhiều loại biểu đồ như biểu đồ tròn, biểu đồ thanh, biểu đồ cột, biểu đồ đường, v.v.

**Câu hỏi 3: Làm thế nào để bắt đầu sử dụng Aspose.Slides cho .NET?**
A3: Cài đặt thư viện bằng NuGet hoặc .NET CLI như mô tả ở trên. Làm theo tài liệu của chúng tôi để tạo biểu đồ đầu tiên của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}