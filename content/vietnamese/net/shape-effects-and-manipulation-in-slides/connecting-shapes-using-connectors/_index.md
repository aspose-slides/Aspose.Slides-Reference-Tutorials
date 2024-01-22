---
title: Aspose.Slides - Kết nối các hình dạng liền mạch trong .NET
linktitle: Kết nối các hình bằng cách sử dụng Connectors trong bài thuyết trình
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Khám phá sức mạnh của Aspose.Slides dành cho .NET, kết nối các hình dạng một cách dễ dàng trong bản trình bày của bạn. Nâng tầm trang trình bày của bạn bằng các đầu nối động.
type: docs
weight: 29
url: /vi/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Giới thiệu
Trong thế giới năng động của bản trình bày, khả năng kết nối các hình dạng bằng cách sử dụng trình kết nối sẽ tăng thêm sự tinh tế cho trang trình bày của bạn. Aspose.Slides for .NET trao quyền cho các nhà phát triển để đạt được điều này một cách liền mạch. Hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình, chia nhỏ từng bước để đảm bảo bạn hiểu rõ ràng.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
- Kiến thức cơ bản về C# và .NET framework.
-  Đã cài đặt Aspose.Slides cho .NET. Nếu không thì tải về[đây](https://releases.aspose.com/slides/net/).
- Một môi trường phát triển được thiết lập.
## Nhập không gian tên
Trong mã C# của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Thiết lập thư mục tài liệu
Bắt đầu bằng cách xác định thư mục cho tài liệu của bạn:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Khởi tạo lớp trình bày
Tạo một thể hiện của lớp Trình bày để thể hiện tệp PPTX của bạn:
```csharp
using (Presentation input = new Presentation())
{
    // Truy cập bộ sưu tập hình dạng cho slide đã chọn
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Thêm hình vào slide
Thêm các hình dạng cần thiết vào slide của bạn, chẳng hạn như Ellipse và Rectangle:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Thêm hình dạng kết nối
Bao gồm hình dạng đường kết nối trong bộ sưu tập hình dạng của trang chiếu:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Kết nối các hình dạng bằng Connector
Chỉ định các hình dạng được kết nối bằng đầu nối:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Định tuyến lại trình kết nối
Gọi phương thức định tuyến lại để đặt đường đi ngắn nhất tự động giữa các hình:
```csharp
connector.Reroute();
```
## 7. Lưu bài thuyết trình
Lưu bản trình bày của bạn để xem các hình dạng được kết nối:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Phần kết luận
Chúc mừng! Bạn đã kết nối thành công các hình dạng bằng trình kết nối trong các trang trình bày bằng Aspose.Slides for .NET. Nâng cao bài thuyết trình của bạn với tính năng nâng cao này và thu hút khán giả của bạn.
## Câu hỏi thường gặp
### Aspose.Slides cho .NET có tương thích với .NET framework mới nhất không?
Có, Aspose.Slides cho .NET được cập nhật thường xuyên để đảm bảo khả năng tương thích với các phiên bản .NET framework mới nhất.
### Tôi có thể kết nối nhiều hơn hai hình bằng một đầu nối không?
Hoàn toàn có thể, bạn có thể kết nối nhiều hình dạng bằng cách mở rộng logic trình kết nối trong mã của mình.
### Có bất kỳ hạn chế nào về hình dạng mà tôi có thể kết nối không?
Aspose.Slides for .NET hỗ trợ kết nối nhiều hình dạng khác nhau, bao gồm các hình dạng cơ bản, nghệ thuật thông minh và hình dạng tùy chỉnh.
### Làm cách nào để tùy chỉnh giao diện của trình kết nối?
Khám phá tài liệu Aspose.Slides để biết các phương pháp tùy chỉnh giao diện của trình kết nối, chẳng hạn như kiểu đường và màu sắc.
### Có diễn đàn cộng đồng nào hỗ trợ Aspose.Slides không?
 Có, bạn có thể tìm sự trợ giúp và chia sẻ kinh nghiệm của mình trong[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).