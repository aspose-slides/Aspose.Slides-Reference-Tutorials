---
title: แผนภูมิที่มีอยู่ใน Java Slides
linktitle: แผนภูมิที่มีอยู่ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ปรับปรุงงานนำเสนอ PowerPoint ของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้การแก้ไขแผนภูมิที่มีอยู่โดยทางโปรแกรม คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับการปรับแต่งแผนภูมิ
weight: 12
url: /th/java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิที่มีอยู่ใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับแผนภูมิที่มีอยู่ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสาธิตวิธีแก้ไขแผนภูมิที่มีอยู่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราจะทำตามขั้นตอนต่างๆ เพื่อเปลี่ยนข้อมูลแผนภูมิ ชื่อหมวดหมู่ ชื่อซีรีส์ และเพิ่มซีรีส์ใหม่ลงในแผนภูมิ ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่า Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Aspose.Slides สำหรับไลบรารี Java ที่รวมอยู่ในโครงการของคุณ
2. งานนำเสนอ PowerPoint ที่มีอยู่พร้อมแผนภูมิที่คุณต้องการแก้ไข
3. ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงสไลด์และแผนภูมิ

```java
// เข้าถึงสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);

// เข้าถึงแผนภูมิบนสไลด์
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## ขั้นตอนที่ 3: เปลี่ยนข้อมูลแผนภูมิและชื่อหมวดหมู่

```java
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;

// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// เปลี่ยนชื่อหมวดหมู่แผนภูมิ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## ขั้นตอนที่ 4: อัปเดตซีรี่ส์แผนภูมิแรก

```java
// ใช้แผนภูมิชุดแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// อัพเดทชื่อซีรีย์
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// อัปเดตข้อมูลซีรีส์
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## ขั้นตอนที่ 5: อัปเดตซีรี่ส์แผนภูมิที่สอง

```java
// ใช้ชุดแผนภูมิที่สอง
series = chart.getChartData().getSeries().get_Item(1);

// อัพเดทชื่อซีรีย์
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// อัปเดตข้อมูลซีรีส์
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## ขั้นตอนที่ 6: เพิ่มซีรี่ส์ใหม่ลงในแผนภูมิ

```java
// การเพิ่มซีรีส์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// ใช้ชุดแผนภูมิที่สาม
series = chart.getChartData().getSeries().get_Item(2);

// เติมข้อมูลชุดข้อมูล
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## ขั้นตอนที่ 7: เปลี่ยนประเภทแผนภูมิ

```java
//เปลี่ยนประเภทแผนภูมิเป็นทรงกระบอกแบบคลัสเตอร์
chart.setType(ChartType.ClusteredCylinder);
```

## ขั้นตอนที่ 8: บันทึกงานนำเสนอที่แก้ไข

```java
// บันทึกงานนำเสนอด้วยแผนภูมิที่ปรับเปลี่ยน
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

ยินดีด้วย! คุณแก้ไขแผนภูมิที่มีอยู่ในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ตอนนี้คุณสามารถใช้โค้ดนี้เพื่อปรับแต่งแผนภูมิในงานนำเสนอ PowerPoint ของคุณโดยทางโปรแกรมได้

## กรอกซอร์สโค้ดสำหรับแผนภูมิที่มีอยู่ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// เข้าถึง SlideMarker แรก
ISlide sld = pres.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = (IChart) sld.getShapes().get_Item(0);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// การเปลี่ยนชื่อหมวดหมู่แผนภูมิ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// ใช้แผนภูมิชุดแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// ขณะนี้กำลังอัปเดตข้อมูลซีรีส์
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// การแก้ไขชื่อซีรีส์
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// ใช้ซีรีส์แผนภูมิที่สอง
series = chart.getChartData().getSeries().get_Item(1);
// ขณะนี้กำลังอัปเดตข้อมูลซีรีส์
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// การแก้ไขชื่อซีรีส์
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// ตอนนี้กำลังเพิ่มซีรี่ส์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// ใช้แผนภูมิลำดับที่ 3
series = chart.getChartData().getSeries().get_Item(2);
// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// บันทึกการนำเสนอด้วยแผนภูมิ
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## บทสรุป

ในบทช่วยสอนที่ครอบคลุมนี้ เราได้เรียนรู้วิธีแก้ไขแผนภูมิที่มีอยู่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอนและการใช้ตัวอย่างซอร์สโค้ด คุณสามารถปรับแต่งและอัปเดตแผนภูมิให้ตรงกับความต้องการเฉพาะของคุณได้อย่างง่ายดาย นี่คือบทสรุปของสิ่งที่เรากล่าวถึง:

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยใช้`chart.setType(ChartType.ChartTypeHere)` วิธี. แทนที่`ChartTypeHere` ด้วยประเภทกราฟที่ต้องการ เช่น`ChartType.ClusteredCylinder` ในตัวอย่างของเรา

### ฉันสามารถเพิ่มจุดข้อมูลลงในซีรีส์ได้หรือไม่

 ใช่ คุณสามารถเพิ่มจุดข้อมูลลงในชุดข้อมูลได้โดยใช้`series.getDataPoints().addDataPointForBarSeries(cell)` วิธี. ตรวจสอบให้แน่ใจว่าได้ให้ข้อมูลเซลล์ที่เหมาะสม

### ฉันจะอัพเดตชื่อหมวดหมู่ได้อย่างไร?

 คุณสามารถอัพเดตชื่อหมวดหมู่ได้โดยใช้`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` เพื่อตั้งชื่อหมวดหมู่ใหม่

### ฉันจะแก้ไขชื่อซีรีส์ได้อย่างไร

 หากต้องการแก้ไขชื่อซีรีส์ ให้ใช้`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` เพื่อตั้งชื่อซีรีส์ใหม่

### มีวิธีลบซีรี่ส์ออกจากแผนภูมิหรือไม่?

 ใช่ คุณสามารถลบชุดข้อมูลออกจากแผนภูมิได้โดยใช้`chart.getChartData().getSeries().removeAt(index)` วิธีการที่ไหน`index`คือดัชนีของซีรีส์ที่คุณต้องการลบ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
