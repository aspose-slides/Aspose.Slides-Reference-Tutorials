---
"date": "2025-04-23"
"description": "Tìm hiểu cách tùy chỉnh thang trục biểu đồ bằng Aspose.Slides trong Python, với các bước chi tiết và ví dụ mã."
"title": "Cách đặt tỷ lệ trục biểu đồ thành NONE trong Aspose.Slides cho Python (Biểu đồ & Đồ thị)"
"url": "/vi/python-net/charts-graphs/aspose-slides-python-chart-axis-scale-none/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách đặt tỷ lệ trục biểu đồ thành NONE bằng Aspose.Slides Python
## Giới thiệu
Việc tạo ra các biểu đồ hấp dẫn về mặt thị giác thường đòi hỏi phải tinh chỉnh tỷ lệ trục của chúng. Hướng dẫn này trình bày cách thiết lập tỷ lệ đơn vị chính của trục ngang thành `NONE` để tạo biểu đồ bằng Aspose.Slides trong Python, hoàn hảo để tùy chỉnh hình ảnh dữ liệu trong bài thuyết trình của bạn.
**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho Python.
- Tạo và tùy chỉnh biểu đồ với cấu hình trục cụ thể.
- Lưu bài thuyết trình theo chương trình.
- Khắc phục các sự cố thường gặp khi làm việc với trục biểu đồ.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
### Thư viện bắt buộc
- **Aspose.Slides cho Python**: Cài đặt qua pip. Yêu cầu Python 3.x trở lên.
### Thiết lập môi trường
- Cài đặt Python từ [python.org](https://www.python.org/).
- Sử dụng trình soạn thảo mã như VSCode hoặc PyCharm.
### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình Python.
- Sự quen thuộc với việc xử lý các bài thuyết trình và biểu đồ sẽ hữu ích nhưng không bắt buộc.

## Thiết lập Aspose.Slides cho Python
Để sử dụng Aspose.Slides trong các dự án của bạn:
**Cài đặt:**
```bash
pip install aspose.slides
```
### Các bước xin cấp giấy phép
- **Dùng thử miễn phí**: Tải xuống phiên bản dùng thử để kiểm tra tính năng.
- **Giấy phép tạm thời**: Xin giấy phép tạm thời để thử nghiệm mở rộng.
- **Mua**: Mua giấy phép đầy đủ để truy cập lâu dài.

**Khởi tạo cơ bản:**
```python
import aspose.slides as slides
```
Thao tác này sẽ nhập tất cả các chức năng của Aspose.Slides.

## Hướng dẫn thực hiện
### Tạo biểu đồ với tỷ lệ trục tùy chỉnh
#### Tổng quan
Chúng tôi sẽ tạo biểu đồ kiểu DIỆN TÍCH và thiết lập thang đơn vị chính theo trục ngang của nó thành `NONE`.
**Bước 1: Khởi tạo bài thuyết trình**
Bắt đầu bằng cách tạo một phiên bản trình bày mới:
```python
with slides.Presentation() as pres:
    # Các hoạt động tiếp theo sẽ được thực hiện ở đây.
```
Trình quản lý ngữ cảnh này đảm bảo quản lý tài nguyên hiệu quả.
#### Bước 2: Thêm biểu đồ
Thêm biểu đồ kiểu DIỆN TÍCH vào trang chiếu của bạn theo tọa độ và kích thước cụ thể:
```python
chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.AREA, 10, 10, 400, 300, True)
```
Thao tác này sẽ thêm một biểu đồ có kích thước 400x300 pixel ở vị trí (10, 10) trên trang chiếu đầu tiên.
#### Bước 3: Đặt Tỷ lệ trục thành NONE
Sửa đổi thang đo đơn vị chính theo trục ngang:
```python
chart.axes.horizontal_axis.major_unit_scale = slides.charts.TimeUnitType.NONE
```
Thiết lập thuộc tính này sẽ xóa các khoảng tỷ lệ được xác định trước dọc theo trục x.
#### Bước 4: Lưu bài thuyết trình
Lưu những thay đổi của bạn vào một tệp có định dạng PPTX:
```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_time_unit_type_enum_out.pptx", slides.export.SaveFormat.PPTX)
```
Thao tác này sẽ lưu biểu đồ tùy chỉnh của bạn trong một tệp trình bày mới.
### Mẹo khắc phục sự cố
- Đảm bảo `aspose.slides` gói được cài đặt đúng cách. Sử dụng `pip show aspose.slides` để xác minh.
- Kiểm tra xem thư mục đầu ra có tồn tại và có quyền ghi phù hợp không.

## Ứng dụng thực tế
Việc thiết lập tỷ lệ trục có thể hữu ích trong:
1. **Báo cáo tài chính**: Tập trung vào các khung thời gian hoặc điểm dữ liệu cụ thể mà không có khoảng thời gian được xác định trước.
2. **Bài thuyết trình khoa học**: Kiểm soát chính xác hình ảnh hóa dữ liệu cho các phát hiện nghiên cứu.
3. **Phân tích tiếp thị**: Làm nổi bật các số liệu quan trọng bằng cách loại bỏ các thông số gây mất tập trung.

## Cân nhắc về hiệu suất
Khi làm việc với Aspose.Slides:
- Sử dụng trình quản lý ngữ cảnh (`with` các câu lệnh) để quản lý tài nguyên một cách hiệu quả.
- Xử lý dữ liệu hiệu quả trong Python để giảm thiểu mức tiêu thụ bộ nhớ.
- Cập nhật phiên bản thư viện thường xuyên để cải thiện hiệu suất và sửa lỗi.

## Phần kết luận
Bạn đã học cách tùy chỉnh thang trục biểu đồ bằng Aspose.Slides for Python, tăng cường độ rõ nét của bản trình bày. Khám phá các tính năng khác như điều khiển hoạt ảnh để nâng cao hơn nữa bản trình bày của bạn.
**Các bước tiếp theo:**
Triển khai giải pháp này vào một dự án để cải thiện khả năng trình bày dữ liệu!

## Phần Câu hỏi thường gặp
1. **Làm thế nào để cập nhật Aspose.Slides?**
   - Sử dụng `pip install --upgrade aspose.slides`.
2. **Tôi có thể đặt cả tỷ lệ trục ngang và trục dọc thành NONE không?**
   - Có, sử dụng `chart.axes.vertical_axis.major_unit_scale = slides.charts.TimeUnitType.NONE`.
3. **Nếu biểu đồ của tôi không lưu đúng cách thì sao?**
   - Kiểm tra đường dẫn tệp và đảm bảo thư mục đầu ra của bạn có thể ghi được.
4. **Có cách nào để xem trước những thay đổi trước khi lưu không?**
   - Aspose.Slides không cung cấp tính năng xem trước trực tiếp, nhưng sẽ lặp lại với các tập lệnh nhỏ hơn cho đến khi hài lòng.
5. **Tôi phải xử lý các loại biểu đồ khác nhau như thế nào?**
   - Thay thế `ChartType.AREA` với các loại khác như `Bar`, `Line`, v.v., khi cần thiết.

## Tài nguyên
- [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Tải xuống Aspose.Slides cho Python](https://releases.aspose.com/slides/python-net/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Dùng thử miễn phí](https://releases.aspose.com/slides/python-net/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}