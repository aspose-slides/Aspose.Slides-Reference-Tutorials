---
"date": "2025-04-15"
"description": "Tìm hiểu cách nâng cao bài thuyết trình của bạn bằng biểu đồ phân tán bằng Aspose.Slides cho .NET. Thực hiện theo hướng dẫn toàn diện này để tạo và tùy chỉnh biểu đồ hiệu quả."
"title": "Thêm Biểu đồ Phân tán vào Bài thuyết trình Sử dụng Aspose.Slides .NET&#58; Hướng dẫn từng bước"
"url": "/vi/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thêm Biểu đồ Phân tán vào Bài thuyết trình Sử dụng Aspose.Slides .NET: Hướng dẫn từng bước

## Giới thiệu
Bạn có muốn cải thiện bài thuyết trình của mình bằng cách tích hợp biểu đồ phân tán một cách dễ dàng không? Với sức mạnh của Aspose.Slides for .NET, việc tạo và tùy chỉnh biểu đồ trở nên dễ dàng. Hướng dẫn này sẽ hướng dẫn bạn cách thêm biểu đồ phân tán vào slide của mình bằng Aspose.Slides for .NET. Bằng cách thành thạo các kỹ thuật này, bạn sẽ trình bày dữ liệu hiệu quả hơn và tạo ra các bài thuyết trình hấp dẫn về mặt hình ảnh.

**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho .NET trong dự án của bạn
- Tạo một bài thuyết trình mới và truy cập vào trang chiếu đầu tiên của bài thuyết trình đó
- Thêm biểu đồ phân tán với các đường thẳng mượt vào slide
- Xóa các chuỗi hiện có và thêm các chuỗi mới vào biểu đồ
- Sửa đổi các điểm dữ liệu và kiểu đánh dấu để tăng cường khả năng trực quan hóa
- Lưu bản trình bày vào một thư mục đã chỉ định

Chúng ta hãy bắt đầu bằng việc xem xét các điều kiện tiên quyết.

## Điều kiện tiên quyết
Trước khi triển khai Aspose.Slides cho .NET, hãy đảm bảo bạn có những điều sau:
- **Aspose.Slides cho Thư viện .NET**: Phiên bản 23.7 trở lên.
- **Môi trường phát triển**: Visual Studio 2019 trở lên với .NET Framework 4.6.1+ hoặc .NET Core/5+.
- **Kiến thức cơ bản về C#**: Quen thuộc với lập trình hướng đối tượng bằng C#.

## Thiết lập Aspose.Slides cho .NET
Để bắt đầu sử dụng Aspose.Slides, bạn cần cài đặt thư viện vào dự án của mình. Sau đây là cách thực hiện:

**Sử dụng .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Sử dụng Package Manager Console:**
```powershell
Install-Package Aspose.Slides
```

**Giao diện người dùng của Trình quản lý gói NuGet:**
- Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.

### Mua lại giấy phép
Bạn có thể bắt đầu bằng bản dùng thử miễn phí hoặc đăng ký giấy phép tạm thời để khám phá tất cả các tính năng. Để mua, hãy làm theo các bước sau:
1. Thăm nom [Mua Aspose.Slides](https://purchase.aspose.com/buy) để mua giấy phép đầy đủ.
2. Để có giấy phép tạm thời, hãy truy cập [Trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

Sau khi có được tệp giấy phép, hãy thêm nó vào dự án của bạn bằng cách sử dụng:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Hướng dẫn thực hiện
Chúng tôi sẽ chia nhỏ quá trình triển khai thành các phần hợp lý dựa trên các tính năng.

### Tạo bài thuyết trình và thêm slide
Phần này trình bày cách tạo bài thuyết trình và truy cập trang chiếu đầu tiên của bài thuyết trình đó.

#### Tổng quan
Bắt đầu bằng cách tạo một phiên bản của `Presentation` lớp, biểu diễn tệp PowerPoint của bạn. Truy cập các slide rất đơn giản khi sử dụng mô hình đối tượng này.

#### Các bước thực hiện
**Bước 1: Khởi tạo bài thuyết trình**
```csharp
using Aspose.Slides;

// Tạo một bài thuyết trình mới
t Presentation pres = new Presentation();
```
Mã này khởi tạo một tài liệu trình bày mới.

**Bước 2: Truy cập trang chiếu đầu tiên**
```csharp
// Truy cập trang chiếu đầu tiên trong bài thuyết trình
ISlide slide = pres.Slides[0];
```
Đây, `pres.Slides[0]` truy cập vào trang chiếu đầu tiên. 

### Thêm biểu đồ phân tán vào trang chiếu
Bây giờ chúng ta hãy thêm biểu đồ phân tán vào bài thuyết trình của bạn.

#### Tổng quan
Thêm biểu đồ có thể giúp bạn thể hiện dữ liệu trực quan trong các bài thuyết trình. Aspose.Slides giúp bạn dễ dàng kết hợp nhiều loại biểu đồ khác nhau, bao gồm cả biểu đồ phân tán.

#### Các bước thực hiện
**Bước 1: Tạo và thêm biểu đồ phân tán**
```csharp
using Aspose.Slides.Charts;

// Tạo và thêm biểu đồ phân tán mặc định với các đường thẳng mượt mà
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Đoạn mã này thêm một biểu đồ phân tán ở vị trí và kích thước đã chỉ định.

### Xóa và Thêm Chuỗi vào Dữ liệu Biểu đồ
#### Tổng quan
Bạn có thể cần tùy chỉnh biểu đồ của mình bằng cách xóa các chuỗi hiện có và thêm các chuỗi mới. Phần này đề cập đến chức năng đó.

#### Các bước thực hiện
**Bước 1: Truy cập Sổ làm việc dữ liệu biểu đồ**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Xóa bất kỳ chuỗi nào đã tồn tại trước đó
chart.ChartData.Series.Clear();
```
Mã này xóa dữ liệu hiện có để bắt đầu lại với chuỗi mới.

**Bước 2: Thêm Series mới**
```csharp
// Thêm một series mới có tên là "Series 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Thêm một series nữa có tên là "Series 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Các bước này thêm hai chuỗi mới vào biểu đồ.

### Sửa đổi Điểm dữ liệu và Kiểu đánh dấu của Chuỗi đầu tiên
#### Tổng quan
Tùy chỉnh các điểm dữ liệu và kiểu đánh dấu để trực quan hóa biểu đồ phân tán của bạn tốt hơn.

#### Các bước thực hiện
**Bước 1: Truy cập và Thêm Điểm Dữ liệu**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Thêm các điểm dữ liệu (1, 3) và (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Bước 2: Sửa đổi Kiểu đánh dấu**
```csharp
// Thay đổi loại chuỗi và sửa đổi kiểu đánh dấu
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Sửa đổi Điểm dữ liệu và Kiểu đánh dấu của Chuỗi thứ hai
#### Tổng quan
Tương tự như vậy, hãy tùy chỉnh loạt bài thứ hai để phù hợp với nhu cầu thuyết trình của bạn.

#### Các bước thực hiện
**Bước 1: Truy cập và Thêm Nhiều Điểm Dữ Liệu**
```csharp
// Truy cập chuỗi biểu đồ thứ hai
series = chart.ChartData.Series[1];

// Thêm nhiều điểm dữ liệu
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Bước 2: Sửa đổi Kiểu đánh dấu**
```csharp
// Thay đổi kích thước và ký hiệu của điểm đánh dấu cho chuỗi thứ hai
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Lưu bài thuyết trình
Cuối cùng, lưu bài thuyết trình của bạn vào một thư mục đã chỉ định.

#### Các bước thực hiện
**Bước 1: Xác định thư mục**
Đảm bảo rằng thư mục đầu ra tồn tại. Nếu không, hãy tạo nó:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Lưu bài thuyết trình
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Mã này lưu tệp trình bày của bạn vào một vị trí đã chỉ định.

## Phần kết luận
Bây giờ bạn đã thêm thành công biểu đồ phân tán vào bài thuyết trình của mình bằng Aspose.Slides for .NET. Tiếp tục khám phá các tính năng bổ sung và tùy chỉnh có sẵn trong thư viện để nâng cao kỹ năng trực quan hóa dữ liệu của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}