---
title: ตั้งค่าป้ายข้อมูลเปอร์เซ็นต์เครื่องหมายใน Java Slides
linktitle: ตั้งค่าป้ายข้อมูลเปอร์เซ็นต์เครื่องหมายใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าป้ายกำกับข้อมูลด้วยเครื่องหมายเปอร์เซ็นต์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สร้างแผนภูมิที่น่าสนใจพร้อมคำแนะนำทีละขั้นตอนและซอร์สโค้ด
weight: 17
url: /th/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าเปอร์เซ็นต์การลงชื่อเข้าใช้ป้ายกำกับข้อมูลใน Aspose.Slides สำหรับ Java

ในคู่มือนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่าป้ายกำกับข้อมูลด้วยเครื่องหมายเปอร์เซ็นต์โดยใช้ Aspose.Slides สำหรับ Java เราจะสร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิคอลัมน์แบบเรียงซ้อนและกำหนดค่าป้ายกำกับข้อมูลที่จะแสดงเปอร์เซ็นต์

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides for Java ให้กับโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก เราสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มสไลด์และแผนภูมิ

ต่อไป เราจะเพิ่มสไลด์และแผนภูมิคอลัมน์แบบเรียงซ้อนลงในงานนำเสนอ

```java
// รับข้อมูลอ้างอิงของสไลด์
ISlide slide = presentation.getSlides().get_Item(0);

// เพิ่มแผนภูมิ PercentsStackedColumn บนสไลด์
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## ขั้นตอนที่ 3: กำหนดค่ารูปแบบหมายเลขแกน

ในการแสดงเปอร์เซ็นต์ เราจำเป็นต้องกำหนดรูปแบบตัวเลขสำหรับแกนตั้งของแผนภูมิ

```java
// ตั้งค่า NumberFormatLinkedToSource เป็นเท็จ
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## ขั้นตอนที่ 4: เพิ่มข้อมูลแผนภูมิ

เราเพิ่มข้อมูลลงในแผนภูมิโดยการสร้างชุดข้อมูลและจุดข้อมูล ในตัวอย่างนี้ เราเพิ่มสองชุดพร้อมกับจุดข้อมูลตามลำดับ

```java
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// เพิ่มซีรีส์ใหม่
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// เพิ่มซีรีส์ใหม่
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## ขั้นตอนที่ 5: ปรับแต่งป้ายกำกับข้อมูล

ตอนนี้ มาปรับแต่งลักษณะที่ปรากฏของป้ายชื่อข้อมูลกัน

```java
// การตั้งค่าคุณสมบัติ LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้าย เราบันทึกงานนำเสนอเป็นไฟล์ PowerPoint

```java
// เขียนงานนำเสนอลงดิสก์
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้สร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิคอลัมน์แบบเรียงซ้อนและกำหนดค่าป้ายกำกับข้อมูลที่จะแสดงเปอร์เซ็นต์โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## ซอร์สโค้ดที่สมบูรณ์สำหรับการตั้งค่าเปอร์เซ็นต์ป้ายชื่อข้อมูลใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
// รับข้อมูลอ้างอิงของสไลด์
ISlide slide = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิ PercentsStackedColumn บนสไลด์
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// ตั้งค่า NumberFormatLinkedToSource เป็นเท็จ
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// เพิ่มซีรีส์ใหม่
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// การตั้งค่าสีเติมของซีรีส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// การตั้งค่าคุณสมบัติ LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// เพิ่มซีรีส์ใหม่
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// การตั้งค่าประเภทการเติมและสี
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// เขียนงานนำเสนอลงดิสก์
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ด้วยการทำตามคำแนะนำนี้ คุณจะได้เรียนรู้วิธีสร้างงานนำเสนอที่น่าสนใจด้วยป้ายข้อมูลตามเปอร์เซ็นต์ ซึ่งจะเป็นประโยชน์อย่างยิ่งในการถ่ายทอดข้อมูลอย่างมีประสิทธิภาพในรายงานทางธุรกิจ เอกสารทางการศึกษา และอื่นๆ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของชุดแผนภูมิได้อย่างไร

 คุณสามารถเปลี่ยนสีเติมของชุดแผนภูมิได้โดยใช้`setFill` วิธีการตามที่แสดงในตัวอย่าง

### ฉันสามารถกำหนดขนาดตัวอักษรของป้ายข้อมูลได้หรือไม่

ได้ คุณสามารถปรับแต่งขนาดตัวอักษรของป้ายกำกับข้อมูลได้โดยการตั้งค่า`setFontHeight` คุณสมบัติตามที่แสดงในรหัส

### ฉันจะเพิ่มซีรี่ส์ลงในแผนภูมิได้อย่างไร

 คุณสามารถเพิ่มซีรี่ส์เพิ่มเติมลงในแผนภูมิได้โดยใช้`add` วิธีการบน`IChartSeriesCollection` วัตถุ.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
