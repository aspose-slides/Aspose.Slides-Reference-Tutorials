---
title: ตัวเลือกพล็อตที่สองสำหรับแผนภูมิใน Java Slides
linktitle: ตัวเลือกพล็อตที่สองสำหรับแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับแต่งแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java สำรวจตัวเลือกพล็อตเรื่องที่สองและปรับปรุงการนำเสนอของคุณ
type: docs
weight: 12
url: /th/java/chart-creation/second-plot-options-charts-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับตัวเลือกพล็อตที่สองสำหรับแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีเพิ่มตัวเลือกพล็อตที่สองให้กับแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java ตัวเลือกการลงจุดที่สองช่วยให้คุณสามารถปรับแต่งลักษณะที่ปรากฏและลักษณะการทำงานของแผนภูมิได้ โดยเฉพาะในสถานการณ์เช่นแผนภูมิวงกลมจากวงกลม เราจะให้คำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ดเพื่อให้บรรลุเป้าหมายนี้ 

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ Java และตั้งค่าในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: สร้างงานนำเสนอ
เริ่มต้นด้วยการสร้างงานนำเสนอใหม่:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์
ต่อไป เราจะเพิ่มแผนภูมิลงในสไลด์ ในตัวอย่างนี้ เราจะสร้างแผนภูมิ Pie of Pie:

```java
// เพิ่มแผนภูมิบนสไลด์
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## ขั้นตอนที่ 3: ปรับแต่งคุณสมบัติแผนภูมิ
ตอนนี้ มาตั้งค่าคุณสมบัติต่างๆ สำหรับแผนภูมิ รวมถึงตัวเลือกการลงจุดที่สอง:

```java
// แสดงป้ายกำกับข้อมูลสำหรับชุดแรก
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// กำหนดขนาดของพายอันที่สอง (เป็นเปอร์เซ็นต์)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// แบ่งพายตามเปอร์เซ็นต์
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// กำหนดตำแหน่งของการแยก
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ
สุดท้าย บันทึกงานนำเสนอด้วยตัวเลือกแผนภูมิและพล็อตที่สอง:

```java
// เขียนงานนำเสนอลงดิสก์
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับตัวเลือกพล็อตที่สอง

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
// เพิ่มแผนภูมิบนสไลด์
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// กำหนดคุณสมบัติที่แตกต่างกัน
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// เขียนงานนำเสนอลงดิสก์
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเพิ่มตัวเลือกพล็อตที่สองให้กับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งคุณสมบัติต่างๆ เพื่อปรับปรุงรูปลักษณ์และการทำงานของแผนภูมิของคุณ ทำให้การนำเสนอของคุณมีข้อมูลมากขึ้นและดึงดูดสายตามากขึ้น

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนขนาดของวงกลมที่สองในแผนภูมิ Pie of Pie ได้อย่างไร

หากต้องการเปลี่ยนขนาดของวงกลมที่สองในแผนภูมิวงกลมจากวงกลม ให้ใช้`setSecondPieSize` วิธีการดังแสดงในตัวอย่างโค้ดด้านบน ปรับค่าเพื่อระบุขนาดเป็นเปอร์เซ็นต์

###  ทำอะไร`PieSplitBy` control in a Pie of Pie chart?

 ที่`PieSplitBy` คุณสมบัติควบคุมวิธีการแบ่งแผนภูมิวงกลม คุณสามารถตั้งค่าเป็นอย่างใดอย่างหนึ่ง`PieSplitType.ByPercentage` หรือ`PieSplitType.ByValue` เพื่อแยกแผนภูมิตามเปอร์เซ็นต์หรือตามค่าเฉพาะตามลำดับ

### ฉันจะกำหนดตำแหน่งของการแยกในแผนภูมิ Pie of Pie ได้อย่างไร

 คุณสามารถกำหนดตำแหน่งของการแยกในแผนภูมิ Pie of Pie ได้โดยใช้`setPieSplitPosition` วิธี. ปรับค่าเพื่อระบุตำแหน่งที่ต้องการ