---
"description": "เรียนรู้วิธีปรับแต่งแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java สำรวจตัวเลือกพล็อตที่สองและปรับปรุงการนำเสนอของคุณ"
"linktitle": "ตัวเลือกพล็อตที่สองสำหรับแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตัวเลือกพล็อตที่สองสำหรับแผนภูมิใน Java Slides"
"url": "/th/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตัวเลือกพล็อตที่สองสำหรับแผนภูมิใน Java Slides


## การแนะนำตัวเลือกพล็อตที่สองสำหรับแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการเพิ่มตัวเลือกพล็อตที่สองให้กับแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java ตัวเลือกพล็อตที่สองช่วยให้คุณปรับแต่งลักษณะและพฤติกรรมของแผนภูมิได้ โดยเฉพาะในสถานการณ์เช่นแผนภูมิวงกลมหรือวงกลม เราจะให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับเพื่อให้บรรลุเป้าหมายนี้ 

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่า Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: สร้างงานนำเสนอ
เริ่มต้นด้วยการสร้างการนำเสนอใหม่:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์
ต่อไปเราจะเพิ่มแผนภูมิลงในสไลด์ ในตัวอย่างนี้ เราจะสร้างแผนภูมิวงกลมของวงกลม:

```java
// เพิ่มแผนภูมิบนสไลด์
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## ขั้นตอนที่ 3: ปรับแต่งคุณสมบัติแผนภูมิ
ตอนนี้เรามาตั้งค่าคุณสมบัติต่างๆ ให้กับแผนภูมิ รวมถึงตัวเลือกพล็อตที่สอง:

```java
// แสดงป้ายข้อมูลสำหรับชุดแรก
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// กำหนดขนาดของพายที่สอง (เป็นเปอร์เซ็นต์)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// แบ่งพายตามเปอร์เซ็นต์
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// ตั้งค่าตำแหน่งการแยก
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกการนำเสนอด้วยแผนภูมิและตัวเลือกพล็อตที่สอง:

```java
// เขียนการนำเสนอลงดิสก์
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับตัวเลือกพล็อตที่สอง

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
// เพิ่มแผนภูมิบนสไลด์
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// ตั้งค่าคุณสมบัติที่แตกต่างกัน
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// เขียนการนำเสนอลงดิสก์
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเพิ่มตัวเลือกพล็อตที่สองให้กับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งคุณสมบัติต่างๆ เพื่อปรับปรุงรูปลักษณ์และการทำงานของแผนภูมิของคุณ ทำให้การนำเสนอของคุณให้ข้อมูลและน่าสนใจยิ่งขึ้น

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนขนาดของวงกลมที่สองในแผนภูมิวงกลมของวงกลมได้อย่างไร

หากต้องการเปลี่ยนขนาดของวงกลมที่สองในแผนภูมิวงกลมของวงกลม ให้ใช้ `setSecondPieSize` วิธีการดังแสดงในตัวอย่างโค้ดด้านบน ปรับค่าเพื่อระบุขนาดเป็นเปอร์เซ็นต์

### อะไร `PieSplitBy` การควบคุมในแผนภูมิวงกลมของวงกลม?

การ `PieSplitBy` คุณสมบัติควบคุมวิธีการแบ่งแผนภูมิวงกลม คุณสามารถตั้งค่าเป็น `PieSplitType.ByPercentage` หรือ `PieSplitType.ByValue` เพื่อแบ่งแผนภูมิตามเปอร์เซ็นต์หรือตามค่าที่ระบุตามลำดับ

### ฉันจะตั้งค่าตำแหน่งการแยกในแผนภูมิวงกลมของวงกลมได้อย่างไร

คุณสามารถกำหนดตำแหน่งการแบ่งในแผนภูมิวงกลมของวงกลมได้โดยใช้ `setPieSplitPosition` วิธีการ ปรับค่าเพื่อระบุตำแหน่งที่ต้องการ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}