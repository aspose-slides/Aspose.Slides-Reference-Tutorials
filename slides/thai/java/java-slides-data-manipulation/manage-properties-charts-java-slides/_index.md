---
title: จัดการแผนภูมิคุณสมบัติใน Java Slides
linktitle: จัดการแผนภูมิคุณสมบัติใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิที่น่าทึ่งและจัดการคุณสมบัติในสไลด์ Java ด้วย Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการนำเสนอที่ทรงพลัง
weight: 13
url: /th/java/data-manipulation/manage-properties-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการจัดการคุณสมบัติและแผนภูมิใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการคุณสมบัติและสร้างแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides Aspose.Slides เป็น Java API ที่ทรงพลังสำหรับการทำงานกับงานนำเสนอ PowerPoint เราจะอธิบายกระบวนการทีละขั้นตอน รวมถึงตัวอย่างซอร์สโค้ด

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## การเพิ่มแผนภูมิลงในสไลด์

เมื่อต้องการเพิ่มแผนภูมิลงในสไลด์ ให้ทำตามขั้นตอนเหล่านี้:

1. นำเข้าคลาสที่จำเป็นและสร้างอินสแตนซ์ของคลาสการนำเสนอ

```java
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

2. เข้าถึงสไลด์ที่คุณต้องการเพิ่มแผนภูมิ ในตัวอย่างนี้ เราเข้าถึงสไลด์แรก

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```

3. เพิ่มแผนภูมิที่มีข้อมูลเริ่มต้น ในกรณีนี้ เรากำลังเพิ่มแผนภูมิ StackedColumn3D

```java
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## การตั้งค่าข้อมูลแผนภูมิ

ในการตั้งค่าข้อมูลแผนภูมิ เราจำเป็นต้องสร้างสมุดงานข้อมูลแผนภูมิและเพิ่มซีรี่ส์และหมวดหมู่ ทำตามขั้นตอนเหล่านี้:

4. ตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ

```java
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
```

5. รับสมุดงานข้อมูลแผนภูมิ

```java
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. เพิ่มซีรีส์ลงในแผนภูมิ ในตัวอย่างนี้ เราเพิ่มสองซีรี่ส์ชื่อ "Series 1" และ "Series 2"

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. เพิ่มหมวดหมู่ลงในแผนภูมิ ที่นี่เราเพิ่มสามหมวดหมู่

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## การตั้งค่าคุณสมบัติการหมุน 3D

ตอนนี้ มาตั้งค่าคุณสมบัติการหมุนสามมิติสำหรับแผนภูมิกัน:

8. ตั้งแกนมุมขวา

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. ตั้งค่ามุมการหมุนสำหรับแกน X และ Y ในตัวอย่างนี้ เราหมุน X คูณ 40 องศา และ Y คูณ 270 องศา

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. ตั้งค่าเปอร์เซ็นต์ความลึกเป็น 150

```java
chart.getRotation3D().setDepthPercents(150);
```

## การเติมข้อมูลซีรี่ส์

11. นำชุดแผนภูมิที่สองมาเติมด้วยจุดข้อมูล

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// เติมข้อมูลชุดข้อมูล
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## การปรับการทับซ้อน

12. ตั้งค่าทับซ้อนสำหรับซีรีส์ ตัวอย่างเช่น คุณสามารถตั้งค่าเป็น 100 เพื่อไม่ให้ทับซ้อนกัน

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## กำลังบันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอลงดิสก์

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณสร้างแผนภูมิคอลัมน์แบบเรียงซ้อน 3 มิติพร้อมคุณสมบัติที่กำหนดเองโดยใช้ Aspose.Slides ใน Java สำเร็จแล้ว

## กรอกซอร์สโค้ดสำหรับจัดการแผนภูมิคุณสมบัติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// เพิ่มซีรีส์
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// เพิ่ม Catrgories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// ตั้งค่าคุณสมบัติ Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// ใช้แผนภูมิชุดที่สอง
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// ตั้งค่าโอเวอร์แลป
series.getParentSeriesGroup().setOverlap((byte) 100);
// เขียนงานนำเสนอลงดิสก์
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เจาะลึกโลกแห่งการจัดการคุณสมบัติและการสร้างแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides Aspose.Slides เป็น Java API ที่แข็งแกร่งซึ่งช่วยให้นักพัฒนาทำงานกับงานนำเสนอ PowerPoint ได้อย่างมีประสิทธิภาพ เราได้ครอบคลุมขั้นตอนที่จำเป็นและให้ตัวอย่างซอร์สโค้ดเพื่อแนะนำคุณตลอดกระบวนการ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแก้ไข`ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิ โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับประเภทแผนภูมิที่มี

### ฉันสามารถปรับแต่งสีแผนภูมิได้หรือไม่

ได้ คุณสามารถปรับแต่งสีแผนภูมิได้โดยการตั้งค่าคุณสมบัติการเติมของจุดข้อมูลชุดข้อมูลหรือหมวดหมู่

### ฉันจะเพิ่มจุดข้อมูลลงในซีรีส์ได้อย่างไร

 คุณสามารถเพิ่มจุดข้อมูลลงในชุดข้อมูลได้โดยใช้`series.getDataPoints().addDataPointForBarSeries()` วิธีการและระบุเซลล์ที่มีค่าข้อมูล

### ฉันจะกำหนดมุมการหมุนที่แตกต่างกันได้อย่างไร

 หากต้องการตั้งค่ามุมการหมุนที่แตกต่างกันสำหรับแกน X และ Y ให้ใช้`chart.getRotation3D().setRotationX()` และ`chart.getRotation3D().setRotationY()` ด้วยค่ามุมที่ต้องการ

### ฉันสามารถปรับแต่งคุณสมบัติ 3D อื่นใดได้อีกบ้าง

คุณสามารถสำรวจคุณสมบัติ 3 มิติอื่นๆ ของแผนภูมิได้ เช่น ความลึก เปอร์สเปคทีฟ และการจัดแสง โดยอ้างอิงจากเอกสารประกอบของ Aspose.Slides
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
