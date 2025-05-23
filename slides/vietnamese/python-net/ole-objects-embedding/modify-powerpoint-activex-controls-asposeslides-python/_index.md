---
"date": "2025-04-22"
"description": "Tìm hiểu cách sửa đổi văn bản TextBox, chú thích nút và hình ảnh trong PowerPoint bằng Aspose.Slides với Python. Nâng cao bài thuyết trình của bạn bằng các thành phần tương tác."
"title": "Làm chủ Aspose.Slides cho Python&#58; Sửa đổi các điều khiển ActiveX của PowerPoint một cách dễ dàng"
"url": "/vi/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Làm chủ Aspose.Slides cho Python: Sửa đổi các điều khiển ActiveX của PowerPoint

Trong bối cảnh kỹ thuật số năng động ngày nay, việc tùy chỉnh các bài thuyết trình Microsoft PowerPoint là điều cần thiết để tạo ra nội dung hấp dẫn. Cho dù bạn đang phát triển các mô-đun đào tạo tương tác hay cải thiện các bài thuyết trình kinh doanh với khả năng nhập dữ liệu của người dùng, việc sửa đổi các điều khiển ActiveX của PowerPoint có thể tăng cường đáng kể chức năng của bài thuyết trình của bạn. Hướng dẫn này khám phá cách sử dụng Aspose.Slides for Python để thay đổi văn bản TextBox và chú thích nút, thay thế hình ảnh, định vị lại hoặc xóa các điều khiển ActiveX khỏi các trang chiếu.

## Những gì bạn sẽ học được
- Cách sửa đổi văn bản TextBox và chú thích nút trong bản trình bày PowerPoint.
- Các kỹ thuật thay thế hình ảnh trong điều khiển ActiveX.
- Phương pháp định vị lại hoặc xóa các điều khiển ActiveX một cách hiệu quả.
- Ứng dụng thực tế của những tính năng này trong các tình huống thực tế.

Trước khi tìm hiểu sâu hơn về Aspose.Slides cho Python, chúng ta hãy cùng xem lại các điều kiện tiên quyết.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, hãy đảm bảo bạn có:
- **Trăn**: Phiên bản 3.6 trở lên được cài đặt trên hệ thống của bạn.
- **Aspose.Slides cho Python qua .NET**: Có thể cài đặt bằng pip.
- Hiểu biết cơ bản về lập trình Python và quen thuộc với cấu trúc của PowerPoint.

### Yêu cầu thiết lập môi trường
1. **Cài đặt Aspose.Slides**:
   Sử dụng lệnh sau để cài đặt Aspose.Slides cho Python qua .NET:

   ```bash
   pip install aspose.slides
   ```

2. **Mua lại giấy phép**: 
   Bắt đầu bằng cách lấy một [giấy phép dùng thử miễn phí](https://releases.aspose.com/slides/python-net/) hoặc xin giấy phép tạm thời để khám phá đầy đủ khả năng mà không có giới hạn.

3. **Khởi tạo cơ bản**:
   Nhập các mô-đun cần thiết và tải tài liệu PowerPoint của bạn như hiển thị bên dưới:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # Mã của bạn sẽ nằm ở đây.
   ```

## Hướng dẫn thực hiện
### Tính năng: Thay đổi văn bản hộp văn bản và thay thế hình ảnh
#### Tổng quan
Tính năng này cho phép bạn cập nhật văn bản trong điều khiển ActiveX TextBox và thay thế hình ảnh liên quan, hữu ích cho việc cá nhân hóa bài thuyết trình hoặc cập nhật nội dung động.

##### Hướng dẫn từng bước
1. **Tải bài thuyết trình**:
   Bắt đầu bằng cách tải bản trình bày PowerPoint có chứa các điều khiển ActiveX.

   ```python
def change_textbox_and_image():
    với slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") làm bài thuyết trình:
        slide = bài thuyết trình.slides[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **Tạo hình ảnh thay thế**:
   Tạo hình ảnh để thay thế nội dung gốc trong quá trình kích hoạt ActiveX.

   ```python
            import aspose.pydrawing as drawing

            # Tạo một hình ảnh có kích thước được chỉ định
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # Thêm đường viền để có giao diện bóng bẩy
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Tính năng: Thay đổi tiêu đề nút và thay thế hình ảnh
#### Tổng quan
Cập nhật chú thích nút trong các điều khiển ActiveX của bài thuyết trình, cung cấp khả năng tương tác năng động với người dùng.

##### Hướng dẫn từng bước
1. **Tải bài thuyết trình**:
   Như trước, hãy bắt đầu bằng cách tải tệp PowerPoint.

   ```python
định nghĩa change_button_caption_and_image():
    với slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") làm bài thuyết trình:
        slide = bài thuyết trình.slides[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **Tạo hình ảnh thay thế**:
   Tạo hình ảnh để thay thế trực quan.

   ```python
            # Tạo một bitmap cho kích thước của nút
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # Thêm đường viền cho tính thẩm mỹ
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Tính năng: Di chuyển các điều khiển ActiveX xuống và lưu bản trình bày
#### Tổng quan
Tìm hiểu cách định vị lại các điều khiển ActiveX trong slide, tăng cường tính linh hoạt của bố cục.

##### Hướng dẫn từng bước
1. **Tải bài thuyết trình**:
   Mở tài liệu PowerPoint của bạn để chỉnh sửa.

   ```python
định nghĩa move_active_x_controls_and_save():
    với slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") làm bài thuyết trình:
        slide = bài thuyết trình.slides[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**Phần kết luận:**
Bằng cách làm theo hướng dẫn này, bạn có thể hiệu quả sửa đổi các điều khiển PowerPoint ActiveX bằng Aspose.Slides for Python. Điều này tăng cường tính tương tác và tùy chỉnh các bài thuyết trình của bạn, khiến chúng hấp dẫn hơn đối với khán giả của bạn.

## Khuyến nghị từ khóa
- "Sửa đổi các điều khiển ActiveX của PowerPoint"
- "Aspose.Slides cho Python"
- "Thay đổi văn bản TextBox trong PowerPoint"
- "Thay thế hình ảnh trong các điều khiển ActiveX"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}