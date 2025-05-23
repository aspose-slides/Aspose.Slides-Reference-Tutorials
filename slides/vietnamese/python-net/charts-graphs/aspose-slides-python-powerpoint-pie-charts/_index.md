---
"date": "2025-04-22"
"description": "Tìm hiểu cách tạo và tùy chỉnh biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides for Python. Nâng cao bài thuyết trình của bạn bằng thông tin chi tiết dựa trên dữ liệu."
"title": "Tạo biểu đồ hình tròn PowerPoint hấp dẫn với Aspose.Slides cho Python | Hướng dẫn biểu đồ & đồ thị"
"url": "/vi/python-net/charts-graphs/aspose-slides-python-powerpoint-pie-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ hình tròn PowerPoint với Aspose.Slides cho Python

**Loại:** Biểu đồ & Đồ thị

Tạo các bài thuyết trình hấp dẫn và nhiều thông tin là chìa khóa để truyền đạt hiệu quả những hiểu biết dựa trên dữ liệu. Nếu bạn đang tìm cách cải thiện các slide PowerPoint của mình bằng cách kết hợp các biểu đồ hình tròn hấp dẫn về mặt thị giác, **Aspose.Slides cho Python** thư viện là một công cụ tuyệt vời giúp đơn giản hóa quá trình này. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách tạo biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides for Python.

## Những gì bạn sẽ học được:
- Cài đặt và thiết lập Aspose.Slides cho Python
- Tạo biểu đồ hình tròn cơ bản trong slide PowerPoint
- Tùy chỉnh biểu đồ hình tròn của bạn với các điểm dữ liệu, màu sắc, đường viền, nhãn, đường dẫn và xoay
- Tối ưu hóa hiệu suất khi làm việc với biểu đồ

Hãy cùng tìm hiểu các bước cần thiết để bắt đầu.

## Điều kiện tiên quyết

Trước khi triển khai mã, hãy đảm bảo bạn có những điều sau:
- Python được cài đặt trên hệ thống của bạn (khuyến nghị phiên bản 3.6 trở lên)
- `pip` trình quản lý gói để cài đặt thư viện
- Hiểu biết cơ bản về lập trình Python và thuyết trình PowerPoint

## Thiết lập Aspose.Slides cho Python

Để bắt đầu làm việc với Aspose.Slides cho Python, bạn cần cài đặt thư viện bằng pip:

```bash
pip install aspose.slides
```

**Mua giấy phép:**
Bạn có thể bắt đầu bằng cách tải xuống giấy phép dùng thử miễn phí từ [Trang tải xuống của Aspose](https://releases.aspose.com/slides/python-net/). Để sử dụng rộng rãi hơn, hãy cân nhắc mua giấy phép đầy đủ hoặc xin giấy phép tạm thời để đánh giá.

### Khởi tạo và thiết lập cơ bản

Sau khi cài đặt Aspose.Slides, hãy nhập các mô-đun cần thiết vào tập lệnh Python của bạn:

```python
import aspose.slides as slides
import aspose.pydrawing as drawing
```

## Hướng dẫn thực hiện

Trong phần này, chúng tôi sẽ chia nhỏ quá trình tạo biểu đồ hình tròn thành các bước chi tiết.

### Tạo và tùy chỉnh biểu đồ hình tròn của bạn

#### Tổng quan
Để tạo biểu đồ hình tròn, bạn cần khởi tạo đối tượng trình bày, thêm trang chiếu, sau đó chèn biểu đồ có các điểm dữ liệu và thành phần trực quan tùy chỉnh.

#### Các bước để tạo biểu đồ hình tròn

1. **Khởi tạo lớp trình bày**
   Bắt đầu bằng cách tạo một phiên bản trình bày. Phiên bản này sẽ đóng vai trò là nơi chứa các slide và biểu đồ của bạn.

   ```python
   with slides.Presentation() as presentation:
       # Truy cập trang chiếu đầu tiên
       slide = presentation.slides[0]
   ```

2. **Thêm biểu đồ hình tròn vào trang chiếu**
   Sử dụng `add_chart` phương pháp chèn biểu đồ hình tròn tại các tọa độ đã chỉ định trên trang chiếu.

   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

3. **Đặt tiêu đề biểu đồ**
   Tùy chỉnh biểu đồ của bạn với tiêu đề phù hợp và định dạng để căn giữa văn bản.

   ```python
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

4. **Sổ làm việc dữ liệu biểu đồ Access**
   Sử dụng `chart_data_workbook` để quản lý và tùy chỉnh danh mục và chuỗi dữ liệu của bạn.

   ```python
   fact = chart.chart_data.chart_data_workbook
   default_worksheet_index = 0

   # Xóa bất kỳ chuỗi hoặc danh mục hiện có nào
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()

   # Thêm danh mục mới (quý)
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   # Thêm một loạt mới
   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   ```

5. **Điền Chuỗi với Điểm Dữ liệu**
   Chèn các điểm dữ liệu vào chuỗi của bạn để biểu diễn các phần khác nhau của biểu đồ tròn.

   ```python
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 3, 1, 30))
   ```

6. **Áp dụng nhiều màu sắc khác nhau cho biểu đồ**
   Tùy chỉnh từng lát bánh bằng các màu sắc khác nhau.

   ```python
   chart.chart_data.series_groups[0].is_color_varied = True

   # Xác định một hàm để tùy chỉnh giao diện điểm
   def customize_point(point, fill_color, line_color):
       point.format.fill.fill_type = slides.FillType.SOLID
       point.format.fill.solid_fill_color.color = drawing.Color(fill_color)
       
       point.format.line.fill_format.fill_type = slides.FillType.SOLID
       point.format.line.fill_format.solid_fill_color.color = drawing.Color(line_color)
       point.format.line.width = 3.0
       point.format.line.style = slides.LineStyle.THIN_THICK
       point.format.line.dash_style = slides.LineDashStyle.DASH_DOT
   
   # Tùy chỉnh giao diện của điểm dữ liệu đầu tiên
   customize_point(series.data_points[0], "Cyan", "Gray")
   ```

7. **Tùy chỉnh nhãn cho điểm dữ liệu**
   Điều chỉnh cài đặt nhãn để hiển thị giá trị, phần trăm hoặc tên chuỗi.

   ```python
   def customize_label(point, show_value=True, show_legend_key=False,
                       show_percentage=False, show_series_name=False):
       lbl = point.label
       lbl.data_label_format.show_value = show_value
       lbl.data_label_format.show_legend_key = show_legend_key
       lbl.data_label_format.show_percentage = show_percentage
       lbl.data_label_format.show_series_name = show_series_name
   
   # Đặt thuộc tính nhãn cho điểm dữ liệu đầu tiên
   customize_label(series.data_points[0], True)
   ```

8. **Bật Đường dẫn và Xoay các lát bánh**
   Để dễ đọc hơn, hãy bật các đường dẫn và xoay các lát cắt khi cần.

   ```python
   series.labels.default_data_label_format.show_leader_lines = True

   # Xoay lát bánh đầu tiên 180 độ
   chart.chart_data.series_groups[0].first_slice_angle = 180
   ```

9. **Lưu bài thuyết trình**
   Cuối cùng, hãy lưu bài thuyết trình của bạn với tất cả các tùy chỉnh đã áp dụng.

   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Mẹo khắc phục sự cố
- Đảm bảo Aspose.Slides được cài đặt và nhập đúng cách.
- Kiểm tra xem có lỗi đánh máy nào trong tên phương thức hoặc tham số không, vì chúng có thể dẫn đến lỗi.
- Xác minh xem đường dẫn thư mục nơi bạn lưu tệp đầu ra có tồn tại không.

## Ứng dụng thực tế

Biểu đồ hình tròn rất linh hoạt và hữu ích trong nhiều lĩnh vực:
1. **Phân tích kinh doanh**Hình dung sự phân bổ doanh thu giữa các sản phẩm hoặc dịch vụ khác nhau.
2. **Báo cáo tiếp thị**: Hiển thị thị phần của các đối thủ cạnh tranh trong một ngành nhất định.
3. **Bài thuyết trình giáo dục**: Trình bày dữ liệu thống kê liên quan đến thành tích hoặc thông tin nhân khẩu học của học sinh.

## Cân nhắc về hiệu suất
- Giảm thiểu việc sử dụng tài nguyên bằng cách tối ưu hóa các thành phần biểu đồ và giảm độ phức tạp không cần thiết.
- Sử dụng cấu trúc dữ liệu hiệu quả khi xử lý các tập dữ liệu lớn để tạo biểu đồ.
- Quản lý bộ nhớ hiệu quả bằng cách giải phóng tài nguyên ngay sau khi sử dụng.

## Phần kết luận

Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides for Python. Bây giờ bạn có thể áp dụng các kỹ thuật này vào bài thuyết trình của mình và khám phá thêm các tùy chọn tùy chỉnh. Hãy cân nhắc tích hợp các loại biểu đồ khác hoặc tận dụng các tính năng bổ sung của Aspose.Slides để nâng cao kỹ năng trực quan hóa dữ liệu của bạn.

### Các bước tiếp theo
- Thử nghiệm với các tùy chỉnh biểu đồ khác nhau
- Khám phá sự tích hợp của biểu đồ trong báo cáo động
- Khám phá sâu hơn tài liệu Aspose.Slides để biết thêm các tính năng nâng cao

## Phần Câu hỏi thường gặp

1. **Aspose.Slides là gì?**
   - Một thư viện mạnh mẽ cho phép tạo và xử lý các bài thuyết trình PowerPoint theo chương trình.
2. **Tôi có thể sử dụng Aspose.Slides miễn phí không?**
   - Có, bạn có thể bắt đầu bằng giấy phép dùng thử hoặc đánh giá khả năng của nó trước khi mua.
3. **Tôi có thể tạo những loại biểu đồ nào khác?**
   - Ngoài biểu đồ hình tròn, bạn có thể tạo biểu đồ thanh, biểu đồ đường, biểu đồ phân tán và nhiều biểu đồ khác bằng Aspose.Slides.

## Khuyến nghị từ khóa
- "Aspose.Slides cho Python"
- "Biểu đồ hình tròn PowerPoint"
- "Biểu đồ PowerPoint Python"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}