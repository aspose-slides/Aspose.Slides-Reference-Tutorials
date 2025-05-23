---
"description": "Tìm hiểu cách thay đổi dữ liệu đối tượng OLE trong PowerPoint bằng Aspose.Slides for Java. Hướng dẫn từng bước để cập nhật hiệu quả và dễ dàng."
"linktitle": "Thay đổi dữ liệu đối tượng OLE trong PowerPoint"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thay đổi dữ liệu đối tượng OLE trong PowerPoint"
"url": "/vi/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thay đổi dữ liệu đối tượng OLE trong PowerPoint

## Giới thiệu
Thay đổi dữ liệu đối tượng OLE trong bản trình bày PowerPoint có thể là một nhiệm vụ quan trọng khi bạn cần cập nhật nội dung nhúng mà không cần chỉnh sửa thủ công từng slide. Hướng dẫn toàn diện này sẽ hướng dẫn bạn thực hiện quy trình bằng Aspose.Slides for Java, một thư viện mạnh mẽ được thiết kế để xử lý các bản trình bày PowerPoint. Cho dù bạn là một nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, bạn sẽ thấy hướng dẫn này hữu ích và dễ làm theo.
## Điều kiện tiên quyết
Trước khi tìm hiểu về mã, hãy đảm bảo rằng bạn có mọi thứ cần thiết để bắt đầu.
1. Java Development Kit (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình. Bạn có thể tải xuống từ [Trang web của Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides cho Java: Tải xuống phiên bản mới nhất từ [Trang tải xuống Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Bạn có thể sử dụng bất kỳ IDE Java nào như IntelliJ IDEA, Eclipse hoặc NetBeans.
4. Aspose.Cells cho Java: Điều này là cần thiết để sửa đổi dữ liệu nhúng trong đối tượng OLE. Tải xuống từ [Trang tải xuống Aspose.Cells](https://releases.aspose.com/cells/java/).
5. Tệp trình bày: Chuẩn bị tệp PowerPoint có đối tượng OLE nhúng. Đối với hướng dẫn này, hãy đặt tên cho nó là `ChangeOLEObjectData.pptx`.
## Nhập gói
Đầu tiên, hãy nhập các gói cần thiết vào dự án Java của bạn.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Bây giờ, chúng ta hãy chia nhỏ quy trình thành các bước đơn giản và dễ quản lý.
## Bước 1: Tải bản trình bày PowerPoint
Để bắt đầu, bạn cần tải bản trình bày PowerPoint có chứa đối tượng OLE.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Bước 2: Truy cập vào Slide chứa Đối tượng OLE
Tiếp theo, lấy slide có nhúng đối tượng OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Bước 3: Tìm Đối tượng OLE trong Slide
Lặp lại các hình dạng trong slide để xác định vị trí đối tượng OLE.
```java
OleObjectFrame ole = null;
// Duyệt tất cả các hình dạng cho khung Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Bước 4: Trích xuất dữ liệu nhúng từ đối tượng OLE
Nếu tìm thấy đối tượng OLE, hãy trích xuất dữ liệu nhúng của đối tượng đó.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Bước 5: Sửa đổi dữ liệu nhúng bằng Aspose.Cells
Bây giờ, hãy sử dụng Aspose.Cells để đọc và sửa đổi dữ liệu nhúng, trong trường hợp này có thể là bảng tính Excel.
```java
    Workbook wb = new Workbook(msln);
    // Sửa đổi dữ liệu bảng tính
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Bước 6: Lưu dữ liệu đã sửa đổi trở lại đối tượng OLE
Sau khi thực hiện những thay đổi cần thiết, hãy lưu lại bảng tính đã sửa đổi vào đối tượng OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Bước 7: Lưu bản trình bày đã cập nhật
Cuối cùng, hãy lưu bản trình bày PowerPoint đã cập nhật.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Phần kết luận
Cập nhật dữ liệu đối tượng OLE trong bản trình bày PowerPoint bằng Aspose.Slides for Java là một quá trình đơn giản khi bạn chia nhỏ thành các bước đơn giản. Hướng dẫn này hướng dẫn bạn cách tải bản trình bày, truy cập và sửa đổi dữ liệu OLE nhúng và lưu bản trình bày đã cập nhật. Với các bước này, bạn có thể quản lý và cập nhật hiệu quả nội dung nhúng trong các slide PowerPoint của mình theo chương trình.
## Câu hỏi thường gặp
### Đối tượng OLE trong PowerPoint là gì?
Đối tượng OLE (Liên kết và Nhúng đối tượng) cho phép nhúng nội dung từ các ứng dụng khác, như bảng tính Excel, vào các slide PowerPoint.
### Tôi có thể sử dụng Aspose.Slides với các ngôn ngữ lập trình khác không?
Có, Aspose.Slides hỗ trợ nhiều ngôn ngữ bao gồm .NET, Python và C++.
### Tôi có cần Aspose.Cells để sửa đổi các đối tượng OLE trong PowerPoint không?
Có, nếu đối tượng OLE là bảng tính Excel, bạn sẽ cần Aspose.Cells để sửa đổi nó.
### Có phiên bản dùng thử của Aspose.Slides không?
Vâng, bạn có thể nhận được một [dùng thử miễn phí](https://releases.aspose.com/) để kiểm tra các tính năng của Aspose.Slides.
### Tôi có thể tìm tài liệu về Aspose.Slides ở đâu?
Bạn có thể tìm thấy tài liệu chi tiết về [Trang tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}