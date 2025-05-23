---
"description": "Tìm hiểu cách thiết lập công thức ô dữ liệu biểu đồ trong bản trình bày Java PowerPoint bằng Aspose.Slides for Java. Tạo biểu đồ động bằng công thức."
"linktitle": "Biểu đồ dữ liệu ô công thức trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ dữ liệu ô công thức trong Java Slides"
"url": "/vi/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ dữ liệu ô công thức trong Java Slides


## Giới thiệu về công thức ô dữ liệu biểu đồ trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các công thức ô dữ liệu biểu đồ bằng Aspose.Slides for Java. Với Aspose.Slides, bạn có thể tạo và thao tác biểu đồ trong các bài thuyết trình PowerPoint, bao gồm cả việc thiết lập công thức cho các ô dữ liệu.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides for Java. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo bài thuyết trình PowerPoint

Đầu tiên, hãy tạo một bản trình bày PowerPoint mới và thêm biểu đồ vào đó.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Thêm biểu đồ vào trang chiếu đầu tiên
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Nhận sổ làm việc cho dữ liệu biểu đồ
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Tiếp tục với các hoạt động của ô dữ liệu
    // ...
    
    // Lưu bài thuyết trình
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Bước 2: Thiết lập công thức cho ô dữ liệu

Bây giờ, hãy thiết lập công thức cho các ô dữ liệu cụ thể trong biểu đồ. Trong ví dụ này, chúng ta sẽ thiết lập công thức cho hai ô khác nhau.

### Ô 1: Sử dụng ký hiệu A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Trong mã trên, chúng ta đặt công thức cho ô B2 bằng cách sử dụng ký hiệu A1. Công thức tính tổng các ô từ F2 đến H5 và thêm 1 vào kết quả.

### Ô 2: Sử dụng ký hiệu R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Ở đây, chúng tôi thiết lập công thức cho ô C2 bằng cách sử dụng ký hiệu R1C1. Công thức tính giá trị lớn nhất trong phạm vi R2C6 đến R5C8 rồi chia cho 3.

## Bước 3: Tính toán công thức

Sau khi thiết lập công thức, điều quan trọng là phải tính toán chúng bằng đoạn mã sau:

```java
workbook.calculateFormulas();
```

Bước này đảm bảo rằng biểu đồ phản ánh các giá trị được cập nhật dựa trên các công thức.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày đã chỉnh sửa vào một tập tin.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho công thức ô dữ liệu biểu đồ trong Java Slides

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách làm việc với các công thức ô dữ liệu biểu đồ trong Aspose.Slides for Java. Chúng tôi đã đề cập đến việc tạo bản trình bày PowerPoint, thêm biểu đồ, thiết lập công thức cho các ô dữ liệu, tính toán công thức và lưu bản trình bày. Bây giờ bạn có thể tận dụng các khả năng này để tạo biểu đồ động và theo dữ liệu trong bản trình bày của mình.

## Câu hỏi thường gặp

### Làm thế nào để thêm biểu đồ vào một slide cụ thể?

Để thêm biểu đồ vào một trang chiếu cụ thể, bạn có thể sử dụng `getSlides().get_Item(slideIndex)` phương pháp để truy cập vào slide mong muốn, sau đó sử dụng `addChart` phương pháp thêm biểu đồ.

### Tôi có thể sử dụng các loại công thức khác nhau trong ô dữ liệu không?

Có, bạn có thể sử dụng nhiều loại công thức khác nhau, bao gồm các phép toán, hàm và tham chiếu đến các ô khác, trong công thức ô dữ liệu.

### Làm thế nào để thay đổi loại biểu đồ?

Bạn có thể thay đổi loại biểu đồ bằng cách sử dụng `setChartType` phương pháp trên `IChart` đối tượng và chỉ định mong muốn `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}