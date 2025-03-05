---
title: Biểu đồ công thức ô dữ liệu trong Java Slides
linktitle: Biểu đồ công thức ô dữ liệu trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt công thức ô dữ liệu biểu đồ trong bản trình bày Java PowerPoint bằng Aspose.Slides cho Java. Tạo biểu đồ động với các công thức.
type: docs
weight: 11
url: /vi/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

## Giới thiệu về Công thức ô dữ liệu biểu đồ trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các công thức ô dữ liệu biểu đồ bằng Aspose.Slides cho Java. Với Aspose.Slides, bạn có thể tạo và thao tác với biểu đồ trong bản trình bày PowerPoint, bao gồm cả việc thiết lập công thức cho các ô dữ liệu.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo bản trình bày PowerPoint

Trước tiên, hãy tạo một bản trình bày PowerPoint mới và thêm biểu đồ vào đó.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Thêm biểu đồ vào slide đầu tiên
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Lấy sổ làm việc cho dữ liệu biểu đồ
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

## Bước 2: Đặt công thức cho ô dữ liệu

Bây giờ, hãy đặt công thức cho các ô dữ liệu cụ thể trong biểu đồ. Trong ví dụ này, chúng tôi sẽ đặt công thức cho hai ô khác nhau.

### Ô 1: Sử dụng ký hiệu A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Trong đoạn mã trên, chúng ta đặt công thức cho ô B2 bằng ký hiệu A1. Công thức tính tổng các ô từ F2 đến H5 và cộng 1 vào kết quả.

### Ô 2: Sử dụng ký hiệu R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Ở đây, chúng tôi đặt công thức cho ô C2 bằng ký hiệu R1C1. Công thức tính giá trị lớn nhất trong phạm vi từ R2C6 đến R5C8 rồi chia cho 3.

## Bước 3: Tính công thức

Sau khi thiết lập các công thức, điều cần thiết là tính toán chúng bằng mã sau:

```java
workbook.calculateFormulas();
```

Bước này đảm bảo rằng biểu đồ phản ánh các giá trị được cập nhật dựa trên các công thức.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày đã sửa đổi vào một tệp.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh cho các công thức ô dữ liệu biểu đồ trong các trang trình bày Java

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

Trong hướng dẫn này, chúng ta đã khám phá cách làm việc với các công thức ô dữ liệu biểu đồ trong Aspose.Slides cho Java. Chúng tôi đã đề cập đến việc tạo bản trình bày PowerPoint, thêm biểu đồ, đặt công thức cho ô dữ liệu, tính toán công thức và lưu bản trình bày. Giờ đây, bạn có thể tận dụng những khả năng này để tạo biểu đồ động và theo hướng dữ liệu trong bản trình bày của mình.

## Câu hỏi thường gặp

### Làm cách nào để thêm biểu đồ vào một trang trình bày cụ thể?

 Để thêm biểu đồ vào một slide cụ thể, bạn có thể sử dụng`getSlides().get_Item(slideIndex)` để truy cập vào slide mong muốn, sau đó sử dụng`addChart` phương pháp thêm biểu đồ.

### Tôi có thể sử dụng các loại công thức khác nhau trong ô dữ liệu không?

Có, bạn có thể sử dụng nhiều loại công thức khác nhau, bao gồm các phép toán, hàm và tham chiếu đến các ô khác trong công thức ô dữ liệu.

### Làm cách nào để thay đổi loại biểu đồ?

 Bạn có thể thay đổi loại biểu đồ bằng cách sử dụng`setChartType` phương pháp trên`IChart` đối tượng và xác định mong muốn`ChartType`.