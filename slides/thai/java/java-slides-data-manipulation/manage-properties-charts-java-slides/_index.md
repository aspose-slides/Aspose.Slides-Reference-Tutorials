---
"description": "เรียนรู้การสร้างแผนภูมิที่สวยงามและการจัดการคุณสมบัติในสไลด์ Java ด้วย Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการนำเสนอที่มีประสิทธิภาพ"
"linktitle": "การจัดการคุณสมบัติแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การจัดการคุณสมบัติแผนภูมิใน Java Slides"
"url": "/th/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการคุณสมบัติแผนภูมิใน Java Slides


## การแนะนำการจัดการคุณสมบัติและแผนภูมิใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการจัดการคุณสมบัติและสร้างแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides Aspose.Slides เป็น Java API ที่ทรงพลังสำหรับการทำงานกับการนำเสนอ PowerPoint เราจะพาคุณผ่านกระบวนการทีละขั้นตอน รวมถึงตัวอย่างโค้ดต้นฉบับ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## การเพิ่มแผนภูมิลงในสไลด์

หากต้องการเพิ่มแผนภูมิลงในสไลด์ ให้ทำตามขั้นตอนเหล่านี้:

1. นำเข้าคลาสที่จำเป็นและสร้างอินสแตนซ์ของคลาสการนำเสนอ

```java
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

2. เข้าถึงสไลด์ที่คุณต้องการเพิ่มแผนภูมิ ในตัวอย่างนี้ เราจะเข้าถึงสไลด์แรก

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```

3. เพิ่มแผนภูมิที่มีข้อมูลเริ่มต้น ในกรณีนี้ เราจะเพิ่มแผนภูมิ StackedColumn3D

```java
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## การตั้งค่าข้อมูลแผนภูมิ

ในการตั้งค่าข้อมูลแผนภูมิ เราต้องสร้างเวิร์กบุ๊กข้อมูลแผนภูมิและเพิ่มชุดข้อมูลและหมวดหมู่ ทำตามขั้นตอนเหล่านี้:

4. ตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ

```java
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
```

5. รับสมุดงานข้อมูลแผนภูมิ

```java
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. เพิ่มชุดข้อมูลลงในแผนภูมิ ในตัวอย่างนี้ เราเพิ่มชุดข้อมูลสองชุดชื่อ "ชุดข้อมูล 1" และ "ชุดข้อมูล 2"

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. เพิ่มหมวดหมู่ลงในแผนภูมิ ที่นี่เราจะเพิ่มสามหมวดหมู่

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## การตั้งค่าคุณสมบัติการหมุน 3 มิติ

ต่อไปเรามาตั้งค่าคุณสมบัติการหมุน 3 มิติให้กับแผนภูมิกัน:

8. ตั้งแกนตั้งฉาก

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. กำหนดมุมการหมุนสำหรับแกน X และ Y ในตัวอย่างนี้ เราหมุนแกน X 40 องศา และแกน Y 270 องศา

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. ตั้งค่าเปอร์เซ็นต์ความลึกเป็น 150

```java
chart.getRotation3D().setDepthPercents(150);
```

## การเติมข้อมูลชุดข้อมูล

11. นำชุดแผนภูมิที่ 2 มาใส่จุดข้อมูล

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// เติมข้อมูลชุด
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## การปรับการทับซ้อน

12. ตั้งค่าการทับซ้อนสำหรับซีรีส์ ตัวอย่างเช่น คุณสามารถตั้งค่าเป็น 100 เพื่อไม่ให้มีการทับซ้อน

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## การบันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอลงดิสก์

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้างแผนภูมิคอลัมน์แบบเรียงซ้อน 3 มิติพร้อมคุณสมบัติที่กำหนดเองได้สำเร็จโดยใช้ Aspose.Slides ใน Java

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการจัดการคุณสมบัติแผนภูมิใน Java Slides

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
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// เพิ่มซีรี่ย์
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// เพิ่มหมวดหมู่
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// ตั้งค่าคุณสมบัติ Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// มาดูแผนภูมิชุดที่สองกัน
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// ตั้งค่าค่า OverLap
series.getParentSeriesGroup().setOverlap((byte) 100);
// เขียนการนำเสนอลงดิสก์
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการจัดการคุณสมบัติและการสร้างแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides Aspose.Slides คือ Java API ที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถทำงานกับการนำเสนอ PowerPoint ได้อย่างมีประสิทธิภาพ เราได้กล่าวถึงขั้นตอนที่สำคัญและให้ตัวอย่างโค้ดต้นฉบับเพื่อแนะนำคุณตลอดกระบวนการ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร

คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแก้ไข `ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิ โปรดดูเอกสาร Aspose.Slides สำหรับประเภทแผนภูมิที่มีให้เลือก

### ฉันสามารถปรับแต่งสีแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับแต่งสีแผนภูมิได้โดยการตั้งค่าคุณสมบัติการเติมของจุดข้อมูลชุดหรือหมวดหมู่

### ฉันจะเพิ่มจุดข้อมูลเพิ่มเติมลงในชุดข้อมูลได้อย่างไร

คุณสามารถเพิ่มจุดข้อมูลเพิ่มเติมลงในชุดข้อมูลได้โดยใช้ `series.getDataPoints().addDataPointForBarSeries()` วิธีการและระบุเซลล์ที่มีค่าข้อมูล

### ฉันจะตั้งค่ามุมการหมุนที่แตกต่างกันได้อย่างไร

หากต้องการตั้งค่ามุมการหมุนที่แตกต่างกันสำหรับแกน X และ Y ให้ใช้ `chart.getRotation3D().setRotationX()` และ `chart.getRotation3D().setRotationY()` ด้วยค่ามุมที่ต้องการ

### ฉันสามารถปรับแต่งคุณสมบัติ 3D อะไรได้อีกบ้าง

คุณสามารถสำรวจคุณสมบัติ 3 มิติอื่นๆ ของแผนภูมิ เช่น ความลึก มุมมอง และแสง โดยอ้างอิงจากเอกสาร Aspose.Slides

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}