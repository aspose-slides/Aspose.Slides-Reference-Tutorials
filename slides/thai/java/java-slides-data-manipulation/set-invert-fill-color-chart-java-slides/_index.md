---
"description": "เรียนรู้วิธีตั้งค่าสีเติมแบบกลับด้านสำหรับแผนภูมิ Java Slides โดยใช้ Aspose.Slides ปรับปรุงการแสดงภาพแผนภูมิของคุณด้วยคู่มือทีละขั้นตอนและโค้ดต้นฉบับนี้"
"linktitle": "ตั้งค่าแผนภูมิสีเติมแบบกลับด้านใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าแผนภูมิสีเติมแบบกลับด้านใน Java Slides"
"url": "/th/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าแผนภูมิสีเติมแบบกลับด้านใน Java Slides


## บทนำสู่การตั้งค่าแผนภูมิสีเติมแบบกลับด้านใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการตั้งค่าสีเติมแบบกลับด้านสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java การกลับสีเติมเป็นฟีเจอร์ที่มีประโยชน์เมื่อคุณต้องการเน้นค่าลบในแผนภูมิด้วยสีเฉพาะ เราจะให้คำแนะนำแบบทีละขั้นตอนและโค้ดต้นฉบับสำหรับการดำเนินการดังกล่าว

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว
2. การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก เราต้องสร้างงานนำเสนอเพื่อเพิ่มแผนภูมิของเรา คุณสามารถใช้โค้ดต่อไปนี้เพื่อสร้างงานนำเสนอ:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ต่อไปเราจะเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในงานนำเสนอ โดยคุณสามารถทำได้ดังนี้:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## ขั้นตอนที่ 3: ตั้งค่าข้อมูลแผนภูมิ

ต่อไปเรามาตั้งค่าข้อมูลแผนภูมิรวมทั้งชุดข้อมูลและหมวดหมู่กัน:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// เพิ่มซีรีย์และหมวดหมู่ใหม่
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## ขั้นตอนที่ 4: เติมข้อมูลชุดข้อมูล

ตอนนี้เรามาเพิ่มข้อมูลชุดให้กับแผนภูมิกัน:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## ขั้นตอนที่ 5: ตั้งค่าสีเติมกลับด้าน

หากต้องการตั้งค่าสีเติมกลับด้านสำหรับชุดแผนภูมิ คุณสามารถใช้โค้ดดังต่อไปนี้:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

ในโค้ดด้านบน เราตั้งค่าชุดข้อมูลเพื่อย้อนกลับสีเติมสำหรับค่าลบ และระบุสีสำหรับการเติมแบบกลับด้าน

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอด้วยแผนภูมิ:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการตั้งค่าแผนภูมิสีแบบ Invert Fill ใน Java Slides

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
// เพิ่มซีรีย์และหมวดหมู่ใหม่
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// ใช้แผนภูมิชุดแรกและเติมข้อมูลชุดข้อมูล
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

ในบทช่วยสอนนี้ เราได้แสดงวิธีการตั้งค่าสีเติมกลับด้านสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ฟีเจอร์นี้ช่วยให้คุณเน้นค่าลบในแผนภูมิด้วยสีเฉพาะ ทำให้ข้อมูลของคุณดูมีข้อมูลมากขึ้น

## คำถามที่พบบ่อย

ในส่วนนี้เราจะกล่าวถึงคำถามทั่วไปบางข้อที่เกี่ยวข้องกับการตั้งค่าสีเติมผกผันสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร?

คุณสามารถติดตั้ง Aspose.Slides สำหรับ Java ได้โดยรวมไฟล์ JAR ของ Aspose.Slides ไว้ในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จาก [หน้าดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/). ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบสำหรับสภาพแวดล้อมการพัฒนาเฉพาะของคุณ

### ฉันสามารถปรับแต่งสีสำหรับการเติมกลับด้านในชุดแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับแต่งสีสำหรับการเติมแบบกลับด้านในชุดแผนภูมิได้ ในตัวอย่างโค้ดที่ให้มา `series.getInvertedSolidFillColor().setColor(Color.RED)` เส้นจะกำหนดสีเป็นสีแดงสำหรับการเติมแบบกลับด้าน คุณสามารถแทนที่ `Color.RED` พร้อมสีอื่น ๆ ตามต้องการ

### ฉันจะปรับเปลี่ยนประเภทแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

คุณสามารถปรับเปลี่ยนประเภทแผนภูมิได้โดยการเปลี่ยน `ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิลงในงานนำเสนอ ในตัวอย่างโค้ด เราใช้ `ChartType.ClusteredColumn`คุณสามารถสำรวจแผนภูมิประเภทอื่น ๆ เช่น แผนภูมิเส้น แผนภูมิแท่ง แผนภูมิวงกลม ฯลฯ โดยระบุแผนภูมิที่เหมาะสม `ChartType` ค่า enum

### ฉันจะเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิได้อย่างไร

หากต้องการเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิ คุณสามารถใช้ `chart.getChartData().getSeries().add(...)` วิธีการสำหรับแต่ละซีรีส์ที่คุณต้องการเพิ่ม ตรวจสอบให้แน่ใจว่าคุณได้ระบุจุดข้อมูลและป้ายกำกับที่เหมาะสมสำหรับแต่ละซีรีส์เพื่อเติมแผนภูมิของคุณด้วยซีรีส์หลายชุด

### มีวิธีปรับแต่งลักษณะอื่น ๆ ของแผนภูมิหรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะต่างๆ ของแผนภูมิได้ เช่น ป้ายแกน ชื่อ คำอธิบาย และอื่นๆ โดยใช้ Aspose.Slides สำหรับ Java โปรดดูเอกสารประกอบสำหรับคำแนะนำโดยละเอียดเกี่ยวกับการปรับแต่งองค์ประกอบและลักษณะแผนภูมิ

### ฉันสามารถบันทึกแผนภูมิในรูปแบบที่แตกต่างกันได้หรือไม่

ใช่ คุณสามารถบันทึกแผนภูมิในรูปแบบต่างๆ ได้โดยใช้ Aspose.Slides สำหรับ Java ในตัวอย่างโค้ดที่ให้มา เราบันทึกการนำเสนอเป็นไฟล์ PPTX คุณสามารถใช้ไฟล์ต่างๆ ได้ `SaveFormat` ตัวเลือกในการบันทึกในรูปแบบอื่นเช่น PDF, PNG หรือ SVG ขึ้นอยู่กับความต้องการของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}