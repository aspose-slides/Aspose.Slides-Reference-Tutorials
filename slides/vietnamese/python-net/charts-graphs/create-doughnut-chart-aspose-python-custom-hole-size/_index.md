---
"date": "2025-04-22"
"description": "Tìm hiểu cách tạo và tùy chỉnh biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides for Python. Hướng dẫn này bao gồm cách thiết lập kích thước lỗ, lưu bản trình bày và các phương pháp hay nhất."
"title": "Cách tạo biểu đồ hình bánh rán trong PowerPoint với kích thước lỗ tùy chỉnh bằng Aspose.Slides cho Python"
"url": "/vi/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ hình bánh rán trong PowerPoint với kích thước lỗ tùy chỉnh bằng Aspose.Slides cho Python

## Giới thiệu
Tạo biểu đồ hấp dẫn trực quan trong PowerPoint có thể giúp dữ liệu của bạn hấp dẫn hơn và dễ hiểu hơn. Một thách thức phổ biến là thiếu tùy chọn tùy chỉnh khi tạo các biểu đồ này theo chương trình. Hướng dẫn này giải quyết vấn đề này bằng cách trình bày cách tạo biểu đồ hình tròn có kích thước lỗ tùy chỉnh bằng Aspose.Slides for Python.

**Từ khóa:** Aspose.Slides Python, Biểu đồ hình tròn, Kích thước lỗ tùy chỉnh

### Những gì bạn sẽ học được:
- Thiết lập và sử dụng Aspose.Slides cho Python
- Tạo biểu đồ hình tròn trong PowerPoint
- Tùy chỉnh kích thước lỗ của biểu đồ bánh rán của bạn
- Thực hành tốt nhất để lưu và xuất bản bài thuyết trình

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có:
- **Python 3.x** được cài đặt trên hệ thống của bạn.
- Kiến thức cơ bản về các khái niệm lập trình Python.
- Các `aspose.slides` thư viện (hướng dẫn cài đặt được cung cấp bên dưới).

## Thiết lập Aspose.Slides cho Python
Để bắt đầu, hãy cài đặt Aspose.Slides cho Python bằng pip:

```bash
pip install aspose.slides
```

### Mua lại giấy phép
Aspose cung cấp bản dùng thử miễn phí cho phép bạn khám phá các tính năng của nó mà không giới hạn số lượng tài liệu hoặc thời gian sử dụng:
- **Dùng thử miễn phí:** Bắt đầu với giấy phép tạm thời để kiểm tra đầy đủ khả năng.
- **Giấy phép tạm thời:** Có sẵn cho mục đích đánh giá.
- **Mua:** Để sử dụng lâu dài, hãy cân nhắc việc mua giấy phép.

Sau khi cài đặt và thiết lập, bạn có thể bắt đầu tạo bài thuyết trình theo chương trình. Sau đây là cách khởi tạo Aspose.Slides:

```python
import aspose.slides as slides

# Khởi tạo một đối tượng trình bày
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # Mã của bạn ở đây
```

## Hướng dẫn thực hiện
Phần này trình bày các bước cần thiết để tạo và tùy chỉnh biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides.

### Bước 1: Truy cập và chỉnh sửa Slide
Để bắt đầu, hãy truy cập trang trình bày đầu tiên của bạn. Đây là nơi bạn sẽ thêm biểu đồ hình tròn tùy chỉnh của mình.

```python
# Truy cập trang chiếu đầu tiên
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### Bước 2: Thêm biểu đồ hình tròn
Bạn có thể thêm biểu đồ hình tròn vào bất kỳ slide nào bằng cách chỉ định vị trí và kích thước của nó. Ở đây, chúng tôi sẽ đặt nó ở tọa độ (50, 50) với kích thước 400x400.

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # Thêm biểu đồ hình tròn
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### Bước 3: Tùy chỉnh kích thước lỗ
Việc điều chỉnh kích thước lỗ của biểu đồ hình bánh rán của bạn rất đơn giản. Đặt thành 90% để có hiệu ứng rõ rệt.

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # Đặt kích thước lỗ tùy chỉnh
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### Bước 4: Lưu bài thuyết trình của bạn
Cuối cùng, lưu bài thuyết trình của bạn vào vị trí mong muốn với tên tệp đã chọn.

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # Lưu bài thuyết trình
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## Ứng dụng thực tế
Việc tạo biểu đồ hình tròn tùy chỉnh có thể hữu ích trong nhiều trường hợp, bao gồm:
- **Báo cáo kinh doanh:** Làm nổi bật các chỉ số hiệu suất chính bằng các phân đoạn trực quan rõ ràng.
- **Nội dung giáo dục:** Minh họa dữ liệu thống kê cho sinh viên hoặc đồng nghiệp.
- **Tài liệu tiếp thị:** Hiển thị thông tin chi tiết về sản phẩm hoặc thông tin nhân khẩu học của khách hàng.

Có thể tích hợp với các hệ thống khác bằng cách xuất biểu đồ dưới dạng hình ảnh hoặc nhúng chúng vào các ứng dụng web bằng API toàn diện của Aspose.

## Cân nhắc về hiệu suất
Khi làm việc với Aspose.Slides, hãy cân nhắc những mẹo sau để có hiệu suất tối ưu:
- Giảm thiểu việc sử dụng tài nguyên bằng cách chỉ tải những slide cần thiết.
- Quản lý bộ nhớ hiệu quả bằng cách kết thúc bài thuyết trình ngay sau khi sử dụng.
- Sử dụng xử lý hàng loạt để tạo nhiều biểu đồ cùng một lúc.

Việc thực hiện các biện pháp tốt nhất sẽ đảm bảo ứng dụng của bạn chạy trơn tru và hiệu quả.

## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo biểu đồ hình bánh rán với kích thước lỗ tùy chỉnh trong PowerPoint bằng Aspose.Slides for Python. Điều này không chỉ tăng cường sức hấp dẫn trực quan cho bài thuyết trình của bạn mà còn cho phép tính linh hoạt hơn trong việc biểu diễn dữ liệu.

Để khám phá thêm các khả năng của Aspose.Slides, hãy cân nhắc thử nghiệm các loại biểu đồ và tính năng trình bày khác. Chúc bạn viết mã vui vẻ!

## Phần Câu hỏi thường gặp
1. **Kích thước lỗ tối đa tôi có thể đặt cho biểu đồ hình tròn là bao nhiêu?**
   - Bạn có thể thiết lập tới 100% cho biểu đồ hình tròn đầy đủ.
2. **Tôi có thể sửa đổi biểu đồ hiện có trong tệp PowerPoint bằng Aspose.Slides không?**
   - Có, bạn có thể tải và chỉnh sửa các bài thuyết trình hiện có.
3. **Tôi phải xử lý lỗi như thế nào khi lưu bài thuyết trình?**
   - Đảm bảo đường dẫn đầu ra có thể ghi được và kiểm tra các vấn đề về quyền.
4. **Có hỗ trợ cho các loại biểu đồ khác ngoài biểu đồ hình tròn không?**
   - Hoàn toàn có thể, Aspose.Slides hỗ trợ nhiều loại biểu đồ khác nhau.
5. **Aspose.Slides có thể sử dụng với các ứng dụng web không?**
   - Có, API của nó có thể được tích hợp vào các hệ thống phụ trợ và cung cấp thông qua các dịch vụ web.

## Tài nguyên
- [Tài liệu](https://reference.aspose.com/slides/python-net/)
- [Tải về](https://releases.aspose.com/slides/python-net/)
- [Mua](https://purchase.aspose.com/buy)
- [Dùng thử miễn phí](https://releases.aspose.com/slides/python-net/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}