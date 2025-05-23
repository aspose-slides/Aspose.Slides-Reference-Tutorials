---
"date": "2025-04-22"
"description": "Tìm hiểu cách hiển thị nhãn phần trăm dễ dàng trên biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Python. Hoàn hảo để nâng cao khả năng trực quan hóa dữ liệu."
"title": "Cách hiển thị nhãn phần trăm trên biểu đồ bằng Aspose.Slides cho Python&#58; Hướng dẫn toàn diện"
"url": "/vi/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách hiển thị nhãn phần trăm trên biểu đồ bằng Aspose.Slides cho Python

## Giới thiệu

Việc trực quan hóa dữ liệu hiệu quả là rất quan trọng trong các bài thuyết trình và báo cáo, đặc biệt là khi bạn muốn làm nổi bật tỷ lệ hoặc phân phối một cách rõ ràng. Nhưng nếu bạn cần hiển thị trực tiếp các phần trăm đó trên biểu đồ của mình thì sao? Hướng dẫn toàn diện này sẽ hướng dẫn bạn cách sử dụng **Aspose.Slides cho Python** để hiển thị giá trị phần trăm dưới dạng nhãn trên biểu đồ một cách dễ dàng.

### Những gì bạn sẽ học được:
- Cách tạo và nhúng biểu đồ vào bản trình bày PowerPoint bằng Aspose.Slides cho Python.
- Hiển thị điểm dữ liệu dưới dạng nhãn phần trăm trên biểu đồ của bạn.
- Lưu và quản lý bài thuyết trình PowerPoint hiệu quả.

Bạn đã sẵn sàng để bắt đầu thêm hình ảnh trực quan sâu sắc vào dữ liệu của mình chưa? Trước tiên, hãy xem những gì bạn cần trước khi bắt tay vào viết mã!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:
- **Aspose.Slides cho Python**:Thư viện này rất cần thiết để tạo và thao tác các bài thuyết trình PowerPoint theo chương trình.
- **Môi trường Python**: Hiểu biết cơ bản về lập trình Python và thiết lập môi trường.
- **Trình quản lý gói PIP**: Được sử dụng để cài đặt Aspose.Slides.

## Thiết lập Aspose.Slides cho Python

Để bắt đầu sử dụng Aspose.Slides, trước tiên bạn cần cài đặt nó:

```bash
pip install aspose.slides
```

### Các bước xin cấp giấy phép:
Bạn có thể bắt đầu dùng thử miễn phí hoặc mua giấy phép tạm thời để khám phá toàn bộ khả năng của Aspose.Slides. Để sử dụng lâu dài, hãy cân nhắc mua đăng ký.

#### Khởi tạo và thiết lập cơ bản

Sau khi cài đặt, bạn sẽ khởi tạo môi trường trình bày của mình như sau:

```python
import aspose.slides as slides

# Khởi tạo một đối tượng Presentation
def create_presentation():
    with slides.Presentation() as presentation:
        # Mã của bạn ở đây
```

## Hướng dẫn thực hiện

Bây giờ chúng ta đã thiết lập xong, hãy cùng tìm hiểu cách hiển thị phần trăm trên biểu đồ.

### Tạo biểu đồ và thêm dữ liệu

#### Tổng quan
Chúng tôi sẽ tạo biểu đồ cột xếp chồng với nhãn phần trăm cho mỗi điểm dữ liệu, cho phép người xem nhìn thấy tỷ lệ chính xác chỉ trong nháy mắt.

##### Bước 1: Thêm biểu đồ vào trang chiếu của bạn

```python
# Truy cập trang chiếu đầu tiên trong bài thuyết trình của bạn
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Thêm biểu đồ cột xếp chồng
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Đoạn mã này thêm một biểu đồ cơ bản vào trang chiếu đầu tiên. `add_chart` phương pháp này chỉ định loại biểu đồ, vị trí và kích thước của biểu đồ.

##### Bước 2: Tính tổng giá trị cho các danh mục

```python
def calculate_totals(chart):
    total_for_category = []
    # Tổng hợp các giá trị trên tất cả các chuỗi cho mỗi danh mục
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Vòng lặp này tính tổng tất cả các điểm dữ liệu trong toàn bộ chuỗi, điều này rất quan trọng đối với các phép tính phần trăm.

#### Thiết lập nhãn phần trăm

##### Bước 3: Cấu hình Điểm dữ liệu chuỗi

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Đặt tùy chọn nhãn mặc định để ẩn thông tin không cần thiết
        series.labels.default_data_label_format.show_legend_key = False
        
        # Tính toán và thiết lập nhãn phần trăm
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Tạo một phần văn bản có giá trị phần trăm
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Xóa nhãn hiện có và thêm nhãn phần trăm mới
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Ẩn các phần tử nhãn dữ liệu khác
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Phân đoạn này xử lý từng điểm dữ liệu để tính toán phần trăm của điểm đó trong tổng số và gán nó làm nhãn.

### Lưu bài thuyết trình của bạn

```python
def save_presentation(presentation, output_directory):
    # Lưu bài thuyết trình của bạn với các sửa đổi
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}