---
"date": "2025-04-23"
"description": "Tìm hiểu cách điều chỉnh góc xoay của tiêu đề biểu đồ trong bài thuyết trình bằng Aspose.Slides cho Python, giúp tăng khả năng đọc và tính thẩm mỹ."
"title": "Cách thiết lập xoay tiêu đề trục dọc của biểu đồ trong Aspose.Slides cho Python"
"url": "/vi/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thiết lập xoay tiêu đề trục dọc của biểu đồ trong Aspose.Slides cho Python

## Giới thiệu

Trong các bài thuyết trình dữ liệu, việc cải thiện khả năng đọc biểu đồ là rất quan trọng. Điều chỉnh góc xoay của tiêu đề trục dọc của biểu đồ bằng Aspose.Slides for Python có thể làm cho tiêu đề vừa vặn hoặc nổi bật trong các slide của bạn. Hướng dẫn này hướng dẫn bạn cách thiết lập góc xoay này để tăng cường cả chức năng và tính hấp dẫn trực quan.

**Những gì bạn sẽ học được:**
- Cách cài đặt và cấu hình Aspose.Slides cho Python.
- Các bước để thêm và tùy chỉnh biểu đồ trong trang chiếu của bạn.
- Kỹ thuật thiết lập góc xoay của tiêu đề biểu đồ.
- Ứng dụng thực tế của các tính năng này trong trực quan hóa dữ liệu.

Chúng ta hãy bắt đầu bằng cách tìm hiểu các điều kiện tiên quyết trước khi bắt tay vào triển khai.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có:
- **Môi trường Python**: Cài đặt Python 3.x từ [python.org](https://www.python.org/).
- **Thư viện Aspose.Slides**: Cài đặt thông qua pip để thao tác trình bày hiệu quả.
- **Kiến thức cơ bản về lập trình Python**:Sự quen thuộc với cú pháp Python và các thao tác với tệp sẽ giúp bạn theo dõi.

## Thiết lập Aspose.Slides cho Python

Để sử dụng Aspose.Slides, hãy cài đặt bằng pip. Mở terminal hoặc dấu nhắc lệnh và chạy:

```bash
pip install aspose.slides
```

### Các bước xin cấp giấy phép

Aspose cung cấp nhiều tùy chọn cấp phép khác nhau:
- **Dùng thử miễn phí**: Tải xuống phiên bản dùng thử từ [Trang phát hành của Aspose](https://releases.aspose.com/slides/python-net/).
- **Giấy phép tạm thời**: Nhận giấy phép tạm thời cho các tính năng mở rộng thông qua [cổng thông tin mua hàng](https://purchase.aspose.com/temporary-license/).
- **Mua**: Hãy cân nhắc mua nếu bạn thấy công cụ này là không thể thiếu, có sẵn tại [Trang mua hàng Aspose](https://purchase.aspose.com/buy).

#### Khởi tạo và thiết lập cơ bản

Sau đây là cách khởi tạo Aspose.Slides trong tập lệnh Python của bạn:

```python
import aspose.slides as slides

# Tạo một đối tượng trình bày
def main():
    with slides.Presentation() as pres:
        # Mã của bạn sẽ được lưu ở đây
        pass

if __name__ == "__main__":
    main()
```

## Hướng dẫn thực hiện

### Thêm và tùy chỉnh biểu đồ

#### Tổng quan

Trong phần này, chúng ta sẽ thêm biểu đồ cột cụm vào trang chiếu của bạn và tùy chỉnh biểu đồ này bằng cách thiết lập góc xoay của tiêu đề trục dọc.

#### Các bước thực hiện:

##### Bước 1: Thêm Biểu đồ Cột Nhóm

Bắt đầu bằng cách thêm biểu đồ ở tọa độ cụ thể với kích thước được xác định:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Thêm biểu đồ cột nhóm vào trang chiếu 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Bước 2: Cấu hình Tiêu đề Trục dọc

Bật và đặt góc xoay cho tiêu đề trục dọc:

```python
def configure_chart(chart):
    # Kích hoạt tiêu đề trục dọc
    chart.axes.vertical_axis.has_title = True
    
    # Đặt góc quay thành 90 độ
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Bước 3: Lưu bài thuyết trình của bạn

Cuối cùng, hãy lưu bản trình bày với những thay đổi sau:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Lưu bài thuyết trình
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}