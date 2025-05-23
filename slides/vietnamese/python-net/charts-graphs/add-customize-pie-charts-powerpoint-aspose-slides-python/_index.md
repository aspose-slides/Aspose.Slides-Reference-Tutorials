---
"date": "2025-04-22"
"description": "Tìm hiểu cách thêm và tùy chỉnh biểu đồ hình tròn trong bản trình bày PowerPoint bằng Aspose.Slides for Python. Tiết kiệm thời gian và đảm bảo tính nhất quán với hướng dẫn từng bước này."
"title": "Cách thêm và tùy chỉnh biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides cho Python"
"url": "/vi/python-net/charts-graphs/add-customize-pie-charts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thêm và tùy chỉnh biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides cho Python

## Giới thiệu
Việc tạo ra các bài thuyết trình hấp dẫn về mặt thị giác là rất quan trọng, đặc biệt là khi bạn cần truyền đạt dữ liệu phức tạp một cách ngắn gọn. Cho dù đó là báo cáo tài chính hay số liệu hiệu suất, biểu đồ hình tròn có thể là một công cụ hiệu quả để minh họa tỷ lệ trong nháy mắt. Tuy nhiên, việc thêm thủ công các biểu đồ này vào slide của bạn có thể tốn thời gian và dễ xảy ra tình trạng không nhất quán.

Với thư viện Python Aspose.Slides, việc tự động hóa quy trình này trở nên liền mạch. Hướng dẫn này sẽ hướng dẫn bạn sử dụng Aspose.Slides cho Python để dễ dàng thêm và tùy chỉnh biểu đồ hình tròn trong bản trình bày PowerPoint. Bằng cách làm theo, bạn không chỉ tiết kiệm thời gian mà còn đảm bảo tính đồng nhất trên các slide của mình.

**Những gì bạn sẽ học được:**
- Cách thêm biểu đồ hình tròn vào trang chiếu
- Đặt tiêu đề và căn giữa văn bản trên biểu đồ hình tròn
- Cấu hình chuỗi dữ liệu và danh mục để có thông tin chi tiết
- Cho phép thay đổi màu tự động cho các lát cắt riêng biệt

Hãy cùng tìm hiểu cách bạn có thể triển khai các tính năng này một cách hiệu quả. Trước khi bắt đầu, hãy đảm bảo môi trường của bạn được thiết lập đúng cách.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn sẽ cần:
- Python được cài đặt trên máy của bạn (khuyến nghị phiên bản 3.x)
- Thư viện Aspose.Slides cho Python
- Hiểu biết cơ bản về lập trình Python và thuyết trình PowerPoint

Đảm bảo rằng bạn có thiết lập cần thiết để thực thi các tập lệnh Python. Nếu không, hãy cân nhắc cài đặt Python từ [python.org](https://www.python.org/downloads/).

## Thiết lập Aspose.Slides cho Python
Để bắt đầu sử dụng Aspose.Slides trong dự án của bạn, hãy cài đặt nó thông qua pip:

```bash
pip install aspose.slides
```

### Các bước xin cấp giấy phép
Aspose cung cấp bản dùng thử miễn phí thư viện của họ. Bạn có thể tải xuống giấy phép tạm thời để khám phá đầy đủ các khả năng mà không bị giới hạn. Để bắt đầu:
- Thăm nom [Trang mua hàng của Aspose](https://purchase.aspose.com/buy) để mua các tùy chọn.
- Xin giấy phép tạm thời thông qua [Trang Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

### Khởi tạo cơ bản
Sau đây là cách bạn có thể khởi tạo Aspose.Slides trong tập lệnh Python của mình:

```python
import aspose.slides as slides

# Khởi tạo lớp Presentation để tạo hoặc mở tệp trình bày
with slides.Presentation() as presentation:
    # Mã của bạn ở đây
    pass
```

Với thiết lập này, bạn đã sẵn sàng để thêm biểu đồ hình tròn vào bài thuyết trình của mình.

## Hướng dẫn thực hiện

### Thêm biểu đồ hình tròn vào trang chiếu
#### Tổng quan
Việc thêm biểu đồ hình tròn cơ bản liên quan đến việc tạo ra một hình dạng mới của loại `Chart` trên trang chiếu của bạn. Phần này sẽ hướng dẫn bạn các bước để thêm biểu đồ hình tròn mặc định.

#### Các bước
1. **Truy cập trang trình bày đầu tiên**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Thêm hình dạng biểu đồ tròn**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

   - Các thông số: `ChartType.PIE` chỉ định loại biểu đồ.
   - Tọa độ và kích thước xác định vị trí và kích thước của biểu đồ hình tròn.

3. **Lưu bài thuyết trình**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_add_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Thiết lập tiêu đề biểu đồ hình tròn và văn bản ở giữa
#### Tổng quan
Việc tùy chỉnh biểu đồ hình tròn bằng tiêu đề sẽ giúp biểu đồ dễ đọc hơn và cung cấp bối cảnh cho người xem.

#### Các bước
1. **Truy cập trang trình bày đầu tiên**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Thêm biểu đồ và đặt tiêu đề**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   # Đặt tiêu đề
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

3. **Lưu bài thuyết trình**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_pie_chart_title_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Cấu hình Chuỗi dữ liệu và Danh mục biểu đồ hình tròn
#### Tổng quan
Để biểu đồ hình tròn của bạn có tính thông tin, bạn cần nhập dữ liệu thực tế vào đó.

#### Các bước
1. **Truy cập trang trình bày đầu tiên**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Cấu hình dữ liệu**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   fact = chart.chart_data.chart_data_workbook
   
   # Xóa dữ liệu hiện có
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()
   
   # Thêm danh mục và chuỗi với các điểm dữ liệu
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   
   # Thêm điểm dữ liệu
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 3, 1, 30))
   ```

3. **Lưu bài thuyết trình**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_configure_pie_chart_data_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Bật màu lát biểu đồ hình tròn tự động
#### Tổng quan
Tăng cường sức hấp dẫn trực quan bằng cách tự động thay đổi màu sắc của lát cắt có thể khiến biểu đồ của bạn hấp dẫn hơn.

#### Các bước
1. **Truy cập trang trình bày đầu tiên**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Bật Biến thể màu**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   series = chart.chart_data.series[0]
   series.parent_series_group.is_color_varied = True
   ```

3. **Lưu bài thuyết trình**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_enable_automatic_pie_slice_colors_out.pptx", slides.export.SaveFormat.PPTX)
   ```

## Ứng dụng thực tế
1. **Báo cáo kinh doanh**:Sử dụng biểu đồ hình tròn để thể hiện sự phân bổ thị phần giữa các đối thủ cạnh tranh.
2. **Tài liệu giáo dục**: Minh họa tỷ lệ phần trăm các chủ đề khác nhau được đề cập trong chương trình giảng dạy.
3. **Phân tích tài chính**: Hiển thị danh mục chi phí theo tỷ lệ tổng ngân sách.
4. **Thông tin chi tiết về tiếp thị**: Hình dung phân khúc khách hàng theo nhân khẩu học hoặc sở thích.

Việc tích hợp với các công cụ phân tích dữ liệu như Pandas có thể tự động hóa quy trình hơn nữa, giúp cập nhật theo thời gian thực trong các bài thuyết trình.

## Cân nhắc về hiệu suất
Khi làm việc với Aspose.Slides và Python:
- Tối ưu hóa mã của bạn để quản lý bộ nhớ hiệu quả, đặc biệt là khi xử lý các tập dữ liệu lớn.
- Tránh các thao tác dư thừa trên các đối tượng trình bày.
- Sử dụng `with` các câu lệnh quản lý ngữ cảnh để đảm bảo tài nguyên được giải phóng phù hợp sau khi sử dụng.

## Phần kết luận
Bây giờ bạn đã hiểu toàn diện về cách tạo và tùy chỉnh biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides for Python. Bằng cách tự động hóa các tác vụ này, bạn có thể tăng đáng kể năng suất đồng thời đảm bảo tính nhất quán trong các bài thuyết trình của mình. 

Để tiến xa hơn, hãy khám phá việc tích hợp các nguồn dữ liệu động hoặc tự động tạo toàn bộ bộ slide.

## Khuyến nghị từ khóa
- "Aspose.Slides cho Python"
- "Biểu đồ hình tròn PowerPoint"
- "tự động hóa biểu đồ PowerPoint bằng Python"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}