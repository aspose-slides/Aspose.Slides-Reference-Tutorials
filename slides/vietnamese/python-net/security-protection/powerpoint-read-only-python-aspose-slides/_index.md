---
"date": "2025-04-23"
"description": "Tìm hiểu cách thiết lập bản trình bày PowerPoint ở chế độ chỉ đọc và đếm số trang chiếu theo chương trình bằng Aspose.Slides for Python. Hoàn hảo để chia sẻ tài liệu an toàn và báo cáo tự động."
"title": "Thiết lập PowerPoint chỉ đọc và đếm số trang chiếu bằng Python sử dụng Aspose.Slides"
"url": "/vi/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thiết lập PowerPoint chỉ đọc và đếm số trang chiếu bằng Python

## Giới thiệu
Bạn đã bao giờ phải đối mặt với thách thức phân phối một bài thuyết trình trong khi vẫn đảm bảo nó không bị thay đổi? Hoặc có lẽ bạn muốn có một cách dễ dàng để xác minh có bao nhiêu slide trong bài thuyết trình của mình mà không cần mở nó? Với **Aspose.Slides cho Python**, những nhiệm vụ này trở nên đơn giản. Hướng dẫn này sẽ hướng dẫn bạn cách thiết lập bản trình bày PowerPoint ở chế độ chỉ đọc và đếm số trang chiếu bằng Aspose.Slides, cung cấp giải pháp mạnh mẽ để quản lý các tệp PowerPoint của bạn theo chương trình.

**Những gì bạn sẽ học được:**
- Cách thiết lập chế độ bảo vệ khi ghi trên bản trình bày PowerPoint.
- Cách lưu tệp PowerPoint với giới hạn chỉ đọc.
- Cách tải bài thuyết trình và đếm số trang trình bày một cách hiệu quả.

Hãy cùng tìm hiểu cách bạn có thể thực hiện các tác vụ này một cách liền mạch trong Python.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có:
- **Python 3.6 trở lên** được cài đặt trên hệ thống của bạn.
- Truy cập vào giao diện dòng lệnh để cài đặt gói.

Bạn cũng sẽ cần cài đặt Aspose.Slides for Python. Thư viện mạnh mẽ này cho phép thao tác nâng cao các tệp PowerPoint ngay từ môi trường Python của bạn. Trong khi phiên bản miễn phí cho phép chức năng hạn chế, việc mua giấy phép (thông qua bản dùng thử miễn phí hoặc mua) sẽ mở rộng khả năng đáng kể.

## Thiết lập Aspose.Slides cho Python
Để bắt đầu làm việc với Aspose.Slides trong Python, trước tiên bạn cần cài đặt nó. Sau đây là cách thực hiện:

### Cài đặt pip
Chạy lệnh sau trong terminal hoặc dấu nhắc lệnh của bạn:

```bash
pip install aspose.slides
```

Thao tác này sẽ tải xuống và cài đặt phiên bản mới nhất của Aspose.Slides cho Python.

### Các bước xin cấp giấy phép
1. **Dùng thử miễn phí**:Bắt đầu bằng bản dùng thử miễn phí để khám phá các chức năng cơ bản.
2. **Giấy phép tạm thời**: Nhận giấy phép tạm thời để mở khóa đầy đủ tính năng trong thời gian dùng thử.
3. **Mua**: Hãy cân nhắc mua giấy phép để tiếp tục được truy cập và hỗ trợ.

Sau khi có tệp giấy phép, hãy tải nó vào tập lệnh của bạn như thế này:

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## Hướng dẫn thực hiện
Trong phần này, chúng tôi sẽ chia nhỏ quá trình triển khai thành hai tính năng chính: thiết lập bản trình bày ở chế độ chỉ đọc và đếm số trang chiếu.

### Tính năng 1: Lưu bài thuyết trình dưới dạng Chỉ đọc
#### Tổng quan
Tính năng này cho phép bạn thiết lập chế độ bảo vệ ghi trên tệp PowerPoint, đảm bảo tệp không thể bị sửa đổi nếu không nhập mật khẩu. Tính năng này đặc biệt hữu ích khi phân phối các bài thuyết trình mà người nhận không được phép thay đổi.

#### Các bước
##### Bước 1: Khởi tạo một đối tượng trình bày
Bắt đầu bằng cách tạo một `Presentation` đối tượng. Điều này thể hiện tệp PPT của bạn trong Python.

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}