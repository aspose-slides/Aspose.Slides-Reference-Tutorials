---
title: Khám phá các đường xu hướng của biểu đồ trong Aspose.Slides cho .NET
linktitle: Biểu đồ đường xu hướng
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách thêm các đường xu hướng khác nhau vào biểu đồ bằng Aspose.Slides cho .NET trong hướng dẫn từng bước này. Nâng cao kỹ năng trực quan hóa dữ liệu của bạn một cách dễ dàng!
type: docs
weight: 12
url: /vi/net/advanced-chart-customization/chart-trend-lines/
---

Trong thế giới trực quan hóa và trình bày dữ liệu, việc kết hợp các biểu đồ có thể là một cách mạnh mẽ để truyền tải thông tin một cách hiệu quả. Aspose.Slides for .NET cung cấp một bộ công cụ giàu tính năng để làm việc với biểu đồ, bao gồm khả năng thêm các đường xu hướng vào biểu đồ của bạn. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình thêm các đường xu hướng vào biểu đồ theo cách từng bước bằng cách sử dụng Aspose.Slides cho .NET. 

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu làm việc với Aspose.Slides cho .NET, bạn cần đảm bảo có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Slides for .NET: Để truy cập và sử dụng thư viện, bạn phải cài đặt Aspose.Slides for .NET. Bạn có thể lấy thư viện từ[trang tải xuống](https://releases.aspose.com/slides/net/).

2. Môi trường phát triển: Bạn nên thiết lập môi trường phát triển, tốt nhất là sử dụng môi trường phát triển tích hợp .NET như Visual Studio.

3. Kiến thức cơ bản về C#: Hiểu biết cơ bản về lập trình C# là có lợi vì chúng ta sẽ sử dụng C# để làm việc với Aspose.Slides cho .NET.

Bây giờ chúng ta đã đề cập đến các điều kiện tiên quyết, hãy chia nhỏ quy trình thêm đường xu hướng vào biểu đồ theo từng bước.

## Nhập không gian tên

Trước tiên, hãy đảm bảo bạn nhập các không gian tên cần thiết vào dự án C# của mình. Những không gian tên này rất cần thiết để làm việc với Aspose.Slides cho .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Bước 1: Tạo bản trình bày

Trong bước này, chúng ta tạo một bản trình bày trống để làm việc.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";

// Tạo thư mục nếu nó chưa có.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Tạo bản trình bày trống
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ vào slide

Tiếp theo, chúng tôi thêm biểu đồ cột được nhóm vào trang chiếu.

```csharp
// Tạo biểu đồ cột được nhóm
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Bước 3: Thêm đường xu hướng vào biểu đồ

Bây giờ, chúng tôi thêm nhiều loại đường xu hướng khác nhau vào chuỗi biểu đồ.

### Thêm một đường xu hướng hàm mũ

```csharp
// Thêm đường xu hướng hàm mũ cho chuỗi biểu đồ 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Thêm một đường xu hướng tuyến tính

```csharp
// Thêm đường xu hướng tuyến tính cho chuỗi biểu đồ 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Thêm một đường xu hướng logarit

```csharp
// Thêm đường xu hướng logarit cho chuỗi biểu đồ 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Thêm đường xu hướng trung bình động

```csharp
// Thêm đường xu hướng trung bình động cho chuỗi biểu đồ 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Thêm một đường xu hướng đa thức

```csharp
// Thêm đường xu hướng đa thức cho chuỗi biểu đồ 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Thêm đường xu hướng quyền lực

```csharp
// Thêm đường xu hướng lũy thừa cho chuỗi biểu đồ 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Bước 4: Lưu bài thuyết trình

Sau khi thêm đường xu hướng vào biểu đồ, hãy lưu bài thuyết trình.

```csharp
// Đang lưu bản trình bày
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã thêm thành công nhiều đường xu hướng khác nhau vào biểu đồ của mình bằng Aspose.Slides for .NET.

## Phần kết luận

Aspose.Slides for .NET là một thư viện đa năng cho phép bạn tạo và thao tác biểu đồ một cách dễ dàng. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể thêm các loại đường xu hướng khác nhau vào biểu đồ của mình, nâng cao khả năng trình bày trực quan cho dữ liệu của bạn.

### Câu hỏi thường gặp

### Tôi có thể tìm tài liệu về Aspose.Slides cho .NET ở đâu?
 Bạn có thể truy cập tài liệu[đây](https://reference.aspose.com/slides/net/).

### Làm cách nào tôi có thể tải xuống Aspose.Slides cho .NET?
 Bạn có thể tải xuống Aspose.Slides cho .NET từ trang tải xuống[đây](https://releases.aspose.com/slides/net/).

### Có bản dùng thử miễn phí dành cho Aspose.Slides cho .NET không?
 Có, bạn có thể dùng thử Aspose.Slides cho .NET miễn phí bằng cách truy cập[liên kết này](https://releases.aspose.com/).

### Tôi có thể mua Aspose.Slides cho .NET ở đâu?
 Để mua Aspose.Slides cho .NET, hãy truy cập trang mua hàng[đây](https://purchase.aspose.com/buy).

### Tôi có cần giấy phép tạm thời cho Aspose.Slides cho .NET không?
 Bạn có thể nhận được giấy phép tạm thời cho Aspose.Slides cho .NET từ[liên kết này](https://purchase.aspose.com/temporary-license/).