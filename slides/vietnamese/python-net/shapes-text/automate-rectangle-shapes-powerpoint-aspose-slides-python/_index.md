---
"date": "2025-04-23"
"description": "Tìm hiểu cách tự động tạo và định dạng hình chữ nhật trong PowerPoint bằng Aspose.Slides for Python. Nâng cao kỹ năng thuyết trình của bạn một cách dễ dàng."
"title": "Tự động hóa hình chữ nhật trong PowerPoint bằng Aspose.Slides cho Python"
"url": "/vi/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo và định dạng hình chữ nhật trong PowerPoint bằng Aspose.Slides cho Python
## Giới thiệu
Bạn đã bao giờ thấy mình cần nhanh chóng thêm các hình dạng tùy chỉnh vào bản trình bày PowerPoint nhưng lại gặp khó khăn vì thiếu tính năng tự động hóa chưa? Nếu bạn đã chán việc định dạng thủ công các hình chữ nhật theo từng slide, thì hướng dẫn này sẽ giúp bạn giải quyết vấn đề này. Tận dụng "Aspose.Slides for Python", chúng tôi sẽ tự động thêm và tạo kiểu cho hình chữ nhật chỉ trong vài dòng mã. Đến cuối hướng dẫn này, bạn sẽ thành thạo:
- Tạo hình chữ nhật theo chương trình
- Áp dụng các tùy chọn định dạng như màu sắc và kiểu đường kẻ
- Lưu bài thuyết trình của bạn một cách dễ dàng
Hãy cùng tìm hiểu cách bạn có thể thay đổi quy trình tạo slide của mình!
### Điều kiện tiên quyết
Trước khi bắt đầu viết mã, hãy đảm bảo bạn đã chuẩn bị những thứ sau:
- **Trăn** được cài đặt trên máy của bạn (khuyến nghị phiên bản 3.6 trở lên)
- **Aspose.Slides cho Python** thư viện, cho phép chúng ta thao tác các bài thuyết trình PowerPoint
- Hiểu biết cơ bản về các khái niệm lập trình Python và quen thuộc với việc cài đặt các gói bằng pip
## Thiết lập Aspose.Slides cho Python
### Cài đặt
Để cài đặt gói Aspose.Slides, hãy mở terminal hoặc dấu nhắc lệnh và chạy:
```bash
pip install aspose.slides
```
Lệnh này sẽ tải và cài đặt phiên bản mới nhất của Aspose.Slides cho Python từ PyPI.
### Mua lại giấy phép
Aspose.Slides là một sản phẩm thương mại, nhưng bạn có thể bắt đầu sử dụng bằng cách dùng thử miễn phí. Sau đây là cách để có được một sản phẩm:
1. **Dùng thử miễn phí:** Thăm nom [Dùng thử miễn phí Aspose](https://releases.aspose.com/slides/python-net/) và đăng ký để được đánh giá.
2. **Giấy phép tạm thời:** Để thử nghiệm rộng rãi hơn mà không có giới hạn, hãy yêu cầu giấy phép tạm thời tại [Trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
3. **Mua:** Khi bạn đã sẵn sàng để hoạt động, hãy mua giấy phép thông qua [Trang mua hàng Aspose](https://purchase.aspose.com/buy).
Sau khi có được giấy phép, hãy làm theo hướng dẫn để áp dụng giấy phép vào dự án của bạn.
### Khởi tạo cơ bản
Sau đây là cách bạn có thể khởi tạo Aspose.Slides cho Python:
```python
import aspose.slides as slides
\# Khởi tạo lớp Presentation
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
Đoạn mã này thiết lập một bản trình bày mới và xác nhận rằng nó đã sẵn sàng để thao tác.
## Hướng dẫn thực hiện
### Tạo hình chữ nhật
#### Tổng quan
Trong phần này, chúng ta sẽ tập trung vào việc thêm hình chữ nhật vào slide PowerPoint bằng Aspose.Slides for Python.
#### Các bước để tạo hình dạng
1. **Mở hoặc tạo một Bài thuyết trình:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # Chúng ta sẽ thêm hình chữ nhật của chúng ta ở đây
   ```
2. **Truy cập vào Slide:**
   Lấy lại trang chiếu đầu tiên mà chúng ta muốn thêm hình dạng.
   ```python
   slide = pres.slides[0]
   ```
3. **Thêm hình chữ nhật:**
   Sử dụng `add_auto_shape` phương pháp tạo hình chữ nhật trên slide.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - Các thông số: `ShapeType.RECTANGLE`, vị trí x (50), vị trí y (150), chiều rộng (150), chiều cao (50).
### Định dạng hình chữ nhật
#### Tổng quan
Tiếp theo, chúng ta sẽ áp dụng định dạng cho hình chữ nhật, bao gồm màu tô và kiểu đường kẻ.
#### Các bước định dạng
1. **Tô màu:**
   Đặt màu tô đặc với màu cụ thể cho phần nền của hình chữ nhật.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **Kiểu đường kẻ:**
   Tùy chỉnh đường viền của hình chữ nhật, bao gồm màu sắc và chiều rộng của đường viền.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **Lưu bài thuyết trình:**
   Cuối cùng, lưu bài thuyết trình vào một tập tin.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}