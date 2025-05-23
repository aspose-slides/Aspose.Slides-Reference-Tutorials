---
"description": "ปรับปรุงการนำเสนอ PowerPoint ของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้การแก้ไขแผนภูมิที่มีอยู่ด้วยโปรแกรม คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการปรับแต่งแผนภูมิ"
"linktitle": "แผนภูมิที่มีอยู่แล้วใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิที่มีอยู่แล้วใน Java Slides"
"url": "/th/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิที่มีอยู่แล้วใน Java Slides


## การแนะนำแผนภูมิที่มีอยู่ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการปรับเปลี่ยนแผนภูมิที่มีอยู่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราจะอธิบายขั้นตอนต่างๆ ในการเปลี่ยนแปลงข้อมูลแผนภูมิ ชื่อหมวดหมู่ ชื่อชุด และเพิ่มชุดใหม่ลงในแผนภูมิ ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่า Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณแล้ว

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. มีไลบรารี Aspose.Slides สำหรับ Java รวมอยู่ในโปรเจ็กต์ของคุณ
2. การนำเสนอ PowerPoint ที่มีอยู่พร้อมแผนภูมิที่คุณต้องการปรับเปลี่ยน
3. การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
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

// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// เปลี่ยนชื่อหมวดหมู่ของแผนภูมิ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## ขั้นตอนที่ 4: อัปเดตชุดแผนภูมิแรก

```java
// มาดูแผนภูมิชุดแรกกัน
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// อัพเดทชื่อซีรีย์
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// อัปเดตข้อมูลซีรีย์
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## ขั้นตอนที่ 5: อัปเดตชุดแผนภูมิที่สอง

```java
// มาดูแผนภูมิชุดที่ 2 กัน
series = chart.getChartData().getSeries().get_Item(1);

// อัพเดทชื่อซีรีย์
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// อัปเดตข้อมูลซีรีย์
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## ขั้นตอนที่ 6: เพิ่มซีรีส์ใหม่ลงในแผนภูมิ

```java
// เพิ่มซีรีย์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// มาดูแผนภูมิชุดที่ 3 กัน
series = chart.getChartData().getSeries().get_Item(2);

// เติมข้อมูลชุด
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## ขั้นตอนที่ 7: เปลี่ยนประเภทแผนภูมิ

```java
// เปลี่ยนประเภทแผนภูมิเป็นทรงกระบอกแบบคลัสเตอร์
chart.setType(ChartType.ClusteredCylinder);
```

## ขั้นตอนที่ 8: บันทึกการนำเสนอที่แก้ไขแล้ว

```java
// บันทึกการนำเสนอด้วยแผนภูมิที่แก้ไขแล้ว
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

ขอแสดงความยินดี! คุณได้แก้ไขแผนภูมิที่มีอยู่ในงานนำเสนอ PowerPoint สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java ตอนนี้คุณสามารถใช้โค้ดนี้เพื่อปรับแต่งแผนภูมิในงานนำเสนอ PowerPoint ของคุณผ่านโปรแกรมได้แล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิที่มีอยู่ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// เข้าถึงสไลด์แรกMarker
ISlide sld = pres.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = (IChart) sld.getShapes().get_Item(0);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// การเปลี่ยนแปลงชื่อหมวดหมู่แผนภูมิ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// เริ่มต้นด้วยชุดแผนภูมิแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// กำลังอัปเดตข้อมูลซีรีย์
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// การแก้ไขชื่อซีรีย์
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// แผนภูมิชุดที่สอง
series = chart.getChartData().getSeries().get_Item(1);
// กำลังอัปเดตข้อมูลซีรีย์
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// การแก้ไขชื่อซีรีย์
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// ตอนนี้กำลังเพิ่มซีรีย์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// นำแผนภูมิชุดที่ 3 มาใช้
series = chart.getChartData().getSeries().get_Item(2);
// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// บันทึกการนำเสนอด้วยแผนภูมิ
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## บทสรุป

ในบทช่วยสอนที่ครอบคลุมนี้ เราได้เรียนรู้วิธีการปรับเปลี่ยนแผนภูมิที่มีอยู่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและใช้ตัวอย่างโค้ดต้นฉบับ คุณสามารถปรับแต่งและอัปเดตแผนภูมิได้อย่างง่ายดายเพื่อตอบสนองความต้องการเฉพาะของคุณ นี่คือบทสรุปของสิ่งที่เราครอบคลุม:

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร

คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยใช้ `chart.setType(ChartType.ChartTypeHere)` วิธีการ. แทนที่ `ChartTypeHere` ด้วยประเภทแผนภูมิที่ต้องการ เช่น `ChartType.ClusteredCylinder` ในตัวอย่างของเรา

### ฉันสามารถเพิ่มจุดข้อมูลเพิ่มเติมลงในชุดข้อมูลได้หรือไม่

ใช่ คุณสามารถเพิ่มจุดข้อมูลเพิ่มเติมลงในชุดข้อมูลได้โดยใช้ `series.getDataPoints().addDataPointForBarSeries(cell)` วิธีการนี้ โปรดแน่ใจว่าคุณให้ข้อมูลเซลล์ที่เหมาะสม

### ฉันจะอัพเดตชื่อหมวดหมู่ได้อย่างไร?

คุณสามารถอัปเดตชื่อหมวดหมู่ได้โดยใช้ `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` เพื่อตั้งชื่อหมวดหมู่ใหม่

### ฉันจะแก้ไขชื่อซีรีย์ได้อย่างไร?

หากต้องการปรับเปลี่ยนชื่อซีรีย์ ให้ใช้ `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` การตั้งชื่อซีรีย์ใหม่

### มีวิธีลบซีรีส์ออกจากแผนภูมิหรือไม่

ใช่ คุณสามารถลบซีรีส์ออกจากแผนภูมิได้โดยใช้ `chart.getChartData().getSeries().removeAt(index)` วิธีการที่ `index` เป็นดัชนีของซีรี่ส์ที่คุณต้องการลบ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}