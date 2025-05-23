---
"date": "2025-04-23"
"description": "Tìm hiểu cách tự động tạo đồ họa SmartArt trong bản trình bày PowerPoint bằng Aspose.Slides cho Python, bao gồm trích xuất và lưu hình thu nhỏ hiệu quả."
"title": "Cách tạo và lấy hình thu nhỏ SmartArt bằng Aspose.Slides cho Python"
"url": "/vi/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo và lấy hình thu nhỏ SmartArt bằng Aspose.Slides cho Python

## Giới thiệu

Tạo các bài thuyết trình hấp dẫn về mặt hình ảnh là điều cần thiết để thu hút sự chú ý của khán giả. Một cách hiệu quả để cải thiện các slide là kết hợp đồ họa động như SmartArt vào các bài thuyết trình PowerPoint. Nếu bạn đang tìm kiếm một phương pháp tự động để tạo các hình ảnh này và trích xuất hình thu nhỏ từ chúng, hướng dẫn này về "Aspose.Slides Python" sẽ vô cùng hữu ích.

Sử dụng Aspose.Slides for Python, bạn có thể dễ dàng tạo đồ họa SmartArt, truy cập các nút cụ thể trong đồ họa, lấy hình thu nhỏ của các nút đó và lưu những hình ảnh này cho các dự án của bạn. Hướng dẫn này sẽ hướng dẫn bạn từng bước chi tiết.

**Những gì bạn sẽ học được:**
- Cách cài đặt và thiết lập Aspose.Slides cho Python.
- Tạo đồ họa SmartArt trong bản trình bày PowerPoint.
- Truy cập các nút trong đồ họa SmartArt.
- Trích xuất và lưu hình ảnh thu nhỏ từ một nút cụ thể.

Chúng ta hãy cùng tìm hiểu các điều kiện tiên quyết trước khi bắt đầu.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị sẵn những thứ sau:

- **Thư viện bắt buộc:** Bạn sẽ cần Aspose.Slides cho Python. Đảm bảo rằng môi trường của bạn hỗ trợ Python 3.x.
- **Yêu cầu thiết lập môi trường:** Cài đặt Python và IDE hoặc trình soạn thảo văn bản phù hợp như VSCode hoặc PyCharm.
- **Điều kiện tiên quyết về kiến thức:** Hiểu biết cơ bản về lập trình Python, bao gồm định nghĩa hàm và thao tác với tệp.

## Thiết lập Aspose.Slides cho Python

Trước tiên, bạn cần cài đặt thư viện Aspose.Slides. Điều này có thể dễ dàng thực hiện bằng pip:

```bash
pip install aspose.slides
```

Sau khi cài đặt, hãy lấy giấy phép nếu bạn muốn khám phá tất cả các tính năng mà không bị giới hạn. Bạn có thể bắt đầu bằng bản dùng thử miễn phí, đăng ký giấy phép tạm thời hoặc mua để sử dụng lâu dài.

Để khởi tạo Aspose.Slides trong môi trường Python của bạn, hãy nhập thư viện vào đầu tập lệnh:

```python
import aspose.slides as slides
```

## Hướng dẫn thực hiện

Chúng ta hãy chia nhỏ quy trình thành các bước rõ ràng để tạo và lấy hình thu nhỏ SmartArt.

### Bước 1: Tạo một phiên bản trình bày mới

Bắt đầu bằng cách tạo một phiên bản trình bày. Đây sẽ là nơi chứa đồ họa SmartArt của bạn.

```python
with slides.Presentation() as pres:
```

Sử dụng `with` đảm bảo rằng các tài nguyên được quản lý đúng cách, tự động lưu và đóng tệp khi thoát.

### Bước 2: Thêm SmartArt vào Slide đầu tiên

Tiếp theo, chúng ta sẽ thêm đồ họa SmartArt vào slide đầu tiên. Đây là cách bạn có thể thực hiện:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Thao tác này sẽ thêm một bố cục chu kỳ cơ bản cho đồ họa SmartArt ở vị trí (10, 10) với kích thước 400x300 pixel.

### Bước 3: Truy cập vào nút thứ hai

Truy cập các nút cụ thể trong SmartArt của bạn. Trong ví dụ này, chúng ta truy cập nút thứ hai:

```python
node = smart.nodes[1]
```

Các nút được lập chỉ mục bắt đầu từ số không; do đó, `nodes[1]` đề cập đến nút thứ hai trong danh sách.

### Bước 4: Lấy lại hình ảnh thu nhỏ

Để có được hình ảnh thu nhỏ của hình dạng bên trong nút đã chọn:

```python
image = node.shapes[0].get_image()
```

Thao tác này sẽ lấy hình ảnh của hình dạng đầu tiên dưới dạng hình thu nhỏ từ nút SmartArt đã chỉ định.

### Bước 5: Lưu hình ảnh đã lấy được

Cuối cùng, lưu hình thu nhỏ này vào vị trí mong muốn ở định dạng JPEG:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}