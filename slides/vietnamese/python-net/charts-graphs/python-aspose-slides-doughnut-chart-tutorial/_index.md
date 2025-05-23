---
"date": "2025-04-22"
"description": "Tìm hiểu cách tạo biểu đồ hình vòng tròn bằng Python và Aspose.Slides. Hướng dẫn từng bước này bao gồm thiết lập, tùy chỉnh và các phương pháp hay nhất để nâng cao bài thuyết trình của bạn."
"title": "Cách tạo biểu đồ hình tròn trong Python bằng Aspose.Slides&#58; Hướng dẫn từng bước"
"url": "/vi/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ hình tròn trong Python bằng Aspose.Slides: Hướng dẫn từng bước

Trong lĩnh vực trực quan hóa dữ liệu, việc trình bày thông tin hiệu quả có thể tác động đáng kể đến việc hiểu và ra quyết định. Cho dù bạn đang soạn thảo bài thuyết trình kinh doanh hay phân tích các tập dữ liệu phức tạp, biểu đồ là công cụ thiết yếu. Trong số nhiều loại biểu đồ, biểu đồ hình bánh rán cung cấp một cách hấp dẫn để biểu diễn dữ liệu tỷ lệ với một lỗ trung tâm trực quan. Hướng dẫn từng bước này sẽ hướng dẫn bạn cách tạo biểu đồ hình bánh rán trong Python bằng Aspose.Slides—một thư viện mạnh mẽ để thao tác các bài thuyết trình.

## Những gì bạn sẽ học được
- Cách thiết lập và sử dụng Aspose.Slides cho Python
- Quá trình thêm biểu đồ hình tròn vào slide thuyết trình của bạn
- Tùy chỉnh chuỗi và danh mục trong biểu đồ
- Điều chỉnh các yếu tố trực quan như nhãn, màu sắc và hiệu ứng nổ
- Các biện pháp thực hành tốt nhất để tối ưu hóa hiệu suất với Aspose.Slides

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có:
- **Môi trường Python**: Python 3.x đã được cài đặt trên máy của bạn.
- **Aspose.Slides cho Python**: Cài đặt thư viện này bằng pip.
- **Hiểu biết cơ bản về lập trình Python**: Sự quen thuộc với vòng lặp và lập trình hướng đối tượng sẽ rất hữu ích.

## Thiết lập Aspose.Slides cho Python
Để bắt đầu, hãy cài đặt thư viện Aspose.Slides qua pip:

```bash
pip install aspose.slides
```

### Mua lại giấy phép
Aspose cung cấp bản dùng thử miễn phí để kiểm tra các tính năng không giới hạn trong thời gian có hạn. Để có được bản dùng thử này:
1. Ghé thăm [Dùng thử miễn phí](https://releases.aspose.com/slides/python-net/) trang.
2. Làm theo hướng dẫn để tải xuống và áp dụng giấy phép tạm thời của bạn.

Để tiếp tục sử dụng, hãy cân nhắc mua đăng ký từ [Trang mua hàng](https://purchase.aspose.com/buy).

### Khởi tạo cơ bản
Sau khi thiết lập Aspose.Slides, hãy khởi tạo nó như sau:

```python
import aspose.slides as slides

# Tạo một phiên bản của lớp Presentation.
with slides.Presentation() as pres:
    # Mã để thao tác bài thuyết trình của bạn sẽ nằm ở đây.

# Lưu bản trình bày sau khi thực hiện thay đổi.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Hướng dẫn thực hiện
Sau khi thiết lập Aspose.Slides, hãy làm theo các bước sau để thêm biểu đồ hình tròn vào từng trang trình bày của bạn.

### Tạo bài thuyết trình mới và thêm trang trình bày
Bắt đầu bằng cách tạo một phiên bản của `Presentation` lớp học:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Truy cập hoặc tạo slide trong bối cảnh này.
```

### Thêm Biểu đồ hình bánh rán vào Slide đầu tiên
Truy cập trang chiếu đầu tiên và sử dụng `add_chart` phương pháp. Chỉ định loại biểu đồ là `DOUGHNUT`, cùng với vị trí và kích thước:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Cấu hình dữ liệu biểu đồ
Xóa dữ liệu hiện có và cấu hình các thiết lập như ẩn chú thích:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Thêm Series và Categories
Thêm nhiều chuỗi và danh mục cho biểu đồ hình tròn. Sau đây là cách tạo 15 chuỗi với các thuộc tính cụ thể:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Thêm các danh mục tương tự:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Thêm điểm dữ liệu cho mỗi chuỗi.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Tùy chỉnh giao diện của từng điểm dữ liệu.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Cấu hình cài đặt nhãn cho loạt cuối cùng.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Lưu bài thuyết trình
Cuối cùng, lưu bài thuyết trình của bạn vào một thư mục được chỉ định:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Ứng dụng thực tế
Biểu đồ hình tròn rất linh hoạt và có thể được sử dụng trong nhiều trường hợp khác nhau như:
1. **Phân bổ ngân sách**: Hiển thị cách các phòng ban khác nhau sử dụng nguồn quỹ được phân bổ.
2. **Phân tích thị phần**: So sánh thị phần của các sản phẩm hoặc công ty cạnh tranh.
3. **Kết quả khảo sát**: Hình dung phản hồi cho các câu hỏi khảo sát về sở thích hoặc mức độ hài lòng.

## Cân nhắc về hiệu suất
Để đảm bảo hiệu suất tối ưu khi sử dụng Aspose.Slides:
- Giảm thiểu việc sử dụng bộ nhớ bằng cách xử lý các đối tượng đúng cách sau khi sử dụng.
- Chỉ tải bài thuyết trình vào bộ nhớ khi cần thiết và đóng chúng lại càng sớm càng tốt.
- Hãy cân nhắc xử lý hàng loạt slide nếu bạn đang làm việc với số lượng lớn biểu đồ.

## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo biểu đồ hình tròn động bằng Aspose.Slides for Python. Các hình ảnh trực quan này có thể cải thiện bài thuyết trình của bạn bằng cách làm cho dữ liệu dễ hiểu và hấp dẫn hơn. Tiếp tục khám phá các tính năng của thư viện để tùy chỉnh và tối ưu hóa biểu đồ của bạn hơn nữa.

## Phần Câu hỏi thường gặp
1. **Tôi có thể sử dụng Aspose.Slides mà không cần mua giấy phép không?**
   - Có, bạn có thể bắt đầu với giấy phép dùng thử miễn phí để đánh giá.
2. **Làm thế nào để thay đổi màu biểu đồ trong Aspose.Slides?**
   - Sử dụng `fill_format` thuộc tính để thiết lập màu mong muốn cho các thành phần biểu đồ của bạn.
3. **Có thể xuất biểu đồ dưới dạng hình ảnh không?**
   - Có, bạn có thể kết xuất các slide chứa biểu đồ thành định dạng hình ảnh bằng cách sử dụng chức năng kết xuất của thư viện.
4. **Một số vấn đề thường gặp khi thêm biểu đồ là gì?**
   - Đảm bảo rằng tất cả các điểm dữ liệu và danh mục được thêm đúng cách trước khi lưu hoặc hiển thị biểu đồ.
5. **Tôi có thể tích hợp Aspose.Slides với các thư viện Python khác không?**
   - Chắc chắn rồi! Bạn có thể sử dụng nó cùng với các thư viện như Pandas để tăng cường khả năng xử lý dữ liệu.

## Tài nguyên
- [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Tải xuống Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Dùng thử miễn phí và Giấy phép tạm thời](https://releases.aspose.com/slides/python-net/)
- [Diễn đàn cộng đồng Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}