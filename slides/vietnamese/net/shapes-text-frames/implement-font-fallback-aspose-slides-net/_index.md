---
"date": "2025-04-16"
"description": "Tìm hiểu cách triển khai các quy tắc dự phòng phông chữ trong Aspose.Slides cho .NET để đảm bảo bản trình bày của bạn hiển thị văn bản chính xác trên nhiều ngôn ngữ và tập lệnh khác nhau."
"title": "Cách thiết lập quy tắc dự phòng phông chữ trong Aspose.Slides cho .NET&#58; Hướng dẫn toàn diện"
"url": "/vi/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thiết lập quy tắc dự phòng phông chữ trong Aspose.Slides cho .NET: Hướng dẫn toàn diện

## Giới thiệu

Tạo bài thuyết trình bằng Aspose.Slides cho .NET đôi khi yêu cầu xử lý các ký tự mà các phông chữ cụ thể không hỗ trợ, chẳng hạn như Tamil hoặc Hiragana tiếng Nhật. Thiết lập các quy tắc dự phòng phông chữ là điều cần thiết để đảm bảo bài thuyết trình của bạn hiển thị văn bản chính xác trên nhiều ngôn ngữ và ký hiệu khác nhau.

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách triển khai các quy tắc dự phòng phông chữ bằng Aspose.Slides cho .NET. Từ cài đặt đến ứng dụng thực tế, hướng dẫn này đảm bảo rằng các bài thuyết trình của bạn duy trì tính nhất quán về mặt hình ảnh bất kể nội dung.

**Những gì bạn sẽ học được:**
- Xác định phạm vi Unicode cho các chữ viết khác nhau.
- Thiết lập phông chữ dự phòng cho các ký tự không được hỗ trợ.
- Áp dụng phông chữ dự phòng trong các tình huống trình bày thực tế.
- Mẹo để tối ưu hóa hiệu suất và tích hợp với các hệ thống khác.

Chúng ta hãy bắt đầu bằng việc xem xét các điều kiện tiên quyết.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có:

- **Aspose.Slides cho .NET** thư viện đã cài đặt. Cài đặt bằng bất kỳ phương pháp nào sau đây:
  - **.NETCLI**: Chạy `dotnet add package Aspose.Slides`
  - **Trình quản lý gói**: Thực hiện `Install-Package Aspose.Slides`
  - **Giao diện người dùng của Trình quản lý gói NuGet**: Tìm kiếm và cài đặt phiên bản mới nhất.
- Môi trường phát triển được thiết lập bằng .NET Core hoặc .NET Framework (phiên bản 4.5 trở lên).
- Hiểu biết cơ bản về lập trình C#.

## Thiết lập Aspose.Slides cho .NET

Để bắt đầu sử dụng Aspose.Slides, hãy mua giấy phép từ [Trang web Aspose](https://purchase.aspose.com/buy). Sau đây là cách thiết lập:

1. **Cài đặt**: Thực hiện theo các bước cài đặt được đề cập ở trên.
2. **Thiết lập giấy phép**:
   - Tải tệp giấy phép vào dự án của bạn bằng cách sử dụng:
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

Thiết lập này cho phép bạn bắt đầu làm việc với Aspose.Slides cho .NET.

## Hướng dẫn thực hiện

Trong phần này, chúng tôi sẽ trình bày quy trình thiết lập quy tắc dự phòng phông chữ theo các bước rõ ràng.

### 1. Xác định phạm vi Unicode và phông chữ dự phòng

Mỗi tập lệnh hoặc bộ ký hiệu yêu cầu phạm vi Unicode cụ thể và phông chữ dự phòng tương ứng để đảm bảo hiển thị chính xác.

#### Chữ viết Tamil

- **Tổng quan**: Sử dụng "Vijaya" cho các ký tự tiếng Tamil khi phông chữ chính không được hỗ trợ.

**Các bước thực hiện:**

##### Bước 1: Xác định phạm vi Unicode
```csharp
uint startUnicodeIndexTamil = 0x0B80; // Bắt đầu phạm vi Tamil
uint endUnicodeIndexTamil = 0x0BFF;   // Kết thúc phạm vi Tamil
```
Đoạn mã này định nghĩa phạm vi Unicode cho các ký tự tiếng Tamil.

##### Bước 2: Tạo quy tắc dự phòng
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
Ở đây, chúng ta tạo một quy tắc dự phòng bằng cách sử dụng "Vijaya" làm phông chữ thay thế.

#### Tiếng Nhật Hiragana

- **Tổng quan**: Sử dụng "MS Mincho" hoặc "MS Gothic" cho các ký tự Hiragana không được hỗ trợ.

**Các bước thực hiện:**

##### Bước 1: Xác định phạm vi Unicode
```csharp
uint startUnicodeIndexHiragana = 0x3040; // Bắt đầu phạm vi Hiragana
uint endUnicodeIndexHiragana = 0x309F;   // Kết thúc phạm vi Hiragana
```
Đoạn mã này thiết lập ranh giới Unicode cho Hiragana.

##### Bước 2: Tạo quy tắc dự phòng
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
Quy tắc này chỉ định nhiều phông chữ dự phòng cho các ký tự Hiragana.

#### Ký tự Emoji

- **Tổng quan**: Đảm bảo biểu tượng cảm xúc hiển thị bằng phông chữ phù hợp như "Segoe UI Emoji".

**Các bước thực hiện:**

##### Bước 1: Xác định phạm vi Unicode
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // Bắt đầu phạm vi biểu tượng cảm xúc
uint endUnicodeIndexEmoji = 0x1F64F;   // Kết thúc phạm vi biểu tượng cảm xúc
```
Phần này xác định phạm vi Unicode cho biểu tượng cảm xúc.

##### Bước 2: Tạo quy tắc dự phòng
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}