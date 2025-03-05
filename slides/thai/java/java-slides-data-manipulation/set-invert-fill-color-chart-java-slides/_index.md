---
title: ตั้งค่าแผนภูมิสีเติมกลับใน Java Slides
linktitle: ตั้งค่าแผนภูมิสีเติมกลับใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าสีเติมกลับด้านสำหรับแผนภูมิ Java Slides โดยใช้ Aspose.Slides ปรับปรุงการแสดงภาพแผนภูมิของคุณด้วยคำแนะนำทีละขั้นตอนและซอร์สโค้ดนี้
type: docs
weight: 22
url: /th/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าแผนภูมิสีกลับด้านใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีตั้งค่าสีเติมกลับด้านสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java การกลับสีเติมเป็นคุณลักษณะที่มีประโยชน์เมื่อคุณต้องการเน้นค่าลบในแผนภูมิที่มีสีเฉพาะเจาะจง เราจะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ดเพื่อให้บรรลุเป้าหมายนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. ติดตั้ง Aspose.Slides สำหรับไลบรารี Java แล้ว
2. ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก เราต้องสร้างงานนำเสนอเพื่อเพิ่มแผนภูมิของเราลงไป คุณสามารถใช้รหัสต่อไปนี้เพื่อสร้างงานนำเสนอ:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ต่อไป เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มในการนำเสนอ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## ขั้นตอนที่ 3: ตั้งค่าข้อมูลแผนภูมิ

ตอนนี้ มาตั้งค่าข้อมูลแผนภูมิ รวมถึงซีรี่ส์และหมวดหมู่:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// เพิ่มซีรี่ส์และหมวดหมู่ใหม่
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## ขั้นตอนที่ 4: เติมข้อมูลซีรี่ส์

ตอนนี้ มาเติมข้อมูลชุดข้อมูลสำหรับแผนภูมิกัน:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## ขั้นตอนที่ 5: ตั้งค่า Invert Fill Color

หากต้องการตั้งค่าสีเติมกลับด้านสำหรับชุดแผนภูมิ คุณสามารถใช้โค้ดต่อไปนี้:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

ในโค้ดด้านบน เราตั้งค่าชุดให้กลับสีเติมสำหรับค่าลบ และระบุสีสำหรับการเติมกลับด้าน

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอด้วยแผนภูมิ:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับตั้งค่า Invert Fill Color Chart ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// เพิ่มซีรี่ส์และหมวดหมู่ใหม่
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// ใช้ชุดแผนภูมิแรกและเติมข้อมูลชุดข้อมูล
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้แสดงวิธีตั้งค่าสีเติมกลับด้านสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณลักษณะนี้ช่วยให้คุณสามารถเน้นค่าลบในแผนภูมิของคุณด้วยสีเฉพาะ ทำให้ข้อมูลของคุณมีข้อมูลเชิงภาพมากขึ้น

## คำถามที่พบบ่อย

ในส่วนนี้ เราจะตอบคำถามทั่วไปบางส่วนที่เกี่ยวข้องกับการตั้งค่าการกลับสีเติมสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถติดตั้ง Aspose.Slides สำหรับ Java โดยรวมไฟล์ JAR ของ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[Aspose.Slides สำหรับหน้าดาวน์โหลด Java](https://releases.aspose.com/slides/java/)- ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบสำหรับสภาพแวดล้อมการพัฒนาเฉพาะของคุณ

### ฉันสามารถปรับแต่งสีสำหรับการเติมแบบกลับด้านในชุดแผนภูมิได้หรือไม่

ได้ คุณสามารถปรับแต่งสีสำหรับการเติมแบบกลับหัวในชุดแผนภูมิได้ ในตัวอย่างโค้ดที่ให้มา`series.getInvertedSolidFillColor().setColor(Color.RED)` เส้นจะตั้งค่าสีเป็นสีแดงสำหรับการเติมแบบกลับด้าน คุณสามารถแทนที่ได้`Color.RED` กับสีอื่นที่คุณเลือก

### ฉันจะแก้ไขประเภทแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถแก้ไขประเภทแผนภูมิได้โดยการเปลี่ยน`ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิลงในการนำเสนอ ในตัวอย่างโค้ดเราใช้`ChartType.ClusteredColumn` - คุณสามารถสำรวจแผนภูมิประเภทอื่นๆ ได้ เช่น แผนภูมิเส้น แผนภูมิแท่ง แผนภูมิวงกลม ฯลฯ โดยระบุแผนภูมิที่เหมาะสม`ChartType` ค่าแจงนับ

### ฉันจะเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิได้อย่างไร

 หากต้องการเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิ คุณสามารถใช้`chart.getChartData().getSeries().add(...)` วิธีการสำหรับแต่ละซีรี่ส์ที่คุณต้องการเพิ่ม ตรวจสอบให้แน่ใจว่าได้จัดเตรียมจุดข้อมูลและป้ายกำกับที่เหมาะสมสำหรับแต่ละชุดข้อมูลเพื่อเติมข้อมูลในแผนภูมิของคุณด้วยชุดข้อมูลหลายชุด

### มีวิธีปรับแต่งลักษณะอื่นๆ ของแผนภูมิหรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะต่างๆ ของลักษณะแผนภูมิได้ รวมถึงป้ายกำกับแกน ชื่อ คำอธิบาย และอื่นๆ โดยใช้ Aspose.Slides สำหรับ Java โปรดดูเอกสารประกอบสำหรับคำแนะนำโดยละเอียดเกี่ยวกับการปรับแต่งองค์ประกอบแผนภูมิและรูปลักษณ์

### ฉันสามารถบันทึกแผนภูมิในรูปแบบอื่นได้หรือไม่

 ได้ คุณสามารถบันทึกแผนภูมิในรูปแบบต่างๆ ได้โดยใช้ Aspose.Slides สำหรับ Java ในตัวอย่างโค้ดที่ให้มา เราได้บันทึกงานนำเสนอเป็นไฟล์ PPTX คุณสามารถใช้ที่แตกต่างกัน`SaveFormat` ตัวเลือกในการบันทึกในรูปแบบอื่น เช่น PDF, PNG หรือ SVG ขึ้นอยู่กับความต้องการของคุณ