---
"description": "Tìm hiểu cách chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài bằng Aspose.Slides cho Java. Hướng dẫn từng bước có mã nguồn."
"linktitle": "Chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong Java Slides"
"url": "/vi/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong Java Slides


## Giới thiệu về Chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài bằng Aspose.Slides for Java. Bạn sẽ học cách chỉnh sửa dữ liệu biểu đồ trong bản trình bày PowerPoint theo chương trình. Đảm bảo rằng bạn đã cài đặt và cấu hình thư viện Aspose.Slides for Java trong dự án của mình.

## Điều kiện tiên quyết

- Aspose.Slides cho Java
- Môi trường phát triển Java

## Bước 1: Tải bài thuyết trình

Đầu tiên, chúng ta cần tải bản trình bày PowerPoint có chứa biểu đồ có dữ liệu mà chúng ta muốn chỉnh sửa. Thay thế `"Your Document Directory"` với đường dẫn thực tế đến tệp trình bày của bạn.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Bước 2: Truy cập Biểu đồ

Sau khi tải xong bản trình bày, chúng ta cần truy cập vào biểu đồ trong bản trình bày. Trong ví dụ này, chúng ta giả sử biểu đồ nằm trên trang chiếu đầu tiên và là hình dạng đầu tiên trên trang chiếu đó.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Bước 3: Sửa đổi dữ liệu biểu đồ

Bây giờ, hãy sửa đổi dữ liệu biểu đồ. Chúng ta sẽ tập trung vào việc thay đổi một điểm dữ liệu cụ thể trong biểu đồ. Trong ví dụ này, chúng ta đặt giá trị của điểm dữ liệu đầu tiên trong chuỗi đầu tiên thành 100. Bạn có thể điều chỉnh giá trị này khi cần.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Bước 4: Lưu bài thuyết trình

Sau khi thực hiện các thay đổi cần thiết cho dữ liệu biểu đồ, hãy lưu bản trình bày đã sửa đổi vào một tệp mới. Bạn có thể chỉ định đường dẫn và định dạng tệp đầu ra theo yêu cầu của mình.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Bước 5: Dọn dẹp

Đừng quên loại bỏ đối tượng trình bày để giải phóng mọi tài nguyên.

```java
if (pres != null) pres.dispose();
```

Bây giờ bạn đã chỉnh sửa thành công dữ liệu biểu đồ trong một sổ làm việc bên ngoài trong bản trình bày PowerPoint của mình bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh mã này để phù hợp với nhu cầu cụ thể của mình và tích hợp nó vào các ứng dụng Java của bạn.

## Mã nguồn đầy đủ

```java
        // Chú ý đường dẫn đến sổ làm việc bên ngoài hầu như không được lưu trong bản trình bày
        // vì vậy hãy sao chép tệp externalWorkbook.xlsx từ thư mục Dữ liệu/Biểu đồ D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ trước khi chạy ví dụ
        // Đường dẫn đến thư mục tài liệu.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Phần kết luận

Trong hướng dẫn toàn diện này, chúng tôi đã khám phá cách chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bằng cách làm theo hướng dẫn từng bước và ví dụ về mã nguồn, bạn đã có được kiến thức và kỹ năng để dễ dàng chỉnh sửa dữ liệu biểu đồ theo chương trình.

## Câu hỏi thường gặp

### Làm thế nào để chỉ định một biểu đồ hoặc trang chiếu khác?

Để truy cập vào biểu đồ hoặc trang chiếu khác, hãy sửa đổi chỉ mục thích hợp trong `getSlides().get_Item()` Và `getShapes().get_Item()` phương pháp. Hãy nhớ rằng lập chỉ mục bắt đầu từ 0.

### Tôi có thể chỉnh sửa dữ liệu trong nhiều biểu đồ trong cùng một bản trình bày không?

Có, bạn có thể chỉnh sửa dữ liệu trong nhiều biểu đồ trong cùng một bản trình bày bằng cách lặp lại các bước sửa đổi dữ liệu biểu đồ cho từng biểu đồ.

### Tôi phải làm sao nếu muốn chỉnh sửa dữ liệu trong một bảng tính ngoài có định dạng khác?

Bạn có thể điều chỉnh mã để xử lý các định dạng sổ làm việc ngoài khác nhau bằng cách sử dụng các lớp và phương thức Aspose.Cells thích hợp để đọc và ghi dữ liệu theo định dạng đó.

### Làm thế nào tôi có thể tự động hóa quy trình này cho nhiều bài thuyết trình?

Bạn có thể tạo vòng lặp để xử lý nhiều bản trình bày, tải từng bản trình bày, thực hiện các thay đổi mong muốn và lưu từng bản trình bày đã sửa đổi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}