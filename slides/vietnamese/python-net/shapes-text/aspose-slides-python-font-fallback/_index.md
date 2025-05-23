---
"date": "2025-04-24"
"description": "Tìm hiểu cách tạo và quản lý các quy tắc dự phòng phông chữ bằng Aspose.Slides for Python để đảm bảo bản trình bày của bạn nhất quán trên các hệ thống khác nhau."
"title": "Làm chủ Font Fallback trong Aspose.Slides cho Python&#58; Hướng dẫn toàn diện"
"url": "/vi/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Làm chủ Font Fallback trong Aspose.Slides cho Python: Hướng dẫn toàn diện

## Giới thiệu

Các vấn đề về khả năng tương thích phông chữ có thể trở nên khó khăn khi tạo bài thuyết trình, đặc biệt là với các ký tự Unicode không được phông chữ chính hỗ trợ. **Aspose.Slides cho Python** cung cấp giải pháp mạnh mẽ thông qua các quy tắc dự phòng phông chữ, đảm bảo tính hấp dẫn trực quan và dễ đọc của bài thuyết trình trên nhiều hệ thống khác nhau.

Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo và quản lý các quy tắc dự phòng phông chữ bằng Aspose.Slides cho Python. Bạn sẽ học:
- Thiết lập môi trường của bạn với Aspose.Slides
- Tạo một bộ sưu tập các quy tắc dự phòng phông chữ
- Quản lý các quy tắc này bằng cách thêm hoặc xóa phông chữ dựa trên phạm vi Unicode
- Áp dụng các quy tắc vào bài thuyết trình và hiển thị các slide dưới dạng hình ảnh

Hãy bắt đầu bằng việc chuẩn bị môi trường của bạn.

## Điều kiện tiên quyết

Đảm bảo môi trường của bạn đã sẵn sàng cho nhiệm vụ này. Sau đây là những gì bạn cần:
1. **Aspose.Slides cho Python**: Thư viện này quản lý các quy tắc dự phòng phông chữ.
2. **Môi trường Python**: Đảm bảo Python (phiên bản 3.6 trở lên) đã được cài đặt.
3. **Kiến thức cơ bản về Python**:Sự quen thuộc với cú pháp và khái niệm Python sẽ hữu ích khi chúng ta đi sâu vào các đoạn mã.

## Thiết lập Aspose.Slides cho Python

### Cài đặt

Để bắt đầu, hãy cài đặt thư viện Aspose.Slides bằng pip:

```bash
pip install aspose.slides
```

### Mua lại giấy phép

Aspose cung cấp giấy phép dùng thử miễn phí để khám phá các tính năng của nó mà không có giới hạn. Sau đây là cách bạn có thể nhận được nó:
- Thăm nom [Trang mua hàng của Aspose](https://purchase.aspose.com/buy) để mua các tùy chọn hoặc truy cập giấy phép tạm thời.
- Ngoài ra, hãy tải xuống bản dùng thử miễn phí từ [Phần tải xuống](https://releases.aspose.com/slides/python-net/).

### Khởi tạo cơ bản

Sau khi cài đặt, hãy khởi tạo Aspose.Slides trong tập lệnh Python của bạn:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Hướng dẫn thực hiện

### Tạo và quản lý quy tắc dự phòng phông chữ

#### Tổng quan

Các quy tắc dự phòng phông chữ đảm bảo tất cả các ký tự trong bản trình bày của bạn đều có phông chữ phù hợp, duy trì khả năng đọc cho các ngôn ngữ có bộ ký tự duy nhất.

#### Các bước thực hiện

**1. Tạo Bộ sưu tập quy tắc dự phòng phông chữ**

Bắt đầu bằng cách tạo một bộ sưu tập để xác định phông chữ dự phòng:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Thêm Quy tắc dự phòng phông chữ**

Xác định quy tắc chỉ định phạm vi Unicode và phông chữ dự phòng:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Các tham số**: `0x400` là sự khởi đầu của phạm vi Unicode, `0x4FF` là kết thúc, và `"Times New Roman"` là phông chữ dự phòng.

**3. Quản lý các quy tắc hiện có**

Lặp lại từng quy tắc để sửa đổi chúng khi cần thiết:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Xóa một quy tắc**

Nếu cần, hãy xóa quy tắc đầu tiên khỏi bộ sưu tập của bạn:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Áp dụng quy tắc Font Fallback vào bài thuyết trình và kết xuất hình ảnh

#### Tổng quan

Sau khi thiết lập các quy tắc phông chữ dự phòng, hãy áp dụng chúng vào bài thuyết trình để đảm bảo văn bản sử dụng phông chữ dự phòng đã chỉ định khi cần thiết.

#### Các bước thực hiện

**1. Khởi tạo môi trường của bạn**

Chuẩn bị thư mục để nhập và xuất:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Áp dụng Quy tắc dự phòng cho Bài thuyết trình**

Tải tệp trình bày của bạn và áp dụng các quy tắc phông chữ:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}