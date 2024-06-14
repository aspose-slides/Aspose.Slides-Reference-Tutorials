---
title: Chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong Java Slides
linktitle: Chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn.
type: docs
weight: 17
url: /vi/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## Giới thiệu về Chỉnh sửa dữ liệu biểu đồ trong Sổ làm việc bên ngoài trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài bằng Aspose.Slides cho Java. Bạn sẽ tìm hiểu cách sửa đổi dữ liệu biểu đồ trong bản trình bày PowerPoint theo chương trình. Đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Slides cho Java trong dự án của mình.

## Điều kiện tiên quyết

- Aspose.Slides cho Java
- Môi trường phát triển Java

## Bước 1: Tải bài thuyết trình

 Trước tiên, chúng ta cần tải bản trình bày PowerPoint chứa biểu đồ có dữ liệu mà chúng ta muốn chỉnh sửa. Thay thế`"Your Document Directory"` với đường dẫn thực tế đến tệp trình bày của bạn.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Bước 2: Truy cập biểu đồ

Sau khi tải xong bản trình bày, chúng ta cần truy cập vào biểu đồ trong bản trình bày. Trong ví dụ này, chúng tôi giả sử biểu đồ nằm trên trang chiếu đầu tiên và là hình đầu tiên trên trang chiếu đó.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Bước 3: Sửa đổi dữ liệu biểu đồ

Bây giờ, hãy sửa đổi dữ liệu biểu đồ. Chúng tôi sẽ tập trung vào việc thay đổi một điểm dữ liệu cụ thể trong biểu đồ. Trong ví dụ này, chúng tôi đặt giá trị của điểm dữ liệu đầu tiên trong chuỗi đầu tiên thành 100. Bạn có thể điều chỉnh giá trị này nếu cần.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Bước 4: Lưu bài thuyết trình

Sau khi thực hiện những thay đổi cần thiết đối với dữ liệu biểu đồ, hãy lưu bản trình bày đã sửa đổi vào một tệp mới. Bạn có thể chỉ định đường dẫn và định dạng tệp đầu ra theo yêu cầu của mình.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Bước 5: Dọn dẹp

Đừng quên loại bỏ đối tượng trình bày để giải phóng bất kỳ tài nguyên nào.

```java
if (pres != null) pres.dispose();
```

Bây giờ bạn đã chỉnh sửa thành công dữ liệu biểu đồ trong sổ làm việc bên ngoài trong bản trình bày PowerPoint của mình bằng Aspose.Slides cho Java. Bạn có thể tùy chỉnh mã này cho phù hợp với nhu cầu cụ thể của mình và tích hợp nó vào các ứng dụng Java của bạn.

## Mã nguồn hoàn chỉnh

```java
        // Chú ý đường dẫn tới bảng tính bên ngoài hầu như không được lưu trong bài thuyết trình
        // vì vậy vui lòng sao chép tệp externalWorkbook.xlsx từ thư mục Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ trước khi chạy ví dụ
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

Trong hướng dẫn toàn diện này, chúng tôi đã khám phá cách chỉnh sửa dữ liệu biểu đồ trong sổ làm việc bên ngoài trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bằng cách làm theo hướng dẫn từng bước và ví dụ về mã nguồn, bạn đã có được kiến thức và kỹ năng để sửa đổi dữ liệu biểu đồ theo chương trình một cách dễ dàng.

## Câu hỏi thường gặp

### Làm cách nào để chỉ định một biểu đồ hoặc trang trình bày khác?

 Để truy cập vào một biểu đồ hoặc trang trình bày khác, hãy sửa đổi chỉ mục thích hợp trong`getSlides().get_Item()` Và`getShapes().get_Item()`phương pháp. Hãy nhớ rằng việc lập chỉ mục bắt đầu từ 0.

### Tôi có thể chỉnh sửa dữ liệu trong nhiều biểu đồ trong cùng một bản trình bày không?

Có, bạn có thể chỉnh sửa dữ liệu trong nhiều biểu đồ trong cùng một bản trình bày bằng cách lặp lại các bước sửa đổi dữ liệu biểu đồ cho từng biểu đồ.

### Nếu tôi muốn chỉnh sửa dữ liệu trong sổ làm việc bên ngoài với định dạng khác thì sao?

Bạn có thể điều chỉnh mã để xử lý các định dạng sổ làm việc bên ngoài khác nhau bằng cách sử dụng các lớp và phương thức Aspose.Cells thích hợp để đọc và ghi dữ liệu ở định dạng đó.

### Làm cách nào tôi có thể tự động hóa quá trình này cho nhiều bài thuyết trình?

Bạn có thể tạo vòng lặp để xử lý nhiều bản trình bày, tải từng bản trình bày, thực hiện các thay đổi mong muốn và lưu từng bản trình bày đã sửa đổi.