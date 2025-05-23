---
"date": "2025-04-23"
"description": "Tìm hiểu cách tùy chỉnh màu siêu liên kết trong bản trình bày PowerPoint bằng Aspose.Slides for Python. Cải thiện slide của bạn bằng các kiểu liên kết được cá nhân hóa một cách hiệu quả."
"title": "Cách thiết lập màu siêu liên kết trong PowerPoint bằng Aspose.Slides cho Python"
"url": "/vi/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thiết lập màu siêu liên kết trong PowerPoint bằng Aspose.Slides cho Python

## Giới thiệu

Tăng cường sức hấp dẫn trực quan cho bài thuyết trình PowerPoint của bạn bằng cách tùy chỉnh màu siêu liên kết thật đơn giản với Aspose.Slides for Python. Hướng dẫn này sẽ hướng dẫn bạn cách thiết lập siêu liên kết với màu sắc cụ thể trong slide của bạn bằng Python.

**Những gì bạn sẽ học được:**
- Cách đặt màu siêu liên kết trong hình dạng văn bản trong PowerPoint.
- Các bước để tạo ra một bài thuyết trình hấp dẫn về mặt hình ảnh.
- Các tính năng chính của Aspose.Slides for Python giúp việc tùy chỉnh này dễ dàng hơn.

Chúng ta hãy cùng tìm hiểu những điều kiện tiên quyết cần thiết trước khi bắt đầu.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo môi trường của bạn đã sẵn sàng với những điều sau:
- **Thư viện và Phiên bản:** Cài đặt `aspose.slides` thư viện. Đảm bảo Python được cài đặt trên máy của bạn.
- **Yêu cầu thiết lập môi trường:** Hướng dẫn này giả định bạn đã thiết lập Python cơ bản trên Windows, Mac hoặc Linux.
- **Điều kiện tiên quyết về kiến thức:** Sự quen thuộc với lập trình Python sẽ có lợi.

## Thiết lập Aspose.Slides cho Python

Để bắt đầu sử dụng Aspose.Slides cho Python, hãy cài đặt gói thông qua pip:

```bash
pip install aspose.slides
```

**Các bước xin cấp giấy phép:**
- **Dùng thử miễn phí:** Tải xuống phiên bản dùng thử từ [Trang phát hành của Aspose](https://releases.aspose.com/slides/python-net/).
- **Giấy phép tạm thời:** Yêu cầu cấp giấy phép tạm thời trên [trang mua hàng](https://purchase.aspose.com/temporary-license/) để mở rộng quyền truy cập.
- **Mua:** Để mở khóa đầy đủ các tính năng mà không có giới hạn, hãy cân nhắc mua giấy phép từ [Trang mua hàng của Aspose](https://purchase.aspose.com/buy).

**Khởi tạo cơ bản:**
Sau khi cài đặt và cấp phép, hãy nhập Aspose.Slides vào tập lệnh của bạn:

```python
import aspose.slides as slides
```

## Hướng dẫn thực hiện

Phần này hướng dẫn bạn cách thiết lập màu siêu liên kết trong bản trình bày PowerPoint.

### Thiết lập tính năng màu siêu liên kết

#### Tổng quan

Tùy chỉnh màu của siêu liên kết được nhúng trong hình dạng văn bản bằng Aspose.Slides for Python. Điều này giúp tăng khả năng đọc và tính hấp dẫn trực quan.

##### Bước 1: Tạo một bài thuyết trình mới

Tạo một phiên bản trình bày:

```python
with slides.Presentation() as presentation:
    # Mã của bạn ở đây
```

##### Bước 2: Thêm hình dạng có văn bản

Thêm hình chữ nhật vào trang chiếu đầu tiên và chèn văn bản có chứa siêu liên kết.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Bước 3: Thiết lập Thuộc tính Siêu liên kết

Chỉ định siêu liên kết và thiết lập màu sắc của nó. `hyperlink_click` thuộc tính này chỉ rõ liên kết sẽ điều hướng đến đâu khi nhấp vào.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Đặt nguồn màu cho siêu liên kết thành định dạng phần và xác định kiểu tô và màu.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Bước 4: Lưu bài thuyết trình

Lưu bài thuyết trình của bạn vào một thư mục được chỉ định:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}