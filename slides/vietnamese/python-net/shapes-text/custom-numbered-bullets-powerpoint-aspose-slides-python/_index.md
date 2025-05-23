---
"date": "2025-04-24"
"description": "Tìm hiểu cách tạo danh sách dấu đầu dòng được đánh số tùy chỉnh trong PowerPoint với Aspose.Slides for Python. Nâng cao bài thuyết trình của bạn với định dạng độc đáo."
"title": "Danh sách Bullet được đánh số tùy chỉnh trong PowerPoint bằng Aspose.Slides cho Python"
"url": "/vi/python-net/shapes-text/custom-numbered-bullets-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Danh sách Bullet được đánh số tùy chỉnh trong PowerPoint bằng Aspose.Slides cho Python

## Giới thiệu
Bạn có muốn nâng cao sức hấp dẫn trực quan của bài thuyết trình PowerPoint của mình ngoài các dấu đầu dòng mặc định không? Cho dù đó là báo cáo của công ty, bài giảng học thuật hay cuộc họp kinh doanh, việc tùy chỉnh danh sách dấu đầu dòng có thể thu hút và giữ sự chú ý của khán giả hiệu quả hơn. Với **Aspose.Slides cho Python**, bạn có thể linh hoạt tùy chỉnh các dấu đầu dòng được đánh số theo nhu cầu định dạng riêng của mình.

Trong hướng dẫn toàn diện này, chúng tôi sẽ trình bày cách thiết lập các dấu đầu dòng được đánh số tùy chỉnh bằng Aspose.Slides trong PowerPoint với Python. Bằng cách tích hợp tính năng này vào bài thuyết trình của bạn, bạn có thể đạt được giao diện chuyên nghiệp và bóng bẩy.

**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho Python
- Tạo danh sách dấu đầu dòng được đánh số tùy chỉnh
- Cấu hình cài đặt bullet theo chương trình
- Tối ưu hóa hiệu suất và khắc phục sự cố thường gặp

Bắt đầu thôi! Hãy đảm bảo bạn đã chuẩn bị mọi thứ sẵn sàng để tiến hành.

## Điều kiện tiên quyết
Trước khi triển khai các dấu đầu dòng được đánh số tùy chỉnh với Aspose.Slides cho Python, hãy đảm bảo bạn có:

### Thư viện bắt buộc:
- **Aspose.Slides cho Python**: Một thư viện mạnh mẽ để tạo và chỉnh sửa các bài thuyết trình PowerPoint.

### Thiết lập môi trường:
- Python 3.x được cài đặt trên hệ thống của bạn.
- Hiểu biết cơ bản về các khái niệm lập trình Python rất hữu ích nhưng không bắt buộc.

## Thiết lập Aspose.Slides cho Python
Để bắt đầu, hãy cài đặt `aspose.slides` thư viện sử dụng pip:

```bash
pip install aspose.slides
```

### Mua giấy phép:
Aspose.Slides là một sản phẩm thương mại cung cấp bản dùng thử miễn phí để kiểm tra khả năng của nó. Bạn có thể mua giấy phép tạm thời hoặc mua một giấy phép để tiếp tục sử dụng.

- **Dùng thử miễn phí**: Truy cập chức năng cơ bản mà không có giới hạn.
- **Giấy phép tạm thời**: Yêu cầu trên trang web Aspose để có quyền truy cập đầy đủ tạm thời.
- **Mua**:Cân nhắc việc mua giấy phép cho các dự án dài hạn.

### Khởi tạo cơ bản:
Sau khi cài đặt, hãy khởi tạo bản trình bày của bạn như sau:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Mã của bạn ở đây...
```

Thiết lập này chuẩn bị môi trường để thêm các dấu đầu dòng được đánh số tùy chỉnh vào trang chiếu PowerPoint của bạn.

## Hướng dẫn thực hiện
Hãy cùng tìm hiểu cách tạo danh sách dấu đầu dòng được đánh số tùy chỉnh. Mỗi bước được chia nhỏ để rõ ràng và dễ thực hiện.

### Thêm hình chữ nhật với khung văn bản
#### Tổng quan:
Đầu tiên, thêm một hình dạng chứa khung văn bản cho các dấu đầu dòng.

```python
# Thêm hình chữ nhật vào slide đầu tiên
shape = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 200, 200, 400, 200)
```
- **Giải thích các thông số**: Các `add_auto_shape` phương pháp này lấy các tham số cho loại hình dạng (hình chữ nhật), vị trí (tọa độ x và y) và kích thước (chiều rộng và chiều cao).

### Cấu hình khung văn bản
#### Tổng quan:
Truy cập vào khung văn bản của hình chữ nhật để thêm dấu đầu dòng.

```python
# Truy cập vào khung văn bản của hình dạng tự động đã tạo
text_frame = shape.text_frame

# Xóa bất kỳ đoạn văn mặc định nào hiện có nếu có
text_frame.paragraphs.clear()
```
- **Mục đích**: Đảm bảo nội dung sạch sẽ trước khi thêm các dấu đầu dòng tùy chỉnh.

### Thêm dấu đầu dòng được đánh số tùy chỉnh
#### Tổng quan:
Thêm đoạn văn với cài đặt dấu đầu dòng cụ thể:

```python
# Thêm đoạn văn với các dấu đầu dòng được đánh số tùy chỉnh
for start_number, bullet_text in [(2, "bullet 2"), (3, "bullet 3"), (7, "bullet 7")]:
    paragraph = slides.Paragraph()
    paragraph.text = bullet_text
    paragraph.paragraph_format.depth = 4
    paragraph.paragraph_format.bullet.numbered_bullet_start_with = start_number
    paragraph.paragraph_format.bullet.type = slides.BulletType.NUMBERED
    text_frame.paragraphs.add(paragraph)
```
- **Cấu hình**:Mỗi đoạn văn bắt đầu bằng một số cụ thể, mang lại sự linh hoạt và khả năng kiểm soát định dạng bài thuyết trình.

### Lưu bài thuyết trình
Cuối cùng, hãy lưu bản trình bày đã cấu hình của bạn:

```python
# Lưu bản trình bày\presentation.save("YOUR_OUTPUT_DIRECTORY/text_set_custom_bullets_number_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}