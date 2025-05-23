---
"date": "2025-04-22"
"description": "Tìm hiểu cách tùy chỉnh các thuộc tính phông chữ chú giải biểu đồ bằng Aspose.Slides for Python. Cải thiện bài thuyết trình của bạn bằng phông chữ đậm, nghiêng và màu cho từng mục chú giải."
"title": "Tùy chỉnh phông chữ chú giải biểu đồ bằng Aspose.Slides cho Python&#58; Hướng dẫn toàn diện"
"url": "/vi/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tùy chỉnh phông chữ chú thích biểu đồ trong bài thuyết trình bằng Aspose.Slides cho Python

## Giới thiệu
Tạo các bài thuyết trình hấp dẫn về mặt thị giác là điều cần thiết, đặc biệt là khi hiển thị dữ liệu thông qua biểu đồ. Một thách thức phổ biến là tùy chỉnh chú giải biểu đồ để phù hợp với phong cách trình bày hoặc nhu cầu xây dựng thương hiệu của bạn. Hướng dẫn này trình bày cách tùy chỉnh các thuộc tính phông chữ như độ đậm, độ nghiêng, kích thước và màu sắc cho từng mục chú giải trong biểu đồ bằng Aspose.Slides for Python.

**Những gì bạn sẽ học được:**
- Thiết lập và sử dụng Aspose.Slides cho Python
- Tùy chỉnh các thuộc tính phông chữ của chú giải biểu đồ
- Áp dụng các kiểu phông chữ cụ thể như in đậm, in nghiêng và thay đổi màu sắc
- Ví dụ thực tế về việc tăng cường biểu đồ bằng phông chữ tùy chỉnh

Hãy cùng khám phá cách bạn có thể thực hiện được tùy chỉnh này.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:
- **Thư viện**: Aspose.Slides cho Python. Cài đặt bằng pip.
- **Môi trường**: Môi trường Python (tốt nhất là Python 3.x) được thiết lập trên máy của bạn.
- **Kiến thức**Hiểu biết cơ bản về lập trình Python và quen thuộc với việc xử lý các bài thuyết trình theo chương trình.

## Thiết lập Aspose.Slides cho Python
### Cài đặt
Để bắt đầu, hãy cài đặt thư viện Aspose.Slides bằng cách chạy lệnh sau trong terminal của bạn:

```bash
pip install aspose.slides
```

### Mua lại giấy phép
Aspose.Slides là một sản phẩm thương mại có nhiều tùy chọn cấp phép khác nhau:
- **Dùng thử miễn phí**: Xin giấy phép tạm thời để sử dụng đầy đủ chức năng.
- **Giấy phép tạm thời**: Xin giấy phép tạm thời để thử nghiệm tất cả các tính năng mà không có giới hạn.
- **Mua**: Mua gói đăng ký hoặc giấy phép vĩnh viễn dựa trên nhu cầu của bạn.

### Khởi tạo cơ bản
Sau đây là cách bạn có thể khởi tạo và thiết lập Aspose.Slides trong tập lệnh Python của mình:

```python
import aspose.slides as slides

# Khởi tạo một phiên bản trình bày\với slides.Presentation() như sau:
    # Mã của bạn ở đây
```

## Hướng dẫn thực hiện
Trong phần này, chúng tôi sẽ hướng dẫn cách tùy chỉnh thuộc tính phông chữ của từng mục chú giải.

### Thêm và Truy cập Biểu đồ
Đầu tiên, hãy thêm biểu đồ cột nhóm vào trang chiếu của bạn:

```python
# Thêm biểu đồ cột nhóm tại vị trí (50, 50) với chiều rộng 600 và chiều cao 400
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # Đây chỉ là chỗ giữ chỗ cho phương thức Aspose.Slides thực tế.
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# Mô phỏng pres.slides[0].shapes
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### Tùy chỉnh Thuộc tính Phông chữ Chú giải
#### Truy cập Định dạng Văn bản của Mục nhập Chú giải
Để sửa đổi thuộc tính phông chữ của một mục chú giải cụ thể:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# Mô phỏng biểu đồ.legend.entries[1].text_format
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### Thiết lập Thuộc tính Phông chữ
Tại đây, chúng tôi tùy chỉnh các khía cạnh như độ đậm, kích thước, chữ nghiêng và màu sắc:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# Đặt kích thước phông chữ thành 20 điểm
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# Đặt màu phông chữ thành màu xanh lam bằng cách sử dụng kiểu tô đặc
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### Lưu bài thuyết trình
Cuối cùng, hãy lưu bài thuyết trình của bạn với những tùy chỉnh sau:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}